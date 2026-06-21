---
name: update-zim-module
description: Update the zsh-ssh module within the Zim Zsh framework.
---

## Trigger

This skill is triggered when:
1. The zsh-ssh module repository has been updated remotely.
2. The user or system requests manual update/sync of Zim modules.
3. The shell environment needs to apply the latest changes of the zsh-ssh module.

## Entry Point

Refer to `/home/cagedbird/.zim/modules/zsh-ssh/README.md` for human-facing installation/usage instructions.
The update execution commands are listed below.

## Workflow

### 1. Update Zim Module (Option A - Update All Zim Modules)
Run:
```zsh
source ~/.zim/zimfw.zsh update
```

### 2. Update Zim Module (Option B - Update Only zsh-ssh)
Run:
```zsh
git -C ~/.zim/modules/zsh-ssh pull
```

### 3. Apply Changes
Reload the shell to load the updated plugin:
```zsh
exec zsh
```
Or start a new terminal tab/session.

## Verification

- Run `git -C ~/.zim/modules/zsh-ssh status` to confirm it is up-to-date with the remote branch.
- In a fresh Zsh session, type `ssh ` and press <kbd>Tab</kbd> to verify the autocompletion tool loads and runs successfully.

## Guardrails

- ❌ NEVER expect the active shell session to auto-load changes after pulling; always reload the shell via `exec zsh` or open a new terminal window.
- ❌ Do not run `zimfw update` unless `~/.zim/zimfw.zsh` exists.
