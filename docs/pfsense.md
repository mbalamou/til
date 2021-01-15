# pfSense

## Increase swap

Netgate SG-3100 can run out of memory when updating [Suricata](https://suricata-ids.org/) or [pfBlocker-NG](https://docs.netgate.com/pfsense/en/latest/packages/pfblocker.html) rules. This can cause pfSense to hang until the kernel kills the offending process.

* [Netgate forum](https://forum.netgate.com/topic/133913/can-i-put-more-memory-in-my-sg-3100?_=1609784043701&lang=en-US)

1. Add this line to the file /etc/fstab
```md99 none swap sw,file=/swapfile.bin 0 0```
1. Create a blank file of size 1 GB:
```dd if=/dev/zero of=/swapfile.bin bs=4096 count=262144```
1. Enable swap (or just reboot as a test):
```swapon -a```
1. Verify swap is enabled:
```swapinfo```
