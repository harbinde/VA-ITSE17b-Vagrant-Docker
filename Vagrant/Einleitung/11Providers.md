# Providers

#### -------------------------------------------------------------------------
#### Kursmaterial: (https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/tree/master/Vagrant/Einleitung/Kursmaterial/11Providers)
#### -------------------------------------------------------------------------

Vagrant Providers erlaubt es für eine Box einen Hypervisor zu definieren. Standardmässig unterstütz Vagrant die Hypervisor VirtualBox von Oracle und Hyper-V von Microsoft. Ausserdem besteht die Möglichkeit mit Vagrant Doker Container zu erstellen. Es besteht auch die Möglichkeit VMWare Providers zu definieren. Dieses Modul ist jedoch kostenpflichtig. Der Provider wird wie die anderen Einstellungen im Vagrantfile definiert. Ausserdem können die CPU's und Memorys angepasst werden. Nun wird auf der Box überprüft wie viel CPU's und RAM zur Verügung stehen.
 
1) Eine SSH-Connection mit der Box starten
2) Den Befehl `vmstat -s` eingeben. Folgende Werte werden ausgegeben:
```bash
vagrant@vagrant-ubuntu-trusty-64:~$ vmstat -s
       501576 K total memory
       .... nicht die vollständige Ausgabe
       Man sieht, das ca. 512 MB zur Verfügung stehen
```
3) Den Befehl `lscpu` eingeben. Folgende Werte werden ausgegeben:
```bash
vagrant@vagrant-ubuntu-trusty-64:~$ lscpu
Architecture:          x86_64
CPU op-mode(s):        32-bit, 64-bit
Byte Order:            Little Endian
CPU(s):                1
On-line CPU(s) list:   0
Thread(s) per core:    1
Core(s) per socket:    1
Socket(s):             1
NUMA node(s):          1
Vendor ID:             GenuineIntel
CPU family:            6
Model:                 142
Stepping:              12
CPU MHz:               1799.701
BogoMIPS:              3599.40
L1d cache:             32K
L1i cache:             32K
L2 cache:              256K
L3 cache:              6144K
NUMA node0 CPU(s):     0
       Man sieht, das ein Prozeror mit einem Kern zur Verfügung steht.
```
4) Möchte man die CPU und Memory Einstellungen der Box ändern kann man dies im Vagrantfile definieren. Damit CPU und RAM angepasst werden kann, muss zwingend der der "Providers Teil" auskommenteirt werden:
```ruby
config.vm.provider "virtualbox" do |vb|
  #   # Display the VirtualBox GUI when booting the machine
  #   vb.gui = true
  #
  #   # Customize the amount of memory on the VM:
  #   vb.memory = "1024"
  end

```
5) Mit dem Wert `vb.memory = "1024"` wird der Box 1GB RAM zugewiesen
6) Mit dem Wert `vb.cpus = "2"` wird der Box 2 CPU's zugewiesen
7) Die Box mit `vagrant reload` neustarten
8) Nun kann man mit den Befehle `vmstat -s` & `lscpu` überprüfen, ob die Einstellugen übernommen wurden
   
