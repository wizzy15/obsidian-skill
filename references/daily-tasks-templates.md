# Daily Notes, Tasks & Templates

## Daily notes

Requires the Daily Notes core plugin.

```bash
# Read today's daily note
obsidian daily:read

# Append (creates daily note if needed)
obsidian daily:append content="- 2pm: Call with team" silent
obsidian daily:append content=" (done)" inline    # same line, no newline
obsidian daily:prepend content="## Morning\n\nPriorities" silent

# Open daily note in editor
obsidian daily
obsidian daily silent                  # return path without opening
obsidian daily paneType=split          # open in split pane
```

## Tasks

### List tasks

```bash
obsidian tasks all todo                # vault-wide incomplete
obsidian tasks all done                # vault-wide completed
obsidian tasks file="Project Plan"     # file-specific
obsidian tasks file="Project Plan" todo
obsidian tasks daily                   # today's daily note
obsidian tasks daily todo

# With file paths and line numbers
obsidian tasks all verbose

# Filter by custom status character
obsidian tasks 'status=?'

# Counts
obsidian tasks all total
obsidian tasks all todo total
```

### Update a task

Use `verbose` first to get line numbers, then target by file+line or ref.

```bash
# Toggle done ↔ todo
obsidian task file="Todo" line=8 toggle
obsidian task ref="Recipe.md:8" toggle     # ref=path:line shorthand
obsidian task daily line=3 toggle

# Set specific status
obsidian task file="Todo" line=8 done      # → [x]
obsidian task file="Todo" line=8 todo      # → [ ]
obsidian task file="Todo" line=8 status="-"  # → [-] (custom)

# Show task info
obsidian task file="Recipe" line=8
```

## Templates

Requires the Templates core plugin.

```bash
# List available templates
obsidian templates
obsidian templates total

# Read template content
obsidian template:read name="Meeting Notes"

# Read with variables resolved ({{date}}, {{time}}, {{title}})
obsidian template:read name="Daily" resolve title="Today"

# Create note from template
obsidian create name="Standup Jan 15" template="Meeting Notes" silent

# Insert template into active file
obsidian template:insert name="Meeting Notes"
```
