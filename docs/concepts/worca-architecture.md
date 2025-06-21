# Worca/JDBX Architecture Documentation

This directory contains the architectural documentation for the Worca/JDBX LLM runtime system.

## Structure

### Architecture Decision Records
All ADRs are located in `/docs/adr/`:
- [ADR-001](../docs/adr/ADR-001-document-centric-architecture.md): Document-Centric Architecture
- [ADR-002](../docs/adr/ADR-002-javascript-as-configuration.md): JavaScript as Configuration Language
- [ADR-003](../docs/adr/ADR-003-pipeline-execution-model.md): Pipeline Execution Model
- [ADR-004](../docs/adr/ADR-004-state-management-strategy.md): State Management Strategy
- [ADR-005](../docs/adr/ADR-005-multi-project-isolation.md): Multi-Project Isolation Strategy
- [ADR-006](../docs/adr/ADR-006-resource-allocation-strategy.md): Resource Allocation Strategy

### Architecture Diagrams
All diagrams are located in `/docs/diagrams/`:
- [System Overview](../docs/diagrams/system-overview.svg): High-level architecture layers
- [Pipeline Execution Flow](../docs/diagrams/pipeline-execution-flow.svg): How pipelines execute with checkpointing
- [Document Model](../docs/diagrams/document-model.svg): Document types and namespace isolation

## Key Architectural Principles

1. **Everything is a Document**
   - Prompts, transformers, configurations, state - all stored as documents
   - Unified storage model simplifies the system

2. **JavaScript Everywhere**
   - Configuration logic in JavaScript
   - Transformers as JavaScript functions
   - Leverages existing developer knowledge

3. **Pipeline-Based Execution**
   - All operations are pipelines
   - Clear stages with checkpointing
   - Error recovery built-in

4. **Namespace Isolation**
   - Projects fully isolated via namespaces
   - No accidental cross-project access
   - Shared resources explicitly marked

5. **Resource Fairness**
   - Token bucket algorithm for rate limiting
   - Priority queues for important projects
   - Cost tracking and limits

## Implementation Status

✅ Proposed Architecture
⏳ ADRs Under Review
🔲 Implementation Phase
🔲 Testing Phase
🔲 Production Ready

## Next Steps

1. Review and approve ADRs
2. Begin prototype implementation
3. Validate architectural decisions
4. Refine based on learnings

## Questions for Consideration

1. Should we support plugins/extensions?
2. How do we handle versioning of transformers?
3. What metrics should we track by default?
4. How do we handle transformer debugging?
5. Should we support transformer composition?

## Contributing

When adding new architectural decisions:
1. Create a new ADR using the [template](./adr/template.md)
2. Number it sequentially
3. Update this README
4. Create supporting diagrams if needed