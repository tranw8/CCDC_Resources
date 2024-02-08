# Backup configs - Linux
```
gzip -rf --best -c /path/to/folder > folder.gz # create backup archive of folder
gzip --best -c /path/to/file > file.gz # create backup archive of file
gunzip file.gz # unzip folder
# if gzip is not available
tar cxzf /path/to/folder/ file.tar.gz # create backup archive of file or folder
tar -xf file.tar.gz # uncompress file
rsync -P archiveFile user@ip:/path/to/remote/store/ # move file to remote machine
```
