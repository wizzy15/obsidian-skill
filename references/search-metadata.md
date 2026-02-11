# Search & Metadata

## Search

```bash
obsidian search query="project deadline"
obsidian search query="API" limit=10
obsidian search query="bug" path="Projects/"     # scope to folder

# Output formats
obsidian search query="todo" format=text         # file paths (default)
obsidian search query="todo" format=json         # JSON array

# Flags
obsidian search query="React" case               # case-sensitive
obsidian search query="fix" matches              # include match context
obsidian search query="review" total             # count only
obsidian search query="TODO" --copy              # copy results to clipboard

# Open search UI in Obsidian
obsidian search:open query="todo"
```

## Tags

```bash
# All tags in vault
obsidian tags all counts sort=count

# Tags for a file
obsidian tags file="Project Plan"

# Tag details
obsidian tag name="project"
obsidian tag name="project" verbose    # file list + count
obsidian tag name="project" total      # occurrence count

# Counts
obsidian tags all total
```

## Properties (frontmatter)

```bash
# List vault properties
obsidian properties all counts sort=count
obsidian properties all format=yaml
obsidian properties all format=tsv

# File properties
obsidian properties file="Note"

# Read
obsidian property:read name="status" file="Task"

# Set
obsidian property:set name="status" value="done" file="Task"
obsidian property:set name="priority" value="1" type=number file="Task"
obsidian property:set name="tags" value="project,active" type=list file="Task"

# Remove
obsidian property:remove name="draft" file="Post"
```

Types: `text`, `list`, `number`, `checkbox`, `date`, `datetime`.

## Aliases

```bash
obsidian aliases all total
obsidian aliases all verbose           # include file paths
obsidian aliases file="Note"
```

## Knowledge graph

### Backlinks

```bash
obsidian backlinks file="API Design"
obsidian backlinks file="API Design" counts    # with link counts
obsidian backlinks file="API Design" total
```

### Outgoing links

```bash
obsidian links file="API Design"
obsidian links file="API Design" total
```

### Orphan notes (no incoming links)

```bash
obsidian orphans total
obsidian orphans
obsidian orphans all                   # include non-markdown
```

### Dead-end notes (no outgoing links)

```bash
obsidian deadends total
obsidian deadends
obsidian deadends all
```

### Unresolved links (broken wikilinks)

```bash
obsidian unresolved total
obsidian unresolved counts             # with occurrence counts
obsidian unresolved verbose            # with source files
```
