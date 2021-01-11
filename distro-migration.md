# Distro Migration 2021

Migrating to Debian 10 Buster for the final, last, very last, never to ever
switch again, time.

## Fedora Prep

- [ ] Rsync entire disk to sega0.

```
mkdir /mnt/sega0/$(date +%F)-Beta/
sudo rsync -aAX --progress / --exclude={"/dev/*","/proc/*","/sys/*","/tmp/*","/run/*","/mnt/*","/media/*","/lost+found"} /mnt/sega0/$(date +%F)-Beta
```

| Option | Flag         | Description                                   |
| :----- | :----------- | :-------------------------------------------- |
| `-a`   | `--archive`  | recursive preserve almost everything.         |
| `-A`   | `--acls`     | Update the destination ACLs, implies --perms. |
| `-X`   | `--xattrs`   | Update the destination extended attributes.   |
| `N/A`  | `--progress` | Show progress bar.                            |

- [ ] Clone entire SSD to sega0 with CloneZilla.

  - Boot, mount, clone! :smile:

## Debian Installation

- [ ] Install Debian 10 Buster from bootable USB.
- [ ] Setup multiple NICS.

## Post Installation Setup

- [ ] Install `.dotfiles` and setup shell environment.
- [ ] Setup fstab for disks.

```fstab
# Sega0
UUID=5c57b510-1884-4a9d-b4e7-594b0fa58573 /mnt/sega0 btrfs defaults,user,exec 0 0

# Sega1
UUID=36a58553-9c0d-442a-ad3f-e35e7a3dcee0 /mnt/sega1 btrfs defaults,user,exec 0 0
```

- [ ] Setup samba shares.

```smb
[sega0]
    comment = Sega0
    valid users = joshua
    path = /mnt/sega0
    browseable = Yes
    read only = No
    inherit acls = Yes

[sega1]
    comment = Sega1
    valid users = joshua
    path = /mnt/sega1
    browseable = Yes
    read only = No
    inherit acls = Yes
```

- [ ] Spend a copeious amount of time to try and get nginx, letsencrypt, and
      certbot all working within a single docker container.
- [ ] Give up and switch back to nginx native.
- [ ] Copy old Docker data files.
- [ ] Install FirewallD.
- [ ] Learn CLI of FirewallD.
- [ ] Install all FirewallD configurations.
- [ ] Install cockpit
- [ ] Raise all docker containers
- [ ] Install all systemd services.

- [ ] Check remote backups
- [ ] Check timers

## Post-post Installation Setup

- [ ] Revamp personal website with devportfolio.
