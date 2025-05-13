for the pourpse of transfar of entier dataset or entire pool first create a snapshot of original pool
```
zfs snapshot -r oldpool/dataset@migration
```
then transfar that to new pool
```
zfs send -R oldpool/dataset@migration | zfs receive -F newpool
```