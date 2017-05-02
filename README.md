# Ubuntu_ARM_filesystem
Ubuntu 14.0.4 root file system, with Linux 3.x kernel headers and modules installed, for Zync7030 chip on Enclustra Mercury ZX1 SoC module


Username:root
Password:xilinx
SSH using : root@<ip_address>
Default static IP assigned to ethernet interface: 10.42.0.5

For Root-user tasks, there will be a sudo error:
1)/etc/sudoers.d is owned by uid 1000, should be 0
Resolve by this command: chown root:root /etc/sudoers /etc/sudoers.d -R

2)if /etc/apt/preferences.d not found error is thrown
Resolve by this command: sudo mkdir /etc/apt/preferences.d
