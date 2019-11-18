# Einleitung 

Die Virtualisierung Technologie ist eine starke Technologie, welche verschiedene Use Cases hat.
Diese werden in der Regel von Entwickler und System Engineers verwendet, um virtuelle Maschinen in isolierten Sandboxen zu entwickeln bzw. zu betreiben.
Grund für diese Technologie ist das Ersparnis von Hardwareanforderungen / Hardwareersparnis und für Testumgebungen.
Das Verwalten von vielen virtuellen Maschinen ist in der Regel sehr einfach, solange nicht viele Maschinen existieren.
Sobald jedoch die Anzahl der virtuellen Maschinen wächst, wird dies in der Regel nicht die Verwaltung erleichtern.
Auf dem Markt gibt es viele Produkte, welche das Erstellen und die Betreuung der Virtuellen Maschinen ermöglichen.
Jedes System hat eine eigene Verwaltungssoftware und proprietäre Datenformate. Dies macht diese Thematik nicht ganz einfach. Doch was wäre jedoch, wenn ein Command Line Progam alle  VM's ausführen und verwalten könnte für nahezu alle Hypervisors? Die Frage ist es ganz zu einfach zu beantworten. Die Lösung für dieses Problem heisst Vagrant.
Für die Vertiefungsarbeit habe ich mich mit der Software ausgiebig befasst undversuchee euch die wichtigsten Funktionen von Vagrant zu erläutern.

In diesem Kurs werden folgende Featureerläutertrt:

* Das Erstellenen einer VM mit Vagrant

* Die Verwaltung von VM's mit Vagrant

* Die Synchronisation von freigegeben Verzeichnisse

* Providers

* Provisioners

* Deployment von Multi-machines mit Vagrant

* Verwaltung von Repositories (Vagrant Cloud)

## Was du wissen solltest

Das ist ein Kurs für Anfänger. Deshalb benötigst du noch keine Erfahrung mit Vagrant.
Es wäre jedoch für diesen Kurs Hilfreich, wenn für dich folgende Dinge kein Fremdwort sind:

* Basiswissen in TCP/IP und DNS

* Hypervisor (VirtualBox)

* Linux Kommandos

* Visual Studio Code (nicht erforderlich, jedoch empfohlen)

## Was du benötigst

Für diesen Kurs wird ein Windows Rechner verwendet. Vagrant wird jedoch auch für aBetriebssystemeysteme unterstützt.

Es wird empfohlen, dass dein Rechner mindesten 8 GB RAM verfügt und einen Prozessor, welchVirtualisierungstechnologieologie (Intel VT-X oder ADM-V). Als Hypervisor wird VirtualBox verwendet. Dieser kann unter https://www.virtualbox.org/wiki/Downloads heruntergeladen und installiert werden. In diesem Kurs werden oftmals Vagrant-Files bearbeHierfürerführ kann jeder Texteditor verwendet werden. Für diesen Kurs wird jedoch VStudioStuido Code verwendet werden. Visual Studio Code kann unter https://code.visualstudio.com/dowheruntergeladeneladen und installiert werden.
