# Pools
- Pools are made up of vdevs
- Vdevs can be raid setups or mirror
- Vdevs are made up raid arrays, files or
- Pools will stripe(raid0) across all vdevs

## Create
Create's a pool with 2 devices raid0
'''
zpool create <poolname> <dev1> <dev2>
'''

Creates a pool stripping across 2 vdevs which are a mirror
'''
zpool create <poolname> mirror c1d0 c2d0 mirror c3d0 c4d0
'''

```
zpool create tank raidz c1t0d0 c2t0d0 c3t0d0 c4t0d0 /dev/dsk/c5t0d0
```

## Delete
'''
zpool destroy <poolname>
'''

'''
zpool destroy -f <poolname>
'''


## Add vdevs to pool
zpool add zeepool mirror c2t1d0 c2t2d0
zpool add rzpool raidz c2t2d0 c2t3d0 c2t4d0

## Check Status

'''
zpool status <poolname>
'''