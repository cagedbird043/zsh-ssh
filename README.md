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

### SSH Config Example

You can use `#_Desc` to set description.

~/.ssh/config

```text
Host Bastion-Host
    Hostname 1.1.1.1
    User sunlei

Host Development-Host
    Hostname 2.2.2.2
    IdentityFile ~/.ssh/development-host
    #_Desc For Development
```
