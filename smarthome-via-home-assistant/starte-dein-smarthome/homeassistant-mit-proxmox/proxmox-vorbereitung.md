# Proxmox Vorbereitung

Als erstes sollte die Enterprise Repo deaktiviert werden und die korrekten Ressourcen hinzugefügt werden.

Das lässt sich sehr einfach und schnell per Script erledigen - einfach folgenden Befehl im Prox Shell ausführen:

```
bash -c "$(wget -qLO - https://github.com/tteck/Proxmox/raw/main/misc/post-pve-install.sh)"
```

<figure><img src="../../../.gitbook/assets/image (9) (5).png" alt=""><figcaption><p>diese Ansicht sollte erscheinen - hier bitte alles mit y bestätigen (Beta habe ich bei mir deaktiviert)</p></figcaption></figure>

Sollte hier nichts erscheinen prüft bitte eure Internetverbindung (bei mir hat es nicht geklappt da der DNS am Prox nicht richtig war)



Hier gibt es auch einen Befehl zum prüfen:

```
RESOLVEDIP=$(nslookup "github.com" | awk -F':' '/^Address: / { matched = 1 } matched { print $2}' | xargs)
if [[ -z "$RESOLVEDIP" ]]; then echo "DNS Lookup Failure";  else echo -e "DNS Resolved github.com to $RESOLVEDIP";  fi
```
