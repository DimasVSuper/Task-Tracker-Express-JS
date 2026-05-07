# Task Tracker CLI

Task Tracker is a simple command line application to manage daily tasks.
This project is built with pure Node.js (no framework) and stores data in a local JSON file.

## Features

- Add new tasks
- Update task descriptions
- Delete tasks
- Mark tasks as `in-progress`
- Mark tasks as `done`
- List all tasks
- List tasks by status: `todo`, `in-progress`, `done`

## Tech Stack

- Node.js with `type: module`
- Built-in Node modules: `fs`, `path`
- Data stored in `data/task.json`

## Usage

From the project folder:

```powershell
.\task-cli.cmd add "Buy groceries"
.\task-cli.cmd list
.\task-cli.cmd mark-in-progress 1
.\task-cli.cmd mark-done 1
.\task-cli.cmd update 1 "Buy groceries and cook dinner"
.\task-cli.cmd delete 1
```

If you want to use `task-cli` directly after a local install:

```powershell
npm link
task-cli add "Buy groceries"
task-cli list
```

## Folder Structure

- `index.mjs` - CLI entry point
- `src/cli.mjs` - command line parser
- `src/commands/taskCommands.mjs` - CLI command routing
- `src/services/taskService.mjs` - task business logic
- `src/model/storage.mjs` - read/write `data/task.json`
- `src/config/constants.mjs` - status constants and help text
- `src/utils/format.mjs` - task output formatting
- `data/task.json` - task data storage

## Notes

This app is designed as an MVP project from the `task-tracker` roadmap.
All features rely on native Node.js without external libraries.

## Link
https://roadmap.sh/projects/task-tracker
