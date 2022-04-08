# Gnome

* [Systemd](./systemd.md)
* [Ubuntu](./ubuntu.md)
* [Xorg](./xorg.md)

## gnome-screensaver settings

* [StackOverflow](http://superuser.com/questions/727120/make-gnome-screen-lock-after-1-hour-not-15-minutes)

```
$ gnome-screensaver-command
$ gsettings get org.gnome.desktop.session idle-delay
$ gsettings get org.gnome.desktop.screensaver lock-delay
$ gsettings set org.gnome.desktop.session idle-delay 3600
$ gsettings set org.gnome.desktop.screensaver lock-delay 4000
```

### Screensaver lockscreen background

* [AskUbuntu](https://askubuntu.com/a/1149151)

```
$ sudo cp ibm-darker-wider.png /usr/share/backgrounds/
$ gsettings get org.gnome.desktop.background picture-uri \
  'file:///usr/share/backgrounds/ibm-darker-wider.png'
$ gsettings get org.gnome.desktop.screensaver picture-uri \
  'file:///usr/share/backgrounds/ibm-darker-wider.png'

$ grep -B1 ibm-darker-wider /usr/share/glib-2.0/schemas/10_ubuntu-settings.gschema.override
[org.gnome.desktop.background]
picture-uri = 'file:///usr/share/backgrounds/ibm-darker-wider.png'
--
[org.gnome.desktop.screensaver]
picture-uri = 'file:///usr/share/backgrounds/ibm-darker-wider.png'

$ sudo glib-compile-schemas /usr/share/glib-2.0/schemas/
$ killall gnome-screensaver
$ gnome-screensaver &
```

## GTK

* [Arch Wiki](https://wiki.archlinux.org/title/GTK)

Change GTK settings using `gnome-tweaks`

Set the GTK2 theme using `gtk-theme-switch2`

```
$ sudo apt-get install -qy adwaita-icon-theme-full gnome-themes-standard
```

Configure GTK2:
```
#~/.gtkrc-2.0
gtk-icon-theme-name = "Adwaita"
gtk-theme-name = "Adwaita"
gtk-font-name = "DejaVu Sans 11"
```
Configure GTK3:
```
# $XDG_CONFIG_HOME/gtk-3.0/settings.ini
[settings]
gtk-icon-theme-name = Adwaita
gtk-theme-name = Adwaita
gtk-font-name = DejaVu Sans 11
```

## OSD

- [notifyosdconfig](https://github.com/amandeepg/notifyosdconfig)
- [notify-osd ppa](https://launchpad.net/~leolik/+archive/ubuntu/leolik)
- [Howto](http://www.webupd8.org/2016/05/customize-notifyosd-notification.html)

## Printing

* [CUPS - localhost:631](http://localhost:631)

```
# Gnome printer settings GUI
system-config-printer
```
