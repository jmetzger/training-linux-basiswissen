# Deb unboxing 

```
apt install -y binutils 
cd /usr/src 
mkdir unwrap-folder 
mv openssh-server-xyz.deb unwrap-folder 
cd unwrap-folder 
tar x openssh-server-xyz.deb 
# additionally might be necessary
tar xvf data.tar.xz 
tar xvf control.tar.xz 
```
