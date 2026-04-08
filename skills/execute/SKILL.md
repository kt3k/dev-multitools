---
name: execute
description: |
  Execute a plan step by step. Reads plan.md in the current working directory
  or a plan from the conversation context, then implements each subtask sequentially.
---

## Execute Skill

Implement a task breakdown plan step by step.

### Plan Resolution

1. If `plan.md` exists in the current working directory, use it.
2. Otherwise, look for a plan in the current conversation context (e.g. output from the `breakdown` skill).
3. If no plan is found, ask the user to provide one or run `breakdown` first.

### Execution Flow

1. **Present the plan**: Show the full list of subtasks to the user and confirm before starting.

2. **Implement step by step**: For each leaf subtask in order:
   - Announce which subtask you are starting (e.g. `## Step 1.1: <subtask name>`)
   - Read relevant source files to understand the current state
   - Implement the changes
   - Verify the changes work (run tests, type checks, etc. if applicable)
   - Mark the subtask as done and briefly report what was done

3. **Report progress**: After completing each subtask, show the updated checklist with completed items checked off.

4. **Handle issues**: If a subtask is blocked or unclear:
   - Stop and ask the user for clarification
   - Do NOT skip subtasks or guess at requirements

### Guidelines

- Follow the plan's order and scope. Do not add work beyond what the plan specifies.
- Keep each step's changes focused and minimal — one subtask at a time.
- If the plan turns out to be wrong or outdated mid-execution, stop and discuss with the user before continuing.
