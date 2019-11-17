# Docker Contaier in ein Image umwandeln.

In diesem Beispiel wird ein Ubuntu Container eigerichtet und dann anschliessend Apache installiert. Danach wird auf diesem Container ain Image erstellt.

1) Termnial öffnen
2) Mit dem Befehl `docker run ubuntu -ti` wird das Ubuntu Images genommen, in einem Container ausgeführt und anschliessend das Terminal von Ubuntu geöffnet.
3) `apt-get update`, `apt-get upgarde` und `apt-get install apache2 -y` durchführen. Nun sollte auf dem Ubuntu Container Apache installiert sein. Mit `exit` wird dann das Bash beendet.
4) `docker ps -a` eingeben und die Container ID kopieren.
5) Den Befehl `docker commit 6de51e922100  ubuntu-apache2 ` eingeben. Der Container wird nun in ein Image umgewandelt. Dabei wird eine Momentaufnahme des Gesamten Datensystem auf dem Container gemacht.

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockercommit.PNG)

6) Mit `docker ps -a` sollte man das neu angelegte image sehen:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockernewimagepsa.PNG

7) Mit `docker save ubuntu-apache2 > ubuntu-apache2.tar` wird das Image als komprimiertes TAR-File exportiert. 


