# Annotation Codebook

This codebook defines the annotation schema and controlled vocabularies for hybrid human-AI workflow papers.

---

## Metadata Fields

| Key | Label | Type |
|-----|-------|------|
| Application_Domain | Application Domain | multi-select |
| Evaluation_Domain | Evaluation Domain | multi-select |
| Task | Task | multi-select |
| Objective | Objective | multi-select |
| Evaluation | Evaluation | select |
| QA_Design | QA Design | multi-select |
| Incentivation | Incentivation | multi-select |
| Derived_Quality_Control | Derived Quality Control | derived |
| Discussion | Discussion | textarea |

## Node Fields

| Key | Label | Type |
|-----|-------|------|
| KE_Task | KE Task | multi-select |
| Subtask | Subtask | select |
| Agent_Type | Agent Type | select |
| Agent_Subtype | Agent Subtype | select |
| Agent_Role | Agent Role | select |
| Granularity | Granularity | select |
| Subtask_Allocation | Subtask Allocation | select |
| Notes | Notes | textarea |

## Edge Fields

| Key | Label | Type |
|-----|-------|------|
| source | From Node | node-select |
| target | To Node | node-select |
| Pattern | Pattern | select |
| Cardinality | Cardinality | select |
| Condition | Condition | text |
| Interaction_Modality | Interaction Modality | select |
| Interaction_Mode | Interaction Mode | select |
| Medium_of_Interaction | Medium of Interaction | text |
| Wire_Type | Wire Type | multi-select |

---

## Code Values

### Domain Codes

| Code | Description |
|------|-------------|
| Cultural Heritage | Museums, archives, historical artifacts, art history |
| Biomedicine | Medical, biomedical, healthcare, life sciences |
| Manufacturing | Industrial processes, production, engineering |
| Education | Learning, teaching, educational resources |
| Geology | Earth sciences, mining, environmental |
| Music | Music theory, composition, audio |
| Legal | Law, regulations, legal documents |
| Finance | Banking, financial services, economics |
| Agriculture | Farming, food production, agronomy |
| Transportation | Logistics, vehicles, mobility |
| Energy | Power, utilities, renewable energy |
| General/Cross-domain | Not specific to a single domain |

### Task Codes

| Code | Description |
|------|-------------|
| Ontology Development | Creating new ontologies (scope, conceptualization, formalization, implementation) |
| Ontology Management | Managing ontology lifecycle (scheduling, controlling, quality, documentation) |
| Ontology Operations | Operations on existing ontologies (evaluation, alignment, merging, refinement) |
| KG Development | Building knowledge graphs (entity extraction, relation extraction, entity linking, validation) |

### Knowledge Engineering Task

| Code | Description |
|------|-------------|
| Ontology development - Determine domain and scope | Defining what the ontology covers |
| Ontology development - Conceptualization | Identifying key concepts |
| Ontology development - Formalization | Expressing concepts formally |
| Ontology development - Implementation | Building the actual ontology |
| Ontology development - Knowledge acquisition | Gathering domain knowledge |
| Ontology development - Reuse of existing ontologies | Using existing ontologies |
| Ontology development - Competency questions | Defining what ontology should answer |
| Ontology development - Validation | Checking ontology correctness |
| Ontology management - Scheduling | Planning ontology work |
| Ontology management - Controlling | Monitoring ontology development |
| Ontology management - Quality management | Overall quality processes |
| Ontology management - Support | Tools and infrastructure |
| Ontology management - Configuration management | Managing ontology versions |
| Ontology management - Documentation | Recording ontology information |
| Ontology operations - Evaluation | Assessing ontology quality |
| Ontology operations - Integration | Combining with other systems |
| Ontology operations - Alignment | Finding correspondences between ontologies |
| Ontology operations - Merging | Combining multiple ontologies |
| Ontology operations - Ontology mappings | Creating mappings between ontologies |
| Ontology operations - Ontology learning | Automatically learning ontology from data |
| Ontology operations - Ontology extraction | Extracting ontology from sources |
| Ontology operations - Ontology pruning | Removing unnecessary elements |
| Ontology operations - Ontology refinement | Improving existing ontology |
| Ontology operations - Import and reuse | Importing external ontologies |
| KG development - Entity extraction | Identifying entities in text |
| KG development - Relation extraction | Identifying relationships between entities |
| KG development - Entity linking | Linking entities to knowledge graph |
| KG development - Validation | Validating knowledge graph content |

### Objective Codes

| Code | Description |
|------|-------------|
| Quality | General output quality improvement |
| Accuracy | Correctness of results |
| Reliability | Consistency and dependability of output |
| Effectiveness | Achieving intended goals |
| Trust | Building confidence in system/output |
| Latency | Minimizing delay/response time |
| Throughput | Maximizing processing rate |
| Cost | Reducing economic costs |
| Human effort | Minimizing human workload |
| Computational resources | Optimizing compute usage |
| Scalability | Handling increasing scale |
| Worker satisfaction | Annotator/worker experience |
| Worker retention | Keeping workers engaged |
| User satisfaction | End-user experience |
| Capacity building | Training and skill development |
| Reusability | Enabling reuse of outputs/methods |
| Adoptability | Ease of adoption by others |
| Interoperability | Working with other systems |
| Sustainability | Long-term viability |

### Evaluation Codes

| Code | Description |
|------|-------------|
| Workflow | The workflow process is evaluated |
| Workflow output | The output of the workflow is evaluated |
| Both | Both workflow and output are evaluated |

### QA Design Codes

| Code | Description |
|------|-------------|
| Worker-preselection | Screening/qualifying workers before participation |
| Defensive task design | Task structure designed to prevent errors |
| Redundancy | Multiple agents perform the same task |
| Degree of peer disclosure | Workers can/cannot see others' work |
| Feedback mechanisms | Structured feedback collection across workflow |
| Reputation system | Tracking agent reliability over time |
| Multilevel review | Hierarchical review process |

### Incentivation Codes

| Code | Description |
|------|-------------|
| Altruism | Contributing for the greater good |
| Enjoyment | Pleasure from the task itself |
| Reciprocity | Mutual benefit expectation |
| Payment | Monetary compensation |
| Reputation | Building status or recognition |
| Competition | Competitive elements |
| Gamification | Game-like elements |
| Economic models | Market-based incentive structures |
| Implicit work | Work embedded in other activities |

### Subtask Codes

| Code | Description |
|------|-------------|
| Generate/Predict | Creating new content, predictions, or outputs |
| Evaluate/Verify | Assessing, validating, or checking quality |
| Improve/Modify/Refine | Enhancing, modifying, or correcting existing content |
| Provide | Offering solutions or information informative to the primary task |
| Display - Information | Presenting supplementary information supporting the primary task |
| Request | Asking for input, action, or information |
| Collect | Gathering or storing outputs to provide to another process |
| Decide | Making choices or routing decisions |
| Delegate | Assigning tasks to other agents |
| Explain | Providing explanations or justifications |
| Focus/Filter | Narrowing scope or filtering content |
| Partition | Dividing work into parts |
| Merge/Aggregate | Combining multiple outputs |

### Agent Type

| Code | Description |
|------|-------------|
| Human | Human agent performs the task |
| Machine | Automated/computational agent performs the task |

### Agent Subtype

**For Human agents:**

| Code | Description |
|------|-------------|
| Expert | Domain expert or specialist |
| Researcher | Academic researcher |
| Engineer | Engineer, e.g., knowledge engineer |
| Citizen scientist | Non-professional contributor with interest |
| Lay person | General public without expertise |
| Crowd | Crowdsourced workers |

**For Machine agents:**

| Code | Description |
|------|-------------|
| LLM | Large Language Model (GPT, Claude, etc.) |
| NLP | Traditional NLP tools (spaCy, NLTK, etc.) |
| System | General software system or pipeline |

### Agent Role

| Code | Description |
|------|-------------|
| Tool | Passive instrument used by another agent |
| Director | Active control, makes decisions, delegates |
| Advisor | Provides guidance or specialized knowledge |
| Collaborator | Equal partner in the task |
| Recipient | Receives guidance or instruction |

### Granularity

| Code | Description |
|------|-------------|
| Microtask | Small, simple, relatively straightforward task, often carried out in parallel |
| Macrotask | Large and complex task, involves specific expertise, spanning minutes to hours |

### Subtask Allocation

| Code | Description |
|------|-------------|
| Static allocation | Fixed assignment determined at design time |
| Dynamic allocation | Assignment decided at runtime based on current conditions |

### Wire Types

| Wire Type | Description |
|-----------|-------------|
| Data | Raw data or artifacts passed between steps |
| Directive | Guidance telling an agent what to do |
| Assessment | Evaluative or factual content (feedback, corrections, information) |
| Request | Asking for a response, action, or resource |

### Edge Types

| Code | Description |
|------|-------------|
| Conditional/Branching | Branch from a Decide node; condition stated on edge |

### Cardinality

| Code | Description |
|------|-------------|
| 1:1 | One-to-one relationship |
| 1:N | One-to-many relationship |
| N:1 | Many-to-one relationship |
| N:N | Many-to-many relationship |

### Interaction Modality

| Code | Description |
|------|-------------|
| Text-based | Textual input/output |
| Visual | Visual display or graphical input |
| Speech/Auditory | Speech or audio interaction |
| Graphical | Graphical user interface interaction |
| Conversational | Conversational or dialogue-based interaction |

### Interaction Mode

| Code | Description |
|------|-------------|
| Sync | Synchronous — agent waits for response before proceeding |
| Async | Asynchronous — agent proceeds without waiting |
