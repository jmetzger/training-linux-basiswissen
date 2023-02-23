# LDAP-Server einbinden

## Grundlagen 

  * Redhat verwendet SSSD und realm um eine Einbindung zu erreichen

## SSSD 

  * System Security Service Daemon 
  * Unterstützt die Möglichkeit sich zu externe ID-Providern zu verbinden (z.B. LDAP)
  * Baut die Verbindung dahin auf. 

### 

```
für ldap braucht man kein realmd sondern sssd reicht aus
```




## Reference 

  * https://www.computerweekly.com/de/ratgeber/So-binden-Sie-RHEL-Server-an-Active-Directory-an
  * https://access.redhat.com/documentation/de-de/red_hat_enterprise_linux/8/html/configuring_authentication_and_authorization_in_rhel/configuring-sssd-to-use-ldap-and-require-tls-authentication_configuring-authentication-and-authorization-in-rhel
