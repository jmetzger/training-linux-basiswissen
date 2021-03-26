# Why a umask of 002 and 022 for normal users ?

```
# Just quoting redhat here.
The setting which determines what permissions are applied to a newly created file or 
directory is called a umask and is configured in the /etc/bashrc file. 

Traditionally on UNIX systems, the umask is set to 022, which allows only the user 
who created the file or directory to make modifications. Under this scheme, 
all other users, including members of the creator's group, are not allowed 
to make any modifications. However, under the UPG scheme, this "group protection" 
is not necessary since every user has their own private group.

# Ref:
https://access.redhat.com/documentation/en-us/red_hat_enterprise_linux/4/html/reference_guide/s1-users-groups-private-groups

```
