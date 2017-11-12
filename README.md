# RAID1 Tests
Some experimentation with Vagrant, VirtualBox and RAID1

## Initialisation
### ext3 + mdadm
```
./test-raid1 init mdadm-ext3 --with-exiting-files
./test-raid1 init mdadm-ext3 --without-exiting-files
```

### btrfs
```
./test-raid1 init btrfs --with-exiting-files
./test-raid1 init btrfs --without-exiting-files
```
