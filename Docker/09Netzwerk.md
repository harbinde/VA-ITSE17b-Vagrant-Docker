# Netzwerke mit Docker verwalten

Mit Docker kann man Netzwerke erstellen und den Container zuweisen. Standarmässig gibt es drei Netzwerkeinstellungen:
* Host: Der Container ist via IP des Host erreichbar. Es ist viel effizienter als die Bridge, da nichts weitergeleitet werden muss.
* Bridge: Der Contairer kann nur mit anderen Container kommunizieren. Möchte man dass man vom Netzwerk darauf zugrff hat, muss man eine Portmapping duchführen.
* None: Der Container ist mit keinem Netzwerk verbunden und ist daher komplett isoliert. Es bietet daher den grössten Schutz

## Neues Netzwerk erstellen

* `docker network create --subnet 172.20.0.0/16 --ip-range 172.20.240.0/20 docnet`

## Container zu einem Netzwerk zuweisen:

* `docker network connect docnet CONTAINERID`

## Container von einem einem Netzwerk entfernen:

* `docker network disconnect docnet CONTAINERID`

### Webserver Container via Netzwerk zugänglich machen

1) Terminal öffen
2) Den Befehl `docker run -ti --network host --name nginx` eingeben. Es öffnet sich nun das Terminal
3) Mit `apt-get update` & `apt-get install nginx -y` wird nginx eingerichtet. Standardmässig verwendet Nginx den Port 80. Auf meinem Docker Host war dieser schon vergeben. Deshalb wurde bei mit der Port auf 8888 umgestellt werden. Dies geschiet mit `nano /etc/nginx/sites-available/default` und ändert die Portseinstellungen auf `8888`. Wenn man nun auf dem Webserver die Host-IP eingibt sollte der Nginx-Webserver aufgerufen werden:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockernetnginx.PNG)
