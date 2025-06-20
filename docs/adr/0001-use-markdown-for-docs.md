# [ADR-0001] Use Markdown for Documentation

## Status

Accepted

## Context

The Extreme Vibe Coding (xVC) methodology requires comprehensive documentation that is:
- Easy to write and maintain
- Version control friendly
- Readable in plain text
- Convertible to other formats
- Universally supported by development tools

We need to choose a documentation format that supports code examples, cross-references, and hierarchical organization while remaining accessible to both humans and AI assistants.

## Decision

We will use Markdown (specifically CommonMark with GitHub Flavored Markdown extensions) for all xVC documentation.

## Consequences

### Positive Consequences

- **Developer Friendly**: Markdown is familiar to most developers
- **AI Compatible**: LLMs are extensively trained on Markdown
- **Version Control**: Plain text works perfectly with Git
- **Tool Support**: Excellent support in all major editors and IDEs
- **Rendering**: Can be rendered beautifully on GitHub, documentation sites, and CLIs
- **Portability**: Easy to convert to HTML, PDF, or other formats
- **Simplicity**: Low barrier to entry for contributors

### Negative Consequences

- **Limited Formatting**: Some complex layouts are difficult or impossible
- **No Dynamic Content**: Cannot include interactive elements without conversion
- **Inconsistent Extensions**: Different flavors may render differently

### Neutral Consequences

- **Learning Curve**: Minimal for those unfamiliar with Markdown
- **Tooling Required**: Need Markdown preview for best experience

## Alternatives Considered

1. **reStructuredText (RST)**: Python documentation standard
   - Pros: More powerful, better for complex documents
   - Cons: Steeper learning curve, less universal support
   - Reason for rejection: Complexity outweighs benefits for our use case

2. **AsciiDoc**: Technical documentation format
   - Pros: Very powerful, good for books and manuals
   - Cons: Less familiar, heavier toolchain
   - Reason for rejection: Overkill for our documentation needs

3. **HTML**: Web standard
   - Pros: Ultimate control over formatting
   - Cons: Verbose, poor readability in source form
   - Reason for rejection: Not human-friendly for writing and editing

4. **LaTeX**: Academic standard
   - Pros: Beautiful output, excellent for mathematical content
   - Cons: Complex, steep learning curve, poor plain text readability
   - Reason for rejection: Too complex for general documentation

## References

- [CommonMark Specification](https://commonmark.org/)
- [GitHub Flavored Markdown](https://github.github.com/gfm/)
- [Markdown Guide](https://www.markdownguide.org/)

## Notes

All existing xVC documentation is already in Markdown format. This ADR formalizes our existing practice and provides guidance for future documentation efforts.

For consistency, we recommend:
- Using `.md` file extension
- Following CommonMark spec with GFM extensions
- Using ATX-style headers (`#` syntax)
- Preferring fenced code blocks with language hints
- Using relative links for internal references

---

**Date**: 2025-01-20
**Author**: xVC Team
**Reviewers**: Documentation Team