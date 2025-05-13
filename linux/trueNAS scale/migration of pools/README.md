for the purpose of transfer of entire dataset or entire pool first create a snapshot of original pool
be in unrestricted shell default user is restricted you can use root(not safe but still i did) or create new user with necessary permission
be sure it is recursive
delete any snapshots at destination as they will hinder the work or just create new dataset in destination to avoid any issue
```
zfs snapshot -r oldpool/dataset@migration
```
then transfar that to new pool
```
zfs send -R oldpool/dataset@migration | zfs receive -F newpool
```