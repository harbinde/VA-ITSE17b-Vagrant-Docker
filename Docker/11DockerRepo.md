# Docker Repositories

Docker Images können wie schon beschrieben anhand von einem Image importiert oder von einem Dockerfile nachgebaut werden. In diesem Abschnitt wird erklärt wie Image auf Docker Hub zur Verfügung gestellt werden kann. Das Image kann man unter https://hub.docker.com/r/harbind/nginxv1 einsehen.

1) https://hub.docker.com/ aufrufen und einen kostenlosen Account erstellen
2) Auf dem Docker Host den Befehl 'docker login' ausführen und sich mit dem Docker Hub Account anmelden.
3) Nun sucht man mit 'docker images' die Image ID des Images, welche man zur Verfügung stellen möchte
4) Das Image wird mit dem Befehl 'docker tag 60f3df0b3c77 harbind/nginxv1:latest' mit dem Hub verknüpft. Nun exestiert das Repo. Das Image jedoch hingegen nicht. Mit 'docker push harbind/nginxv1' wird das Image auf das Repo hochgeladen:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockerrepo3.PNG)

5) Für Testzwecke wurde das Image auf meinem Docker Host entfernt. Nun wird mit 'docker pull harbind/nginxv1:latest' das aktuelle Image heruntergeladen und dann mit 'docker run --net host harbind/nginxv1:latest' als Container ausgeführt. Der Nginx Webserver sollte via Docker Host IP erreichbar sein:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockerrepo4.PNG)

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockerrepo5.PNG)
