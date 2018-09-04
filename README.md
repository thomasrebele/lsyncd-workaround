# lsyncd-workaround
Example configuration for using lsyncd with a server with limited capabilities, e.g., no TTY

This can be used as a replacement for `scp` or `rsync`, if the remote does not support those commands:

```
$ scp src remote:/target
sh: scp: not found
lost connection
```

```
$ rsync ...
sh: rsync: not found
rsync: connection unexpectedly closed (0 bytes received so far) [sender]
rsync error: error in rsync protocol data stream (code 12) at io.c(235) [sender=3.1.2]
```

## Prerequisits

* Install https://github.com/axkibe/lsyncd on client. (Debian, Ubuntu: `apt install lsyncd`)
* SSH connection to server that can execute commands on the server
* `tar` on client and server

## Usage

1. Set port, remote, source, and target in `no-tty.lsync`
2. Start synchronization: `lsyncd no-tty.lsync`.
   The command will print successfully transmitted files.
3. Modify files in the source folder. They will be copied to the target on the server as long as lsyncd is running


## Possible improvements

* add support for compression
* emulate `tar` with `mkdir` and `cat`
