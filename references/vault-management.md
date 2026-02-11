# Vault Management & Advanced

## Vault info

```bash
obsidian vault                         # full info (name, path, files, folders, size)
obsidian vault info=name
obsidian vault info=path
obsidian vault info=size

obsidian vaults                        # list known vaults
obsidian vaults verbose                # include paths
obsidian vaults total
```

In the TUI, `vault:open name="Other Vault"` switches to a different vault.

## Files & folders

```bash
obsidian files ext=md total            # count markdown files
obsidian files folder="Projects/"      # list files in folder
obsidian folders                       # all folders
obsidian folders total
obsidian folders folder="Projects/"   # filter by parent
obsidian folder path="Projects/" info=files
obsidian recents                       # recently opened
obsidian recents total
```

## Bookmarks

```bash
obsidian bookmarks
obsidian bookmarks verbose

obsidian bookmark file="Important Doc"
obsidian bookmark file="Doc" subpath="Heading"   # bookmark heading/block within file
obsidian bookmark folder="Projects/"              # bookmark a folder
obsidian bookmark url="https://example.com" title="Reference"
obsidian bookmark search="project deadline"
```

## Plugins

```bash
obsidian plugins                       # all installed
obsidian plugins filter=community versions
obsidian plugins:enabled
obsidian plugins:enabled filter=community versions

obsidian plugin id=dataview            # plugin info
obsidian plugin:enable id=dataview
obsidian plugin:enable id=daily-notes filter=core
obsidian plugin:disable id=calendar
obsidian plugin:install id=obsidian-git enable
obsidian plugin:uninstall id=obsidian-git
obsidian plugin:reload id=my-plugin    # for developers

obsidian plugins:restrict on           # enable restricted mode
obsidian plugins:restrict off
```

## Workspaces

```bash
obsidian workspaces
obsidian workspaces total
obsidian workspace                     # current layout tree
obsidian workspace ids

obsidian workspace:save name="Research"
obsidian workspace:load name="Research"
obsidian workspace:delete name="Old"
```

## Tabs

```bash
obsidian tabs
obsidian tabs ids

obsidian tab:open
obsidian tab:open file="Note.md"
obsidian tab:open view=graph
obsidian tab:open group=2
```

## Themes & snippets

```bash
obsidian theme                         # active theme
obsidian themes                        # installed
obsidian themes versions
obsidian theme:install name="Minimal" enable
obsidian theme:set name="Minimal"
obsidian theme:uninstall name="Old"

obsidian snippets
obsidian snippets:enabled
obsidian snippet:enable name="custom"
obsidian snippet:disable name="custom"
```

## Sync

Requires Obsidian Sync subscription.

```bash
obsidian sync:status
obsidian sync on                       # resume
obsidian sync off                      # pause

obsidian sync:history file="Doc"
obsidian sync:history file="Doc" total
obsidian sync:read file="Doc" version=3
obsidian sync:restore file="Doc" version=3
obsidian sync:open file="Doc"          # open sync history UI
obsidian sync:deleted
obsidian sync:deleted total
```

## File history & diff

```bash
# Local file recovery
obsidian history:list                  # files with history
obsidian history file="Note"           # list versions
obsidian history:read file="Note" version=2
obsidian history:restore file="Note" version=2
obsidian history:open file="Note"

# Diff (local + sync versions)
obsidian diff file="Note"
obsidian diff file="Note" filter=local
obsidian diff file="Note" filter=sync
obsidian diff file="Note" from=2 to=1
```

## Publish

Requires Obsidian Publish subscription.

```bash
obsidian publish:site                  # site info (slug, URL)
obsidian publish:list
obsidian publish:list total

obsidian publish:status
obsidian publish:status new
obsidian publish:status changed
obsidian publish:status total

obsidian publish:add file="Note"
obsidian publish:add changed           # publish all changes
obsidian publish:remove file="Note"
obsidian publish:open file="Note"      # open on published site
```

## Bases

Requires Bases core plugin.

```bash
obsidian bases
obsidian base:views
obsidian base:query file="Tasks DB"
obsidian base:query file="Tasks DB" view="Active" format=json
obsidian base:query file="Tasks DB" format=csv
obsidian base:query file="Tasks DB" format=paths  # file paths only
obsidian base:create name="Item" content="text" silent
```

## Web viewer

```bash
obsidian web url="https://example.com"
obsidian web url="https://example.com" newtab
```

## Command palette

```bash
obsidian commands                      # list all command IDs
obsidian commands filter="editor"
obsidian command id=app:open-settings  # execute a command
obsidian command id=graph:open

obsidian hotkeys
obsidian hotkeys all verbose
obsidian hotkey id=app:open-settings
```

## Developer tools

```bash
obsidian devtools                      # toggle Electron DevTools
obsidian eval code="app.vault.getFiles().length"
obsidian dev:screenshot path="screenshot.png"

obsidian dev:console
obsidian dev:console level=error limit=20
obsidian dev:console clear
obsidian dev:errors
obsidian dev:errors clear

obsidian dev:dom selector=".workspace-leaf" total
obsidian dev:dom selector="h1" text
obsidian dev:dom selector="h1" inner all
obsidian dev:css selector=".workspace" prop=background-color

obsidian dev:cdp method="Runtime.evaluate" params='{"expression":"1+1"}'
obsidian dev:debug on
obsidian dev:debug off
obsidian dev:mobile on
obsidian dev:mobile off
```

## Misc

```bash
obsidian help
obsidian version
obsidian reload
obsidian restart
```
