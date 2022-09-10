# Fix nach Update auf 1.5



#### Wie update ich auf Version 1.5

da ihr hoffentlich `fire-dom-event` benutzt habt braucht ihr nur folgendes ändern

```
action: fire-dom-event
browser_mod:
  command: popup
  title: My title
  card:
    type: ...etc...
```

zu

```
action: fire-dom-event
browser_mod:
  service: browser_mod.popup
  data:
    title: My title
    content:
      type: ...etc...
```
