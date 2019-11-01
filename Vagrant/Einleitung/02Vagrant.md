# Vagrant
Was ist Vagrant und für welche Zwecke wird diese Software verwendet?
Vagrant hat verschiedene Anwendungszwecke. Beispielsweise nutzen Entwickler und Systemengineers Vagrant um Virtuelle Maschinen für Testzwecke schnell und einfach zu Verfügung zu stellen.
Dabei kann die Maschine so konfiguriert werden, dass dieser beim Deployment die benötigten Tools und Programme mitinstalliert.
Eine Vagrant VM befindet sich in einem eingefrorenem Zustand. Das heisst, dass die Versionen der Tools, welche installiert werden beim nächsten Start der VM immer noch die gleiche Version hat.
Das Arbeiten mit Vagrant VM's macht die ganze sache portabel. Mann kann die Snapshots erstellen und anderen zur Verfügung stellen.
Diese können dann ganz einfach die Files auf dem Rechner lokal hinterlegen und die Vagrant VM starten.
Vagrant macht es sehr einfach eine Virtuelle Maschine über die sogennante Vagrant Cloud einzurichten.

## Die Vagrant Komponenten
#### CLI
* Das CLI ist das Command Line Tool von Vagrant. Das CLI wird benötigt um Vgrant VM's verwalten zu können.
#### Vagrantfile
* In dieser Datei, werden die Vagrant VM's definiert. Das Vagrantfile wird in der Programiersprache Ruby geschrieben und werden von der CLI ausgeführt, damit Vagrant VM's entstehen können. Selbst wenn man sich nicht mit Ruby auskennt, stellt dies kein hindernis dar, da die Gliederung und das Editieren der Vagrant files sehr simpel ist, da die Ruby Befehle mehr als Statements angesehen werden können, welche keine Komplexität aufweisen.
#### Vagrant Cloud
* Vagrant Cloud ist eine Repository, welche der Hersteller von Vagrant (HashiCorp) zur Verfügung stellt. Das Format von Vagrant VM's macht es sehr einfach die Maschinen freizugeben. Die Benutzer mit einem Vagrant Cloud Account können selbst erstellte VM's dort lagern und  der Öffentlichkeit oder gewisse Personen auch freigeben.
## Merkmale von Vagrant
Vagrant beihnahltet zahlreiche Features, um Vgrant VM's verwalten zu können. Diese wären folgende Merkmale
* Mann kann mit der CLI per SSH auf die VM eine Verbindung aufbauen
* Ordner (inklusive Daten), welche sich auf dem Host befinden können mir der virtuellen Maschine synchronisiert werden
* Vagrant bietet dem Benutzer an viele Netzwerkeinstellungen zu machen.
* Vagrant bietet das Plugin Providers an, welche den gewünschten Hypervisor ansprechen kann.
* Mit Provisiners können Befehle beim ersten Build der VM's ausgeführt werden. Diese können Beispielsweisse Programme installieren oder gewisse Konfigurationen einrichten.
* In einem Vagrantfile können gleich mehrere VM's installiert und ausgerollt werden
