# AGENTS.md - Hot Skills Repository

This repository publishes agent skills for the Hot programming language.
`skills/hot-language/` mirrors the source files from the Hot CLI at
`hot/resources/ai/skills/hot-language/` so they can be listed on skills.sh.

## Workflow

- Edit source files in the `hot` repo under `resources/ai/skills/`.
- Do not commit installed `.skills/` copies or `hot-skill-hash` marker lines.
- Run `npx skills add . --list` to verify skills CLI discovery.
- After changing the source skill, sync this mirror from the `hot` repo with
  `bash scripts/sync-ai-assets.sh ../hot-skills`.

## Hot Syntax Reminders

Hot is a functional, expression-based language with syntax that differs from
mainstream languages:

| Wrong | Correct | Rule |
| --- | --- | --- |
| `name = "Alice"` | `name "Alice"` | No `=` for assignment |
| `a + b` | `add(a, b)` | No infix operators |
| `a == b` | `eq(a, b)` | Comparison is a function |
| `if (x) { } else { }` | `if(x, then, else)` or `cond` | No if/else blocks |
| `for x in items` | `map(items, ...)` | No loops |

Every `.hot` file must start with a namespace declaration, for example:

```hot
::demo::example ns
```

Use `skills/hot-language/references/` for detailed syntax and library context.
