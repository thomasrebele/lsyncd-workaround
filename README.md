# lsyncd-workaround
Example configuration for using lsyncd with a server with limited capabilities, e.g., no TTY

## Prerequisits

* Install https://github.com/axkibe/lsyncd on client. (Debian, Ubuntu: `apt install lsyncd`)
* SSH connection to server that can execute commands on the server
* `tar` on client and server

## Usage

1. Set port, remote, source, and target in `no-tty.lsync`
2. Start synchronization: `lsync no-tty.lsync`
3. Modify files in the source folder. They will be copied to the target on the server as long as lsyncd is running
