# LB2  Dokumentation - Kevin Lang


[TOC]

file:///C:/Users/kevin/AppData/Local/Temp/nw8920_8943/viewer.html#k1---umgebung-auf-eigenem-notebook-eingerichtet-und-funktionsfähig-(4p.)
## K1 - Umgebung auf eigenem Notebook eingerichtet und funktionsfähig (4p.)
### VirtualBox
VM manuell erstellt
Name: M300.1
Typ: Linux (Ubuntu (64-bit))

VM kopiert von GitHub (Vagrant file)
Name: VagrantVMs_default_1551088078848_94350
Typ: Linux (Ubuntu (64-bit))
Speicherort: C:/Users/kevin/M300/vagrant/user

### Vagrant
Eingerichtet und über Git-Client verwendet

### Git-Client
Eingerichtet und gebraucht (Git Bash)

### SSH-Key für Client erstellt
MB SSH-Key: 49:ff:56:b6:2d:ea:a9:ae:7a:ba:fa:ae:e6:26:c4:ad
Überprüfbar unter: https://github.com/settings/keys

## K2 - Eigene Lernumgebung eingerichtet (5p.)
### GitHub oder Gitlab-Account ist erstellt
Mein Github Account lautet: KevinLang76 (https://github.com/KevinLang76)

### Git-Client wurde verwendet
Git Bash für jegliche Einrichtungen gebraucht

### Dokumentation ist als Mark Down vorhanden
^^Ja

###Mark down-Editor ausgewählt und eingerichtet
HarooPad Mark Down editor verwendet.
HarooPad ist deshalb empfehlenswert, weil es Bearbeitungs und Preview Fenster gleichzeitig anzeigen kann und Formatbefehle in Optionen vordefinert ausgewählt werden kann.

### Mark down ist strukturiert
+ Reihenfolge aller Themen entspricht der von den Bewertungskriterien.
+ Automatisches Inhaltsverzeichniss

## K3 (5p.)
### Bestehende VM aus Vagrant-Cloud einrichten

C:\Users\kevin\VirtualBox VMs\VagrantVMs_default_1551088078848_94350

### Kennt die Vagrant-Befehle
Wichtigste Befehle die ich für das Einrichten der VMs gebraucht habe:

| Befehl | Beschreibung |
|--------|--------|
|   vagrant init     |   Initialisiert im aktuellen Verzeichnis eine Vagrant-Umgebung und erstellt, falls nicht vorhanden, ein Vagrantfile     |
| vagrant up | Erzeugt und Konfiguriert eine neue Virtuelle Maschine, basierend auf dem Vagrantfile |
|vagrant ssh  | Baut eine SSH-Verbindung zur gewünschten VM auf|
|vagrant halt| Stoppt die laufende Virtuelle Maschine|
|vagrant destroy| Stoppt die Virtuelle Maschine und zerstört sie|


###Funktionsweise getestet inkl. Dokumentation der Tetfälle
Persöhnlicher GitHub per Browser muss erreichbar sein: True
Kopie der M300 Infrastruktur auf Persöhnlicher Umgebung: True
VirtualBox VM mit vagrant einschaltbar: True
VirtualVow VM kann mit SSH im GitBash verbunden werden: True
Übersichtliche eingene Infrastruktur: False

###andere, vorgefertigte vm auf eigenem Notebook aufgesetzt
siehe K1 - VirtualBox
> VM manuell erstellt
Name: M300.1
Typ: Linux (Ubuntu (64-bit))

### Projekt mit Git und Mark Down dokumentiert
^^MarkDown

## K4 Sicherheitsaspekte sind implementiert (5p.)
Bemerkung: Weil am 24.3 plötzlich keine Verbindung zu den VM bestanden, wurde einiges am 25.3 neu erstellt. Mögliche Ungenauigkeiten der Doku können daraus bestanden sein.
### Firewall eingerichtet inkl. Rules
vagrant@db01:~$ sudo ufw status
Status: active

|Rule Number |To              |           Action  |    From
|---|--         |                ------   |   ----
|[ 1]| Anywhere     |              ALLOW IN |   192.168.80.1
|[ 2]| 80/tcp     |                ALLOW IN |   Anywhere
|[ 3] |22        |                 ALLOW IN  |  192.168.80.1|
|[ 4]| 3306          |             ALLOW IN  |  192.168.80.1
|[ 5] |80/tcp (v6)  |              ALLOW IN  |  Anywhere (v6)

### Reverse-Proxy eingerichtet
failed

### Zugang mit SSH-Tunnel abgesichert
failed

### Projekt mit Git und Mark Down dokumentiert
^^MarkDown

## K 5 (5p.)
### Vergleich Vorwissen - Wissenszuwachs
Ich weiss einigermassen was Vagrant ist, für was es zu gebrauchen ist und wie man es verwenden sollte. Mit Linux habe ich immer noch sehr viel mühe.

### Reflexion
Während der ganzen LB hatte ich nie wirklich ahnung was ich überhaupt mache und war somit eigentlich immer recht verloren. Anleitungen habe ich immer auf irgend eine weise falsch befolgt. Ich habe versucht von Zuhause aus meine Fehler von während den Lektionen zu beheben, aber auch dies resultierte nur in weiteren für mich nicht nachvollziegbaren Problemen. Schlussendlich war all die investierte Zeit für nichts.



