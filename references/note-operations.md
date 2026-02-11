# Note Operations

## Read

```bash
obsidian read file="Note"
obsidian read path="Folder/Note.md"
obsidian read                         # active file
obsidian read --copy                  # read + copy to clipboard
```

## Outline

```bash
obsidian outline file="Doc"
obsidian outline file="Doc" format=tree   # indented tree (default)
obsidian outline file="Doc" format=md     # markdown headings
obsidian outline file="Doc" total         # heading count
```

## Word count

```bash
obsidian wordcount file="Essay"
obsidian wordcount file="Essay" words       # word count only
obsidian wordcount file="Essay" characters  # character count only
```

## File info

Returns path, name, extension, size, created, modified timestamps.

```bash
obsidian file file="Note"
obsidian file path="Folder/Note.md"
```

## Create

```bash
obsidian create name="Note" content="# Title\n\nBody"
obsidian create name="Note" path="Folder/"
obsidian create name="Note" template="Meeting Notes"
obsidian create name="Note" content="text" silent       # don't open in editor
obsidian create name="Note" content="text" overwrite    # replace existing
obsidian create name="Note" content="text" newtab       # open in new tab
```

`create` fails if file exists unless `overwrite` is set. Prefer `append`/`prepend` for existing files.

## Append

Adds content at end of file.

```bash
obsidian append file="Journal" content="- New entry"
obsidian append file="Log" content=" (updated)" inline   # same line, no newline
```

## Prepend

Inserts content after frontmatter (not at byte 0).

```bash
obsidian prepend file="Ideas" content="## New section"
obsidian prepend file="Log" content="prefix" inline
```

## Move / rename

```bash
obsidian move file="Old Name" to="Archive/Old Name.md"
obsidian move path="Drafts/Note.md" to="Published/Note.md"
```

## Delete

Moves to system trash by default.

```bash
obsidian delete file="Scratch"
obsidian delete file="Scratch" permanent   # bypass trash
```

## Unique note

Creates a note with a unique ID (Zettelkasten-style, requires Unique Note Creator plugin).

```bash
obsidian unique name="Fleeting thought" content="text"
obsidian unique content="text" silent
obsidian unique name="Note" paneType=split
```

## Open

Opens a file in the Obsidian editor.

```bash
obsidian open file="Note"
obsidian open file="Note" newtab
```

## Random note

```bash
obsidian random                        # open random note
obsidian random folder="Zettelkasten/"
obsidian random:read                   # read content without opening
obsidian random silent                 # return path without opening
```
