# iptables 

## Überblick

![iptables Überblick](https://webguy.vip/wp-content/uploads/2021/07/IPTABLES.jpg))

```
Quelle: https://webguy.vip/example-of-iptables/
```

## Was wird unter der Haube verwendet (iptables oder nf_tables) 

```
# Hier unter der Haube nf_tables 
iptables --version 
# iptables v1.8.7 (nf_tables)

# Ansonsten muss hier (legacy) stehen 
# Dann ist es ein reines iptables 
```


## Tables 

```
INPUT 
OUTPUT 
FORWARD 

PREROUTING 
POSTROUTING 

```

## Cheatsheet 

```
manage chain:
# iptables -N new_chain				// create a chain
# iptables -E new_chain old_chain  		// edit a chain
# iptables -X old_chain				// delete a chain

redirecting packet to a user chain:
# iptables -A INPUT -p icmp -j new_chain

listing rules:
# iptables -L					// list all rules of all tables
# iptables -L -v				// display rules and their counters
# iptables -L -t nat				// display rules for a specific tables
# iptables -L -n --line-numbers			// listing rules with line number for all tables
# iptables -L INPUT -n --line-numbers		// listing rules with line number for specific table

manage rules:
# iptables -A chain				// append rules to the bottom of the chain
# iptables -I chain [rulenum]			// insert in chain as rulenum (default at the top or 1)
# iptables -R chain rulenum			// replace rules with rules specified for the rulnum
# iptables -D chain	rulenum			// delete rules matching rulenum (default 1)
# iptables -D chain				// delete matching rules

change default policy:
# iptables -P chain target			// change policy on chain to target
# iptables -P INPUT DROP			// change INPUT table policy to DROP
# iptables -P OUTPUT DROP			// change OUTPUT chain policy to DROP
# iptables -P FORWARD DROP			// change FORWARD chain policy to DROP
```

## Beispiel: ssh / apache konfigurieren

```
# Variante nur eingehender Traffic 
iptables -A INPUT -i lo -j ACCEPT
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j ACCEPT

iptables -L -v

iptables -P INPUT DROP
```



```
# Variante mit ausgehendem Traffic 
 # Standard policy of drop setzen 
iptables -P INPUT DROP
iptables -P FORWARD DROP
iptables -P OUTPUT DROP 

iptables -A INPUT -i lo -j ACCEPT
iptables -A INPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A INPUT -p tcp --dport 22 -j ACCEPT

iptables -A OUTPUT -m state --state ESTABLISHED,RELATED -j ACCEPT
iptables -A OUTPUT -p tcp --sport 22 -j ACCEPT
```

```
# Tables flushen
iptables -F
```

## Regeln persistent setzen 

```
apt install iptables-persistent 
# wahrscheinlich 
zypper install iptables-service 

systemctl cat iptables-service 
systemctl status iptables-service 

# Regeln speichern, um sie beim Booten zu setzen
iptables-save > /etc/iptables/rules.v4 
```


## Ausblick 

  * Unter der Haube wird heute inftables verwendet 
  * s. iptables -L (alt: legacy) 

## Referenzen 

 * https://www.karlrupp.net/de/computer/nat_tutorial
