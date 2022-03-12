# Ubuntu

* [Gnome](./gnome.md)
* [Systemd](./systemd.md)
* [Xorg](./xorg.md)

## Applications and packages

Application | Description
--- | ---
[aseprite](https://www.aseprite.org/)|Pixel art tool
[blueman](https://wiki.archlinux.org/title/Blueman)|Bluetooth manager
[evince](https://en.wikipedia.org/wiki/Evince)|Document viewer
[gnome-disks](https://gitlab.gnome.org/GNOME/gnome-disk-utility)|Tool to manage storage devices
[heroic](https://github.com/Heroic-Games-Launcher/HeroicGamesLauncher)|"Epic Games Store" launcher
[lutris](https://lutris.net/)|Wine, Steam, etc game launcher
[obs](https://obsproject.com/)|Tool to record video and perform live streaming
[pcmanfm](https://sourceforge.net/projects/pcmanfm/)|File manager
[piper](https://github.com/libratbag/piper)|Configure mouse DPI
[retroarch](https://www.retroarch.com/)|ROM game and emulator launcher
[seahorse](https://wiki.gnome.org/Apps/Seahorse) | Tool to manage the Gnome keyring
[solaar](https://pwr-solaar.github.io/Solaar/)|Manage Logitech unifying receivers and devices
[usb-creator-gtk](https://launchpad.net/ubuntu/+source/usb-creator)|Tool to write ISO files to USB storage devices

### Desktop environment

Application | Description
--- | ---
[BSPWM](https://github.com/baskerville/bspwm)|Tiling window manager for X11 ([ansible-role-bspwm](https://github.com/andornaut/ansible-role-bspwm/))
[River WM](https://github.com/riverwm/river)|Dynamic tiling Wayland compositor 
[Sway WM](https://swaywm.org/)|i3-compatible Wayland compositor 
[Waybar](https://github.com/Alexays/Waybar)|Bar for Wayland

### Monitoring and statistics commands

Command | Description
--- | ---
atop | AT Computing's System & Process Monitor
htop | ncurses-based process viewer for Linux
iostat | CPU and input/output statistics for devices and partitions
lsof | Lists on its standard output file information about files opened by processes
mtr | Combines  the functionality of the traceroute and ping programs in a single network diagnostic tool
nethogs | Net top tool grouping bandwidth per process
netstat | Print network connections, routing tables, interface statistics, masquerade connections, and multicast memberships
pidstat | Monitor individual tasks currently being managed by the Linux kernel
powertop | Power consumption and power management diagnosis tool
sensors | Print temperature sensors information
vmstat | Report virtual memory statistics

### Search for installed applications

```
grep -li ${SEARCH_TEXT} /usr/share/applications/*.desktop
# or
dpkg -l | grep ${SEARCH_TEXT}

# eg.
$ grep -li music /usr/share/applications/*.desktop
/usr/share/applications/spotify.desktop
```

### Search for Ubuntu packages by filename

```
sudo apt-get install apt-file
apt-file update
apt-file search ${pattern}
```

### Default application associations

* [StackOverflow](https://unix.stackexchange.com/a/59088)

Edit `~/.config/mimeapps.list`:
```
[Default Applications]
text/html=firefox.desktop
application/pdf=org.gnome.Evince.desktop
```

Associate PDFs with Evince:
```
xdg-mime default org.gnome.Evince.desktop application/pdf
```

### Post-install cleanup / Uninstall packages

* [Ask Ubuntu](https://askubuntu.com/a/984800)

```
sudo apt purge evolution* language-selector-gnome whoopsie*

# Remove Snap
sudo rm -rf /var/cache/snapd/
sudo apt autoremove --purge snapd gnome-software-plugin-snap
sudo apt-mark hold snapd
rm -rf ~/snap

# Free up disk-space
sudo apt autoremove && sudo apt clean
```

## Upgrade Ubuntu from LTS to non-LTS

```
sudo sed -i 's/^\(Prompt\s*=\s*\)\w\+/\1normal/g' /etc/update-manager/release-upgrades
sudo do-release-upgrade
```

## Disable release upgrade notifications

* [Ask Ubuntu](https://askubuntu.com/questions/843778/how-to-disable-release-upgrade-notification-emails)

```
sudo sed -i 's/^\(Prompt\s*=\s*\)\w\+/\1never/g' /etc/update-manager/release-upgrades
echo -n "" > /var/lib/ubuntu-release-upgrader/release-upgrade-available
```

## Disable language switcher

Use `dconf watch /` to monitor changes.

Using dconf:

[@au [] specifies the type of the empty array](https://developer.gnome.org/glib/stable/gvariant-text.html#gvariant-text-type-annotations) (which would not parse otherwise)

```
# Remove language switcher keyboard shortcut
dconf write /org/gnome/desktop/wm/keybindings/switch-input-source '@au []'

# Disable "Intelligent Input Bus Daemon"
dconf write /org/gnome/settings-daemon/plugins/keyboard/active false

# Restart (replace) ibus-daemon
ibus-daemon -rd
```

Using dconf-editor:
```
apt install dconf-editor
dconf-editor
# Navigate to: /org/gnome/desktop/wm/keybindings/switch-input-source
# Set to []
```

## Magic SysRq Keys

Force reboot an unresponsive system.

```
ALT + SHIFT + PRINT SCR + R E I S U B

unRaw      (take control of keyboard back from X),
 tErminate (send SIGTERM to all processes, allowing them to terminate gracefully),
 kIll      (send SIGKILL to all processes, forcing them to terminate immediately),
  Sync     (flush data to disk),
  Unmount  (remount all filesystems read-only),
reBoot.
```

## Mount a network share in fstab

```
$ echo '
//$HOSTNAME/stuff /media/stuff cifs defaults,guest,ro 0 0' | sudo tee -a /etc/fstab
```

## Preserve $PATH when using sudo

- [StackOverflow](http://unix.stackexchange.com/a/83194)

```
$ sudo env "PATH=$PATH" command
```

## sysctl settings

- [Inotify instructions](https://confluence.jetbrains.com/display/IDEADEV/Inotify+Watches+Limit)

```
$ echo '
fs.file-max = 100000
fs.inotify.max_user_watches = 524288' | sudo tee -a /etc/sysctl.conf

$ sudo sysctl -pf
```

## Temporarily change the date/time using timedatectl

* [Wiki](https://wiki.archlinux.org/index.php/time)

```
timedatectl set-ntp false
timedatectl set-time "2016-06-20 10:00:00"
timedatectl set-time "10:00:00"
timedatectl set-ntp true
```

## Wipe storage device using hdparm

* [Howto](https://wiki.archlinux.org/index.php/SSD_memory_cell_clearing)

```
hdparm -I /dev/sdX (result: Security:not enabled)
hdparm --user-master u --security-set-pass PasSWorD /dev/sdX
hdparm -I /dev/sdX (result: Security:enabled)
hdparm --user-master u --security-erase PasSWorD /dev/sdX
hdparm -I /dev/sdX (result: Security:not enabled)
```

## Xephyr

Grap mouse and keyboard input
```
CTRL + SHIFT + C
```

## debconf

```
sudo debconf-show ${packageName}

# or

sudo debconf-get-selections|grep -i ${packageName}
```

## Debugging and troubleshooting

* [LiveCdRecovery](https://help.ubuntu.com/community/LiveCdRecovery) - Chroot an Ubuntu ISO on a USB drive

### Fix broken grub install

```
mount /dev/sda1 /mnt \
  mount --bind /dev /mnt/dev \
  mount --bind /proc /mnt/proc \
  mount --bind /sys /mnt/sys \
  chroot /mnt

grub-install /dev/sda

umount /mnt/proc/ /mnt/dev /mnt/sys /mnt
```

### apt update 404

* [StackOverflow](https://askubuntu.com/questions/549777/getting-404-not-found-errors-when-doing-sudo-apt-get-update)

This error occurs when running `apt update` on an unsupported version of Ubuntu.

```
sudo sed -i -e 's/\([a-z]*.\?\)\?archive.ubuntu.com\|security.ubuntu.com/old-releases.ubuntu.com/g' /etc/apt/sources.list
```

### gnome-control-center segmentation fault on startup

* [StackOverflow](https://askubuntu.com/a/1356965)

This can be caused by accessing the "Sound" section/tab of Gnome Control Center on an installation provisioned by [ansible-workstation](https://github.com/andornaut/ansible-workstation).

```
rm -rf .config/dconf/
```
