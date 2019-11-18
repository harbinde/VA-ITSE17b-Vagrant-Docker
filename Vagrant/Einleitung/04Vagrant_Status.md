# Statusabfrage der Vagrant BOX
#### Lokale Statusabfrage
Man weiss nun wie man eine Box zum Laufen bringt. Die VM, welche vorhin erstellt wurde, läuft nun im sogenannten Headless-Modus.
Dies bedeutet, dass die VM ohne eine grafische Schnittstelle im Hintergrund läuft. Um zu überprüfen, ob die Vagrant VM auch wirklich im Moment ausgeführt wird, kann man mit der CLI (man muss sich im Verzeichnis der Vagrant VM befinden) den Befehl `vagrant status` eingeben:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_status.JPG)

Es wird der momentane Status der VM ausgegeben und teilt in diesem Fall mit, dass die VM nicht läuft. Mit dem Befehl `vagrant up` kann die VM wieder ausgeführt werden.
#### Globale Statusabfrage
Die `vagrant status` Methode funktioniert gut, wenn man sich in einem Vagrant VM Verzeichnis befindet. Doch irgendwann hat man wahrscheinlich mehrere Vagrant VM's und möchte eine Statusabfrage aller VM's durchführen. Dies kann man mit dem Befehl  `vagrant global-status` durchführen. Es werden alle VM's aufgelistet, welche sich auf der Vagrant Instanz befinden:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_status_global.JPG)

Unsere Vagrant_Hello VM besitzt die ID `bc26ee0`. Möchte man beispielsweise die VM beendet, so gibt man den Befehl `vagrant halt bc26ee0` ein.

