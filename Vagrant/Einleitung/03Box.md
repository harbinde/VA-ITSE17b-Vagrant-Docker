# Eine Box mit Vagrant ausführen
Hier Wird beschrieben wie man eine Vagarnt Box ausführt. Eine Box ist ein komprimiertes File, wellche alle Informationen / Daten enthält um eine Vagrant VM zu starten.

1) Auf dem Desktop den Ordner "Vagrant_Hello" erstellen.
2) CMD starten.
3) Mit `cd C:\Users\USER\Desktop\Vagrant_Hello` ins Verzeichniss wechseln.
4) Damit eine Box aus der Vagrant Cloud als VM ausgeführt werden kann, muss zuerst die BOX initialisiert werden.
Für diesen Test werden wir eine Ubuntu Maschine nehmen.
Mit dem Befehl `vagrant init ubuntu/trusty64` wird die Box initialisiert:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_init_hello.JPG)
5) Es wurde in dem Pfad in Vagrant File hinterlegt. Das jetzige Verzeichnis ist nun ein sogennantes Vagrant Direcotry, welches von anderen Vagrant Verzeichnisse isoliert. Jede änderung hat keinen Einfluss auf die Vagrant Base Box. Unsere Umgebung ist nun startklar, wurde jedoch noch nicht ausgeführt.
6) Mit dem Befehel `vagrant up`
