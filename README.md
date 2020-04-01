# ts3-server-update

## Description

This tool automates the updating process of a Teamspeak3 Server installation.

## Dependencies

* python3 (3.5.3+)
* python3-requests

## Configuration

The updating process follows the informations set in ts3-update.conf. This file should be located in /etc.

Example:
```
[system]
os = linux
arch = x86_64
rootu = root
logdir = /var/log/

[init]
start = systemctl start ts3
stop = systemctl stop ts3

[teamspeak]
dl_dir = /tmp/
ts_dir = /home/ts3user/teamspeak3-server_linux_amd64
backup_dir = /home/ts3user/
user = ts3user
```

## Logging

ts3-update logs output depending on log level (default: WARNING). In order to log the complete update process, level=INFO should be used.

## Usage

Updating the Server with verbose output to the command line:
```
ts3-update -v
```

You can also change the log level to enable even more verbose output:
```
ts3-update -v -l INFO
```

If you only want to know whether a new version is available, you can do a dry run:
```
ts3-update -dv -l INFO
```
