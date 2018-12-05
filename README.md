# Install Gitkraken on Pop!_OS
[Gitkraken | How to install](https://support.gitkraken.com/how-to-install)

# .deb
1. Download the debian package
```
wget https://release.gitkraken.com/linux/gitkraken-amd64.deb
```

2. Go to Applications -> Utilities
3. Open Eddy
4. Using Eddy, open the Gitkraken debian package and install it
5. Done

Much simpler than untarring it...mainly, because I ran into multiple issues.

# .tar

1. Download the tar file

```
wget https://release.gitkraken.com/linux/gitkraken-amd64.tar.gz
tar -xvzf gitkraken-amd64.tar.gz
```

2. Untar the file

3. Move the `gitkraken` directory to the `/opt/` directory

```
sudo mv gitkraken /opt/
```

# Tar Issues
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

2. Error with libgnome-keyring.so.0

```
libgnome-keyring.so.0: cannot open shared object file: No such file or directory
Error: libgnome-keyring.so.0: cannot open shared object file: No such file or directory
```
Run the following command to address the dependency issue.

```
sudo apt install libgnome-keyring-common libgnome-keyring-dev
```

# Tar issue that I was unable to resolve

```
(gitkraken:29817): GConf-WARNING **: 00:21:33.736: Client failed to connect to the D-BUS daemon:
Failed to connect to socket /run/user/1000/bus: Connection refused
```
