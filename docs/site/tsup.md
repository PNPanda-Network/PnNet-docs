# TeamSpeak 3 Server Installer and Updater

Ein leichtgewichtiges Skript zum Installieren oder Aktualisieren eines TeamSpeak 3-Servers unter Linux oder FreeBSD.

## Requirements

- **jq** 1.6 or newer (https://stedolan.github.io/jq/download/)
- curl
- shasum, sha256, or sha256sum
- tar
- bzip2

# How to use [Linux]

# Installieren einen neuen TeamSpeak 3-Server

Speicher das Skript an der Stelle, an der Sie den TS-Server installieren soll, und machen das Script ausführbar `chmod +x ts3updater.sh` und starte es mit `./ts3updater.sh`. Nach der Installation verschiebt sich das Skript in den Installationsordner. Führen Sie es von dort aus, wann immer Sie den Server aktualisieren möchten.

## Aktualisiert eine vorhandene TeamSpeak 3-Server installation

Kopiere das Skript im Verzeichnis Ihrer vorhandenen TS-Installation. Dies bedeutet, dass sich das Skript im selben Verzeichnis wie die `ts3server_startscript.sh`. Datei befinden muss Mache es ausführbar mit `chmod +x ts3updater.sh` und starte es mit `./ts3updater.sh`.

Wenn TSDNS verwendet wirt, stelle sicher, dass der Dienst gestoppt ist, bevor dieses Skript ausführt wird.

## Aktualisieren Sie den Server automatisch

Da der Server nur aktualisiert wird, wenn eine neue Version verfügbar ist, können Sie das Skript auch zum Automatisieren von Updates verwenden. Erstellen Sie einfach einen Cronjob, der das Skript beispielsweise stündlich oder täglich ausführt.

Ein Crontab-Eintrag, um ts3updater täglich um 13:28 Uhr auszuführen, könnte so aussehen: `28 13 * * * /home/ts/teamspeak3-server_linux_amd64/ts3updater.sh`.
Wenn du nicht jedes Mal eine E-Mail erhalten möchten, wenn das Skript ausgeführt wird. hänge das an den Crontab ` >/dev/null 2>&1`

du must die Serverlizenzvereinbarung akzeptieren, bevor Sie den Cronjob erstellen. Wechseln dazu in das Verzeichnis der TS-Installation und lesen Sie die Datei `LICENSE`und erstellen Sie eine Datei mit dem Namen `.ts3server_license_accepted`.

## Befehlszeilenparameter

Alle Parameter werden an übergeben `ts3server_startscript.sh` wenn der Server gestartet wird. Wenn du den Server nach der Installation oder Aktualisierung nicht starten möchten, verwenden den Parameter`--dont-start`.

#

# How to use [Windows]

## Installieren einen neuen TeamSpeak 3-Server

Speicher das Skript an der Stelle, an der Sie den TS-Server installieren soll.
in der `ts3updater.bat` die Variable server dein Server verzeichnis angeben
Ein Crontab-Eintrag, um ts3updater täglich um 13:28 Uhr auszuführen, könnte so aussehen: `set server= D:\Teamspeak-server_win64`.und starte die `ts3updater.bat`

## Aktualisiert eine vorhandene TeamSpeak 3-Server installation

Kopiere das Skript im Verzeichnis Ihrer vorhandenen TS-Installation.
starte die `ts3updater.bat`
