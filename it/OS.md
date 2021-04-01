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

### Commands

```bash
# free disk space
df -h 

# find out which ports are used
sudo netstat -tulpn | grep LISTEN 

# list key-bindings
gsettings list-recursively org.gnome.desktop.wm.keybindings | sort | more 

# start teams in a different window
google-chrome --app='https://teams.microsoft.com' 

# prints all command before executing them
set -x 
# debug
set -o xtrace 

ssh-keygen

# find out shell
echo $0
```

### Useful

- `Alt>Esc` : cycle-windows
- `Alt>0` : switch in application
- create desktop icon
  - in `~/.local/share/applications/` eclipse.desktop

``` conf
[Desktop Entry]
Name=Eclipse
Exec=/full/path/to/the/executable
Terminal=false
Type=Application
Icon=/full/path/to/the/icon-file
```

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
  - often Cinnamon desktop (~ Windows)

### Package Manager

#### Debian Package (dpkg)

- low level
- database
  - /var/lib/dpkg (in status file are the installed packages)

```bash
# to install
dpkg -i filename.deb

# to list installed packages
dpkg -l [optional pattern]

# to remove
dpkg -r packagename
```

#### Advanced Package Tool (apt)

- higher-lever 
- software-user interface for software installation & removal
- collection of tools
  - apt
  - apt-get
  - apt-cache
- ~ front-end to dpkg

```bash
# to install
sudo apt install XY

# to updates available packages (does not do install/upgrade)
sudo apt update

# to actually upgrade
sudo apt upgrade

```

#### Snap

- packaging, deployment and distribution
- packages: snaps
- tool: snapd
- installation target: `/snap/bin`

#### Homebrew

- ~ apt, but 3rd party, not native
- originally for macOS
  
### Security

- Device encription
  - [dm-crypt](https://wiki.archlinux.org/index.php/Dm-crypt/Device_encryption)

### Errors

#### Sub-process dpkg error

```bash
E: Sub-process /usr/bin/dpkg returned an error code (1)

sudo rm /var/cache/debconf/*.dat
sudo dpkg --configure -a
```

#### Bluetooth cannot be turned on

```bash
sudo apt-get install --reinstall bluez  # and reboot system
```
