# Dockerfile

Bis jetzt wurden Docker Images und Container von Hand ausgeführt. Nun möchte man jedoch nicht dies immer von Hand machen und die Container anhand von Images automatisieren. Hier kommt das Dockerfile ins Spiel.
Das Dockerfile ist eine Datei,  in dem definiert werden kann, wie wie ein Contaier konfiguriert  und was alles mit installiert wird.
Hier geht es vor allem um die Automatisierung von Containern. Das Dockerfile ist ein von Docker definiertes Skript, welche gewisse Paramter für die Container und Sktipts definiert und diese beim Start des Skriptes ausgeführt wird.
Die Dockefiles werden mit dem Befehl `docker build -t Name .`. Der Punkt definiert Die Location des Dockerfiles und bedeutet, dass es sich im aktuellen Verzeichnis befindet, wo der Befehl ausgeführt wird. Jede Zeile, welche aus dem Dockerfile ausgeführt wird, erstellt ein Neues Image.
Jeder Schritt, welcher vom Dockerfile ausgeführt wird, wird gecached. Das spart sehr viel Zeit und Speicher. Wenn man Beispielsweise das Dockerfile anpassen würde, würde er nur die "Teilimages" aus dem Cache anpassen, welche auch wirklich verändert wurden.

FROM

MAINTAINER

ADD

COPY

RUN

ENV

USER

CMD

ENTRYPOINT

VOLUME

EXPOSE

ONBUILD


1) Als erstes wird auf dem Desktop das Verzeichnis DockerApache angelegt. In diesem Verzeichnis wird dann das File `Dockerfile` angelegt.
2) 
