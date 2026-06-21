# zsh-ssh Agent 指南

## 项目定位
更好的 SSH 主机 Zsh 补全模块，集成 fzf 提供交互式选择与预览。

## 路由入口
- 运行时的 Agent 任务与相关 Skills 已在 [README.md](README.md#agent-native-skills) 中定义。
- 模块更新说明见 [README.md](README.md#更新)。

## 关键路径
- `zsh-ssh.zsh`: 核心实现，利用 fzf 提取并选择 ssh 配置。
- `zsh-ssh.plugin.zsh`: Zsh 插件加载入口。

## 禁止事项
- ❌ 禁止在未确认 fzf 是否安装的情况下加载插件。
- ❌ 禁止在没有手动运行更新命令或重启终端的情况下预期更改自动生效。

## 最小验证入口
- 在 Zsh 中输入 `ssh ` 并按 <kbd>Tab</kbd>，确认弹出的 fzf 窗口正常工作。
