# Klipper auf ältere Version zurücksetzen

{% embed url="https://www.youtube.com/watch?list=PLWqnUinimMN37qSZhCR6XeglkRS4fza0D&v=gbWBC41iQtk" %}
Klipper auf ältere Version setzten
{% endembed %}

{% hint style="danger" %}
Vorher immer Backups erstellen.\
FTP -> klipper\_config ordner sichern
{% endhint %}

Aktuelle Version des Klipper ordners anzeigen

```
cd ~/klipper
git show
```

Letzte Commits anzeigen:

```
git log --stat
```

Klipper Ordner zurücksetzten

```
git reset --hard <COMMIT_NUMMER>
```
