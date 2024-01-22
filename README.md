#  3-iX-WSL-JG
## _Automation Scripts for TrueNAS Systems & Custom Servers_

These scripts are used for Client Configuration (CC) and Sofware Quality Control (SWQC) to configure and validate system configuration based on iX Redbooks & customer needs

- Automating Redbook Qualified Configuration
- Log And Archive Configuration Results
- Gather system information and Debug for SWQC

## Features

- Multi Script Menu
- WSL Based & Can Be Used With Any Windows System Running ([Windows Subsystem for Linux](https://learn.microsoft.com/en-us/windows/wsl/about))
- Importing Multiple Hosts Using KEY.txt File For Batch Configuration
- Supermicro Update Manager ([SUM](https://www.supermicro.com/en/solutions/management-software/supermicro-update-manager)) Intergration For Batch BIOS Configuration & [OOB/DCMS](https://store.supermicro.com/us_en/software/software-license-key-activation-usage) License Activation
- Added Logic For Error Checking And Accurate Results
 
## Tech

In order to run some scripts, Certain dependancies must be install into the WSL Ubuntu VM:

- [[ipmitool]](https://linux.die.net/man/1/ipmitool) - utility for controlling IPMI-enabled devices 
- [[sshpass]](https://linux.die.net/man/1/sshpass) - noninteractive ssh password provider 
- [[pv]](https://linux.die.net/man/1/pv) - monitor the progress of data through a pipe 
- [[postgresql-client]](https://ubuntu.com/server/docs/databases-postgresql) - PostgreSQL (also known as Postgres) is an object-relational database system that has the features of traditional commercial database systems with enhancements to be found in next-generation database management systems (DBMS).
- [[sqlite3]](https://linux.die.net/man/1/sqlite3) - A command line interface for SQLite version 3
- [[python3]](https://www.python.org/downloads/) - Python is a programming language that lets you work more quickly and integrate your systems more effectively.
- [[pdfgrep]](https://pdfgrep.org/) - a commandline utility to search text in PDF files
- [[lynx]](https://linux.die.net/man/1/lynx) - a general purpose distributed information browser for the World Wide Web 
- [[curl]](https://linux.die.net/man/1/curl) - transfer a URL 
- [[git]](https://linux.die.net/man/1/git) - Git is a fast, scalable, distributed revision control system with an unusually rich command set that provides both high-level operations and full access to internals.
- [[zsh]](https://linux.die.net/man/1/zsh) - the Z shell 