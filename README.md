# ZFS

- You cannot extend a raidz or raidz2 vdev
- You can only add more vdevs to the pool
- More vdevs = more write iops?

## Install
Make sure these binaries exist
- `/usr/bin/zpool`
	- Manages pools
- `/usr/bin/zfs`
	- Datasets


## Status
```
zfs list
```

## Types of vdevs
| Vdev command | Meaning |
| :-: | :- |
|  | Stripped (raid0) |
| san | Linear span (jbod) |
| mirror | Mirrored (raid0) |
| raidz | Single parity (raid5) |
| raidz2 | Double parity (raid6) |
| raidz3 | Triple parity (raid7) |

## Cron
### Weekly
- Scrub pool

### Monthly
- Check pool vdev states

## Deduplication
- Only good for storing stuff that gets versionned alot
	- Large amount of similar VMs
	- Entire computer backups for people in the company
- Do not use if lots of unique data
	 - The deduplication table will be massive

## Datasets
- Similar to independant partitions and filesystems
- Overhead when copying files over from one dataset to another
- Set compressions, deduplication and other things here

## Snapshots

## Simulation mode
- Vdevs are block devices
	- Physical
	- Vdevs