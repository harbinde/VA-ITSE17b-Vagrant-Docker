# Vagrant Provisoners

#### -------------------------------------------------------------------------
#### Kursmaterial: (https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/tree/master/Vagrant/Einleitung/Kursmaterial/12Provisoners)
#### -------------------------------------------------------------------------

Vagrant Provisoners sind Skripts, welche im Vagratfile oder einem externen File definiert werden. Standardmässig, werden die Provisoners nur beim ersten Ausführen der Box durchgeführt.
Provisoners können Applikationen herunterladen, installieren und Konfigurationen tätigen. Vagrant Provisoners eignen sich deshalb ausgezeichnet um eine Vagrant Box zu automatisieren. Möchte man Beispielsweisse ein Box-Template haben, welche automatisch einen Apache Webserver mitinstalliert, so kann man dies im Provisoners-Abschnitt im Vagrantfile definieren.
Damit wir so ein Template erstellen können, wird zuerst die alte Box entfernt:

1) `vagrant destroy` ausführen
2) Im Root-Verzeichnis des Vagrant Projektess `Vagrant_Hello` den Ordnern `installer` erstellen 
3) Im Verzeichnis `installer` wird nun die Datei `install_apache2.sh` erstellt, welche folgende Befehle enthalten:
- sudo apt-get update
- sudo apt-get upgrade
- sudo apt-get install -y apache2
4) Das File sichern
5) Provisoner Skripts können wie schon vorhin erwähnt im Vagrantfile oder mit externen Skript definiert werden. Standardmässig macht man dies im Vagrantfile. Doch in diesem Fall haben wir ein externes File definiert, was das Ganze auch viel übersichtlicher und einfacher macht, solche Skripts zu verwalten.
6) Vagrantfile öffnen
7) Den Befehl `# config.vm.provision "shell", inline: <<-SHELL` auskommentieren
8) Den Befehl durch dieses Statement ändern:
- `config.vm.provision "shell", path: "installer/install_apache2.sh"`
9) Vagrantfile sichern
10) Mit `vagrant up` die Box neu einrichten
11) Die NAT-Regeln befinden sich immer noch im Vagrantfile. Sobald also die VM vollständig eingerichtet wurde, kann mit dem Web-Browser überprüft werden, ob auch wirklich Apache installiert bzw. konfiguriert wurde:
- http://localhost:8888
![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_nat_apache_site.PNG)
12) Die Box wurde erfolgreich mit einem Provisoners File eingerichtet
