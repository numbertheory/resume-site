---
title: "Starship"
date: 2023-12-28T14:06:34-08:00
draft: false
---

[Starship.rs](https://starship.rs/) is an excellent prompt formatter, for practically any shell. This is my simple configuration. It changes depending on the current working directory. For Python projects, it will show the currently activated version, for node it shows the version of NodeJS in use.

The best feature is that it shows the branch, commit, tag, and lets you know at a glance if your branch is clean or not.

```
format = '''
[┌─:$python$nodejs](bold green)
[│](bold green)$directory$git_branch$git_commit$git_status
[└─>](bold green) '''

[directory]
format = '[$path]($style)[$read_only]($read_only_style) '
truncate_to_repo = false

[git_commit]
format = '[\($hash\)](yellow)[$tag](blue bold) '
tag_disabled = false
only_detached = false
tag_symbol = ' 󱩺 '

[git_branch]
format = 'on [$symbol$branch(:$remote_branch)]($style) '

[git_status]
format = '([\[$all_status$ahead_behind\]]($style) )'

[python]
format = ' [$symbol${pyenv_prefix}(${version}) (\($virtualenv\) )](yellow)'
symbol = '󰌠 '

[nodejs]
format = ' [$symbol$version](yellow) '

```

The symbols for Python, NodeJS, and git tags won't render in a normal browser, but if you're using Starship, you should also install a [NerdFont](https://www.nerdfonts.com/font-downloads) to get the additional symbols.

## Screenshot

![Screenshot of Starship in action.](/images/node_git_python_status.png)