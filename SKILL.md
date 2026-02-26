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
joplin config sync.6.path "https://your-webdav-server/path"
joplin config sync.6.username "your-username"
joplin config sync.6.password "your-password"
joplin sync
```

## Common Commands

### List Notebooks and Notes
```bash
joplin ls                          # List notebooks
joplin ls "Notebook Name"          # List notes in a notebook
joplin status                      # Show sync status and note counts
```

### Read Note
```bash
joplin cat <note-id>               # Display note content
joplin note <note-id>              # Open note in editor
```

### Create Note
```bash
joplin mknote "Note Title"         # Create note in default notebook
joplin mknote "Note Title" --notebook "Notebook Name"
joplin mkbook "New Notebook"       # Create new notebook
```

### Edit Note
```bash
joplin edit --note <note-id>       # Edit note in editor
```

### Delete Note
```bash
joplin rmnote <note-id>            # Delete note
joplin rmbook "Notebook Name"      # Delete notebook
```

### Todos
```bash
joplin todos                       # List all todos
joplin todo <note-id>              # Toggle todo status
joplin done <note-id>              # Mark as done
joplin undone <note-id>            # Mark as not done
```

### Sync
```bash
joplin sync                        # Sync with WebDAV server
```

### Export
```bash
joplin export <note-id> --format md
joplin export <note-id> --format html
joplin export <note-id> --format pdf
```

### Search

Note: `joplin search` is only available in GUI mode. Use `joplin ls` and pipe to grep instead.
