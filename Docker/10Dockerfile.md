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


1) Als erstes wird auf dem Desktop das Verzeichnis Dockerfile angelegt. In diesem Verzeichnis wird dann das File `Dockerfile` angelegt.
2) Es wird die Datei default erstellt. Das ist die Config-Datei des Nginx Servers:
```BASH
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
        #       proxy_pass http://127.0.0.1:8080;
        #}

        #error_page 404 /404.html;

        # redirect server error pages to the static page /50x.html
        #
        #error_page 500 502 503 504 /50x.html;
        #location = /50x.html {
        #       root /usr/share/nginx/html;
        #}

        # pass the PHP scripts to FastCGI server listening on 127.0.0.1:9000
        #
        #location ~ \.php$ {
        #       fastcgi_split_path_info ^(.+\.php)(/.+)$;
        #       # NOTE: You should have "cgi.fix_pathinfo = 0;" in php.ini
        #
        #       # With php5-cgi alone:
        #       fastcgi_pass 127.0.0.1:9000;
        #       # With php5-fpm:
        #       fastcgi_pass unix:/var/run/php5-fpm.sock;
        #       fastcgi_index index.php;
        #       include fastcgi_params;
        #}

        # deny access to .htaccess files, if Apache's document root
        # concurs with nginx's one
        #
        #location ~ /\.ht {
        #       deny all;
        #}
}
```
 
3) Das Dockerfile wird folgendermassen bearbeitet:
```Dockerfile
#Definiert, welches Image verwendet werden soll
FROM ubuntu
#Definiert den Author des Dockerfiles
MAINTAINER Harbin Dehari <harbin@dehari.ch>

#RUN Befehle fuehren auf dem Container Befehle durch.
# In diesem Beispiel werden die Installations  Libaries aktualisiert und anschliessend Nginx installiert
RUN apt-get update -y
RUN apt-get install nginx -y
RUN apt-get install nano -y
#Kopiert die Datei default, welche sich auf dem Host in das Verzeichnis des Containers
ADD default /etc/nginx/sites-available/default
RUN service nginx restart

```
4) Nun wird aus dem Dockerfile mit `docker build -t nginxv1` ein Image erstellt:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/dockerbuild.PNG)

