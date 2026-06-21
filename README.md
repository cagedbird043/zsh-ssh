# zsh-ssh

Better host completion for ssh in Zsh.

[![asciicast](https://asciinema.org/a/381405.svg)](https://asciinema.org/a/381405)

Works on Linux and macOS.

- [zsh-ssh](#zsh-ssh)
    - [Installation](#installation)
        - [macOS Notes](#macos-notes)
        - [Zinit](#zinit)
        - [Antigen](#antigen)
        - [Oh My Zsh](#oh-my-zsh)
        - [Sheldon](#sheldon)
        - [Manual (Git Clone)](#manual-git-clone)
    - [Usage](#usage)
        - [SSH Config Example](#ssh-config-example)

## Installation

Make sure you have [fzf](https://github.com/junegunn/fzf) installed.

### macOS Notes

- Install `fzf` first:

  ```shell
  brew install fzf
  $(brew --prefix)/opt/fzf/install
  ```

- No extra `realpath` or `coreutils` dependency is required.

### Zinit

```shell
zinit light cagedbird043/zsh-ssh
```

### Antigen

```shell
antigen bundle cagedbird043/zsh-ssh
```

### Oh My Zsh

1. Clone this repository into `$ZSH_CUSTOM/plugins` (by default `~/.oh-my-zsh/custom/plugins`)

    ```shell
    git clone https://github.com/cagedbird043/zsh-ssh ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-ssh
    ```

2. Add the plugin to the list of plugins for Oh My Zsh to load (inside `~/.zshrc`):

    ```shell
    plugins=(zsh-ssh $plugins)
    ```

3. Start a new terminal session.

### Sheldon

1. Add this config to `~/.config/sheldon/plugins.toml`

    ```toml
    [plugins.zsh-ssh]
    github = 'cagedbird043/zsh-ssh'
    ```

2. Run `sheldon lock` to install the plugin.

3. Start a new terminal session.

### Manual (Git Clone)

1. Clone this repository somewhere on your machine. For example: `~/.zsh/zsh-ssh`.

    ```shell
    git clone https://github.com/cagedbird043/zsh-ssh ~/.zsh/zsh-ssh
    ```

2. Add the following to your `.zshrc`:

    ```shell
    source ~/.zsh/zsh-ssh/zsh-ssh.zsh
    ```

3. Start a new terminal session.

## Usage

Just press <kbd>Tab</kbd> after `ssh` command as usual.

The host list stays compact by showing `Alias / Hostname / User` in the main
fzf panel. If you add `#_Desc` to an SSH config entry, the full description is
shown in the preview pane, so long notes remain readable even in a narrow
terminal.

You can add multiple `#_Desc` lines to the same host block. They will be joined
as multiple lines in the preview pane.

If you want to tune the popup size, set these variables before the plugin is
loaded:

```shell
export fzf_ssh_height='60%'
export fzf_ssh_preview_window='down:70%:wrap'
```

### SSH Config Example

You can use one or more `#_Desc` lines to set description.

~/.ssh/config

```text
Host Bastion-Host
    Hostname 1.1.1.1
    User sunlei

Host Development-Host
    Hostname 2.2.2.2
    IdentityFile ~/.ssh/development-host
    #_Desc For Development
    #_Desc Private network only
```

## 更新

Zim 模块不会自动更新。对该模块进行修改并推送到远程仓库后，使用者需要手动在终端中更新：

```zsh
source ~/.zim/zimfw.zsh update   # 更新所有 Zim 模块
# 或
git -C ~/.zim/modules/zsh-ssh pull  # 只更新 zsh-ssh 模块
```

更新后，需要新开终端标签页或运行 `exec zsh` 以便使新代码生效。当前 shell 进程不会自动重新加载该模块的更改。

## Agent-native Skills

### Start here

- **Zim 模块更新** → 先读 `README.md` 中的 [Skills](#skills) 部分 → 需要执行 SOP 时再读 `.agents/skills/update-zim-module/SKILL.md` → 需要背景证据时再读 `README.md` 中的 [更新](#更新) 部分。

### Skills

- [update-zim-module](.agents/skills/update-zim-module/SKILL.md): Triggered when updating the zsh-ssh module within the Zim Zsh framework.

### Do not read everything

Agents MUST start by reading the repository `README.md` first and follow the links to specific skills. Avoid scanning the entire repository.
