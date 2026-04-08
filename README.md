# dev-multitools

Swiss army knife for software development — a Claude Code plugin that helps you improve overall code quality by developing carefully and steadily.

## Install

First, add the marketplace:

```sh
claude plugin marketplace add kt3k/dev-multitools
```

Then, install the plugin:

```sh
claude plugin install dev-multitools
```

## Skills

### `/breakdown`

Break down a given task into subtasks with time estimates. Analyzes the codebase and task requirements to produce a structured plan with estimated effort (XS/S/M/L/XL) for each step. Optionally saves the plan as `plan.md`.

### `/execute`

Execute a plan step by step. Reads `plan.md` in the current working directory or a plan from the conversation context, then implements each subtask sequentially with verification at each step.

### `/simplify`

Read source code and find opportunities to simplify, deduplicate, and consolidate. Applies changes after user approval.

## License

MIT
