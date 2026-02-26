---
name: joplin
description: Interact with Joplin notes via CLI. Use when user wants to: (1) Search, read, create, edit, or delete notes, (2) List notebooks or folders, (3) Manage todos, (4) Sync notes with WebDAV, (5) Export notes to PDF/HTML/Markdown
---

# Joplin CLI Skill

Use `joplin` CLI to interact with Joplin notes.

## Setup

If Joplin is not configured with WebDAV, configure it:

```bash
joplin config sync.target 6
joplin config sync.6.url "https://your-webdav-server/path"
joplin config sync.6.username "your-username"
joplin config sync.6.password "your-password"
joplin sync
```

## Common Commands

### Search Notes
```bash
joplin search "query"
joplin search "query" --folder "folder-name"
```

### List Notebooks/Folders
```bash
joplin ls-folders
joplin notebook ls
```

### Read Note
```bash
joplin cat <note-id>
joplin note <note-id>
```

### Create Note
```bash
joplin mknote "Note Title"
joplin mkbook "New Notebook"
```

### Edit Note
```bash
joplin edit --note <note-id>
```

### Delete Note
```bash
joplin rmnote <note-id>
```

### Todos
```bash
joplin todos
joplin todo <note-id>
```

### Sync
```bash
joplin sync
```

### Export
```bash
joplin export <note-id> --format md
joplin export <note-id> --format html
joplin export <note-id> --format pdf
```

## Note ID Retrieval

Get note ID from search:
```bash
joplin search "query" --short
```

Get folder ID:
```bash
joplin ls-folders --short
```
