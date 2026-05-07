# MVP - Task Tracker

## Goal
Build a Task Tracker CLI from the `task-tracker` roadmap that manages tasks using pure Node.js and a JSON file for storage.

## Requirements

1. A command line application running on Node.js.
2. Accept input via positional arguments.
3. Store task data in `data/task.json`.
4. Auto-create the JSON file if it does not exist.
5. Use built-in Node.js modules only (`fs`, `path`).
6. No external dependencies.
7. Handle errors and edge cases gracefully.

## Features

- `task-cli add "description"`
  - Add a new task with `todo` status.
- `task-cli update <id> "new description"`
  - Update a task description.
- `task-cli delete <id>`
  - Delete a task by ID.
- `task-cli mark-in-progress <id>`
  - Change task status to `in-progress`.
- `task-cli mark-done <id>`
  - Change task status to `done`.
- `task-cli list`
  - List all tasks.
- `task-cli list todo`
  - List tasks with `todo` status.
- `task-cli list in-progress`
  - List tasks with `in-progress` status.
- `task-cli list done`
  - List tasks with `done` status.

## Task Properties
Each task must have these properties:

- `id`: unique identifier
- `description`: task description
- `status`: `todo`, `in-progress`, or `done`
- `createdAt`: timestamp when the task is created
- `updatedAt`: timestamp when the task is last updated

## Command Example

```powershell
task-cli add "Buy groceries"
# Task added successfully (ID: 1)

task-cli list
# ID: 1
#   Description: Buy groceries
#   Status: todo
#   Created: 2026-05-07T10:18:08.747Z
#   Updated: 2026-05-07T10:18:08.747Z
```

## Implementation Notes

- `index.mjs` as the CLI entry point.
- `src/cli.mjs` for argument parsing.
- `src/commands/taskCommands.mjs` for command routing.
- `src/services/taskService.mjs` for business logic.
- `src/model/storage.mjs` for reading/writing `data/task.json`.
- `src/config/constants.mjs` for status constants and help text.
- `src/utils/format.mjs` for output formatting.

This document covers all requirements and core commands for the MVP Task Tracker from the roadmap.