# Knowledge Graph Generator

A Python-based knowledge graph implementation that supports abstract entities, their relationships, and specific instances. The implementation uses both NetworkX for graph operations and RDFLib for RDF-based knowledge representation.

## Features

- Create abstract entities and their instances
- Define and add relationships between instances
- Generate random knowledge graphs
- Export to RDF format (Turtle)
- Query relationships and instances

## Installation

1. Clone this repository
2. Install dependencies:
```bash
pip install -r requirements.txt
```

## Usage

Run the example script to see the knowledge graph in action:
```bash
python example.py
```

### Creating Your Own Knowledge Graph

```python
from knowledge_graph import KnowledgeGraph

# Create a new knowledge graph
kg = KnowledgeGraph()

# Add abstract entities
kg.add_abstract_entity("Person")
kg.add_abstract_entity("Organization")

# Add relations
kg.add_relation("works_for")
kg.add_relation("manages")

# Add instances
kg.add_instance("John", "Person")
kg.add_instance("Alice", "Person")
kg.add_instance("ACME Corp", "Organization")

# Add relationships
kg.add_relationship("John", "works_for", "ACME Corp")
kg.add_relationship("Alice", "manages", "John")

# Export to RDF
print(kg.export_to_rdf())
```

## Implementation Details

The knowledge graph is implemented using two main components:
1. A NetworkX DiGraph for storing and querying the graph structure
2. An RDF Graph for semantic representation and export

The implementation supports:
- Abstract entities (classes)
- Instances of entities
- Relations between instances
- RDF export in various formats
