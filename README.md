# Hot Skills

[![skills.sh](https://skills.sh/b/hot-dev/hot-skills)](https://skills.sh/hot-dev/hot-skills)

AI Agent skills for the Hot programming language.

## Install

Install the Hot skills from the public skills ecosystem:

```bash
npx skills add hot-dev/hot-skills
```

For local development before this repository is published:

```bash
npx skills add . --list
```

The Hot CLI can install the skill snapshots bundled with that particular Hot
release. Use this when you do not want a network dependency; available skills
vary by Hot version, and `hot ai list` shows that release's catalog:

```bash
hot ai add
hot ai add --global
```

## Skills

- `hot-language` - Write, edit, and review `.hot` files. Includes syntax rules,
  standard library notes, examples, and focused test fixtures.
- `hot-ai-agents` - Build and review durable Hot AI agents and their
  JavaScript/TypeScript, Python, Go, Rust, or Java SDK clients.

## Repository Layout

```text
skills/
  hot-ai-agents/
    SKILL.md
    agents/
    references/
    examples/
  hot-language/
    SKILL.md
    references/
    examples/
    test/
```

## Development

Check that the skills CLI can discover the repository before publishing changes:

```bash
npx skills add . --list
```

The canonical skill files live in the `hot` repo under
`resources/ai/skills/`. This repository mirrors those files so the skills can
be listed on skills.sh and available via `npx skills`. After changing skill
files in `hot`, sync this mirror from the `hot` checkout:

```bash
cd ../hot
./scripts/sync-ai-assets.sh ../hot-skills
./scripts/check-ai-assets-sync.sh ../hot-skills
```

Do not edit generated or installed copies under `.skills/`; the CLI tracks them
with a hidden sidecar manifest and they are not source files.

## License

Apache-2.0. See [LICENSE](LICENSE).
