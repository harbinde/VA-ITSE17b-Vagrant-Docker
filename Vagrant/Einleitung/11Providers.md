# Providers
Vagrant Providers erlaubt es für eine Box einen Hypervisor zu definieren. Standardmässig unterstütz Vagrant die Hypervisor VirtualBox von Oracle und Hyper-V von Microsoft. Ausserdem besteht die Möglichkeit mit Vagrant Doker Container zu erstellen. Es besteht auch die Möglichkeit VMWare Providers zu definieren. Dieses Modul ist jedoch kostenpflichtig. Der Provider wird wie die anderen Einstellungen im Vagrantfile definiert. Ausserdem können die CPU's und Memorys angepasst werden. Nun wird auf der Box überprüft wie viel CPU's und RAM zur Verügung stehen.
 
1) Eine SSH-Connection mit der Box starten
2) Den Befehl `vmstat -s` eingeben. Folgende Werte werden ausgegeben:
```bash
vagrant@vagrant-ubuntu-trusty-64:~$ vmstat -s
       501576 K total memory
       .... nicht die vollständige Ausgabe
```
3) Man sieht, dass die
