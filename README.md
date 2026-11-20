# Hot Skills

[![skills.sh](https://skills.sh/b/hot-dev/hot-skills)](https://skills.sh/hot-dev/hot-skills/hot-language)

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
hot ai add             # project: .agents/skills/ and .claude/skills/
hot ai add --global    # home folder: ~/.agents/skills/ and ~/.claude/skills/
```

From Hot 3.0.13, these folders are where agents look: Codex, Cursor, Gemini
CLI, GitHub Copilot and OpenCode read `.agents/skills/`, and Claude Code reads
only `.claude/skills/`. Run `hot ai update` after upgrading Hot (`hot update`
refreshes global skills itself). Hot 3.0.12 and earlier installed skills in
`.skills/`, which agents don't read; `hot ai update` on 3.0.13 or later moves
them.

## Skills

- [`hot-language`](https://skills.sh/hot-dev/hot-skills/hot-language) - Write,
  edit, and review `.hot` files. Includes syntax rules, standard library notes,
  examples, and focused test fixtures.
- [`hot-ai-agents`](https://skills.sh/hot-dev/hot-skills/hot-ai-agents) - Build
  and review durable Hot AI agents and their JavaScript/TypeScript, Python, Go,
  Rust, or Java SDK clients.

Each skill's `metadata.version` in `SKILL.md` changes whenever its content
does, and a `vX.Y.Z` tag marks the snapshot that ships with that Hot release.

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

Do not edit installed copies under `.agents/skills/`, `.claude/skills/` or the
old `.skills/`; the CLI tracks them with a hidden sidecar manifest and they are
not source files.

## License

Apache-2.0. See [LICENSE](LICENSE).
