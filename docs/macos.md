# macOS

## Keyboard Shortcuts

[All shortcuts](https://support.apple.com/en-ca/HT201236)

Meta keys:

- Command ⌘
- Shift ⇧
- Option (Alt) ⌥
- Control (Ctrl) ⌃
- Caps Lock ⇪
- Fn

| Key combination | Description |
| --- | --- |
| Control Command Space | Open [Emoji Viewer](https://support.apple.com/en-ca/guide/mac-help/mchlp1560/mac) |
| Command Shift . | [Show hidden files](https://osxdaily.com/2009/02/25/show-hidden-files-in-os-x/) |
| Command n | New window |
| Control Command q | Lock screen |
| / | [Go to a directory](https://support.apple.com/en-ca/guide/mac-help/mchlp1236/mac) when focussed on a Finder window |

## Initial setup

```
brew install \
    bash \
    coreutils \
    jq \
    mosh \
    nmap \
    rxvt-unicode \
    svn \
    watch \
    wget \
    xclip

# Fonts
brew tap homebrew/cask-fonts
brew install --cask font-source-code-pro \
  font-droid-sans-mono-nerd-font \
  font-inconsolata \
  font-source-code-pro \
  font-source-sans-pro \
  font-ubuntu
```

[Enable font smoothing](https://pezcoder.medium.com/how-i-migrated-from-iterm-to-alacritty-c50a04705f95#fa82):
```
defaults write -g CGFontRenderingFontSmoothingDisabled -bool NO
defaults -currentHost write -globalDomain AppleFontSmoothing -int 2
```

## Common commands

```
brew upgrade
port -d selfupdate
```

## Customizations

* [ChangeMenuBarColor](https://github.com/igorkulman/ChangeMenuBarColor)
* [HazeOver](https://hazeover.com/) - Dim inactive windows

### Reduce menu (top bar) transparency

1. Navigate to: Accessibility > Display > Display (tab)
1. Enable: Reduce transparency

### Dock

* [uBar](https://brawersoftware.com/products/ubar) - Dock alternative
* [How to hide the dock](https://apple.stackexchange.com/a/298826)

```
# Hide Dock
defaults write com.apple.dock autohide -bool true && killall Dock
defaults write com.apple.dock autohide-delay -float 1000 && killall Dock
defaults write com.apple.dock no-bouncing -bool TRUE && killall Dock

# Restore Dock
defaults write com.apple.dock autohide -bool false && killall Dock
defaults delete com.apple.dock autohide-delay && killall Dock
defaults write com.apple.dock no-bouncing -bool FALSE && killall Dock
```

### Disable command+h (hide window)

* [StackOverflow](https://superuser.com/a/1354665)

1. Install [Karabiner-elements](https://karabiner-elements.pqrs.org/)
1. Import and enable the [Prevent unintended command-h](https://ke-complex-modifications.pqrs.org/?q=Prevent%20unintended%20command-h) "complex modification rule"

## KVM

1. System Preferences -> Energy Saver -> Power Adapter
1. Enable: "Enable Power Nap while plugged into a power adapter"

### Fix flakiness

* Use [display_switch](https://github.com/haimgel/display-switch) to workaround flaky KVM switching.

```
$ cat ~/Library/Preferences/display-switch.ini
# Logs are in:
# $ tail -F ~/Library/Logs/display-switch/display-switch.log
# USB Devices:
# * 14b0:011e StarTech.com Ltd. USB 3.0 4 Port HUB
# * 1532:0e03 1532 Razer Kiyo
# The Genesys is the KVM. It is not added/removed when switching ports, so we must use another device such as the StarTech hub.
usb_device = "1532:0e03"
on_usb_connect = "DisplayPort1"
#on_usb_disconnect = "DisplayPort1"

$ launchctl load ~/Library/LaunchAgents/dev.haim.display-switch.daemon.plist

# Unload with:
# $ launchctl load ~/Library/LaunchAgents/dev.haim.display-switch.daemon.plist
```

* [Linux support](https://github.com/haimgel/display-switch/pull/22)

```
sudo apt install libudev-dev i2c-tools
sudo usermod ${USER} -aG i2c

# Save config to:
# ~/.config/display-switch/display-switch.ini
```

## Troubleshooting

### Increase maxfiles

* [Blog](https://docs.riak.com/riak/kv/latest/using/performance/open-files-limit/index.html#mac-os-x-el-capitan)
* [Facebook Watchman](https://facebook.github.io/watchman/docs/install.html#installing-on-os-x-via-homebrew)
* [StackOverflow](https://apple.stackexchange.com/a/366319)

```
$ echo 'ulimit -n 65536 104857' >> ~/.bashrc

$ cat <<-END >> /etc/sysctl.conf
kern.maxfiles=10485760
kern.maxfilesperproc=104857
END
```

### Fix OpenSSL errors

* [Bundler SSL Guide](https://bundler.io/guides/rubygems_tls_ssl_troubleshooting_guide.html#troubleshooting-certificate-errors)

```
curl -Lks 'https://git.io/rg-ssl' | ruby
brew info openssl
sudo cp /usr/local/etc/openssl\@1.1/cert.pem  /opt/local/etc/openssl/cert.pem
```

## Reinstall xcode

```
# Get Xcode version
xcode-select  --version

# Re-install Xcode CLI tools
sudo rm -rf /Library/Developer/CommandLineTools
sudo xcode-select --install
```
