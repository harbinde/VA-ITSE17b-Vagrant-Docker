# Docker Image ausführen

Vorhin haben wir Docker installiert. Daher befndet sich noch nichts im Zusemanhang mit Images und Container. 
In diesem Abschnitt wird beschriebn wie man ein Image herunteläd und als Container ausführt.

1) Terminal öffnen
2) Den Befehl `docker pull httpd`. Dieser Befehl lädt aus dem Docker Hub das Image herunter und installiert das Offiziele Docker Image von Apache. Das Image wird von Apache auf dem Docker Repository zur Verfügung (Docker Hub) gestellt.
3) Wenn man nun `docker images` eingibt, werden alle vorhanden Docker Images aufgelistet. Dieser Befehl listet under anderem auf wie das Repository dieses Images heisst, welchen Tag (Version) und welche Image ID für dieses Image generiert wurde.

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/docker_pull_list_image.PNG)

4) Möchte man das httpd Image starten so führt man den Befehl `docker run httpd:latest` aus. Man kann das Image auch mit der ID starten. dann würde dieser Befehl `docker run IMAGE_ID` lauten.
5) Das Image httpd benötigt gewisse Einstellungen, dass es auch ausgeführt wird. Deshalb habe ich noch das Ubuntu Image mit `docker pull ubuntu` heruntergeladen und danach gestartet. Möchte man nun auf den laufendem Container eine Verbindung aufbauen, so gibt man den Befehl `docker run -ti ubuntu -` oder `docker run -ti Image-ID` ausführen. Mit `exit` kann jederzeit das Bash des Containers beendet werden.
