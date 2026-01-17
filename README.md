# Termboard Analyze

This repository contains resources, documentation, and case studies for using [Termboard](https://termboard.com) as an investigative analysis tool for network analysis, intelligence work, and investigative journalism.

## Overview

Termboard, originally designed for semantic modeling and knowledge graphs, has powerful capabilities that make it suitable for investigative analysis:

- **Network Visualization**: Map relationships between people, organizations, and events
- **Structured Metadata**: Use XFields to categorize entities by type, status, and other attributes
- **Visual Semantics**: Color-code nodes by category and status for instant pattern recognition
- **AI-Assisted Analysis**: Extract entities and relationships from unstructured documents

## Contents

### Case Studies

#### Madlanga Commission

A real-world example analyzing the South African Madlanga Commission investigation network:

- Network grew from 52 individuals/75 relationships to 67 individuals/140 relationships
- Entities categorized by role: Cartel members, Politicians, SAPS officials, Victims, Witnesses
- Demonstrates complex relationship mapping and evidence linking

### Documentation

- **[Investigative Workflow Guide](New%20documentation/INVESTIGATIVE_WORKFLOW_GUIDE.md)** - Step-by-step methodology for conducting complex investigations with Termboard, covering:
  - Ontology setup and XField definitions
  - Data ingestion strategies (Excel bulk import, AI-assisted extraction)
  - Relationship structuring and temporal anchoring
  - Layout best practices for different entity types

### Feature Roadmap

- **[Product Roadmap for Investigations](New%20Features/PRODUCT_ROADMAP_INVESTIGATIONS.md)** - Proposed features to enhance Termboard for investigative use, including:
  - Relation XFields for structured relationship types
  - Swimlane and timeline layouts
  - Evidence management and attachment support
  - Geospatial integration
  - Advanced pathfinding tools

## Quick Start for Investigators

1. **Define your ontology** - Create Category and Status XFields before adding data
2. **Map visual semantics** - Assign colors to categories and border colors to statuses
3. **Use strong verbs** - Name relationships with action verbs (e.g., "Instructed", "Paid", not "Related to")
4. **Anchor temporally** - Create Event nodes to track when people intersected
5. **Link evidence** - Create evidence nodes as intermediaries between entity connections

## Example Entity Categories

| Category           | Description                             | Example Color |
| ------------------ | --------------------------------------- | ------------- |
| Person of Interest | Politicians, executives, key figures    | 🔴 Red        |
| Organization       | Companies, departments, shell entities  | 🟢 Green      |
| Event              | Meetings, incidents, transactions       | 🔵 Blue       |
| Evidence           | Documents, records, testimony           | ⚫ Gray       |
| Location           | Physical locations relevant to the case | 🟠 Orange     |

## Example Status Markers

| Status    | Description               | Border Color |
| --------- | ------------------------- | ------------ |
| Active    | Currently operating/alive | Default      |
| Suspended | Under investigation       | 🟠 Orange    |
| Deceased  | No longer alive           | ⚫ Black     |
| Detained  | In custody or charged     | 🔴 Red       |
| Witness   | Protected witness         | 🔵 Blue      |

## License

This documentation and methodology is provided for research and educational purposes. The case study data is based on publicly available information.
