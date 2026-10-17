# Rozee Job Search CLI

A small Bun-powered CLI and Agent Skill for searching public Rozee.pk job
listings in Pakistan. It parses search results into a compact format and can
fetch a selected listing's structured details.

## Usage

Install [Bun](https://bun.sh/), then run the CLI from the repository root:

```bash
bun run .agents/skills/rozee-search/cli/src/cli.ts search \
  --query "Machine Learning Intern" \
  --location Islamabad \
  --limit 10 \
  --format table
```

To inspect a result, pass its returned `id` or `url`:

```bash
bun run .agents/skills/rozee-search/cli/src/cli.ts detail "<result-id>" --format plain
```

The CLI supports JSON, table, and plain-text output. See
`.agents/skills/rozee-search/SKILL.md` for the complete command reference.

## Development

```bash
cd .agents/skills/rozee-search/cli
bun install
bun run typecheck
bun test
```

The normal test suite is local-only. A low-volume live search/detail smoke test
is opt-in; follow the instructions in the CLI README and review Rozee.pk's
current terms before running it.

## Responsible use

Automated access is not clearly confirmed by the accessible Rozee.pk terms.
Keep searches low-volume and for personal use. Do not bulk-collect or
redistribute listing content, and seek permission before reusing it.

## License and attribution

MIT licensed. The original workspace license and copyright notice are retained.
The surrounding job-search framework is
[MadsLorentzen/ai-job-search](https://github.com/MadsLorentzen/ai-job-search).
