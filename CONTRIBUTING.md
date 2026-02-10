# Contributing to Awesome Performance Engineering

Thanks for your interest in contributing! This project aims to maintain a high-quality, opinionated collection of performance engineering tools and resources.

## What we welcome

- **New tools** that fit the performance engineering scope (observability, performance testing, profiling, chaos engineering, etc.)
- **Improvements** to existing descriptions or categorization
- **Corrections** to broken or outdated links
- **New categories** backed by concrete use cases
- **Learning resources** (books, articles, talks) of lasting value

## What we avoid

- Unmaintained or abandoned tools (no activity for 2+ years without explanation)
- Tools without documentation or public references
- Duplicate entries across sections (use cross-references instead)
- Purely promotional or marketing-driven content
- Tools that require private access or have no public information

## How to contribute

### Suggesting a tool

The easiest way to contribute is to [open an issue](../../issues/new/choose) using the **Tool Suggestion** template. This lets us discuss the tool before adding it.

### Submitting a pull request

1. **Fork** the repository
2. **Create a branch** from `main` (`git checkout -b add-tool-name`)
3. **Add your entry** following the format conventions below
4. **Submit a pull request** with a clear description of why this tool belongs here

### Entry format

Each tool entry follows this pattern:

```markdown
* **[Tool Name](https://tool-website.com/)** INDICATORS — One to three sentence description. What it does, what makes it notable, where it fits. [Language] [License] — [GitHub](https://github.com/org/repo)
```

**Indicators** are emoji tags from the legend in each list (e.g., `⭐🟢🔵📚`). Apply them honestly based on the tool's actual status, not aspirations.

**Guidelines for descriptions:**

- Be factual and concise (1-3 sentences)
- Mention what makes the tool distinctive, not just what it does
- Include the primary language, license, and GitHub link when available
- For commercial tools, use `[Commercial]` instead of a license

### Placement

- Add new tools at the end of the relevant section (we reorder periodically)
- If a tool spans multiple categories, place it in the most relevant one and add cross-references

## Quality standards

- Every link must be valid and point to an official or canonical source
- Descriptions must be original (not copied from the tool's own marketing)
- Indicators must be accurate and applied consistently with existing entries
- Commercial tools are welcome but must be clearly marked with `🟠`

## Code of conduct

Be respectful, constructive, and focused on the goal: helping practitioners find the right tools for their context.

## License

By contributing, you agree that your contributions will be released under [CC0 1.0 Universal](LICENSE).
