# Script Docker 

## cloud-init script 

```
#!/bin/bash
groupadd sshadmin
USERS="11trainingdo"
for USER in $USERS
do
  echo "Adding user $USER"
  useradd -s /bin/bash $USER
  usermod -aG sshadmin $USER
  echo "$USER:11dortmund22" | chpasswd
done

# We can sudo with 11trainingdo
usermod -aG sudo 11trainingdo 

# Setup ssh stuff 
sed -i "s/PasswordAuthentication no/PasswordAuthentication yes/g" /etc/ssh/sshd_config
usermod -aG sshadmin root
echo "AllowGroups sshadmin" >> /etc/ssh/sshd_config 
systemctl reload sshd 

# specifically fix do - stuff in new versions of cloud-init 
sed -i "s/PasswordAuthentication no/PasswordAuthentication yes/g" /etc/ssh/sshd_config.d/50-cloud-init.conf

apt update
# install dependencies 
sudo apt install apt-transport-https curl gnupg-agent ca-certificates software-properties-common -y

# get the gpgkey
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

# prepare repo for jammy (22.04 LTS)
add-apt-repository "deb [arch=amd64] https://download.docker.com/linux/ubuntu jammy stable"

# now install the packages 
apt install docker-ce docker-ce-cli containerd.io -y



```
