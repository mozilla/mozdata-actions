# mozdata-actions

Shared GitHub Actions workflows for Mozilla Data Engineering repositories.

## `claude-review` - Claude Code Review

Reviews pull requests with [Claude Code](https://claude.ai/code) through
`anthropics/claude-code-action` and posts a single `COMMENT` review with inline findings.

### Usage

Copy [`examples/claude-review.yml`](examples/claude-review.yml) to `.github/workflows/` in a target
repository and add an `ANTHROPIC_API_KEY` secret.

### Inputs

| Input                 | Default  | Description                                                                                       |
| --------------------- | -------- | ------------------------------------------------------------------------------------------------- |
| `review-instructions` | `""`     | Repository-specific review guidance added to the prompt. Without it, Claude reads `AGENTS.md`/`CLAUDE.md` if present. |
| `clone-repo`          | `""`     | Additional public repository (`owner/name`) cloned at `../<name>` so Claude can read its conventions.         |
| `max-budget-usd`      | `"6.00"` | Maximum spend per review in USD.                                                                  |

| Secret              | Required | Description       |
| ------------------- | -------- | ----------------- |
| `ANTHROPIC_API_KEY` | yes      | Anthropic API key |
