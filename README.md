# Rooting the Korg Kronos (version: April 2021)

This is the updated version of https://kronoshacker.blogspot.com/2015/06/rooting-korg-kronos.html

Sincere appreciation goes to kronoshacker for his work; the current update is based on his version from 2015.
However, all binaries have been recompiled and built from scratch, as no source code was provided for the binaries included in his package.

The update procedure works like any Kronos System Update, but <u>make sure to create a backup before starting!</u> Also, ensure that you are using at least Kronos OS 3.1.0 or newer (older versions were not tested).

**NO WARRANTY - USE IT AT YOUR OWN RISK!**

## Changelog:

### Busybox updated from 1.23.2 to 1.32.1:
* Removed all unnecessary applets.
* Patched to work on the original filesystem and bypass the integrity check at boot.
* Added two new custom applets:
    * `drumtrack` (switch drumtrack ON or OFF)
    * `publicid` (returns your public id - it's easier to copy if you need it somewhere else)
    * Other applets may be added in the future (e.g. activating karma, changing tempo, saving screenshots, and many more...)

### Dropbear updated from 2015.67 to 2020.81
* `scp` should work now!
    * You can now transfer files using `scp` from your Kronos to any other device over the network
    * kronoshacker version of `scp` was not working (error was `/usr/bin/dbclient: No such file or directory`)
* Added `sftp-server`
    * You can upload or download all files from Kronos using SSH/SFTP (port 22) instead of FTP, including files that are not visible via FTP. **Be careful not to overwrite any important or system files!**

### Added working nano Editor
* updated from 2.6.3 to 5.6.1
* kronoshacker version of `nano` editor was not working (`error while loading shared libraries: libmagic.so.1: cannot open shared object file: No such file or directory`)

### Added rsync 2.6.1
* You can use `rsync` to download, upload, or back-up multiple directories from your Kronos to your desired location over the network.
    * Back up all files from your Kronos to a backup-host: <br>`rsync -av -e 'dbclient -y' /korg/rw/HD user@backup-host:/home/user/kronos-backup-202104/`


## Future updates
My e-mail address might change, be blocked, or even be deleted.<br />
For this reason, please download my GPG key from https://pgp.surfnet.nl to verify any future releases or messages.

GPG key id: `0x28C3115145834007`<br />
GPG fingerprint: `BB17 C3DE F75E 7EDB 7481 32D2 28C3 1151 4583 4007`<br />

### Support by donating crypto

BTC: `bc1qvg9de6lmeet6wvxnjx9af0ertgkejkrf4kpe88`

XMR: `89MSD7JY8mzKWRKMtc5w2S95XzE4EUmRM9wyKdDNr8kvKEDtbdyqic4R5Cc4rdMCKoC4mWSRQ2P7f3NtZXGH5z2YNUPube`
