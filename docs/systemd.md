# systemd

* [Debug unit cycles](https://unix.stackexchange.com/questions/193714/generic-methodology-to-debug-ordering-cycles-in-systemd)

## systemctl commands

[man systemd](https://www.freedesktop.org/software/systemd/man/systemd.html)
[Docs](https://www.digitalocean.com/community/tutorials/how-to-use-systemctl-to-manage-systemd-services-and-units)

```
# Reload unit files
systemctl daemon-reload

# Start service on boot
systemctl enable $service

# Show units
systemctl list-units
systemctl list-units --state=failed
systemctl list-units --type=mount

# List dependencies
systemctl list-dependencies $service

# Show tree of critical path targets
systemd-analyze critical-chain
```

## journalctl commands

```
# Tail logs for a service
journalctl -f -u $sevice

# View last 50 logs
journalctl -n 50

# View logs since last boot
journalctl -b

# View logs from the previous boot until the last reboot
journalctl --boot=-1

# Delete all but 1GB of logs
journalctl --vacuum-size=1G
```

## User units

Add unit files to `~/.config/systemd/user/`. eg

```
[Unit]
Description=Music Player Daemon

[Service]
ExecStart=/usr/bin/mpd --no-daemon

[Install]
WantedBy=default.target
```

The default target is "default.target"

User units cannot depend on system units.

User commands are similar to the system-wide systemctl, except that they do not require sudo, eg.:
```
systemctl --user daemon-reload
```

### Lingering

[man loginctl](https://www.freedesktop.org/software/systemd/man/loginctl.html#enable-linger%20USER...)

> The user@.service is started automatically when the user first logs in, and stays around as long as at least one login session is open. After the user logs out of the last session, user@.service and all services underneath it are terminated. This behavior is the default, when "lingering" is not enabled for that user. Enabling lingering means that user@.service is started automatically during boot, even if the user is not logged in, and that the service is not terminated when the user logs out.

> Enabling lingering allows the user to run processes without being logged in, for example to allow screen to persist after the user logs out, even if the session scope is terminated. In the default configuration, users can enable lingering for themselves:

```
loginctl enable-linger ${USER}
```
