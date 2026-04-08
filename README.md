# FAIRWorkflows - Workflow Annotation Tool

A self-contained, browser-based annotation tool for capturing workflows from academic papers. You an open `index.html` in any modern browser.


## Files

```
annotation-tool/
├── index.html      — the tool (single file, no dependencies to install)
├── codebook.md     — schema + controlled vocabularies
```


## Getting Started

1. Open `index.html` in a browser.
2. Click **Load Codebook** and upload `codebook.md` (or your own codebook). This instantly populates all field dropdowns and creates the metadata, node, and edge editors.
3. Click **Load PDF** to open the paper alongside the editor.
4. Annotate (see workflow below).
5. Export CSVs when done.

## Annotation Workflow

### From scratch

1. Load codebook → will populate editor fields
2. Load PDF → paper opens in left panel
3. Enter the DOI/paper ID in the toolbar
4. Click **+ Node** to add each workflow step; fill in the editor on the right
5. Click **+ Edge** to connect nodes; fill in interaction details
6. Click **Derive Patterns** to auto-detect structural motifs (needs to be linked to a derive script) 
7. Fill in workflow-level **metadata** by clicking the Metadata button
8. Export: **Export Nodes**, **Export Edges**, **Export Metadata**

### Loading existing annotations

1. Load codebook
2. Load Nodes CSV, Edges CSV, Metadata CSV (any order)
3. Review and edit by clicking nodes or edges in the graph
4. Export updated CSVs


## Codebook Format

The codebook is a Markdown file that defines both the annotation **schema** and the **controlled vocabularies**. It has two kinds of tables.

### Field definition tables

Tables with a `Key | Label | Type` header define what fields exist for each entity type. The tool creates the editor forms from these tables when the codebook is loaded.

```markdown
## Metadata Fields

| Key | Label | Type |
|-----|-------|------|
| Application_Domain | Application Domain | multi-select |
| Discussion | Discussion | textarea |
```

**Supported types:**

| Type | Behaviour |
|------|-----------|
| `select` | Single-value dropdown; options from matching code table |
| `multi-select` | Multi-value picker; options from matching code table |
| `text` | Free-text single line |
| `textarea` | Free-text multi-line |
| `node-select` | Dropdown listing current node IDs (used for edge source/target) |
| `derived` | Read-only field auto-populated by Derive Patterns |

For every `select`, `multi-select`, or `text` field, the tool automatically creates a companion `_Quote` textarea for provenance.

The heading must contain one of the keywords **`metadata`**, **`node`**, or **`edge`** to be recognised.

### Code tables

Tables with a `Code | Description` header define the valid values for a field. The tool matches each field's label/key to the best-fitting code table by keyword similarity.

```markdown
### Subtask Codes

| Code | Description |
|------|-------------|
| Generate/Predict | Creating new content or predictions |
| Evaluate/Verify  | Assessing or validating quality |
```

**Sub-sections** (bold lines like `**For Human agents:**`) split a code table into groups. The tool uses these groups to assign distinct node colours (warm palette for the first group, cool palette for the second).

Wire type colours are assigned in the order the codes appear in the `Wire Types` table.


## Exports

| Button | Output |
|--------|--------|
| Export Nodes | `<doi>_nodes.csv` — one row per node |
| Export Edges | `<doi>_edges.csv` — one row per edge |
| Export Metadata | `<doi>_metadata.csv` — one row for the paper |
| Export Patterns | `<doi>_patterns.csv` — detected structural motifs |
| Export HTML | Standalone HTML snapshot with all data baked in |

Exported CSVs use the column names defined in the codebook field tables (with `Node_ID`, `From`, `To` as canonical names for the identifier columns). They can be re-loaded into the tool on a later session.


## Structural Pattern Detection

Click **Derive Patterns** to automatically identify recurring graph motifs. The way these patterns should be derived should be added as a script to the tool. 

Patterns can be shown/hidden via the overlay dropdown in the toolbar. Detected patterns also drive the **Derived Quality Control** metadata field.


## Extending the Codebook

To add a new field, add a row to the relevant field-definition table in `codebook.md`. To add new code values, add rows to the appropriate code table. The tool picks up all changes on the next codebook load; no code changes needed.

To add an entirely new field type for a new entity (e.g., a `Pattern Fields` section), add a field-definition table whose heading contains the keyword you want and update the tool's `applyCodebookToFields` function to recognise it.
