# Vagrant Box zurücksetzten
Vagrant bietet die Funktion an, eine Vagrant Box zurückzusetzen. Dies macht Beispielsweise dann Sinn, wenn man eine VM ruiniert hat und die ursprüngliche Box (Initial State) wieder haben möchte.

1) Den Befehl `vagrant destroy` eingeben. Dieser Befehl wird alle Ressourcen, welche mit der Box in Verbindung steht. Das Vagrantfile wird jedoch beibehalten. Mit `y` wird danach bestätigt, dass die Box zertört werden darf.
2) Nun kann man wieder `vagrant up` ausführen. Die Ubuntu Box wird vom Chache wieder importiert und danach wieder gestartet.
