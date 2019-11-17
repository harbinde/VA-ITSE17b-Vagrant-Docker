# Docker Image ausführen

Vorhin haben wir Docker installiert. Daher befndet sich noch nichts im Zusemanhang mit Images und Container. 
In diesem Abschnitt wird beschriebn wie man ein Image herunteläd und als Container ausführt.

1) Terminal öffnen
2) Den Befehl `docker pull httpd`. Dieser Befehl lädt aus dem Docker Hub das neuste Image herunter und installiert das Offiziele Docker Image von Apache. Das Image wird von Apache auf dem Docker Repository zur Verfügung (Docker Hub) gestellt.
3) Wenn man nun `docker images` eingibt, werden alle vorhanden Docker Images aufgelistet. Dieser Befehl listet under anderem auf wie das Repository dieses Images heisst, welchen Tag (Version) und welche Image ID für dieses Image generiert wurde.

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/docker_pull_list_image.PNG)

4) Möchte man das httpd Image starten so führt man den Befehl `docker run httpd:latest` aus. Man kann das Image auch mit der ID starten. dann würde dieser Befehl `docker run IMAGE_ID` lauten.
5) Das Image httpd benötigt gewisse Einstellungen, dass es auch ausgeführt wird. Deshalb habe ich noch das Ubuntu Image mit `docker pull ubuntu` heruntergeladen und danach gestartet. Möchte man nun auf den laufendem Container eine Verbindung aufbauen, so gibt man den Befehl `docker run -ti ubuntu -` oder `docker run -ti Image-ID` ausführen. Möchte man das Terminal schliessen so muss man CMD beenden. Mit `exit` kann jederzeit das Bash und der Container beendet werden.

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/docker_run.PNG)

6) Wenn man unter Windows nun Hyper-V Manager öffnet sieht man, dass die VM `DockerDesktopVM` exestiert. Auf dieser VM läuft Docker und die Container:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Docker/IMG/hyperv_dockervm.PNG)


## Docker run `PARAMETER` `IMAGE`

Der `docker run` Befhel ist der am häufigsten verwendete Docker Befehl und unterstütz sehr viele docker parametisierungen. Untenstehend werden die wichtigsten Befehle erläutert:

#### Docker Parameter

###### -ti:
* Startet das Image als Container und öffnet anschliessen das Bach (Terminal) des Containers

###### --name:
* Definiert den Namen & Hostname des Containers

###### --cpuset="0,1":
* Definiert die Anzahl CPU & Cores, welche dem Container zur verfügung steht

###### --cpu-shares="1024":
* Definiert die maximale CPU auslastung. Der Wert kann 0-1024 definiert werden. 0 bedeutet, dass der Container 100% der CPU ressourcen zur Verfügung hat. 

###### -m="512m":
* Definiert die Anzahl in MB der RAM, welche dem Container zur Verfügung steht.

###### --priviliged:
* Gibt dem dem User des Containers alle Rechte. Der User kann dan Beispielsweise auch änderungen der Netzwerkeinstellungen tätigen.

###### -P 80
* Docker definiert selbst das NAT auf dem Port 80 des Containers einen Dynamischen Port auf dem Host, welches freigegeben wird.

###### -p 80:8888
* Docker definiert das NAT mit dem Port 80 auf dem Container und leitet es dem Host auf dem Port 8888 weiter.

###### --link container1:container2
* Docker erlaubt die Kommunikation zweichen Contaiainer 1 und Container 2

##### -v C:LocationVonHost\Folder:/ContainerVolume
* Dieser Befehl definiert einen lokalen Ordner, welcher sich auf dem Host befindet und verlinkt diesen auf dem Container. Hier werden die Verzeichnisse und Files jeweils synchronisiert.

##### 

#### Docker container update

Möchte man auf einem bereits erstellen Container eine Anpassung vornehmen kann man dies mit `docker update CONTAINER PARAMETER` machen.

#### Docker Images löschen

Mit dem Befehl `docker rmi IMAGE` kann man die Image(s) entfernen



