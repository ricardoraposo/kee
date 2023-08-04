# Kee - a CLI interval timer

Kee is a small CLI timer, made to be integrated with other applications that allow running
terminal commands inside it. For example TMUX and vim.

## Usage

```sh
kee start   # it starts the timer according to the default time
kee start <duration>
kee start hour
kee set default 10m   # it sets the default timer to 10 minutes
kee stop
kee help
```

Run 'kee help' for more details

It is possible to pass a time unit for `<duration>`.

Valid time units are "s", "m", "h".
If no unit is passed, than nothing is considered, the timer starts with 0.

## Install

```sh
curl -sSO https://raw.githubusercontent.com/ricardoraposo/kee/main/kee
chmod +x kee
sudo mv kee ~/.local/bin # you can move it to wherever you feel it's best for you, as long as it's on your PATH
```

## Tab Completion

To activate tab completion just use the `complete -C` option from your
`.bashrc` or command line.
It also works on zsh if you have Oh My Zsh installed.

```
complete -C kee kee
```

## Integration with TMUX

Here's an example of how to add `kee` to your TMUX configuration.
Add the lines below to your `.tmux.conf` file.

```tmux
set -g status-interval 1
set -g status-right "#(kee)"
```

## Integration with vim/neovim

Here's an example of how to add `kee` to your TMUX configuration.
This didn't look good, I'm sure you can do better than me.

```vim
function! Kee()
  return system("kee")
endfunction
set statusline+=%{Kee()}
```
