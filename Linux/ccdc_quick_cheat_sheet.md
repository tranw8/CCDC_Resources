### Backup configs - Linux
```
gzip -rf --best -c /path/to/folder > folder.gz # create backup archive of folder
gzip --best -c /path/to/file > file.gz # create backup archive of file
gunzip file.gz # unzip folder
# if gzip is not available
tar cxzf /path/to/folder/ file.tar.gz # create backup archive of file or folder
tar -xf file.tar.gz # uncompress file
rsync -P archiveFile user@ip:/path/to/remote/store/ # move file to remote machine
```

### Audit Users
```
passwd -l root # Changes/locks ‘root’ pass
getent passwd 0 # should only be one, root
getent group root admin sudo wheel # list all root and admin
getent passwd | cut -d : -f 1 | xargs groups # List all users, with groups they’re in
deluser -rf <usr> # Delete 
gpasswd -d <usr> <group> # remove <usr> group
usermod -aG <group> <usr> # add <usr> group
```

### Check sudoers files
```
visudo # edit/
# Expected entries:
# root ALL=(ALL:ALL) ALL
# %wheel ALL=(ALL) ALL
# %sudo ALL=(ALL) ALL
```

### Check ssh config
Config at: /etc/ssh/sshd_config
Change to: PermitRootLogin no
SSH:
(Ubuntu)
Service ssh restart
(Centos / Fedora)
Service sshd restart

### Firewall
```
ufw allow <ports> # do for all ports allowed
ufw default deny # set default rule
ufw enable # start firewall
ufw status numbered # check rules
ufw delete <num> # delete bad rules
```

### apt
GUI: Software & Updates
Config: /etc/apt/sources.list and /etc/apt/sources.list.d/
```
apt update # refresh sources
apt upgrade -y # install updates
apt install <pkg> # install program
apt remove --purge <pkg> # uninstall program
apt list --installed # view installed programs
```

### yum
Config: /etc/yum.repos.d/
```
# Every yum command refreshes the sources
yum update # update packages
yum install <pkg> # install package
yum remove <pkg> # uninstall package
```
