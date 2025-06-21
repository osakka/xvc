# ADR-001: Document-Centric Architecture

### Status
Proposed

### Context
We need to decide on the fundamental data model for the worca/jdbx LLM runtime system. Options include:
- Traditional relational model with separate tables
- Object-oriented model with class hierarchies
- Document-based model where everything is a document
- Hybrid approach mixing multiple paradigms

The system needs to handle:
- LLM prompts and templates
- JavaScript transformers
- Session state
- Configuration
- Integration definitions
- Execution history

### Decision
We will adopt a pure document-centric architecture where EVERYTHING is stored as a document in jdbx, including:
- Prompts
- Transformers (JavaScript code as documents)
- LLM integrations
- Session state
- Configuration
- Execution logs

Documents will have a standard structure:
```json
{
  "_id": "unique-identifier",
  "_type": "document-type",
  "_version": 1,
  "_created": "2024-01-20T10:00:00Z",
  "_modified": "2024-01-20T10:00:00Z",
  // Type-specific fields
}
```

### Consequences

#### Positive
- Unified storage model - one pattern to rule them all
- Flexible schema evolution
- Easy versioning and history tracking
- Natural fit for JSON-based LLM interactions
- JavaScript transformers can be stored and executed directly

#### Negative
- May need indexes for relationships between documents
- Complex queries might require multiple document fetches
- Type safety must be enforced at application level

#### Neutral
- All data access goes through document API
- Requires careful document type design

### References
- JDBX case study showing success of document model
- MongoDB's document model proving scalability