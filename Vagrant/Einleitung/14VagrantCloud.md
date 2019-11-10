# Eine Box in Vagrant Cloud bereitstellen

Vagrant bietet die Funktion, lebsterstelle Boxen in der Cloud hochzuladen und für andere verfügbar zu machen. In diesem Beispiel wrd erläutert wie man dies macht. Die Base Box finden man unter 

1) Die Website https://app.vagrantup.com aufrufen
2) Ein kostenloses Vagrant Account erstellen und sich damit anmelden
3) Unter Dashboard "New Vagrant Box" auswählen
4) Den Namen der Box definieren und auf "Create Box" klicken. In diesem Fall habe ich mich für NginxBox entschieden
5) Die Version mit `0.0.1` definieren
6) Ins Verzeichnis der Vagrant Box wechseln und `vagrant up` ausführen.
7) Mit `vagrant package --vagrantfile Vagrantfile --output NginxBox.box` wird aus der VM eine Box erstellt.
8) Mit dem Befehl `certutil -hashfile NginxBox.com -SHA256` wird der Hash dieser Box erzeugt. Dieser wird dan später benötigt
9) Nun wechselt man wieder zu Vagrant Cloud und klickt auf "Add a Provider". Als Provider wird "VirtualBox" definiert. Als File Hosting wird Vagrant Cloud verwendet. Nun wird die Checksumme auf SHA256 definiert und der Hashwert, welches vorhin erzeugt wurde hinzugefügt. Anschliessend wird die Box hochgeladen. Danach klickt man auf "Release Version". Die Box steht nun allen zur Verfügung.

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrantcloud_1.PNG)
