# Dockerfile

#### -------------------------------------------------------------------------
#### Kursmaterial: (https://wan.dehari.ch:5001/sharing/E73qXA4bT)
#### -------------------------------------------------------------------------

Bis jetzt wurden Docker Images und Container von Hand ausgeführt. Nun möchte man jedoch nicht dies immer von Hand machen und die Container anhand von Images automatisieren. Hier kommt das Dockerfile ins Spiel.
Das Dockerfile ist eine Datei, in dem definiert werden kann, wie  ein Container konfiguriert und was alles mit installiert wird.
Hier geht es vor allem um die Automatisierung von Containern. Das Dockerfile ist ein von Docker definiertes Skript, welche gewisse Parameter für die Container und Skripts definiert und diese beim Start des Skriptes ausgeführt wird.
Die Dockefiles werden mit dem Befehl 'docker build -t Name .'. Der Punkt definiert die Location des Dockerfiles und bedeutet, dass es sich im aktuellen Verzeichnis befindet, wo der Befehl ausgeführt wird. Jede Zeile, welche aus dem Dockerfile ausgeführt wird, erstellt ein neues Image.
Jeder Schritt, welcher vom Dockerfile ausgeführt wird, wird gecached. Das spart sehr viel Zeit und Speicher. Wenn man Beispielsweise das Dockerfile anpassen würde, würde er nur die "Teilimages" aus dem Cache anpassen, welche auch wirklich verändert wurden.

## Nginx Image mithilfe eines Dockerfile ausführen

1) Als Erstes wird auf dem Desktop das Verzeichnis Dockerfile angelegt. In diesem Verzeichnis wird dann das File 'Dockerfile' angelegt.
2) Es wird die Datei default erstellt. Das ist die Config-Datei des Nginx Servers:

```sh
server {
listen 8888 default_server;
listen [::]:8888 default_server ipv6only=on;

root /usr/share/nginx/html;
index index.html index.htm;

# Make site accessible from http://localhost/
server_name localhost;

location / {
# First attempt to serve request as file, then
# as directory, then fall back to displaying a 404.
try_files $uri $uri/ =404;
# Uncomment to enable naxsi on this location
# include /etc/nginx/naxsi.rules
}

# Only for nginx-naxsi used with nginx-naxsi-ui : process denied reques$
#location /RequestDenied {
# proxy_pass http://127.0.0.1:8080;
#}

#error_page 404 /404.html;

# redirect server error pages to the static page /50x.html
#
#error_page 500 502 503 504 /50x.html;
#location = /50x.html {
# root /usr/share/nginx/html;
#}

# pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
#
#location ~ \.php$ {
# fastcgi_split_path_info ^(.+\.php)(/.+)$;
# # NOTE: You should have "cgi.fix_pathinfo = 0;" in php.ini
#
# # With php5-cgi alone:
# fastcgi_pass 127.0.0.1:9000;
# # With php5-fpm:
# fastcgi_pass unix:/var/run/php5-fpm.sock;
# fastcgi_index index.php;
# include fastcgi_params;
#}

# deny access to .htaccess files, if Apache's document root
# concurs with nginx's one
#
#location ~ /\.ht {
# deny all;
#}
}
```

3) Das Dockerfile wird folgendermassen bearbeitet:
'''sh
#Definiert, welches Image verwendet werden soll
FROM ubuntu
#Definiert den Author des Dockerfiles
MAINTAINER Harbin Dehari <harbin@dehari.ch>

#RUN Befehle fuehren auf dem Container Befehle durch.
#In diesem Beispiel werden die Installations Libaries aktualisiert und anschliessend Nginx installiert
RUN apt-get update -y
RUN apt-get install nginx -y
RUN apt-get install nano -y
#Kopiert die Datei default, welche sich auf dem Host in das Verzeichnis des Containers
ADD default /etc/nginx/sites-available/default
RUN service nginx reload

'''
4) Nun wird aus dem Dockerfile mit 'docker build -t nginxv1' ein Image erstellt:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockerbuild.PNG)

5) Mit 'dockr run -ti --net host --name nginxcontainer nginxv1' wird das Image als Container gestartet und ins Host netzwerk hinzugefügt. Nun kann auf mit dem Web-Browser überpüft werden, ob dieser via HOST IP zu erreichen ist:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockernetnginx.PNG)

## Dockefile Befehle

##### FROM IMAGE:
* Definiert das Image welches vom Docker Hub genommen werden soll

##### MAINTAINER NAME SURNAME <mail@mail.com>:

* Definiert den Author des Dockerfile
##### COPY file /locantion/file:
* Koppiert ein File vom Host zum Container Verzeichnis

##### ADD file.tar /location/:
* Koppiert auch ein File vom Host zum Container Verzeichnis. Kommt jedoch mit der Zusatzfunktion, dass kopmrimierte Verzeichnise automatisch entpackt und kopiert werden. Es unterstützt auch URL's.

##### RUN SHELL Befehl:
* Führt einen Shell Befehl aus

##### ENV Variable=WERT
* Hier können Variablen definiert werden, welche Beispielsweise mit den RUN Befehlen ausgeführt werden.

##### VOLUME "C:\HostLocation" "/container/location"
* Richtet einen Shared Volume ein, welcher mit dem Host synchronisiert.

##### EXPOSE 8080
* Definiert das Port Mapping für Port 8080 auf beiden Seiten

##### User Harbin
* Definiert einen User, welcher auf dem Container sich dann befindet

Weitere Dockerfile Befehle können unter https://docs.docker.com/engine/reference/builder/ eingesehen werden.
