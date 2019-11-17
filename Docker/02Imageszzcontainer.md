# Docker Workflow

Nun haben wir Docker auf unsere Windows Maschine eingerichtet und haben angeschaut was Container sind und was Docker ist. Nun wird euch erläutert was jedoch Docker genau tut.
In Docker fängt alles mit einem Image an. Ein Image beinhaltet alle Komponenten und Daten, welche benötigt wird um dies als Container auszuführen. Es ist Portabel und kann jederzeit auf andere Dockerumgebungen verschoben werden. Dies kann man sich am Besten vorstellen, wenn man Beispielsweise einen Apache Webserver früher auf einem System eingerichtet hat.
Dafür benötigte man bevor man den eigentlichen Dienst installieren konnte, ein Betriebsystem auf dem dann der Apache Webserver installiert wurde. Mit Docker wird dies viel einfacher. Wenn ich einen Apache Container betreiben möchte benötige ich lediglich ein Image. Wenn nun das Image ausgeführt wird, entsteht daraus ein Container, welecher nur bis zum Ende der Laufzeit exestiert. Würde man den Container ausschaulten, wären alle Daten/Änderungen verloren gehen, welche im Container angepasst wurden.
Es ist sogar möglioch eine Momentaufnahme der Container zu erstellen. Dabei wird auch ein Image erstellt, welche den aktuellen Zustand festhält.Damit man verschiedene Momentaufnahmen von Images machen kann gibt es hierführ die Versionierung. 
Die Operationen der Conatiner werden alle durch den Eigentlichen Host abgewickelt. In diesem Kurs wird dies von einer virtuellen Linux Maschine durchgeführt . Würde man jedoch Docker auf einer Linux Maschine einrichtn, würden die Operationen dann vom Linux Host ausgeführt werden. 

Wenn man einen Docker Image nimmt und diesen mit dem Befehl `docker run` auswühren würde, wird daraus ein laufender Container entstehen. In diesem Container werden ein oder mehrere Prozesse ausgeführt, welches "etwas tut".

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockerrmimage.PNG)
