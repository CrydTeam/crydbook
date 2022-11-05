---
description: 'falls du keinen Nginx nutze kannst du weitere Dienste freigeben:'
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

