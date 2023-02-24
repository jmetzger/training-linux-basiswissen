# LDAP-Server einbinden

## Grundlagen 

  * Redhat verwendet SSSD um eine Einbindung zu erreichen
  * authselect hilft mir auf einfach Weise die Authentifizierung umzustellen 

## SSSD 

  * System Security Service Daemon 
  * Unterstützt die Möglichkeit sich zu externe ID-Providern zu verbinden (z.B. LDAP)
  * Baut die Verbindung dahin auf. 

### authselect 

  * Stellt die Nutzung von ldap für Authentifizierung ein.
  * statt dass ich das selbst händisch machen muss.
 
### Installation 

```
dnf install sssd sssd-tools 
```

### Konfiguration für sssd einrichten

#### Config von sssd 

```
cat > /etc/sssd/sssd.conf << EOL
[sssd]
services = nss, pam, sudo
config_file_version = 2
domains = default

[sudo]

[nss]

[pam]
offline_credentials_expiration = 60

[domain/default]
ldap_id_use_start_tls = True
cache_credentials = True
ldap_search_base = dc=ldapmaster,dc=kifarunix-demo,dc=com
id_provider = ldap
auth_provider = ldap
chpass_provider = ldap
access_provider = ldap
sudo_provider = ldap
ldap_uri = ldap://ldapmaster.kifarunix-demo.com
ldap_default_bind_dn = cn=readonly,ou=system,dc=ldapmaster,dc=kifarunix-demo,dc=com
ldap_default_authtok = P@ssWOrd
ldap_tls_reqcert = demand
ldap_tls_cacert = /etc/pki/tls/cacert.crt
ldap_tls_cacertdir = /etc/pki/tls
ldap_search_timeout = 50
ldap_network_timeout = 60
ldap_sudo_search_base = ou=SUDOers,dc=ldapmaster,dc=kifarunix-demo,dc=com
ldap_access_order = filter
ldap_access_filter = (objectClass=posixAccount)
EOL
```

#### Erklärung: sudo 

```
## sudo with auch über ldap gezogen 
## d.h. ob jemand sudo darf:
## wenn man das nicht möchte, muss man es auskommentieren 
services = nss, pam, sudo
.....

[sudo]
ldap_sudo_search_base = ou=SUDOers,dc=ldapmaster,dc=kifarunix-demo,dc=com


```

#### Zertifikat vom ldap - server holen und lokal speichern als CA 

```
# Test it - to see if you get a certificate 
openssl s_client -connect ldapmaster.kifarunix-demo.com:636 -showcerts < /dev/null | openssl x509 -text 
# now write it 
openssl s_client -connect ldapmaster.kifarunix-demo.com:636 -showcerts < /dev/null | openssl x509 -text > /etc/pki/tls/cacert.crt

```

#### Configure ldap.conf 

```
# vim /etv/openldap/ldap.conf 
# change the following lines 
BASE    dc=ldapmaster,dc=kifarunix-demo,dc=com
URI     ldaps://ldapmaster.kifarunix-demo.com:636
SUDOERS_BASE    ou=SUDOers,dc=ldapmaster,dc=kifarunix-demo,dc=com
...
...
TLS_CACERT      /etc/pki/tls/cacert.crt
```

#### Configure auth-system with authselect 


```
# authselect will modifiy these files 
/etc/pam.d/system-auth
/etc/pam.d/password-auth
/etc/pam.d/fingerprint-auth
/etc/pam.d/smartcard-auth
/etc/pam.d/postlogin
/etc/nsswitch.conf
```

```
# configure system to use ldap through sssd 
authselect select sssd 
# oder falls files akutell dort liegen 
authselect select --force sssd 
```

```
# What did it change ? (most important file) 
cat /etc/nsswitch.conf 
e.g. 
files sss
```

```
# for using sudoers you would need to add 
echo "sudoers:    files sss" >> /etc/nsswitch.conf
```

#### Weiteres: z.B. home-verzeichnisse erstellen 

```
# oddjob-home 
  * https://kifarunix.com/configure-sssd-for-ldap-authentication-on-rocky-linux-8/
```

#### Wichtig: Bekommt der Authentifizierungsprozess die Daten von ldap ? 

```
getent passwd 
# oder 
# hier einen usernamen nehmen, den es lokal nicht gibt. 
getent passwd username 
```


## Reference 

  * https://kifarunix.com/configure-sssd-for-ldap-authentication-on-rocky-linux-8/
