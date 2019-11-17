# Veränderungen von Images und Container auslesen
Mit Docker kann man die Veränderungen der Images und Container abrufen.

## Container

1) Terminal öffnen
2) Mit `docker ps -a` die Container ID des gewünschten Containers kopieren
3) Mit `docker diff 88b591ae6ac` werden 

## Images

1) Terminal öffnen
2) Mit `docker images` die Image ID des gewünschten Image kopieren
3) Mit `docker history 63d7368967d8` werden Änderungen der Images dargestellt:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockerhistory.PNG)

