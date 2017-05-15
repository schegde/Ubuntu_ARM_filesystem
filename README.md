# Ubuntu_ARM_filesystem
Ubuntu 14.0.4 root file system, with Linux 3.x kernel headers and modules installed, for Zync7030 chip on Enclustra Mercury ZX1 SoC module


Write about formatting of SD card :boot and rootfs partion, and sudo cp -a into the rootfs ext4 partition

Username:root
Password:xilinx
SSH using : root@<ip_address>
Default static IP assigned to ethernet interface: 10.42.0.5

For sudo tasks(root user), there will be a sudo error:
1)/etc/sudoers.d is owned by uid 1000, should be 0
Resolve by these commands:

chmod 644 /usr/lib/sudo/sudoers.so
chown -R root /usr/lib/sudo
chown root:root /etc/sudoers /etc/sudoers.d -R

2)if /etc/apt/preferences.d not found error is thrown or /var/lib/dpkg/updates/ directory not found error is thrown during package installations:
Resolve by these commands: 
sudo mkdir /etc/apt/preferences.d
sudo mkdir /var/lib/dpkg/updates/

NOTE!!!: Many of directory not found errors may pop up because in version-controlling of this file system through git, these empty folders did not get added to the git repository and hence don't come on github!. Just use sudo mkdir <directory> for directory not found errors.


Write about network bring up:refer zedboard network bring up

Type an exit in terminal after booting up to correct some weird serial getTTY behaviour, that doesn't put terminal prompts on seperate lines.
