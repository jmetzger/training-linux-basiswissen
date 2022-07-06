# Install offline 

## Walkthrough 

```
# Step 1:
# offline computer:
sudo apt-offline set ~/my.sig

# Step 2: 
# copy .sig file from offline - computer to online 
# on online-computer
sudo apt-offline get -d /my-packages /path_to/my.sig
# tar folder /my-packages
sudo tar cvfz my-packages.tar.gz /my-packages 

# Step 3:
# copy tar to offline computer and unpack it 
# on offline computer 
cd /
sudo tar xvf my-packages.tar.gz 
sudo apt-offline install /my-packages 


```

## Reference

https://itsfoss.com/upgrade-or-update-ubuntu-offline-without-internet/#:~:text=Updating%20or%20upgrading%20Ubuntu%20with,about%20the%20latest%20updates%20available.
