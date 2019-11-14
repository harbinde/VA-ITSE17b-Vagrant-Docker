# Docker Workflow

# Theorie

Nun haben wir Docker auf unsere Windows Maschine eingerichtet und haben angeschaut was Container sind und was Docker ist. Nun wird euch erläutert was jedoch Docker genau tut.
In Docker fängt alles mit einem Image an. Ein Image beinhaltet alle Komponenten und Daten, welche benötigt wird um dies als Container auszuführen. Dies kann man sich am Besten vorstellen, wenn man Beispielsweise einen Apache Webserver früher auf einem System eingerichtet hat.
Dafür benötigte man bevor man den eigentlichen Dienst installieren konnte, ein Betriebsystem auf dem dann der Apache Webserver installiert wurde. Mit Docker wird dies viel einfacher. Wenn ich einen Apache Container betreiben möchte benötige ich lediglich ein Image. Wenn nun das Image ausgeführt wird, entsteht daraus ein Container. Die Operationen der Conatiner werden alle durch den Eigentlichen Host abgewickelt. In diesem Kurs wird dies von einer virtuellen Linux Maschine durchgeführt . Würde man jedoch Docker auf einer Linux Maschine einrichtn, würden die Operationen dann vom Linux Host ausgeführt werden. 

Wenn man einen Docker Image nimmt und diesen mit dem Befehl `docker run` auswühren würde, wird daraus ein laufender Container entstehen. In diesem Container werden ein oder mehrere Prozesse ausgeführt, welches "etwas tut".

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockerimageworkflow.PNG)

# Praxis

Vorhin haben wir Docker installiert. Daher befndet sich noch nichts im Zusemanhang mit Images und Container. Um das obenbeschriebene darzustellen wird folgendes durchgefphrt:

1) Terminal öffnen
2) Den Befehl `docker pull httpd`. Dieser Befehl installiert das Offiziele Docker Image von Apache. Das Image wird von Apache auf dem Docker Repository zur Verfügung (Docker Hub) gestellt.
3) Wenn man nun `docker images` eingibt, werden alle vorhanden Docker Images aufgelistet. Dieser Befehl listet under anderem auf wie das Repository dieses Images heisst, welchen Tag (Version) und welche Image ID für dieses Image generiert wurde.

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/docker_pull_list_image.PNG)