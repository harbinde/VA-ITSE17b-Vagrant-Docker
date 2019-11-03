# Einen lokalen Ordner mit Vagranr auf der VM synchronisieren.
Die Meisten Hypervisor bieten die Funtkion an einen Ordner, welche sich auf dem loaken Maschine befindet mit der VM zu synchronisieren.
Das bedeutet, dass alle Daten auch via VM zugänglich wären. Für diesen Schritten nutzen wir dar Projekt "Vagrant_Hello".

1) Im Verzeichnis "Vgarant_Hello" wird der Ordner "share" erstellt der einem leeren Textdokument (test.txt).
2) Das Vagrantfile bearbeiten
3) Den werte `# config.vm.synced_folder "../data", "/vagrant_data"` auskomentieren und durch folgende Werte ersetzen:
- `config.vm.synced_folder "share", "/share"`.
4) Das Vagrantfile speichern.
5)
