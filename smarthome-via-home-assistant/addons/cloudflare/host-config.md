---
description: 'hiermit kannst du noch andere Dienste freigeben:'
---

# Host Config



```
- hostname: "router.example.com"
  service: "http://192.168.1.1"
- hostname: "diskstation.example.com"
  service: "https://192.168.1.2:5001"
- hostname: "website.example.com"
  service: "http://192.168.1.3:8080"
```

{% hint style="info" %}
ACHTUNG! Du teilst diesen Dienst im Netz bitte beachte das du keinerlei Dienste teilst die kein Passwort benötigen - wie z.B. die 3D Druck Seite etc.
{% endhint %}
