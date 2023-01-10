# Random Notes
- ERP ------- Enterprise Resource Planning ------- how companies acquire, manage, and consume physical/financial/people resources
- CRM ----- Customer Relationship Management ----- track customer interactions
- EDMS -- Electronic Document Management System -- electronic documents
- CMS -------- Content Management System --------- simple interface to accomplish complex-code tasks

<br>
<br>

# Where Projects May Live

## Organization Structures
- Functional Org: function silos, ex: IT staff all under one VP, operations staff all under another VP, no exceptions
- Projectized Org: project silos, ex: Project A all under one VP, Project B all under another VP, no exceptions
- Matrix Org: function setup but with project managers bleeding across each function (employees have two managers, "dual hats")
    * "Weak" matrix: bleed-across project manager does not control budget/staffing
    * "Strong" matrix: bleed-across project manager has substantial budget and staffing control (not all, though)
    * dual-hat is operational work (consistent things) and projectized work (temporary initiatives)

## Roles
- Project Manager: day-to-day project management, get delegated operations from the project sponsor
    * build the team, secure resources, build project charter/scope, establish logs/processes
        * charter: KPIs (targets, leading indicators (foreshadows) / lagging indicators (observed); short term)
    * define tasks, ensure deliverables are met, give status/performance updates
        * OKR: objective (goal) and key results (milestones/events), short term
- Business Analyst: translator between business and IT, understands both
    * help define project, gather business/IT requirements, keep requirements in check, translate requirements between business/IT
    * verify deliverables against requirements, help test/validate
- Architect: look at org structure/systems and design solutions; many flavors
    * help design solutions, build system blueprints, evaluate systems on org standards (ex: infosec)
- Developer/Engineer: specialized expertise in building things
    * write good code, follow blueprints/plan, report progress
- Tester/QA: ensure code quality; write tests, run tests
- Customer/End-User: XP has this role on a team, some other teams do too
    * offer usability perspective, suggest features, help design
- Vendor: supplier/partner (external to the company)
    * provide contracted work (anything), maintain SLAs, maintain comms/productive relationships
- Stakeholder: those affected by the project
    * understand project's purpose, communicate support/disapproval, give timely feedback
- SME: anyone who is an expert
### Role Extras
- Core members (fulltime) and extended members (parttime)
    * Extended members do "Percentage of Time", "Availability by Phase", "Available on Request"

## Documents/Charts
- Project Management Plan:
    * Detailed Scope Statement
    * WBS or Backlog
    * Resource Plan
    * Project Schedule
    * Quality Management Plan
    * Risk Management Plan
    * Communication Plan
    * Stakeholder Management Plan
    * Project Baselines
    * Project Budget
    * Project Plan Approval
- Project Charter: brief overview (ex: high-level risks); clarify purpose/expected outcomes, clarify PM's role/authority, source of truth (vision/direction)
    * other docs to go in-depth (ex: risk register captures all risks/responses throughout the project)
    * use a template; keep it short/sweet (max 3 sentences per item); use visualizations; use clear/concise language
    * collab w team to build it, have project sponsor review it, THEN distribute
- Timeline charts: road map (feature rollout visual), milestone chart (more details than road map), Gantt chart (highly detailed, horizontal bars+arrows)
- Fishbone chart: problem on right, 6Ps on left; `policy`, `process`, `people`, `plant`, `program`, `product`
- Preliminary Scope Statment: detailed version of Project Charter's scope info
    * scope description (summary), acceptance criteria (success criteria), in-scope deliverables (will deliver), out-of-scope deliverables (won't deliver)
    * assumptions, proven constraints (proven-true assumptions), unproven constraints (assumptions)
- Records Management Plan: plan of how to manage records for a project; proper creation, storage, archival/disposal
    * docs to manage: project management artifacts (budget/stakeholder engagement/etc), project artifacts (requirements, blueprints)
    * more docs to manage: legal documents (agreements), communications (meeting notes, status reports, written communications)
        * communications: capture information, centralize information, reflect reality
        * confusingly, public, confidential, and critical classifications are for communications
    * public, internal, confidential, restricted data types
    * plan must comply with org policies; be organized/easy to find; make info accessible (to authorized users); establish comm channels
- Communication Plan: strategy for how team/stakeholders receive updates
    * identify stakeholders -> get stakeholder comm preferences -> create the comm plan -> share/finalize the plan -> schedule everything -> revise the plan
    * communication, audience, goals, schedule, format
- Escalation Plan: how to handle scenarios in case they happen
    * category (type of escalation), level (who to escalate to), escalation owner (the one at a given level), trigger (conditions leading to escalation)
- Solution Design Document: 
    * overview, audience, purpose, references, glossary, summary of existinf functionality, functional requirements details, NFR details, ...
    * ... assumptions and prerequisites, HLD, LLD, impact analysis, (what is) out of scope, risks and mitigation, appendix
    * HLD: technical feasibility of project; created by project sponsor (acquisition), solution architect (comprehensive), and technical staff (sorta-SME)
        * non-functional requirements (NFRs): "scalability", "portability", "extensibility", etc
    * LLD: sort out project details; created by solution architect (comprehensive) and SMEs (detail-oriented)
        * functional requirements: requested features
- Procurement Plan: if project needs external resources
    * procurement needs assessment + high-level procurement plan created in early stages of planning
    * procurement plan is a business case, involves: 
        * needed goods/services, critical dates, financial/risk impacts of procuring these, contract types, eval methods, vendor options / perf metrics
- Needs Assessment: identify what projects needs; includes skills, software, equipment, etc
    * identifies gaps early, reduces number of unknowns, reduces issues
    * understand project requirements -> identify current resources -> identify resource gaps -> address the gaps (create plan, activate plan)
- Gap Analysis: differences between future state and current state; used everywhere; for PM this is resource gaps and required tasks
    * skill gaps, feature/function gaps, resource utilization gaps (too-high usage rates)
- Risk Management Plan: how risks will be managed (by project manager)
    * Approach (to risks), ex: risk analysis tool selection, "Positive Risk" vs "Opportunity" (word choice), more
    * Risk Identification Plan (what work will be done in pursuit of detecting risk occurrence)
    * Risk Register: a list of risks and their info; updated as time goes on
        * Risk ID, Risk description, Risk analysis summary, Impact/priority/other scoring criteria, Risk priority/ranking, Risk owner, Risk response/treatment
    * Risk Breakdown Structure, ex: technical risks, management risks, organizational risks...
    * Risk Assessment Strategy (scoring risks)
    * Risk Response Strategy
    * Funding
    * Risk Monitoring (strategy)
    * Schedule (of risk management tasks)
- Risk Report: overall report about risk management stuff
- Transition Plan: how to hand off the work of the project; can be a checklist or detailed format
    * roles and responsibilities: specify transition plan owner, transition activity completers, maintenance owners
    * transition schedule (when work ends + more)
    * maintenance schedule (for after work ends)
    * training (what is needed to use the product, ex: hands-on workshop, certification, more)
    * activities: all other tasks, ex: setup, asset turnover, review sessions
    * tools/techniques: what ops team needs longterm + access requirements
    * product documentation
    * asset turnover plan (how/when transfer happens)
    * impact analysis of transition completion
- Contingency plan (after risk occurs) and risk mitigation plan (ongoing tasts to try to keep risk from occurring)... annoying
- WBS: breaking down the work into work packages; this is for resource allocation, planning, and timing reasons
    * determine scope -> identify deliverables -> identify team members -> build level 2 -> build remaining levels -> build WBS dictionary
    * WBS dictionary: Work package ID, Work package name, Work package description, Assigned to, Date of assignment, Due date, Estimated cost

## Programs
- a container for many projects, all leading to something
    * PORTFOLIOS DON'T LEAD TO ANYTHING; JUST A COLLECTION OF PROJECTS/PROGRAMS
- overlapping/chaining projects in pursuit of a goal
    * ex: Imo's Pizzas, program for new business model of packaged pizza sales (not just restaurant sales)
    * packaged pizzas require mass production, marketing, sales; these projects make up the program
- increases importance of each project (since they rely on one another)
    * A project can fail if the required previous project failed
- a PROGRAM MANAGER leads many PROJECT MANAGERS
    * there's also PROGRAM STAKEHOLDERS and PROGRAM STAFF
- bulk nature of program allows bulk discounts on things, saving costs

## Project Management Office (PMO)
- the functional department for all project managers
- evaluates new projects, assigns them to a project manager
- does admin support, ex: archives, best practices, project management tools, performance/metrics tracking
- can do coaching/training as well
- three types: SUPPORTIVE (help on request), CONTROLLING (resource/PM selection), DIRECTIVE (full authority over everything)
    * DIRECTIVE is practically required in many cases; it is responsible for strategic alignment and will start/change/halt projects to succeed

## Project Schedule
- Project schedule: the project plan, includes specific dates/sequence of starting/fininshing activities or meeting milestones
- Milestone: date-dependent critical event (flexible date or specific, indicated by diamond on timeline)
    * usually a summary of the work leading to it; "project approval", "project kickoff", ...
    * one of a project's milestones is completion of the project schedule
    * great motivator, and scheduling per-milestone is easier than overall scheduling

## MEETING TYPES (BORING)
- INFORMATIVE: DEMOS/PRESENTATIONS, PROJECT STATUS, STAND-UPS
- DECISIVE: TASK SETTING (PLAN WORK), PROJECT STEERING COMMITTEE MEETING (HELPS MAKE FEATURE DECISIONS), REFINEMENT (FIX THE BACKLOG)
- COLLABORATIVE: FOCUS GROUPS, WORKSHOPS (SOLVE A SPECIFIC PROBLEM OR GAIN KNOWLEDGE), JOIN APPLICATION DEVELOPMENT (CUSTOMER HELPS DESIGN)
    * BRAINSTORMING TOO; EX: RISK ASSESSMENT MEETING ("WHAT IF...") AT START/THROUGHOUT PROJECT
- ARTIFACTS: AGENDA (PURPOSE+TOPICS), TIMEBOX (MEETING LENGTH), ACTION ITEMS (TO-DOs), MEETING MINUTES (WHAT HAPPENED), FOLLOW-UP
    * AGENDA "POWER START": SET THE (P)URPOSE, (O)UTCOMES, (W)HAT'S IN IT FOR ME, (E)NGAGEMENT, (R)OLES/RESPONSIBILITIES OF THE MEETING

## Conflict Management
- conflict types: substantial (task-based) and emotional (relationship/feeling based)
    * conflict can be good (avoid groupthink, stay challenged)
- conflict escalation: tension -> debate -> actions replace words (discussion ends) -> coalitions -> loss of face (lie about others) -> threats
    * keep going... limited destruction (okay with losing if other loses more) -> annihilation (destroy other) -> abyss (destroy it all)
- conflict resolution approaches: 
    * collaborating: use when both sides have something to lose
    * competing: get to the best solution by helping the conflict to a winner
    * compromise: use when both arguments have merit
    * forcing: use in an emergency when no discussion is needed
    * accommodating/smoothing: use when situation is angry and nearing violence
    * avoiding: use when conflict is minor and doesn't impact project

## Risk
- Risk: Something that you think will happen that you don’t control
    * Issue: something has already happened that you don't control
    * Change: either happened/will happen and you do control it
    * Interconnectivity: issues affect other risks/issues
    * Detectability: how quickly a risk occurrence can be detected
    * Escape: something with an undetected deviation/defect
        * Quality escape (undetected defective product) and Notice Of Escape (reporting it after detection to source)
- Risk management identifies risks and creates response plans for if they occur
- A risk CAN BE POSITIVE OR NEGATIVE; YES, THERE ARE "POSITIVE RISKS", this is so dumb just call it a positive event or something
    * when POSITIVE RISK actually happens, it becomes an issue... a positive issue... so stupid
- identify a risk -> analyze the risk -> treat the risk -> monitor the risk
    * identifying risk: try FMEA to analyze one process for all risks + prioritize risks with scores; Failure Mode and Effects Analysis
    * treat risk: Avoidance, Mitigation, Transference, Acceptance (negative); Exploit (seek), Enhance (exacerbate), Share, Accept
- Risk manager: the project manager
    * senior management is ultimately accountable for risks, but passes responsibilities to risk managers
    * administers the risk register, ex: assigning risk owners
    * leads risk analysis (analyzing chance/impact of risk occuring) and response
    * monitors/reports risk management progress and events
- Risk owner: fully accountable for risks; "A" in the RACI chart, "owner" on risk register
    * develops response plans for risks occuring
    * delegates risk management tasks / collaborates with others
    * identifies when risks occur, react to it
- Internal risk: New (higher-priority) project; digital transformation (positive risk); new management; reorganization; merger/acquisition
- External risk: Infrastructure EOL (vendor product EOL); cybersecurity incident (hackers=external); regulatory environment changes (new laws)
- qualitative risk (low/med/high, 1-10 (subjective risk thresholds)) and quantitative risk (actual data + probability of occurrence)

## Issues
- Issue severity: low (ignore) -> minor (all works but...) -> major (one thing is broken) -> critical (it's all broken)
- Issue urgency: minor (ignore) -> medium (fix within days) -> major (fix within hours) -> critical (fix immediately)
- Issue impact (project): low (project is fine) -> medium (project may be delayed) -> high (project may fail)
- Issue impact (org): low (impacts few) -> medium (impacts many) -> high (impacts most)
- Issue escalation: low (no plans to escalate) -> medium (plan but has not been executed) -> high (plan and has been executed)
- Issue prioritization: score each of the above beforehand, then for each issue, assign a score and sum up to the prioritization number
- Monitoring: make sure issues stay resolved; make sure open issues aren't worse; watch project performance for more issues
    * make sure issues are actually resolved; remove (temporary) workarounds; complete (issue resolution) outcome documentation

## Procurement
- determine needs -> submit requisition to procurement team -> complete solicitation with procurement team -> select vendor(s) -> manage orders/records
- selecting vendors: RFIs (one vendor), RFPs (proposals), RFB (bids), RFQ (quotes)
    * RFI: we're interested in Product A from your company
    * RFP: we're interested in a Type-1 Product, the solution is very important to us, please send us a proposal to provide a Type-1 Product
    * RFB: we're interested in a Type-1 Product, cost is most important to us, please send us a bid for providing a Type-1 Product
    * RFQ: we're interested in a product with specifically A, B, C, D, E, ...., please send us a quote for providing this exact product
- Procurement contract: agree to purchase some thing(s)
    * purchase orders (POs): the actual purchases
- SOW: DESIGN (specify how to deliver work), FUNCTIONAL (specify an outcome, who cares about how), PERFORMANCE (specify performance level, who cares about how)
    * TOR: SOW-like but it's not focused on good/services; it establishes working relationships/groups, it's used in consultancy

<br>
<br>

# Initiating a Project

## Project Life Cycle
- Concept or Discovery Phase
    * before project start; review project ideas and report the review
    * most ideas get filtered; if an idea turns out to be good, PMs can request approval to initiate the project
    * REMEMBER THAT PROJECTS ARE TEMPORARY, COMPLETABLE THINGS
        * Operational Work is NONSTOP, NONCOMPLETABLE
- Initiation Phase
    * after approval; the start of project work
    * LEARN about the project goals/deliverables/final product
    * SET/EXPLAIN roles
        * Position - Core/Extended - Availability  - Subteam or Grouping  - Project Responsibilities - Preferred Contact Methods - Manager  - Organization
        * EX: SWE  - Core         - 100% for 2yrs  - Back-end development - Python/Java development  - Anything / Chat / Email   - Namehere - Catfacts INC
        * EX: Dev  - Extended     - 25% (10hrs)    - 
    * KICK OFF PROJECT
- Planning Phase
    * after project start; team builds detailed plan
    * PM's role is making sure team has adequate resources, keep team on track, share progress
    * by end of planning, will have everything needed to begin work + schedule + metrics
- Execution Phase
    * after planning; the delivery of the work
    * attempt to meet all Initiation goals using Planning plan
- Closing
    * wind down project
    * wrap up tasks, documentation, financial summary
    * request project close, and after close is approved, disband team

## Business Case
- also called "Business Justification" / "Business Objective"
- serves as FIRST project proposal
- summarizes info about a project
    * analysis of business problem
    * potential solutions to that problem
    * financial impact
- helps sponsors/stakeholders understand the value of the project
    * and hopefully they assess the project is a good investment
    * so that they approve the project start and open up funding/resources
- can be about money, ESG factors, both
    * ESG factors are the company's identity/mission/reputation pieces
    * including ESG factors can win over business leaders ("this is solidly my company")
### Structure of Business Case
- Executive Summary
    * problem, solution, expected results
    * WRITTEN LAST!!! include short problem statement, solution, expected result writeup
- Problem Statement
    * concise details about the current situation, business problem (less than a paragraph)
    * describes THE PROBLEM (that will be fixed) and RESULT OF AN UNSPECIFIED FIX (options)
- Problem Analysis
    * the PROBLEM'S data and supporting analysis; historical performance data, environmental assessment, etc
    * this analysis should SUPPORT THE BUSINESS CASE
- Options
    * business case AND alternatives to business case; each of their impacts/needed resources; 3-5 opions
    * compare between each option with pros + cons
    * always have two options: DO NOTHING (problem is serious!!) and BUSINESS CASE, plus at least one more (max 3 more)
- Project Definition
    * Business Case: RESOURCES NEEDED (scope) and IMPLEMENTATION TIMELINE (timeline/milestones)
    * scope: requirements for time, money, personnel, equipment
    * timeline: expected time for the project and milestones along the way
- Financial Overview
    * Business Case: cost of project, where money will come from, what company will gain, and risks/assumptions
        * assumptions (the EXPECTATION, used in calculating everything)
        * risks (EVENTS THAT COULD HAPPEN that would drastically affect financials)
    * cost/sourcing/gains are in COST-BENEFIT ANALYSIS and ROI ANALYSIS
        * ROI: (net profit from project / cost of project) * 100
        * ROI might be negative (if options are required / all negative)
- Recommendation
    * recommended option from the Options section, why that option, next steps to confirm the project
    * should include current state v future state, ex: costs now, savings later
    * could include visual differences in workflow (simplifying processes)
### Example Business Case (in pieces)
* **Problem Statement:**
* **Problem:** Telephony expenses have increased by 75% in the last five years. (details) Employee survey scores have dropped in areas related to equipment availability (details), and open comments suggest that employees are using their personal cell phones for more calls as remote work has increased. (details)
* **Expected Outcomes:** Reduce telephony costs by 50% (if problem removed, what happens). Increase equipment availability to make reliable telephony available to all employees (if problem removed, what happens).

## Responsibility Assignment Matrix (RAM)
- exact responsibilities of each team member and stakeholder
    * responsible (does the work), accountable (owns the work), consulted (advice/direction for the work), informed (gets info)
- creating a RAM / "RACI chart":
    * Side: List activities (product backlog items) with reference numbers and text description
    * Top: List members, stakeholders, any relevant party
    * Content: R, A, C, I for each person and the activity (consider color-coding these)
- RAM/"RACI charts" are updated as the project goes on to reflect current status

## Stakeholder Engagement Plan
- project manager plans / performs engagement with stakeholders to get thoughts, explain things, etc; great for many reasons, and great at start of project
- learn who supports/opposes project, build more support (gives them comm channels, opens collab), extends reach of project, helps refine messaging (practice)
- inputs can help clarify/direct project towards more success
- identify stakeholders/POCs (list) ->  prioritize stakeholders -> understand stakeholders (talk to them) -> develop the stakeholder engagement plan
    * Stakeholder prioritization: High Power/High Impact (engage), High Power/Low Impact (satisfy), Low Power/High Impact (inform), Low Power/Low Impact (monitor)
- Stakeholder engagement plan: info (side) and roles (top), info: Power-Influence, Engagement Approach, Engagement Needs, Engagement Methods, Freq, Project Phase

<br>
<br>

# Project Methodologies

## Waterfall
- probably the oldest methodology in software development; LINEAR, SIMPLE, INFLEXIBLE, THOROUGH DOCUMENTATION
- STRICT BUDGET
- Requirements (define) -> Design (specify) -> Implementation (complete work) -> Testing -> Delivery/Deployment -> Maintenance
    * a phase is COMPLETED, THEN next phase begins (no overlaps)
- use case: requirements are fixed and there are no unknowns
- use case: late changes are incredibly costly (ex: construction) and all decisions need to be made upfront / fully considered
- use case: short, simple projects
- AVOID FOR CHANGE-LATER PROJECTS due to inflexibility; changes require the entire thing to start over

## AGILE
- designed for uncertainty; ITERATIVE/INCREMENTAL, FLEXIBLE, SCOPE CREEP / BAD DOCUMENTATION
- FLEXIBLE BUDGET
- Iterative: multiple features getting small changes, constant feedback, typically 1-4 weeks for an iteration
- Incremental: one feature getting released at a time, feedback at completion
- IID: iterative AND incremental development, one feature at a time (incremental) but reviewed when pieces of the feature are done (iterative)
    * REVIEWED IN ITERATIONS, not released. only released when the one feature is done
- use case: requirements will change/emerge throughout the project
- use case: team is stable enough to self-organize
- AVOID FOR SHORT/SIMPLE PROJECTS

## Scrum
- A VERSION OF AGILE; SPRINTS, LIGHTWEIGHT, FLEXIBLE, MEANT FOR ONE HIGH-PERFORMANCE CROSS-FUNCTIONAL TEAM
- usually in two-week sprints
- "it's everything-Scrum or it isn't Scrum"; ZILLIONS OF TERMS, SO ANNOYING
- empiricism (avoid predictions), lean thinking (reduce waste/redundancy/unnecessary work)
- scrum values: commitment, focus, openness, respect, courage
- scrum pillars: transparency (improves decisions), inspection (finds problems), adaptation (handle inspection results)
- scrum process overall: product owner sets backlog+priorities -> scrum team selects items for sprint -> sprint -> sprint reviewed -> repeat
    * scrum roles: scrum master (coach Scrum principles lmfao), product owner (own/fill the backlog), developers (all other members of scrum team)
- sprint itself: sprint planning (choose from backlog) -> daily scrum -> sprint review (review work performed) -> sprint retrospective (review teamwork)
- product key terms: product backlog, product backlog items (PBIs), product goal (delivered by product backlog, summarizes PBIs)
    * increment: complete body of work ("what does done mean?"), a piece moving the effort towards the product goal
- sprint key terms: sprint backlog (sprint-specific), sprint goal (sprint-specific)
- use cases: great teams, larger/complex/adaptable projects
- use case: anything customer-centric thanks to sprint review feedback

## Kanban
- A VERSION OF AGILE; LIGHTWEIGHT, SIMPLE, BACKLOG CLEARANCE, PHASES OF WORK-IN-PROGRESS
- product owner sets the backlog -> team member moves top item into progress -> team moves item through phases -> team selects next top item
- great for routine tasks with defined phasing
- bad when iterative/incremental review is required (development)
- use case: backlog/worklist changes often (ex: ticketing/request systems)
- use case: workflow (phases) are stable

## XP
- A VERSION OF AGILE; EXTREME PROGRAMMING, DEV QUALITY OF LIFE, HIGHLY EFFICIENT, NOT USEFUL OUTSIDE CODE
- write tests -> write code to beat tests -> continue
- customer on dev team; knowledge sharing importance == development importance (avoid single point of failure); least amount of work (simple code)
- use case: small, co-located teams with changing/unknown requirements
- use case: able to automate tests

## DevOps
- A VERSION OF AGILE; MIX CODE AND DEPLOY TEAMS, AUTOMATED PIPELINES, REQUIRES SKILLS
- dev team: plan -> code -> build -> test
- ops team: receive software -> release -> deploy -> operate -> monitor
- devops: dev and ops on same team to optimize/automate entire process together, test for late bugs earlier
- CI/CD: CI is XP practice of build tests then code, CDelivery is the rest except deployment (choose to deploy), CDeployment is rest plus deployment
- use case: good staffing + automation tools
- use case: fast increments, automated deployments
### DevSecOps
- adding security test automation and security members into DevOps
- security testing tools are vital for non-security devs to address problems!!
- security is handed over to devs!! dangerous but important to keep security in mind while developing!!

## Scaled Agile
- AGILE WITH MULTIPLE TEAMS; SYNC AGILE CHOICES ACROSS TEAMS, TEAMS PLAN TOGETHER, GREAT FOR DEV/NON-DEV TEAMWORK, LOTS OF OVERHEAD
- SAFe: a proprietary scaled agile framework
- agile team: same as scrum/kanban team
- agile release train (ART): multiple agile teams together
- iteration: same as scrum sprint or XP weekly cycle, length is standardized across teams
- program increment (PI): like XP's quarterly cycle with more than one team
    * program increment planning (PI planning): the agile release team (multiple teams together) planning session
- use case: company's projects spread across multiple teams
- use case: many agile teams that need to coordinate/communicate

## SDLM/SDLC
- MULTIPLE MODELS; THOROUGH PLANNING AND A MODEL CHOICE, COMPREHENSIVE, CONSTRAINING
- models: waterfall, iterative (waterfall with internal iterations), spiral (chase MVP, chase iterations), agile (customer reviews product)
- planning -> requirements -> design/prototyping -> development -> testing -> deployment -> ops/maintenance

## PRINCE2
- WATERFALL; PREDEFINED PHASES, ROLES, AND TASKS; EXECUTIVE INVOLVEMENT, HIGH OVERHEAD
- project board: authorizes resources/funding; single executive, 1+ senior users, 1+ senior suppliers
- principles (PRINCE2 adherence)
- themes (seven ways to implement principles)
- processes: starting up (viability) -> initiating (define) -> directing (approval) -> controlling (execution) -> manage delivery -> manage stage boundary -> close
- use case: EUROPE/UK
- use case: executives want in on the goings-ons
- use case: documentation is valued