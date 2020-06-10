# OS

## Windows

- [WSL](https://en.wikipedia.org/wiki/Windows_Subsystem_for_Linux): linux in Windows

Package Manager

- [winget](https://github.com/microsoft/winget-cli), [doku](https://docs.microsoft.com/en-us/windows/package-manager/)

## Linux

### Kernel

- get current kernel version: `uname -r`
- revert to previous kernel
  - boot from previous kernel: Grub screen: Advanced Options for Ubuntu -> choose
  - remove the bad kernel
    - list all: `dpkg -l | grep linux-image`
    - remove kernel: `sudo apt-get purge linux-image-VERSION-generic`
    - remove header: `sudo apt-get purge linux-headers-VERSION-generic`
    - reboot

### Useful

- list key-bindings: `gsettings list-recursively org.gnome.desktop.wm.keybindings | sort | more`
- `Alt>Esc` : cycle-windows
- `Alt>0` : switch in application
- `google-chrome --app='https://teams.microsoft.com'` start teams in a different window

### Distributions

#### Red Hat based

- rpm package manager

- Red Hat Enterprise Linux (RHELL)
  - for commercial market
  - open source, but not free
- CentOS
  - free, popular server
- Fedora
  - testing ground for RHELL

#### Debian based

- apt package manager

- Debian
  - stable releases
- Ubuntu
  - system to "just work"
  - LTS every 2nd year
- Linux Mint
  - often Cinnamon desktop (~Windows)

### Package Manager

- dpkg
  - Debian Package Manager, low level
  - database: /var/lib/dpkg (in status file are the installed packages)
- apt
  - Advanced Package Tool, higher-lever tool, can fetch from remote & resolve dependencies: tools like apt/apt-get... can interact with it
  - apt is a subset of apt-get & apt-cache, start using apt
  - softwares can be installed with apt
  - update: updates the list of available packages but does not installs/upgrades
  - upgrade: installs available updates
- Homebrew

### Bash Commands

- debug: set -o xtrace
- free disk space: df -h

### Softwares/Tools

- [autojump](https://github.com/wting/autojump): instead of aliases
- Terminator
- KeePassXC
- Shutter

### Errors

Problem

```shell
E: Sub-process /usr/bin/dpkg returned an error code (1)
```

Solution

```shell
sudo rm /var/cache/debconf/-.dat
sudo dpkg --configure -a
```

Problem

- Bluetooth cannot be turned on

Solution

```shell
sudo apt-get install --reinstall bluez  // and reboot system
```
