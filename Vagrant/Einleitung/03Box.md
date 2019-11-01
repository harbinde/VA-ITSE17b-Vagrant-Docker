# Eine Box mit Vagrant ausführen
#### -------------------------------------------------------------------------
#### Kursmaterial: (https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_init_hello.JPG)
#### -------------------------------------------------------------------------

Hier Wird beschrieben wie man eine Vagarnt Box ausführt. Eine Box ist ein komprimiertes File, wellche alle Informationen / Daten enthält um eine Vagrant VM zu starten.

1) Auf dem Desktop den Ordner "Vagrant_Hello" erstellen.
2) CMD starten.
3) Mit `cd C:\Users\USER\Desktop\Vagrant_Hello` ins Verzeichniss wechseln.
4) Damit eine Box aus der Vagrant Cloud als VM ausgeführt werden kann, muss zuerst die BOX initialisiert werden.
Für diesen Test werden wir eine Ubuntu Maschine nehmen.
Mit dem Befehl `vagrant init ubuntu/trusty64` wird die Box initialisiert:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_init_hello.JPG)

5) Es wurde in dem Pfad in Vagrant File hinterlegt. Das jetzige Verzeichnis ist nun ein sogennantes Vagrant Direcotry, welches von anderen Vagrant Verzeichnisse isoliert. Jede änderung hat keinen Einfluss auf die Vagrant Base Box. Unsere Umgebung ist nun startklar, wurde jedoch noch nicht ausgeführt.
6) Mit dem Befehel `vagrant up` wird nun die Box ausgeführt. 

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_up_hello.JPG)

7) Dieser Befehl sorgt dafürt, dass der Name der Box auf `ubuntu/trusty64` gesetzt wird. Diese Box bezieht sich auf die Box, welche sich auf der Vagrant Cloud befindet. Der Name ubuntu bezieht sich auf die Organisation, welche die Box auf der Cloud anbietet. Der Zweite Teil des Namens definiert die Version dieser Box. Jede Box, welche ausgeführt wird wird in einem Cache gelagert. Die Boxen werden in komprimierten Daten gelagert. Vagrant wird die Daten lokal auf dem lokalen Cache herunteladen. Der Cache befindet sich im Verzeichnis `C:\Users\USER\.vagrant.d\boxes\ubuntu-VAGRANTSLASH-trusty64\20190429.0.1\virtualbox` befinden. Dort ist unter anderem die VM, virtuelle Disk und das "orginale" Vagrantfile hinterlegt. Vagrant wird die Box in dem Verzeichnis importieren, wo der init Befehl ausgeführt wurde.

