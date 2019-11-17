# Docker Workflow

# Theorie

Nun haben wir Docker auf unsere Windows Maschine eingerichtet und haben angeschaut was Container sind und was Docker ist. Nun wird euch erläutert was jedoch Docker genau tut.
In Docker fängt alles mit einem Image an. Ein Image beinhaltet alle Komponenten und Daten, welche benötigt wird um dies als Container auszuführen und unterliegt eine entsprechendem Image Version. Es ist Portabel und kann jederzeit auf andere Dockerumgebungen verschoben werden. Es ist sozusagen eine Momentaufnahme einer Anwendung. Dies kann man sich am Besten vorstellen, wenn man Beispielsweise einen Apache Webserver früher auf einem System eingerichtet hat.
Dafür benötigte man bevor man den eigentlichen Dienst installieren konnte, ein Betriebsystem auf dem dann der Apache Webserver installiert wurde. Mit Docker wird dies viel einfacher. Wenn ich einen Apache Container betreiben möchte benötige ich lediglich ein Image. Wenn nun das Image ausgeführt wird, entsteht daraus ein Container. Die Operationen der Conatiner werden alle durch den Eigentlichen Host abgewickelt. In diesem Kurs wird dies von einer virtuellen Linux Maschine durchgeführt . Würde man jedoch Docker auf einer Linux Maschine einrichtn, würden die Operationen dann vom Linux Host ausgeführt werden. 

Wenn man einen Docker Image nimmt und diesen mit dem Befehl `docker run` auswühren würde, wird daraus ein laufender Container entstehen. In diesem Container werden ein oder mehrere Prozesse ausgeführt, welches "etwas tut".

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockerimageworkflow.PNG)

# Praxis

Vorhin haben wir Docker installiert. Daher befndet sich noch nichts im Zusemanhang mit Images und Container. Um das obenbeschriebene darzustellen wird folgendes durchgefphrt:

1) Terminal öffnen
2) Den Befehl `docker pull httpd`. Dieser Befehl installiert das Offiziele Docker Image von Apache. Das Image wird von Apache auf dem Docker Repository zur Verfügung (Docker Hub) gestellt.
3) Wenn man nun `docker images` eingibt, werden alle vorhanden Docker Images aufgelistet. Dieser Befehl listet under anderem auf wie das Repository dieses Images heisst, welchen Tag (Version) und welche Image ID für dieses Image generiert wurde.

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/docker_pull_list_image.PNG)
4) Möchte man das httpd Image starten so führt man den Befehl `docker run httpd:latest` aus. Man kann das Image auch mit der ID starten. dann würde dieser Befehl `docker run IMAGE_ID` lauten.
5) Das Image httpd benötigt gewisse Einstellungen, dass es auch ausgeführt wird. Deshalb habe ich noch das Ubuntu Image mit `docker pull ubuntu` heruntergeladen und danach gestartet. Möchte man nun auf den laufendem Container eine Verbindung aufbauen, so gibt man den Befehl `docker run -ti ubuntu -` oder `docker run -ti Image-ID` ausführen. Mit `exit` kann jederzeit das Bash des Containers beendet werden.
