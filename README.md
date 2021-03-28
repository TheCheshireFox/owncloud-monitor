# owncloud-monitor
Simple service which watches changes in owncloud user directories and calls `files:scan` for each create or deletion of files and directories.


## Usage

### Configuration
Adjust config file in `/etc/owncloud-monitor/monitor.conf`:
```INI
OWNCLOUD_DIR=/var/www/owncloud
OC_USER=www-data
```
Where `OWNCLOUD_DIR` is root directory of owncloud installation (where occ placed) and `OC_USER` user who can run `occ`

### Creating service
`owncloud-monitor` is systemd service, so:

For start use:
```bash
systemctl start owncloud-monitor@owncloud_user
```

For autostart:
```bash
systemctl enable owncloud-monitor@owncloud_user
```

## TODO
 - Installation packages
 - Add option to start service to listen all users
 - Windows support (?)
