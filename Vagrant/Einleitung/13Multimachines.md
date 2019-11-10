# Multi-Machines mit Vagrant erstellen

Wir haben bis jetzt jeweils nur eine Vagrant Box automatisiert. Vagrant unterstützt jedoch auch, dass man mit nur einem Vagrantfile gleich mehrere Virtuelle Machines erstellen kann.
Dies macht Beispielsweise dann Sinn, wenn man eine Testumgebung benötigt, wo man den Service in verschieden Tiers teilen möchte, indem man auf einer Box einen Webserver einrichtet und auf der andere Box eine Datenbank betreibt.

1) In unserem Projekt `Vagrant_Hello` wurde schon eine eine Apache Webserver automatisiet. Nun möchten wir eine zusätzlie Box ausrollen. In diesem Fall habe ich mich für Nginx entschieden. Es kann jedoch auch Beispielsweise eine Datenbank eingerichtet werden.
2) Vagrantfile öffnen
3) Alle zusätlichen Statements, welche bis jetzt hinzugefügt wurden werden mit "#" wieder kommentiert.
4) Eine zusätzliche Box muss sich unterhalb des Statesments `Vagrant.configure("2") do |config|` befinden. Nun werden folgedene Statements hinzugefügt:
```ruby

# -*- mode: ruby -*-
# vi: set ft=ruby :

Vagrant.configure("2") do |config|

config.vm.define "nginx" do |nginx|
  nginx.vm.box = "ubuntu/trusty64"
  nginx.vm.provider "virtualbox" do |vb|
  vb.memory = "512"
  vb.cpus = "2"
  end
  nginx.vm.network "private_network", ip: "192,168.0.71" 
  nginx.vm.network "forwarded_port", guest: 80, host: 7777, host_ip: "192.168.0.71"
  nginx.vm.provision "shell", path: "installer/install_nginx.sh"
  end

  config.vm.define "apache2" do |apache2|
  apache2.vm.box = "ubuntu/trusty64"
  apache2.vm.provider "virtualbox" do |vb|
  vb.memory = "512"
  vb.cpus = "2"
  end
  apache2.vm.network "private_network", ip: "192,168.0.71" 
  apache2.vm.network "forwarded_port", guest: 80, host: 8888, host_ip: "192.168.0.71"
  apache2.vm.provision "shell", path: "installer/install_apache2.sh"
  end
  
  config.vm.box = "ubuntu/trusty64"

end


```
