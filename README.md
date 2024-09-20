# Installation des Projekts
### Klonen des Repositories
Um ein GitHub-Repository zu klonen, muss man zuerst die Repository-URL über den Code-Button auf GitHub kopieren. Dann muss man ein Terminal öffnen und in das gewünschte Verzeichnis navigieren. Anschließend muss man den Befehl ```git clone repository-url```ausführen. Bei der Nutzung von SSH muss man sicherstellen, dass der SSH-Schlüssel korrekt eingerichtet ist.
### Installation der notwendigen Pakete
Als erstes geht man in ein Terminal und gibt dort den Befehl ```docker init``` ein. Dann werden einige Abfragen gemacht die man folgendermassen beantworten muss: 
```text
? What application platform does your project use? Node
? What version of Node do you want to use? 18.0.0
? Which package manager do you want to use? npm
? What command do you want to use to start the app: node src/index.js
? What port does your server listen on? 3000
```
### Docker-Konfiguration und -Installation
Man muss Docker Desktop von der offiziellen [Docker-Website](https://docs.docker.com/desktop/install/windows-install/) herunterladen und installieren, egal ob auf Windows oder macOS. Optional installiert man Docker Compose, um mehrere Container-Dienste effizient zu verwalten.
Zur Überprüfung muss man ```docker run hello-world``` ausführen. Container lassen sich mit ```docker run -d -p 80:80 nginx```starten. Für eigene Container erstellt man eine Dockerfile und baut das Image mit ```docker build```.
### Starten der Applikation in einem Docker-Container
Um die Applikation in einem Docker-Container zu starten muss man wieder ein Terminal öffnen und den Befehl ```docker compose up --build``` eingeben. Dann ist die Applikation schon einmal gestartet. Es könnte bei diesem Schritt zu einem ERROR führen! Man sollte dann Docker deinstallieren und dann noch einmal Installieren doch diesmal das ganze als Admin öffnen. Falls das auch nicht gehen sollte kann man auch anstatt den Befehl ```docker compose up --build``` den Befehl ```docker compose up --build --force-recreate``` verwenden. Das sollte den ERROR beheben, weil das Programm solange wartet bis alle Dateien implementiert wurden und dann startet es erst. Doch momentan sieht man noch nicht wie das ganze im Frontend aussieht. Dazu müssen wir nur noch folgenden [Link](http://localhost:3000/) aufrufen. Um die Applikation dann wieder zu stoppen kann man einfach den Befehl ```docker compose down``` eingeben und die Applikation wird gestoppt.
