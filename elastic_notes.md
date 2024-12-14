<!--
#######                                           #    ######  ###        
#       #        ##    ####  ##### #  ####       # #   #     #  #   ####  
#       #       #  #  #        #   # #    #     #   #  #     #  #  #      
#####   #      #    #  ####    #   # #         #     # ######   #   ####  
#       #      ######      #   #   # #         ####### #        #       # 
#       #      #    # #    #   #   # #    #    #     # #        #  #    # 
####### ###### #    #  ####    #   #  ####     #     # #       ###  ####  
-->

# Elastic APIs
```
The Elastic suite is very powerful for data transform/storage and analytics.
The suite is extremely well-documented and has many useful APIs.
I focus on Elasticsearch's APIs because it's the database in the stack.
Kibana is the user interface for this data and has various useful features.
We have many approaches for these APIs, like Kibana Console, cURL, and Python.
```

--------------------------------------------------------------------------------
<!-- Polished -->
## cURL vs Elasticsearch
- cURL is on practically every system, making it great for compatibility
- Can call every Elasticsearch API and store the results of each call
- Certain APIs are easier to work with in Python with `elasticsearch-py` library
### cURL via Shell Script
```sh
# SAVE THIS INTO A .sh FILE AND RUN IT (BASH/ZSHELL) #
rm -rf mycooltestspace
mkdir mycooltestspace
cd mycooltestspace
echo '--user elastic:elastic' > c.txt
echo '"Content-Type: application/json"' > h1.txt
echo '"Content-Type: application/x-ndjson"' > h2.txt
echo '{"mappings": {"properties": {"hi": {"type": "keyword"}}}}' > m.json
echo '{"query": {"match_all": {}}}' > q.json
echo '
{"index":{}}
{"event": {"code": 1}, "process": {"executable": "C:\\Users\\asc\\hi.exe"}}
{"index":{}}
{"event": {"code": 1}, "process": {"executable": "C:\\Users\\asc\\hello.exe"}}
{"index":{}}
{"event": {"code": 1}, "process": {"executable": "C:\\Users\\asc\\yo.exe"}}
{"index":{}}
{"event": {"code": 1}, "process": {"executable": "C:\\Users\\asc\\sup.exe"}}
' > u.json
curl -k -K c.txt -XGET "https://localhost:9200/_cat/indices?expand_wildcards=all" > r1.json
curl -k -K c.txt -H @h1.txt -XPUT "https://localhost:9200/my-cool-index" -d m.json > r2.json
curl -k -K c.txt -H @h1.txt -XGET "https://localhost:9200/_search" -d @q.json > r3.json
curl -k -K c.txt -H @h2.txt -XPOST "https://localhost:9200/my-cool-index/_bulk" --data-binary @u.json > r4.json
curl -k -K c.txt -XDELETE "https://localhost:9200/my-cool-index" > r5.json
read -p "Press enter to continue"
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Python vs Elasticsearch
- The Elastic team maintains useful Python libraries, like: `elasticsearch-py`
- Python offers additional libraries that simplify data processing/analysis
- In combination, Python is a highly effective tool for Elasticsearch work
### Python: Record Pull
```python
# -- DEFINITION BLOCK -- #
def pull_records(query_object, pullcount_limit=None, shh=False, add_id=False):
    response = query_object.execute()
    if not response.success():
        print("Connection failed!")
        return None
    rows, i = [], 0
    try:
        for i, record in enumerate(query_object.scan()):
            if i == pullcount_limit:
                i = i - 1
                break
            if shh is False and i % 1_000 == 0:
                print_progress(i)
            obj = record.to_dict()
            if add_id:
                obj["_id"] = record.meta.id
            row = flatten_json(obj)
            del obj
            rows.append(row)
            del row
    except Exception as error:
        print(f"Something went wrong! The query likely failed. Error:\n{error}")
    if shh is False:
        print(f"Total records pulled: {i + 1}")
    if len(rows) == 0:
        return None
    df = pd.DataFrame(rows)
    del rows
    return df
def flatten_json(json_input, keyout_lists=False):
    output_dict = {}
    def flatten(current_structure, name=""):
        if type(current_structure) is dict:
            for element in current_structure:
                flatten(current_structure[element], name + element + ".")
        elif type(current_structure) is list:
            if keyout_lists:
                for i, element in enumerate(current_structure):
                    flatten(element, name + str(i) + "_")
            else:
                output_dict[name[:-1]] = current_structure
        else:
            output_dict[name[:-1]] = current_structure
    flatten(json_input)
    return output_dict
def print_progress(i):
    if i < 1_000_000 and i % 1_000 == 0 and i != 0:
        print(f"{i // 1_000}k records pulled...", end="\r", flush=True)
    elif i % 10_000 == 0 and i != 0:
        print(f"{i / 1_000_000}mil records pulled...", end="\r", flush=True)
# -- EXECUTION BLOCK -- #
ip, user, password = "https://192.168.0.1:9200", "coolguy", "coolpassword"
index_pattern = "winlogbeat-*"
import pandas as pd
from elasticsearch import Elasticsearch as ES
from elasticsearch_dsl import Search
client = ES([ip], ca_certs=False, verify_certs=False, http_auth=(user,password))
search_context = Search(using=client, index=index_pattern, doc_type="doc")
s1 = search_context\
    .query("match", winlog__event_id=4624)\
    .filter("range", **{"@timestamp": {"gte": "now-1d"}})\
    .source(fields=["winlog.provider_name","winlog.event_id"])
df1 = pull_records(s1, 21_000)
s2 = search_context.extra(**{
    "query": {"match": {"event.code": 4624}},
    "fields": ["event.code", "winlog.event_data.LogonType", "related.user"]})
df2 = pull_records(s2, 192_168_010)
```
### Python: Index Operations
```python
# IMPORTS
from elasticsearch import Elasticsearch as ES, helpers
import pandas as pd
import json
import random
from time import sleep
# SET UP CONNECTION TO ELASTICSEARCH
elastic_backend = "https://localhost:9200"
ssl_cert = "C:\\Users\\asc\\ELKstack\\7.16.2\\certs\\ca.crt"
login_creds = ("elastic", "elastic")
client = ES([elastic_backend], ca_certs=ssl_cert, http_auth=login_creds)
# CHOOSE SOURCE INDEX FOR MAPPINGS/SETTINGS, AND NAME THE NEW CUSTOM INDEX
existing_index = "winlogbeat-*"
custom_index_name = "my-custom-index"
# CHECK EXISTING INDICES
indices = sorted(list(client.indices.get_alias(index_pattern).keys()))
print("# of indices:", len(indices))
# PULL EXISTING MAPPINGS/SETTINGS AND SAVE THEM TO A FILE
def pull_index_config(client, alias="winlogbeat-*"):
    """Grab mappings/settings from index in pattern for the new custom index"""
    mappings = client.indices.get_mapping(index=alias) # GRAB INDEX MAPPINGS
    ind_name = list(mappings.keys())[-1]        # CHOOSE NEWEST INDEX IN PATTERN
    put_body = mappings[ind_name]               # SAVE NEWEST INDEX'S MAPPINGS
    ind_sets = client.indices.get_settings(index=ind_name) # GRAB INDEX SETTINGS
    settings = ind_sets[ind_name]["settings"]   # ISOLATE NEWEST INDEX SETTINGS
    del settings["index"]["uuid"]               # DELETE TO PREVENT CONFLICT
    del settings["index"]["creation_date"]      # DELETE TO PREVENT CONFLICT
    del settings["index"]["provided_name"]      # DELETE TO PREVENT CONFLICT
    del settings["index"]["version"]["created"] # DELETE TO PREVENT CONFLICT
    put_body["settings"] = settings             # SAVE NEWEST INDEX'S SETTINGS
    return put_body                             # CUSTOM INDEX'S FULL 'PUT' BODY
winlogbeat_index_definition = pull_index_config(client, existing_index)
with open("put_body.json", "w") as f:
    f.write(json.dumps(winlogbeat_index_definition))
# LOAD EXISTING MAPPINGS/SETTINGS FROM A FILE, CREATE A CUSTOM INDEX WITH THEM
with open("put_body.json", "r") as f:
    put_body = json.loads(f.read())
response = client.indices.create(index=custom_index_name, body=put_body)
print(f"INDEX CREATION:\n{response}\n------------")
sleep(3)    # GIVE ELASTICSEARCH TIME TO REGISTER THE CREATED INDEX
# GENERATE RANDOM DUMMY DATA THAT WE CAN UPLOAD (CREATES CSV FILE)
colors = ["red","orange","yellow","green","blue","purple"]
attitudes = ["caring","chillax","optimistic","pessimistic","punctual","serious"]
trends = ["upward", "downward", "steady"]
new_data = []
for i in range(25_000):                  # GENERATE 25,000 SYNTHETIC RECORDS
    new_record = {
        "favorite_color": random.choice(colors), 
        "attitude.style": random.choice(attitudes), 
        "attitude.positivity.score": random.choice(range(100)) / 100,
        "attitude.positivity.trend": random.choice(trends),
        "is_available": random.choice([True, False])}
    new_data.append(new_record)
df = pd.DataFrame(new_data)              # ASSEMBLE DATA AS DATAFRAME
df.to_csv("dummy_data.csv", index=None)  # OUTPUT DATAFRAME TO dummy_data.csv
# IMPORT DATA FROM CSV, PREP DATA FOR INGEST, THEN INGEST TO OUR CUSTOM INDEX
df = pd.read_csv("dummy_data.csv")
data_to_ingest = [dict(row[1]) for row in df.iterrows()]
ingest_target = {"index":custom_index_name}
response = helpers.bulk(client, actions=data_to_ingest, params=ingest_target)
print(f"INGEST DATA:\n{response}\n------------")
sleep(3)    # GIVE ELASTICSEARCH TIME TO REGISTER THE INGESTED RECORDS
# TRUNCATE INDEX (REMOVE ALL RECORDS BUT PRESERVE INDEX STRUCTURE/DEFINITIONS)
delete_by_query = {"query": {"match_all": {}}}
response = client.delete_by_query(custom_index_name, delete_by_query)
print(f"TRUNCATE INDEX:\n{response}\n------------")
sleep(3)    # GIVE ELASTICSEARCH TIME TO REGISTER THE TRUNCATED INDEX
# DELETE INDEX (REMOVE INDEX STRUCTURE/DEFINITIONS AND ANY CONTAINED DATA)
response = client.indices.delete(index=custom_index_name)
print(f"DELETE INDEX:\n{response}\n------------")
sleep(3)    # GIVE ELASTICSEARCH TIME TO REGISTER THE DELETED INDEX
```

--------------------------------------------------------------------------------
<!-- Polished -->
## Kibana Console vs Elasticsearch
- Kibana's "Dev Tools" includes a Console that can send Elasticsearch API calls
- Kibana users can jump into Console and quickly call any Elasticsearch API
    * Kibana ties directly to the Elasticsearch database (guaranteed connection)
- Console simplifies syntax for API calls, ex: no credentials or certs required
    * This is nice for one-off actions and testing/drafting before scripting
### Kibana Console: _search API
```json
GET filebeat-*/_search
{
  "size": 0,
  "query": {"bool": {
    "must": [
        {"exists": {"field": "source.ip"}},
        {"query_string": {"query": "network.transport: (tcp OR udp)"}}
    ],
    "must_not": [
      {"match": {"source.ip": "123.45.67.89"}}
    ],
    "filter": [
      {"range": {"@timestamp": {"gte":"2001-01-01T00:00:00", "lte":"now-3d"}}},
      {"script": {"script": {"source": "return doc['first2'].value != '0.0';"}}}
    ]
  }},
  "runtime_mappings": {
    "first2": {"type": "keyword", "script": """
    String ip_address = doc['source.ip'].value.toString();
    String firsttwo_octets = '';
    def octets = ip_address.splitOnToken('.');
    for (int i = 0; i < 2 && octets.length == 4; i++) {
      firsttwo_octets = firsttwo_octets + octets[i] + '.';
    }
    if (firsttwo_octets != '') { emit(firsttwo_octets); }
    """},
    "sentmore_192_168": {"type": "boolean", "script": """
    String srcip = doc['source.ip'].value;
    int total_sent = doc['source.bytes'].value;
    int total_rcvd = doc['destination.bytes'].value;
    def myregex = /192\\.168\\.\\d{1,3}\\.\\d{1,3}/.matcher(srcip);
    if (myregex.matches()) {emit(total_sent > total_rcvd) && (total_rcvd > 0);}
    """}
  },
  "aggs": {
    "unique_first2": {"terms": {"field": "first2", "size": 1000}},
    "rare_first2": {"rare_terms": {"field": "first2"}},
    "most_sent"
  }
}
```
### Kibana Console: One-Off API Calls
```json
# CHECK ALL INDICES
GET _cat/indices?h=index&expand_wildcards=all

# ADD CUSTOM INDEX (WITH MAPPINGS!)
PUT /my-cool-index
{
  "mappings": {"properties": {
    "event": {"properties": {
      "code": {
        "type": "keyword", 
        "ignore_above": 20
      }
    }},
    "process": {"properties": {
      "executable": {
        "type": "keyword", 
        "ignore_above": 555,
        "fields": {"text": {"type": "match_only_text"}}
      }
    }}
  }}
}

# GET MAPPINGS OR SETTINGS OF A INDEX
GET my-cool-index/_mapping
GET my-cool-index/_setting

# ADD DATA IN BULK
POST my-cool-index/_bulk?refresh=true
{"index":{}}
{"event": {"code": 1}, "process": {"executable": "C:\\Users\\asc\\hi.exe"}}
{"index":{}}
{"event": {"code": 1}, "process": {"executable": "C:\\Users\\asc\\hello.exe"}}
{"index":{}}
{"event": {"code": 1}, "process": {"executable": "C:\\Users\\asc\\yo.exe"}}
{"index":{}}
{"event": {"code": 1}, "process": {"executable": "C:\\Users\\asc\\sup.exe"}}

# REINDEX DATA (COPY AND TRANSFORM) FROM ONE INDEX INTO ANOTHER INDEX
POST _reindex
{
  "max_docs": 100000,
  "source": {
    "index": "winlogbeat-*",
    "query": {"match_all": {}},
    "_source": ["@timestamp","agent.name","event.code","process.executable"]
  },
  "script": {"source": """
    ctx._source.investigation = 'early-1';
    ctx._source.norm_exec = ctx._source.process.executable.toLowerCase();
  """},
  "dest": {"index": "my-cool-index"}
}

# IF _REINDEX TIMES OUT, YOU CAN CHECK RUNNING REINDEXING OPERATIONS...
GET _tasks?detailed=true&actions=*reindex

# ...THEN, CHECK THAT SPECIFIC TASK'S PROGRESS...
GET _tasks/Ovbg8nVuREaqV3INCO13Og:361012073

# ...AND IF YOU NEED, YOU CAN CANCEL THAT SPECIFIC TASK...
# NOTE: COPIED RECORDS REMAIN IN THE TARGET INDEX (PROCESSED RECORDS NOT UNDONE)
POST _tasks/Ovbg8nVuREaqV3INCO13Og:361012073/_cancel

# ...THEN YOU CAN DELETE THE RECORDS OUT IF NECESSARY...
POST my-cool-index/_delete_by_query
{"query": {"match_all": {}}}

# ...OR, DELETE THE ENTIRE INDEX AND MAPPINGS!
DELETE my-cool-index
```