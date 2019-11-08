# Providers
Vagrant Providers erlaubt es für eine Box einen Hypervisor zu definieren. Standardmässig unterstütz Vagrant die Hypervisor VirtualBox von Oracle und Hyper-V von Microsoft. Ausserdem besteht die Möglichkeit mit Vagrant Doker Container zu erstellen. Es besteht auch die Möglichkeit VMWare Providers zu definieren. Dieses Modul ist jedoch kostenpflichtig. Der Provider wird wie die anderen Einstellungen im Vagrantfile definiert. Ausserdem können die CPU's und Memorys angepasst werden. Nun wird auf der Box überprüft wie viel CPU's und RAM zur Verügung stehen.
 
1) Eine SSH-Connection mit der Box starten
2) Den Befehl `vmstat -s` eingeben. Folgende Werte werden ausgegeben:
```bash
vagrant@vagrant-ubuntu-trusty-64:~$ vmstat -s
       501576 K total memory
       205272 K used memory
       122900 K active memory
        45868 K inactive memory
       296304 K free memory
        11816 K buffer memory
        75948 K swap cache
            0 K total swap
            0 K used swap
            0 K free swap
          862 non-nice user cpu ticks
            0 nice user cpu ticks
          789 system cpu ticks
       225036 idle cpu ticks
           40 IO-wait cpu ticks
            0 IRQ cpu ticks
           16 softirq cpu ticks
            0 stolen cpu ticks
        98753 pages paged in
         1952 pages paged out
            0 pages swapped in
            0 pages swapped out
        62168 interrupts
       160187 CPU context switches
   1573206634 boot time
         1982 forks
```

