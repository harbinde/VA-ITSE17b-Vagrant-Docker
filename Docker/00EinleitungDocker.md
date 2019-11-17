# Einleitung
Die Hauptaufgabe von Docker besteht Container auf einer Linux Umgebung zu verwalten und diesen bei Bedarf starten und zu stoppen. Nun ist es so, dass nicht die Meisten mit einer Linux Umgebung arbeiten.  Deshalb richtet Docker bei einer Windows Installation eine Linux VM, wo die Containerisierung läuft. Docker bietet ein Tool an, mit dem die Verwaltung von Container nahezu transaprent ist.  Wir werden uns Schritt für Schritt in dieser Thematik aufarbeiten. Zuerst sehen wir an, wie Docker aufgebaut ist. Danach wird erläutert wie es installiert, konfiguriert und verwaltet wird.
Seitdem es Docker gibt, hört man immer mehr über die sogennante Containisierung. Doch was ist eigentlich ein Container?
Ein Container kann man sich wie der Name schon sagt als einen Container (isolierter Bereich) ansehen, welche eine Anwendung mitsamt der Abhängigkeiten (Konfiguration, Datenbanken, etc.) läuft.

Bei Docker handelt es sich um eine Art der Virtualisierung. Es ist deshalb möglich, mehrere Systeme auf der gleichen Hardware auszuführen. Die Vorteile der Containisierung sind die bessere Ressourcenutzung von CPU, Speicher und Netzwerk. Im Vergleich zur virtualisierung kann ist Docker für kostengünstiger, da man keine besondere Hardware benötigt und es viel effizienter ist als andere Virtualisierungstechnologien.
Wichtig zu wissen ist, dass es sich bei Docker um eine Anwendunsgvirtuallisierung auf der Betriesystemebene handelt. Deshalbh ist Docker kein Hypervisior.

Docker basiert auf das Prinzip Continious Integration. Hierbei handelt es sich um die einfache Skallierung der Anwendungsfälle. Man kann die Container soagr auf mehreren Docker Cluster ausweiten, sodass sogar Zero Down Time Deployments möglich sind. Bei einem Ausfall eines Host würde der andere Docker Host die Anwendung übernehmen und den Betrieb des Containers sicherstellen.
Ein grosser Vorteil von Docker ist dabei auch die Portabilität. Die Container können jederzeit angepasst oder sogar auch ausgelagert werden. Dabei spielt die eigentliche Linux Distribution keine Rolle, da alle unterstütz werden. 

## Container

Container ist keine Technlologie, welche von Docker erfunden wurde. Diese Technologie wurde schon in Linux Kernsel von ca. 10 Jahren eingebaut. Für die Containisierung von Linux Container war die Bibliothek Linux Containers (LXC) zuständig. Hierbei wird eine eine Anwendung vom eigentlichen Betriebsystem isoliert und macht es auch Betriebsystemunabhängig. Deshalb wird dies auch als Container bezeichnit, weil diese jederzeit verschoben (verschift) werden kann. Huete ist es jedoch so, dass Docker eine eigene Bibliothek Libcontainer für die Containisierung bereitstellt. 

## Funktion von Docker

Docker ist ein Systemdienst, welche via eine Schnittstelle über die Kommandozeile angesteuert werden kann. Wird Docker nun durch ein Kommando angesteurt, greift dieser durch die Bibliothe Libcontainer zu und richtet dann die Kernel-Funktionen für die entsprechenden Anwendungen ein. Diese Funktionen bestehen aus cgroups und naespaces. Cgroups sin Ressourcenlimit, welche für alle I/O Systeme (Beispielsweise, CPU, Kerne, Filesysteme, etc.) konfiguriert werden können. Namespaces machen die Simulationen der isolierten Umgebungen möglich. Diese bestehen aus, eigene User, Prozesse, Mountpunkte, Hostnames, Geräte und Netzwerkgeräte. 
