# Einleitung 
Die Virttualisierungs Technlogie ist starke Technlogie, welche verschiedene Use-Cases hat.
Diese werden in der Regel von Entwickler und System engineers verwendet, um virtuelle Maschinen in issolierten Sandobex zu entwicken bzw. zu betreiben.
Grund für diese Technlogie ist das Erspirnis von Hardwareanforderungen / Hardwareersparnis und für Testumgebungen.
Das verwalten von vielen virtuellen Maschinen ist in der Regel sehr einfach, solange nicht viele Maschinen exestieren.
Sobald jedoch die Anzahl der virtuellen Maschinen wächst, wird dies in der Regel nicht die Verwaltung errleichtern.
Auf dem Markt gibt es viele Produkte, welche das Erstellen und die Betreung der Virtuellen Maschinen ermöglichen.
Jedes System hat eine eigene Verwaltungssoftware und propritäre Datenformate. Dies macht diese Thematik nicht ganz einfach. Doch was wäre jedoch, wenn ein Command Line Progam alle  VM's ausführen und verwalten könnte für nahezu alle Hypervisors? Die Frage ist es ganz zu einfach zu beantworten. Die Lösung für dieses Problem heisst Vagrant.

Für die Vertiefungsarbeit habe ich mich mit dies Software ausgiebig befasst und verusche euch die wichtigsten Funktionen von Vagrant zu erläutern.

In diesem Kurs werden folgende Features erläuert:
* Das erstellen einer VM mit Vagrant
* Die Verwaltung von VM's mit Vagrant
* Die Synchronisation von freigegeben Verzeichnisse
* Providers
* Provisioners
* Deployment von Multi-machines mit Vagrant
* Verwaltung von Repositories (Vagrant Cloud)

## Was du wissen solltest

Das ist ein Kurs für Beginner. Deshalb benötisgt du noch keine Erfahrung mit Vagrant.
Es wäre jedoch für diesen Kurs Hilfreich, wenn für dich folgende Dinge kein Fremdwort sind:

* Basiswissen in TCP/IP und DNS
* Hypervisor (VirtualBox)
* Linux Kommandos
* Visual Studio Code

## Was du benötigst
Für diesen Kurs wird ein Windows Rechner verwendet. Vagrant wird jedoch auch für andere Betriebsysteme unterstützt.
Es wird empfohlen, dass dein Rechner mindesten 8 GB RAM verfügt und einen Prozessor, welche die Virtualisierung unterstütz (Intel VT-X oder ADM-V). Als Hypervisor wird VirtualBox verwendet. Dieser kann unter https://www.virtualbox.org/wiki/Downloads heruntergeladen und installiert werden. Für Windows 
