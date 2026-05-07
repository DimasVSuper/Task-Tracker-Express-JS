# Architecture

## Overview

This project is a pure Node.js CLI application for tracking tasks. It uses a modular architecture that separates command parsing, business logic, storage, configuration, and output formatting.

## Layers

- **Entry point**: `index.mjs`
  - Starts the CLI and passes command line arguments to the CLI layer.

- **CLI layer**: `src/cli.mjs`
  - Parses `process.argv` and delegates commands to the command router.

- **Commands layer**: `src/commands/taskCommands.mjs`
  - Routes commands such as `add`, `update`, `delete`, `mark-in-progress`, `mark-done`, and `list` to service functions.
  - Contains the help text for invalid or missing commands.

- **Service layer**: `src/services/taskService.mjs`
  - Implements the core task operations and business rules.
  - Validates input, updates task metadata, and returns formatted output.

- **Model layer**: `src/model/storage.mjs`
  - Reads and writes JSON task data from `data/task.json`.
  - Ensures the storage file exists and handles invalid JSON safely.

- **Utility layer**: `src/utils/format.mjs`
  - Formats task objects into user-friendly CLI output.

- **Configuration**: `src/config/constants.mjs`
  - Defines task statuses and help text constants.

## Data flow

1. User runs `task-cli <command> ...`.
2. `index.mjs` forwards arguments to `src/cli.mjs`.
3. `src/cli.mjs` identifies the command and calls `runCommand`.
4. `src/commands/taskCommands.mjs` invokes the appropriate service method.
5. `src/services/taskService.mjs` reads current tasks from `src/model/storage.mjs`.
6. Service methods modify the task list and save it back through `writeTasks`.
7. The CLI prints success or error messages to the console.

## File structure

- `index.mjs`
- `package.json`
- `docs/ARCHITECTURE.md`
- `MVP.md`
- `README.md`
- `data/task.json`
- `src/cli.mjs`
- `src/commands/taskCommands.mjs`
- `src/services/taskService.mjs`
- `src/model/storage.mjs`
- `src/utils/format.mjs`
- `src/config/constants.mjs`

## Notes

- The architecture keeps I/O and business logic separate for easier maintenance.
- The project is designed to be testable and extensible while staying lightweight.