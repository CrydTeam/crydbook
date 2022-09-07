# SD Karten Formatierung unter Mac

```
 sudo diskutil list sudo diskutil unmountdisk <value from list e.g. /dev/disk2> sudo newfs_msdos -F 32 -c 8 -v micro <value from list e.g. /dev/disk2>
```

