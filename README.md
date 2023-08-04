# Kee - a CLI interval timer

Kee is a small CLI timer, made to be integrated with other applications that allow running
terminal commands inside it. For example tmux and vim.

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