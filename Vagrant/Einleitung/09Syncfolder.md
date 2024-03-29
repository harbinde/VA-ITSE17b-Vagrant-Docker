# Einen lokalen Ordner mit Vagrant auf der VM synchronisieren.
#### -------------------------------------------------------------------------
#### Kursmaterial: (https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/Kursmaterial/09SyncedFolder/)
#### -------------------------------------------------------------------------

Die Meisten Hypervisor bieten die Funktion an einen Ordner, welche sich auf dem lokalen Maschine befindet mit der VM zu synchronisieren.
Das bedeutet, dass alle Daten auch via VM zugänglich wären. Für diesen Schritten nutzen wir dar Projekt "Vagrant_Hello".

1) Im Verzeichnis "Vgarant_Hello" wird der Ordner "share" erstellt der einem leeren Textdokument (test.txt).
2) Das Vagrantfile bearbeiten
3) Den werte `# config.vm.synced_folder "../data", "/vagrant_data"` auskommentieren und durch folgende Werte ersetzen:
- `config.vm.synced_folder "share", "/share"`.
4) Das Vagrantfile speichern.
5) Die VM Muss nun neugestartet werden, damit die Einstellungen des Vagrantfiles übernommen werden. Dies geschieht mit dem Befehl `vagrant reload`.
6) Mit `vagrant ssh` wird eine SSH Connection zur VM aufgebaut angezeigt:

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_synced_share.JPG)

8) Wechselt man nun mit `cd /vagrant/share` und gibt `ls` ein, sieht man Testfile "test.txt", welches vorhin auf der Windows Maschine erstellt wurde: 

![alt text](https://github.com/harbinde/VA-ITSE17b-Vagrant-Docker/blob/master/Vagrant/Einleitung/IMG/vagrant_synced_share_textfile.JPG)
