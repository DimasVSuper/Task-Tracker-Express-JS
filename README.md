# Task Tracker CLI

Task Tracker adalah aplikasi command line sederhana untuk mengelola tugas sehari-hari.
Proyek ini dibuat dengan pure Node.js tanpa framework, menggunakan penyimpanan lokal dalam file JSON.

## Fitur

- Tambah tugas baru
- Perbarui deskripsi tugas
- Hapus tugas
- Tandai tugas sebagai `in-progress`
- Tandai tugas sebagai `done`
- Daftar semua tugas
- Daftar tugas berdasarkan status: `todo`, `in-progress`, `done`

## Teknologi

- Node.js dengan `type: module`
- Modul bawaan Node: `fs`, `path`
- Penyimpanan data di `data/task.json`

## Cara Pakai

Dari folder proyek:

```powershell
.\task-cli.cmd add "Buy groceries"
.\task-cli.cmd list
.\task-cli.cmd mark-in-progress 1
.\task-cli.cmd mark-done 1
.\task-cli.cmd update 1 "Buy groceries and cook dinner"
.\task-cli.cmd delete 1
```

Jika ingin menggunakan `task-cli` langsung setelah install lokal:

```powershell
npm link
task-cli add "Buy groceries"
task-cli list
```

## Struktur Folder

- `index.mjs` - entry point CLI
- `src/cli.mjs` - parser command line
- `src/commands/taskCommands.mjs` - routing perintah CLI
- `src/services/taskService.mjs` - business logic task
- `src/model/storage.mjs` - baca/tulis `data/task.json`
- `src/config/constants.mjs` - konstanta status dan help text
- `src/utils/format.mjs` - format output task
- `data/task.json` - penyimpanan data tugas

## Catatan

Aplikasi ini dirancang sebagai project MVP dari roadmap `task-tracker`.
Semua fitur menggunakan native Node.js tanpa library eksternal.


## Link 
https://roadmap.sh/projects/task-tracker
