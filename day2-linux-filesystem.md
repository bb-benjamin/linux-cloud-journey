# Day 2 — Linux File System Structure

## Key Directories Learned

| Directory | Purpose | Cloud Engineering Use |
|-----------|---------|----------------------|
| /etc | Configuration files | Configure nginx, SSH, services |
| /var | Variable data and logs | Check /var/log when troubleshooting |
| /home | User home directories | Where you land after SSH |
| /tmp | Temporary files | Cleared on reboot — never store important files |
| /bin | Essential commands | ls, cd, mkdir all live here |
| /proc | Process information (virtual) | Monitor running processes |
| /dev | Device files | /dev/null for silencing output |
| /mnt | Mount points | Mounting EBS volumes on AWS EC2 |
| /opt | Optional software | Third party application installs |
| /root | Root user home | Administrator home directory |

## Key Insight Today

Everything in Linux is organised under 
one root directory /.
No random folders. Every directory 
has a specific purpose.

## How This Connects To AWS

- /var/log → troubleshooting EC2 servers
- /etc → configuring services on servers  
- /mnt → mounting EBS storage volumes
- /tmp → temporary space during installations

## Commands To Practice Tomorrow

```bash
ls /          # List root directory
ls /etc       # See configuration files
ls /var/log   # See system logs
cd /home      # Go to home directory
pwd           # Show current location
```
