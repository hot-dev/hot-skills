# Hot Skills

[![skills.sh](https://skills.sh/b/hot-dev/hot-skills)](https://skills.sh/hot-dev/hot-skills)

AI Agent skills for the Hot programming language.

## Install

Install the Hot language skill from the public skills ecosystem:

```bash
npx skills add hot-dev/hot-skills
```

For local development before this repository is published:

```bash
npx skills add . --list
```

Hot ships the source copy of these skills in the CLI. Use this when you want the
version bundled with your installed Hot release and do not want a network
dependency:

```bash
hot ai add
hot ai add --global
```

## Skills

- `hot-language` - Write, edit, and review `.hot` files. Includes syntax rules,
  standard library notes, examples, and focused test fixtures.

## Repository Layout

```text
skills/
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
`resources/ai/skills/hot-language`. This repository mirrors those files so the
skills can be listed on skills.sh and available via `npx skills`. After changing
skill files in `hot`, sync this mirror from the `hot` checkout:

```bash
cd ../hot
./scripts/sync-ai-assets.sh ../hot-skills
./scripts/check-ai-assets-sync.sh ../hot-skills
```

Do not edit generated or installed copies under `.skills/`; those include
`hot-skill-hash` markers and are not source files.

## License

Apache-2.0. See [LICENSE](LICENSE).
