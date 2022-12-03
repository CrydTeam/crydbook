# Fehler

Sollte bei der Installation folgender Fehler auftreten müsst ihr im Bios die Virtualisierung aktivieren.

<figure><img src="../../../.gitbook/assets/image (8) (3).png" alt=""><figcaption></figcaption></figure>

Sollte bei euch die Installation im Startbildschirm nach 20 Minuten nicht weiter gehen klickt auf den pulsierenden Punkt.

Dort erscheint dann ein Log:

```
22-11-15 11:00:29 ERROR (SyncWorker_3) [supervisor.docker.interface] Can't install ghcr.io/home-assistant/qemux86-64-homeassistant:2022.11.2: 500 Server Error for http+docker://localhost/v1.41/images/create?tag=2022.11.2&fromImage=ghcr.io%2Fhome-assistant%2Fqemux86-64-homeassistant&platform=linux%2Famd64: Internal Server Error ("Get "https://ghcr.io/v2/": dial tcp: lookup ghcr.io: no such host")
22-11-15 11:00:29 WARNING (MainThread) [supervisor.homeassistant.core] Error on Home Assistant installation. Retry in 30sec
22-11-15 11:00:59 INFO (SyncWorker_1) [supervisor.docker.interface] Updating image ghcr.io/home-assistant/qemux86-64-homeassistant:landingpage to ghcr.io/home-assistant/qemux86-64-homeassistant:2022.11.2
22-11-15 11:00:59 INFO (SyncWorker_1) [supervisor.docker.interface] Downloading docker image ghcr.io/home-assistant/qemux86-64-homeassistant with tag 2022.11.2.
```

Sollte diese oder ähnliche Meldung erscheinen habt ihr ein DNS Problem was man in der HA Konsole evtl. mit folgendem Befehl beheben kann:

```
dns options --servers dns://1.1.1.1
dns restart
```

falls dies keine Abhilfe bringt überprüft den lokalen DNS (Adguard kann hier evtl ein Problem sein)
