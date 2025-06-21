# ADR-004: State Management Strategy

### Status
Proposed

### Context
LLM sessions require sophisticated state management for:
- Context window tracking
- Token counting
- Checkpoint recovery
- Multi-project state isolation
- Session history

Options:
- In-memory state with periodic persistence
- Full database persistence for every change
- Hybrid approach with checkpoints
- Event sourcing
- Redis-style caching layer

### Decision
We will implement a checkpoint-based state management system:
- Session state is maintained in memory during execution
- Checkpoints are created at stage boundaries
- Checkpoints are full state snapshots stored as documents
- Recovery loads the latest checkpoint
- History is maintained through checkpoint chain

Checkpoint document structure:
```json
{
  "_id": "checkpoint:session-x-stage-3",
  "_type": "checkpoint",
  "session_id": "session:project-x-2024-01-20",
  "stage": "code_generation",
  "state": {
    "context_tokens": 15000,
    "messages": [...],
    "variables": {...}
  },
  "previous": "checkpoint:session-x-stage-2"
}
```

### Consequences

#### Positive
- Fast in-memory operations during execution
- Clear recovery points
- Natural stage boundaries for checkpoints
- Can replay from any checkpoint
- Efficient storage (only checkpoint at boundaries)

#### Negative
- Potential data loss between checkpoints
- Memory usage for large sessions
- Checkpoint storage grows over time

#### Neutral
- Need checkpoint garbage collection strategy
- Stage design affects checkpoint frequency

### References
- JDBX checkpoint-based memory management success
- Database transaction log concepts