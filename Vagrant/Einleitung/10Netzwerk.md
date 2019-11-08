# Netzwerke mit Vagrant

Vagrant unterstützt drei Möglichkeiten für die Netzwerkkonfigurationen. Diese wären folgende Möglichkeiten:
- Portweiterleitungen
- Private Netzwerke
- Öffentliche Netzwerke

Standardmässig sind Vagrant Boxen nicht sicher. User, Kennwörter und kryptografische Schlüssel sind in der Regel Standard. Deshalb empfiehl sich dies nicht für öffentliche Netzwerke. Für diesen Einsatz müsste man diese ändern. Dies ist jeoch nicht bestandteil dieses Kurses.

#### Portweiterleitungen:
Mit dieser Funktionen können Pors von der VM auf dem Host weitergeleitet werden. Dies macht Beispielsweise Sinn, wenn man die Ports eines Apache-Webservers an dem Host weiterleiten möchte. Hier wird dies Bildlich dargestellt:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_forwarding.PNG)

Damit ihr dies auch praktisch umserzen werdet werden wir einen Apache-Webserver auf der Ubuntu Box installieren und eine Portweiterleitung konfigurieren:

1) Starte die Box `vagrant up`.
2) Starte mit `vagrant ssh` eine SSH-Connection mit der Box.
3) Folgende Bash Befehle eingeben:
- `sudo apt-get update`
- `sudo apt-get upgrade`
- `sudo apt-get install apache2`
