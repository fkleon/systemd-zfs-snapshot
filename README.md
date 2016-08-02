# zfs-snapshot

A systemd zfs snapshot service and timer.

Uses zfsnap to create a weekly snapshot of a zpool and/or dataset.  
The default retention time is 2 months.

## Installation

Requires [zfsnap2](https://github.com/zfsnap/zfsnap).

### Linux

    install -m 644 -o root -g root zfs-snapshot-weekly@.service /etc/systemd/system
    install -m 644 -o root -g root zfs-snapshot-weekly@.timer /etc/systemd/system

    systemctl daemon-reload
    systemctl enable --now zfs-snapshot-weekly@tank.timer
