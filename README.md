<img src="logo.png" width="200" />

# kt3k-skills

Swiss army knife for software development. Improve the overall code quality by developing carefully and steadily.

## Install

First, add the marketplace:

```sh
claude plugin marketplace add kt3k/skills
```

Then, install the plugin:

```sh
claude plugin install kt
```

## Skills

### `/kt:breakdown`

Break down a given task into subtasks with time estimates. Analyzes the codebase and task requirements to produce a structured plan with estimated effort (XS/S/M/L/XL) for each step. Optionally saves the plan as `plan.md`.

### `/kt:execute`

Execute a plan step by step. Reads `plan.md` in the current working directory or a plan from the conversation context, then implements each subtask sequentially with verification at each step.

### `/kt:simplify`

Read source code and find opportunities to simplify, deduplicate, and consolidate. Applies changes after user approval.

### `/kt:review-testability`

Review code or diffs with a focus on testability, simplicity, and sustainable design. Evaluates dependency injection, side-effect separation, behavior-vs-implementation testing, test quality, YAGNI, quality-speed tradeoffs, technical debt, and refactoring opportunities. Produces a severity-rated report with concrete suggestions.

### `/kt:review-ddd`

Review the codebase from a Domain-Driven Design perspective. Evaluate bounded contexts, aggregates, entities, value objects, domain services, repositories, domain events, and ubiquitous language usage. Produces a scored report with concrete improvement suggestions.

### `/kt:find-ubiquitous-language`

Analyze the codebase to discover and extract the ubiquitous language. Identifies domain terms, their definitions, code locations, and inconsistencies such as synonyms, homonyms, and missing terms. Outputs a structured glossary.

### `/kt:document-ddd`

Generate or update DDD documentation based on the current state of the codebase. Produces a single `DOMAIN.md` with context map, glossary, and per-aggregate documentation. Shows a diff and asks for confirmation before writing.

## License

MIT
