# Install Gitkraken on Pop!_OS
[Gitkraken | How to install](https://support.gitkraken.com/how-to-install)

1. Download the tar file

```
wget https://release.gitkraken.com/linux/gitkraken-amd64.tar.gz
tar -xvzf gitkraken-amd64.tar.gz
```

2. Untar the file

3. Move the `gitkraken` directory to the `/opts/` directory

```
sudo mv gitkraken /opt/
```

# Issue
1. Error with libcurl.so.4
Error: libcurl.so.4: cannot open shared object file: No such file or directory.

```
yoda@pop-os:/opt/gitkraken$ ./gitkraken
./gitkraken: error while loading shared libraries: libgconf-2.so.4: cannot open shared object file: No such file or directory
```
Run the following command to address the dependency issue.

```
sudo apt -y install libgconf2-4
```

# Need to resolve

(gitkraken:29817): GConf-WARNING **: 00:21:33.736: Client failed to connect to the D-BUS daemon:
Failed to connect to socket /run/user/1000/bus: Connection refused
libgnome-keyring.so.0: cannot open shared object file: No such file or directory
Error: libgnome-keyring.so.0: cannot open shared object file: No such file or directory
