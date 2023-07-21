## Star Schema / Dimensional Model
- Two tables: fact tables, dimension tables
    * Fact table: observations
    * Dimension table: description (author, store, etc)

## Snowflake Schema
- Star schema but there's subordination
    * Booksale: at a (store table), store in a (city table), city in a (state table), state in a (country table)