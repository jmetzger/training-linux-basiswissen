# Install offline 

## Install apt-offline on offline system 

```
## Online Server
# Get file from online server by downloading them there
apt install -d --reinstall apt-offline 
cd /var/cache/apt/archives/
mkdir /usr/src/pakete 
# in 2 weeks there probably will be new vesrion
cp -a python3-magic*.deb python3-pycurl*.deb python3-pysimplesoap_*_all.deb debian-archive-keyring*all.deb apt-offline*all.deb python3-debianbts*all.deb /usr/src/pakete/
cd /usr/src/pakete/
tar cfvz pakete.tar.gz pakete
# faked, instead use usb-stick 
scp pakete.tar.gz 11trainingdo@10.135.0.10:/home/11trainingdo


# for usage on online server 
apt install apt-offline 

```

```
# Offline - Server
cd 
tar xvf pakete.tar.gz 
cd pakete
dpkg -i python*.deb
dpkg -i debian*.deb
dpkg -i apt-offline*.deb

```

## Walkthrough 

```
# Step 1:
# offline computer:
sudo apt-offline set ~/my.sig

# Step 2: 
# copy .sig file from offline - computer to online 
# normally: per usb - stick
# in our case:
scp 11trainingdo@<ip-of-offline-computer>:/home/11trainingdo/my.sig .
scp my.sig 11trainingdo@<ip-private-ip>:/home/11trainingdo

# ---> 

# on ONLINE-computer
sudo apt-offline get -d /my-packages my.sig
# tar folder /my-packages
sudo tar cvfz my-packages.tar.gz /my-packages 

# Step 3:
# copy tar to OFFLINE computer and unpack it 
# on offline computer 
# normally usb-stick
scp my-packages.tar.gz 11trainingdo@10.135.0.10:/home/11trainingdo

# OFFLINE server 
cd 
sudo tar xvf my-packages.tar.gz 
sudo apt-offline install /my-packages 


```

## Reference

https://itsfoss.com/upgrade-or-update-ubuntu-offline-without-internet/#:~:text=Updating%20or%20upgrading%20Ubuntu%20with,about%20the%20latest%20updates%20available.
