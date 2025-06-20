# Architecture Decision Records

This directory contains Architecture Decision Records (ADRs) for the Extreme Vibe Coding (xVC) project.

## What is an ADR?

An Architecture Decision Record (ADR) captures an important architectural or methodological decision made along with its context and consequences.

## ADR Process

1. **Propose**: Create a new ADR using the [template](template.md)
2. **Discuss**: Review with stakeholders
3. **Decide**: Mark as accepted, rejected, or superseded
4. **Document**: Record the decision and rationale

## ADR Format

We use a lightweight format focusing on:
- **Title**: Brief noun phrase
- **Status**: Proposed, Accepted, Rejected, Superseded
- **Context**: What prompted this decision?
- **Decision**: What we decided
- **Consequences**: What happens as a result

## Naming Convention

ADRs are numbered sequentially:
- Format: `NNNN-brief-description.md`
- Example: `0001-use-markdown-for-docs.md`

## ADR Index

| ADR | Title | Status | Date |
|-----|-------|--------|------|
| [0001](0001-use-markdown-for-docs.md) | Use Markdown for Documentation | Accepted | 2025-01-20 |

## Creating a New ADR

1. Copy the [template](template.md)
2. Name it with the next sequential number
3. Fill in all sections
4. Submit for review
5. Update this index when accepted

## Principles for ADRs

- **Immutable**: Once accepted, ADRs are not edited (supersede instead)
- **Contextual**: Include enough context for future readers
- **Decisive**: Clear decision statement
- **Consequential**: Honest about trade-offs

## When to Write an ADR

Write an ADR when:
- Selecting between competing technologies
- Establishing new patterns or practices
- Making decisions with long-term impact
- Changing established practices
- Resolving significant debates

## References

- [Michael Nygard's ADR article](https://cognitect.com/blog/2011/11/15/documenting-architecture-decisions)
- [ADR GitHub organization](https://adr.github.io/)