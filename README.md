# pzsh
pzsh is a lightweight Zsh plugin that lets you launch a private Zsh shell session with **no history saved, no logging, and no trace**. It also prevents the `pzsh` command itself from being saved in your main shell history.

## Features

- Launch a **private shell session** using the `pzsh` command
- Disables in-memory and file-based command history
- Prevents `pzsh` itself from being saved in `.zsh_history`
- Simple, clean, and fast no external dependencies

## Installation
```shell
git clone https://github.com/iniridwanul/pzsh ~/.oh-my-zsh/custom/plugins
```
Then add the plugin name to your `~/.zshrc` plugins list:
```shell
plugins=(pzsh)
```
## Usage
To launch a private shell session, run:
```shell
pzsh
```
Inside this session:
- No commands will be saved to history
- `~/.zsh_history` remains untouched
- Your original shell remains unchanged

To return to your normal shell, just run:
```shell
exit
```

## How It Works
- Defines a `pzsh` function that sets temporary history environment variables and options
- Hooks into `zshaddhistory` to filter out the pzsh command from global history
- Uses a minimal and clean implementation compatible with most setups

## Contribution
Feel free to fork, contribute, or suggest improvements via issues or pull requests!