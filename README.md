<img src="logo.png" width="200" />

# dev-multitools

A collection of Claude Code plugins for software development.

## Install

First, add the marketplace:

```sh
claude plugin marketplace add kt3k/dev-multitools
```

Then, install the plugins you want:

```sh
claude plugin install dev-multitools
claude plugin install ddd
```

## Plugins

### dev-multitools (`mt`)

Swiss army knife for software development. Improve the overall code quality by developing carefully and steadily.

#### `/mt:breakdown`

Break down a given task into subtasks with time estimates. Analyzes the codebase and task requirements to produce a structured plan with estimated effort (XS/S/M/L/XL) for each step. Optionally saves the plan as `plan.md`.

#### `/mt:execute`

Execute a plan step by step. Reads `plan.md` in the current working directory or a plan from the conversation context, then implements each subtask sequentially with verification at each step.

#### `/mt:simplify`

Read source code and find opportunities to simplify, deduplicate, and consolidate. Applies changes after user approval.

### ddd (`ddd`)

Domain-Driven Design toolkit. Review code from DDD perspective, discover ubiquitous language, and maintain DDD documentation.

#### `/ddd:review`

Review the codebase from a Domain-Driven Design perspective. Evaluate bounded contexts, aggregates, entities, value objects, domain services, repositories, domain events, and ubiquitous language usage. Produces a scored report with concrete improvement suggestions.

#### `/ddd:find-ubiquitous-language`

Analyze the codebase to discover and extract the ubiquitous language. Identifies domain terms, their definitions, code locations, and inconsistencies such as synonyms, homonyms, and missing terms. Outputs a structured glossary.

#### `/ddd:update-docs`

Generate or update DDD documentation based on the current state of the codebase. Creates context maps, glossaries, and per-aggregate documentation under `docs/ddd/`. Shows a diff and asks for confirmation before writing.

### twada (`twada`)

Code review from the perspective of @t_wada (Takuto Wada). Focuses on testability, simplicity, and sustainable software design.

#### `/twada:review`

Review code or diffs from the perspective of @t_wada. Evaluates testability (dependency injection, side effect separation, behavior vs implementation testing), test quality (coverage, failure messages, over-mocking), simplicity and YAGNI, quality-speed tradeoffs, technical debt management, and refactoring opportunities. Produces a severity-rated report with concrete suggestions.

## License

MIT
