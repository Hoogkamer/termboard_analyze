# Product Roadmap: Termboard for Investigations
**Goal:** Transform Termboard into a specialized tool for Intelligence Analysis and Investigative Journalism.

---

## 1. High-Priority Feature Gaps (The "Must-Haves")

### A. Structured Relation Types (Ontology)
*   **Problem:** Relations currently rely on free-text names (e.g., "Allegedly paid"). This makes filtering impossible.
*   **Solution:** Implement **Relation XFields** (similar to Term XFields).
    *   Allow users to define Relation Types: `Financial`, `Social`, `Command`, `Kinship`.
    *   Allow attributes on relations: `Date`, `Amount`, `Confidence Level` (Confirmed vs. Alleged).
*   **Benefit:** Enables queries like "Show me all *Financial* links > R100,000".

### B. Smart Layouts (Swimlanes & Hierarchies)
*   **Problem:** Users (and AI) currently have to calculate X/Y coordinates manually to get a readable chart.
*   **Solution:** Implement a "Semantically Aware" Layout engine.
    *   **Swimlane Layout:** Auto-arrange nodes into horizontal/vertical lanes based on their `Category` XField (e.g., Politicians Top, Police Middle, Cartel Bottom).
    *   **Timeline Layout:** Arrange nodes horizontally based on a `Date` field.

### C. Event & Temporal Analysis
*   **Problem:** Investigations are 4D (Time is critical). The current graph is a static snapshot.
*   **Solution:**
    *   **Timeline View:** A bottom-panel slider that filters the graph based on dates. "Show me the network state in *2024* vs *2025*."
    *   **Date Fields:** Native support for Date types in XFields.

---

## 2. Medium-Priority Enhancements (The "Should-Haves")

### A. Evidence Management
*   **Problem:** Evidence is currently text descriptions.
*   **Solution:**
    *   **Attachment Support:** Allow users to drag-and-drop PDFs/Images onto a node.
    *   **Source Citation:** specific field for "Source" (e.g., Affidavit A, Page 12) that appears on hover.

### B. Geospatial Integration
*   **Problem:** Location data (e.g., "Nigel Dam", "Steyn City") is just text.
*   **Solution:**
    *   **Map View:** If a node has a "Location" category and coordinates, plot it on a Leaflet/Google Map layer.

### C. Advanced Pathfinding
*   **Problem:** Finding the link between two distant entities is hard in a large graph.
*   **Solution:**
    *   **"Shortest Path" Tool:** User selects Entity A and Entity B -> Termboard highlights the chain of connections between them.
    *   **"Common Connection" Tool:** "Who do A and B both know?"

---

## 3. AI Integration Opportunities

### A. "Unstructured to Structured" Pipeline
*   **Feature:** "Document Parsing Agent"
*   **Workflow:** Upload a PDF (e.g., a court judgment). The AI extracts Entities, Relations, Dates, and Amounts and proposes a subgraph to merge into the main board.

### B. Anomaly Detection
*   **Feature:** "Conflict Checker"
*   **Function:** AI scans the graph for logical inconsistencies (e.g., "Person A attended Meeting B, but Person A is marked as 'Deceased' before that date").

---

## 4. Technical Debt / Refactoring Requirements
*   **Performance:** The current Cytoscape implementation may struggle with 10,000+ nodes (common in bank statement analysis). Investigate WebGL-based rendering optimizations or server-side graph processing.
*   **Mobile Support:** Field agents need to view (and perhaps edit) graphs on tablets. The current UI is likely desktop-centric.
