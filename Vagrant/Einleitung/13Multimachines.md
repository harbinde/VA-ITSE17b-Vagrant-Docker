# Multi-Machines mit Vagrant erstellen

#### -------------------------------------------------------------------------
#### Kursmaterial: (https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/tree/master/Vagrant/Einleitung/Kursmaterial/13Multimachines)
#### -------------------------------------------------------------------------

Wir haben bis jetzt jeweils nur eine Vagrant Box automatisiert. Vagrant unterstützt jedoch auch, dass man mit nur einem Vagrantfile gleich mehrere Virtuelle Maschinen erstellen kann.
Dies macht Beispielsweise dann Sinn, wenn man eine Testumgebung benötigt, wo man den Service in verschieden Tiers teilen möchte, indem man auf einer Box einen Webserver einrichtet und auf der andere Box eine Datenbank betreibt.

1) In unserem Projekt `Vagrant_Hello` wurde schon eine eine Apache Webserver automatisiert. Nun möchten wir eine zusätzliche Box ausrollen. In diesem Fall habe ich mich für Nginx entschieden. Es kann jedoch auch Beispielsweise eine Datenbank eingerichtet werden.
2) Vagrantfile öffnen
3) Alle zusätzliche Statements, welche bis jetzt hinzugefügt wurden werden mit "#" wieder kommentiert.
4) Eine zusätzliche Box muss sich unterhalb des Statesments `Vagrant.configure("2") do |config|` befinden. Nun werden folgedene Statements hinzugefügt:
```ruby
# -*- mode: ruby -*-
# vi: set ft=ruby :
Vagrant.configure("2") do |config|
config.vm.define "nginx" do |nginx|
  nginx.vm.box = "ubuntu/trusty64"
  nginx.vm.provider "virtualbox" do |vb|
  vb.memory = "512"
  vb.cpus = "1"
  end
  nginx.vm.network "private_network", ip: "10.62.117.70" 
  nginx.vm.network "forwarded_port", guest: 80, host: 7777, host_ip: "127.0.0.1"
  nginx.vm.provision "shell", path: "installer/install_nginx.sh"
  end

config.vm.define "apache" do |apache|
  apache.vm.box = "ubuntu/trusty64"
  apache.vm.provider "virtualbox" do |vb|
  vb.memory = "512"
  vb.cpus = "1"
  end
  apache.vm.network "private_network", ip: "10.62.117.71" 
  apache.vm.network "forwarded_port", guest: 80, host: 8888, host_ip: "127.0.0.1"
  apache.vm.provision "shell", path: "installer/install_nginx.sh"
  end

  config.vm.box = "ubuntu/trusty64"
end
```

5) Eine Box wird immer mit config.vm.definie "BOXNAME" |BOXNAME| definiert. Wenn man nun für diese Box Beispielsweise eine eine IP zuweisen möchte, so gibt man vor den Statements noch den Boxnamen ein (`BOXNAME.vm.network "private_network", ip: "X.X.X.X" `)
6) Mit `vagrant up` werden die Boxen eingerichtet
7) Nun kann man mit dem Web-Browser die Adressen http://127.0.0.1:7777 und http://127.0.0.1:8888 aufrufen. Es wurden nun zwei Vagrant Boxen ausgerollt:
