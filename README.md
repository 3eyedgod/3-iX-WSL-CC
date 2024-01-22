# 3-iX-WSL-CC

[![IXSYSTEMS INC.](https://raw.githubusercontent.com/3eyedgod/3-iX-WSL-CC/main/IMAGES/iX_Logo.png)](https://www.ixsystems.com/)

## _Automation Scripts for TrueNAS Systems & Custom Servers_

These scripts are used for Client Configuration (CC) and Sofware Quality Control (SWQC) to configure and validate system configuration based on iX Redbooks & customer needs

- Automating Redbook Qualified Configuration
- Increase The Number Of Systems That Can Go Through CC
- Log And Archive Configuration Results
- Gather System Information & Debug Files To Automate The SWQC Process

## Features

- Multi Script Menu
- WSL Based & Can Be Used With Any Windows System Running ([Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/about))
- Importing Multiple Hosts Using _KEY.txt_ File For Batch Configuration
- Supermicro Update Manager ([SUM](https://www.supermicro.com/en/solutions/management-software/supermicro-update-manager)) Intergration For Batch BIOS Configuration & [OOB/DCMS](https://store.supermicro.com/us_en/software/software-license-key-activation-usage) License Activation
- Added Logic For Error Checking And Accurate Results

## Dependencies

In order to run some scripts, Certain dependancies must be installed on the WSL Ubuntu VM:

- [[ipmitool]](https://linux.die.net/man/1/ipmitool) - Utility for controlling IPMI-enabled devices
- [[sshpass]](https://linux.die.net/man/1/sshpass) - Noninteractive ssh password provider
- [[pv]](https://linux.die.net/man/1/pv) - Monitor the progress of data through a pipe
- [[postgresql-client]](https://ubuntu.com/server/docs/databases-postgresql) - PostgreSQL (also known as Postgres) is an object-relational database system that has the features of traditional commercial database systems with enhancements to be found in next-generation database management systems (DBMS)
- [[sqlite3]](https://linux.die.net/man/1/sqlite3) - A command line interface for SQLite version 3
- [[python3]](https://www.python.org/downloads/) - Python is a programming language that lets you work more quickly and integrate your systems more effectively
- [[pdfgrep]](https://pdfgrep.org/) - A commandline utility to search text in PDF files
- [[lynx]](https://linux.die.net/man/1/lynx) - A general purpose distributed information browser for the World Wide Web
- [[curl]](https://linux.die.net/man/1/curl) - Transfer a URL
- [[git]](https://linux.die.net/man/1/git) - Git is a fast, scalable, distributed revision control system with an unusually rich command set that provides both high-level operations and full access to internals
- [[zsh]](https://linux.die.net/man/1/zsh) - The Z shell

## Installation

[WSL](https://learn.microsoft.com/en-us/windows/wsl/install) must be installed in on any Windows PC

Open up a PowerShell command prompt (Run as Administrator) & type the following:
```powershell
wsl --install
```

Once your Ubuntu user is setup update the repositories by typing the following:
```bash
sudo apt-get update && sudo apt-get full-upgrade -y
```

Install required dependancies with:
```bash
sudo apt install ipmitool sshpass pv postgresql-client sqlite3 python3 dialog pdfgrep lynx curl git zsh -y
```

Run the following command to install [oh-my-zsh](https://ohmyz.sh/)
```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)" -y
```

Copy theme over to [oh-my-zsh](https://ohmyz.sh/)
```bash
cp ~/3-iX-WSL-CC/SETUP/3eyedgod.zsh-theme ~/.oh-my-zsh/themes/
```

Changing theme on .zshrc file
```bash
sed -i 's/ZSH_THEME="robbyrussell"/ZSH_THEME="3eyedgod"/g' ~/.zshrc
```

Add the following aliases to .zshrc file
```zsh
alias ixcc="cd ~/3-iX-WSL-JG;./3-iX-CC.sh"
alias 1up="sudo hwclock -s && sudo apt-get update && sudo apt-get full-upgrade -y && sudo apt-get autoremove -y"
alias sums="cd ~/3-iX-WSL-JG/SUMS/"
alias oob="./sum -l OOB-LIC.txt -c ActivateProductKey"
alias dcms="./sum -l DCMS-LIC.txt -c ActivateProductKey"
```
