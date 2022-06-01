# Download blockchain snapshots template
## Overview
Snapshots significantly reduce the cost and time-to-value when spinning up new nodes. The snapshots are created by a trusted node and hosted via StorjDCS.
This guide shows how to download snapshots from StorjDCS using their Uplink CLI tool. Two options are provided to cater to multiple use-cases. The first being limited node disk space and the second for faster downloads maximizing network throughput. 
## Download Snapshot
### Install Uplink
Linux AMD64
```
curl -L https://github.com/storj/storj/releases/latest/download/uplink_linux_amd64.zip -o uplink_linux_amd64.zip
unzip -o uplink_linux_amd64.zip
sudo install uplink /usr/local/bin/uplink
```
For different uplink binaries see [Download Uplink CLI](https://docs.storj.io/dcs/downloads/download-uplink-cli/)
### Pick *one* of two methods
#### 1) Download and extract (No extra storage)
(Fast) Extract snapshot to your target directory as it is downloaded from the network. The node disk can be allocated to the size of the snapshot. 
Note: Do not increase parallelism past 2 when using pipe. To increase parallelism see other download method
```
uplink --access <your_access_grant> cp --parallelism 2 sj://blockchains/snapshot.tar - | tar -xz -C ~/.blockchain/data
```
 
#### 2) Download then extract (Requires 2x disk storage)
(Faster) Download with higher parallelism for maximum throughput. You need to have at least double storage space to allow for the snapshot download and then extract it to another directory. Scale parallelism to at most 2x your thread count (16 threads = 32 parallelism). 
```
uplink --access <youraccessgrant> cp --parallelism 32 sj://blockchains/snapshot.tar snapshot.tar
tar -xzc snapshot.tar -C ~/.blockchain/data
```
