# Eine Verbindung zur Vagrant VM aufbauen
Wir haben vorhin mit Vagrant eine Ubuntu VM eingerichtet. Diese hat kein GUI und läuft auch im Hintergrund. Auf dem ersten Blick meint man, dass keine Verbindung zur VM möglich ist.
Doch dem ist nicht so. Vagrant kommt mit einer eingebauten SSH-Funktion daher. Möchte man auf die VM zugreifen, kann man dies mit SSH tun.
Sobald Vagrant eine Box konfiguriert, wird automatisch SSH mitsamt einem Schlüsselpaar konfiguriert, welche zur authorisierung dient.
Dies macht es sehr einfach eine SSH-Verbindung via Vagrant CLI aufzubauen.

#### SSH Verbindung  (lokal)
1) Ins Verzechnis mit `cd PFAD` wechsel, wo sich die Box befindet.
2) Den Befehl `vagrant ssh` eingegeben
3) Nun hat man auf die VM mithilfe von SSH aufgebaut.
4) Mit `exit` wird die SSH Verbindung verlassen

#### SSH Verbindung  (global)

1) Hier wird der Befehl "vagrant ssh ID" eingegben. In diesem Fall lautet dies `vagrant ssh bc26ee0`:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_ssh.JPG)

2) Mit `exit` wird die SSH Verbindung verlassen
