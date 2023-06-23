# Wichtigste Schritte nach Installation 

## Schritt 1:

  * Alle Software deinstallieren, die nicht benötigt wird
  * z.B. anhand von lsof -i (offene Ports)

## Schritt 2: Dienste härten durch Konfiguration 

  * Alles was nicht benötigt wird abschalten (module) 
    * ssh
    * Apache
   
## Schritt 2.5: Firewall einrichten 

  * Nur services / ports freigeben die benötigt werden
  * Standard bei firewalld -> Zone: public
  * Am besten sogar nach egress (ausgehender Traffic), nur bestimmte Ziele erlauben 
   
## Schritt 3: Zugänge absichern 

  * ssh: nur bestimmte Nutzer dürfen zuzgreifen
  * sudo: nur bestimmte Gruppen
  * ssh: idealerweise kein Zugriff per password

## Schritt 4; (s. auch Schritt 2)

  * Was möchte ich eigentlich zeigen ? z.B. kein ServerToken (oder nur prod für Apache)

## Schritt 5: (regelmäßige Updates) 

  * evt. automatisch
    * unattended-upgrades
    * https://access.redhat.com/documentation/de-de/red_hat_enterprise_linux/9/html/managing_software_with_the_dnf_tool/assembly_automating-software-updates-in-rhel-9_managing-software-with-the-dnf-tool
   
## Extra - ssh absichern 

```
sshd_config:
# nur on, when server als jump 
AllowAgentForwarding no
AllowTcpForwarding no
# Auskommentieren, wenn nicht benötigt
# Subsystem     sftp    /usr/libexec/openssh/sftp-server

# Nur bestimmmte Gruppen erlauben (Unix-Gruppe
# Beispiel 
# groupadd sshadmin
# usermod -aG sshadmin kurs 
AllowGroups sshadmin 

```
