# How to Conduct Complex Investigations with Termboard

**Target Audience:** Investigative Journalists, Legal Researchers, Intelligence Analysts
**Use Case:** Network Analysis (e.g., State Capture, Organized Crime, Corporate Fraud)

---

## Phase 1: The Setup (Defining the Ontology)

Before adding a single term, you must define the "language" of your investigation using **XFields**. A chaotic graph is useless; a structured graph is evidence.

### 1. Define Entity Categories (The "What")

Create a Dropdown XField named `Category`. Do not rely on color alone; data must be structured.

- **Recommended Values:**
  - `Person of Interest` (Politicians, CEOs)
  - `Organization` (Shell companies, Government Depts)
  - `Event` (Meetings, Murders, Payments)
  - `Location` (Safe houses, Offices)
  - `Evidence` (Phone Records, Bank Statements)

### 2. Define Status Markers (The "State")

Create a Dropdown XField named `Status` to track the lifecycle of entities.

- **Recommended Values:**
  - `Active` / `Operating`
  - `Suspended` / `Under Investigation`
  - `Deceased` / `Liquidated`
  - `Detained` / `Charged`
  - `Witness` (Protected)

### 3. Visual Semantics

Go to **Settings > XField Settings**.

- Map `Category` to **Node Color** (e.g., Red for Criminals, Blue for Police).
- Map `Status` to **Border Color** (e.g., Black for Deceased, Orange for Suspended).
- _Why?_ This allows you to assess the state of the network at a glance (e.g., "Why is the Police cluster mostly Orange? -> They are all suspended").

---

## Phase 2: Data Ingestion (The Collection)

### Method A: The Bulk Skeleton (Excel)

Use Excel to build the initial "skeleton" of the network.

1.  **Tab 1 (Terms):** List every name, company, and department mentioned in documents. Fill in the `Category` column.
2.  **Tab 2 (Relations):** If you know them, map clear hierarchies (e.g., `Mchunu` -> `Head of` -> `Police Ministry`).
3.  **Import:** Use Termboard's Excel Import feature to generate the base nodes.

### Method B: AI-Assisted Extraction

When dealing with unstructured text (affidavits, news articles):

1.  Paste the text into an LLM.
2.  Use a prompt: _"Extract all people and organizations from this text. Identify relationships involving payments or commands. Format as ????"_"
3.  TODO: add output format and import instructions

---

## Phase 3: Linking and Structuring (The Analysis)

### 1. The "Verb" Rule

When creating relations, never use generic names like "Related to." Use strong **Verbs**:

- `Instructed`
- `Paid` (Include amount in description)
- `Met with`
- `Ordered hit on`

### 2. Temporal Anchoring (Crucial)

Since Termboard (currently) lacks a dedicated timeline, you must embed time in the data:

- **Nodes:** Create specific Event nodes (e.g., "Meeting at Steyn City - Dec 2024").
- **Links:** Connect people to these events (`Cele` -> `Attended` -> `Meeting`).
- **Result:** This prevents the graph from looking like a hairball and shows _when_ people intersected.

### 3. Evidence Linking

Do not just link Person A to Person B.

- **Bad:** `Molefe` -> `Called` -> `Tau`
- **Good:** `Molefe` -> `Linked via` -> `Phone Records (Item 4b)` -> `Linked via` -> `Tau`
- _Why:_ This creates a chain of custody for your assertions.

---

## Phase 4: Layout and Visualization

### 1. Grouping

Use **Parent Terms** to create clusters.

- Create a node `SAPS Management`.
- Set it as the **Parent** for `Sibiya`, `Masemola`, etc.
- This collapses complex hierarchies into manageable boxes.

### 2. Flow Direction

Arrange your graph logically (manually or via layout tools):

- **Top:** Influencers/Funders (Politicians)
- **Middle:** Operators (Police Generals, Bureaucrats)
- **Bottom:** Executioners (Hitmen, Ground forces)
- **Right/Periphery:** Victims and Witnesses.

---

## Phase 5: Reporting

1.  **Snapshots:** Take screenshots of specific clusters (e.g., "The Money Flow").
2.  **Narrative:** Use the graph to write your report (like the Madlanga Report generated previously). Walk the edges of the graph to tell the story.
3.  **Export:** Export the JSON/Excel data for legal teams or further analysis.
