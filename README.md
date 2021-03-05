# whiterabbit--monitor-script
Python script to monitor ec2 resources like CPU, Memory, Disk usage etc
#### Installing Script Dependencies

```sh
$ sudo yum install python3
$ sudo yum install python3-devel -y
$ sudo yum install gcc -y
$ sudo pip3 install psutil
```
#### Script

```sh
$ vim monitor.py

import subprocess
import psutil

print('System CPU Count')
print('----------------')
print('Total Number Of Cpu : {}'.format(psutil.cpu_count()))
print()

print('Load Average')
print('------------')

load = []
for item in psutil.getloadavg():
  load.append(item)

print('Load Average : {}'.format(load))
print()


print('System Disk Usage Info')
print('----------------------')
subprocess.call('df -h',shell=True)
print()

print('System Memory Usage Info')
print('------------------------')
subprocess.call('free -m',shell=True)
print()

print('System Memory Usage Info')
print('------------------------')
subprocess.call('free -m',shell=True)
print()

```

#### output

```sh
System CPU Count
----------------
Total Number Of Cpu : 1

Load Average
------------
Load Average : [2.16, 2.13, 1.84]

System Disk Usage Info
----------------------
Filesystem      Size  Used Avail Use% Mounted on
devtmpfs        482M     0  482M   0% /dev
tmpfs           492M     0  492M   0% /dev/shm
tmpfs           492M  700K  491M   1% /run
tmpfs           492M     0  492M   0% /sys/fs/cgroup
/dev/xvda1      8.0G  3.1G  5.0G  39% /
tmpfs            99M     0   99M   0% /run/user/0
tmpfs            99M     0   99M   0% /run/user/1000

System Memory Usage Info
------------------------
              total        used        free      shared  buff/cache   available
Mem:            983         659         133          25         190         157
Swap:             0           0           0

System Memory Usage Info
------------------------
              total        used        free      shared  buff/cache   available
Mem:            983         659         133          25         190         157
Swap:             0           0           0

```
