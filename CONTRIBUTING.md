# Contributing to Awesome Performance Engineering

Thanks for your interest in contributing. This list is an opinionated, curated collection of performance engineering tools, covering observability and performance testing as complementary disciplines.

## What belongs here

- **Tools and services** within the performance engineering scope: observability, performance testing, profiling, benchmarking, chaos engineering, and adjacent tooling.
- **Improvements** to existing descriptions, indicators, or categorization.
- **Corrections** to broken, redirected, or outdated links.
- **New categories**, when backed by several concrete tools that have no good home in the existing sections.
- **Other awesome lists** on adjacent topics, for the [Related](README.md#related) section.

## What does not belong here

- Unmaintained or abandoned tools — no activity for two years or more without an explanation.
- Tools without public documentation or verifiable references.
- Tools that require private access, an invitation, or a sales call to evaluate.
- Duplicate entries. A tool spanning several categories is listed once, in the most relevant one; `awesome-lint` rejects repeated links.
- Purely promotional or marketing-driven content.
- Articles, tutorials, blog posts, books, and talks. This list is a single `awesome-lint`-compliant file of tools and has no section for learning resources.

## Entry format

Every entry is a **single line** matching the pattern `awesome-lint` validates:

```markdown
- [Tool Name](https://github.com/org/repo) - INDICATORS Description ending with a period.
```

- **Bullet** — a hyphen `-`, not an asterisk.
- **Link text** — the plain tool name. No bold, no backticks.
- **Separator** — ` - `, a single hyphen surrounded by spaces. Not an em dash.
- **Indicators** — emoji from the legend, placed at the start of the description in legend order: ⭐ widely adopted, 🟢 active, 🔵 cloud-native, 🟠 commercial, 🚀 high performance. Apply them honestly, based on the tool's actual status rather than its ambitions.
- **Description** — one to three factual sentences in neutral third person, in your own words, ending with a period. Keep it on one line; a wrapped continuation line breaks the convention even though the linters tolerate it.
- **URL** — prefer the GitHub repository. Fall back to the official website for commercial tools with no public repo, and link the English version when the site is localized.
- **No bracketed metadata** — tokens such as `[Language]` or `[License]` are parsed as undefined link references and fail `awesome-lint`.

Add new tools at the end of the relevant section; sections are reordered periodically.

### Writing the description

- Say what the tool does and what makes it distinctive, not what its homepage claims.
- Use original wording. Descriptions copied or lightly paraphrased from a project's own tagline, README, or package summary are rejected.
- Avoid comparative marketing ("unlike X", "the only tool that"), superlatives, and claims a reader cannot verify.
- Do not address the reader — no "your favorite framework", no second person.

## How to contribute

### Suggesting a tool

The easiest path is to [open an issue](https://github.com/be-next/awesome-performance-engineering/issues/new/choose) with the **Tool Suggestion** template, so the tool can be discussed before it is added.

### Submitting a pull request

1. **Fork** the repository.
2. **Create a branch** from `main`, for example `git checkout -b add-tool-name`.
3. **Add your entry** following the format above.
4. **Run the checks** locally — both must pass with zero errors:

   ```bash
   npx markdownlint-cli2 "**/*.md"
   npx awesome-lint
   ```

5. **Open the pull request**, explaining why the tool belongs in the section you chose.

Keep one pull request to one change. Unrelated fixes are welcome, as separate pull requests.

## Quality standards

- Every link must resolve and point to an official or canonical source.
- Descriptions must be original and factual.
- Indicators must be accurate and consistent with the entries around them.
- Commercial tools are welcome and must carry `🟠`.
- Content changes to `README.md` are recorded in [CHANGELOG.md](CHANGELOG.md) under the current date.

## Code of conduct

Please read and follow the [Code of Conduct](code-of-conduct.md). Be respectful, constructive, and focused on the goal: helping practitioners find the right tools for their context.

## License

By contributing, you agree that your contributions will be released under [CC0 1.0 Universal](LICENSE).
