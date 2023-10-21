Docker Cheat Sheet:

| Erklärung | Befehle |
| --- | --- |
| Docker Version überprüfen | docker --version |
| Docker-Informationen anzeigen | docker info |
| Container erstellen und ausführen | docker \<image\_name\> |
| Container anzeigen | docker ps |
| Alle Container anzeigen (auch gestoppte) | docker ps -a |
| Container stoppen | docker stop \<container\_id\> |
| Container starten | docker start \<container\_id\> |
| Container löschen | docker rm \<container\_id\> |
| Images anzeigen | docker images |
| Images löschen | docker rmi \<image\_name\> |
| Container mit Namen erstellen | docker run --name \<container\_name\> \<image\_name\> |
| Container interaktiv ausführen | docker run -it \<image\_name\> /bin/bash |
| Container Ports weiterleiten | docker run -p \<host\_port\>:\<container\_port\> \<image\_name\> |
| Container Ordner mounten | docker run -v \<host\_path\>:\<container\_path\> \<image\_name\> |
| Container Umgebungsvariablen setzen | docker run -e \<variable\_name\>=\<value\> \<image\_name\> |
| Container Logs anzeigen | docker logs \<container\_id\> |
| Interaktiven Modus verlassen (ohne Container zu stoppen) | Ctrl + P, Ctrl + Q |
| Docker Image erstellen (Dockerfile im aktuellen Verzeichnis verwenden) | docker build -t \<image\_name\> . |
| Docker Image mit Dockerfile erstellen | docker build -t \<image\_name\> \<path\_to\_dockerfile\> |
| Docker Image von Docker Hub herunterladen | docker pull \<image\_name\> |
| Docker Image mit Tag erstellen | docker build -t \<image\_name\>:\<tag\> . |
| Docker Compose konfiguriertes Setup ausführen | docker compose up |
| Docker Compose im Hintergrund ausführen | docker compose up -d |
| Docker Compose Stoppen | docker compose down |
| Docker Compose Logs anzeigen | docker compose logs |
| Docker Volume erstellen | docker volume create \<volume\_name\> |
| Docker Volume löschen | docker volume rm \<volume\_name\> |
| Bind-Mounts verwenden (Ordner des Hosts im Container mounten) | docker run -v \<host\_path\>:\<container\_path\> \<image\_name\> |
| Docker Compose mit einem alternativen Dateinamen ausführen | docker compose -f \<file\_name\>.yml up |

Grundstruktur eines Dockerfiles:

Verwende ein Basisimage

FROM \<base\_image\>

Setze Metadaten (optional)

LABEL maintainer="\<maintainer\_name\>"

Führe Befehle im Container aus

RUN \<command\>

Kopiere Dateien vom Host in den Container

COPY \<src\> \<dest\>

Setze Arbeitsverzeichnis

WORKDIR \<path\>

Exponiere Ports (wenn erforderlich)

EXPOSE \<port\>

Führe Befehle bei Containerstart aus

CMD ["\<command\>", "\<arg1\>", "\<arg2\>"]

FROM: Gibt das Basisimage an, auf dem das neue Image aufbaut.

RUN: Führt Befehle aus, um Software zu installieren oder Konfigurationen vorzunehmen.

COPY und ADD: Kopieren Dateien vom Host in das Image.

WORKDIR: Setzt das Arbeitsverzeichnis für nachfolgende Anweisungen.

EXPOSE: Gibt an, welche Ports im Container verfügbar sein sollen.

CMD oder ENTRYPOINT: Gibt die auszuführende Befehlszeile oder das Programm an, wenn der Container gestartet wird.

Docker Compose Grundlagen:

Docker Compose-Datei erstellen (z.B. docker-compose.yml):

version: '3'

services:

\<service\_name\>:

image: \<image\_name\>

ports:

- "\<host\_port\>:\<container\_port\>"

volumes:

- \<host\_path\>:\<container\_path\>

environment:

- \<variable\_name\>=\<value\>

Was ist eine Dockerfile?

Ein Dockerfile ist eine textbasierte Datei, die eine Reihe von Anweisungen enthält, um ein Docker Image zu erstellen. Es definiert, wie die Schichten des Images aufgebaut werden sollen, welche Abhängigkeiten installiert werden müssen und wie die Anwendung konfiguriert wird. Das Dockerfile enthält Befehle zum Kopieren von Dateien, Ausführen von Befehlen, Einstellen von Umgebungsvariablen und mehr.

Was ist ein Docker Image?

Ein Docker Image ist eine eigenständige, ausführbare und portierbare Einheit, die eine Anwendung und ihre Abhängigkeiten enthält. Es wird aus einer Reihe von Schichten erstellt, die aufeinander aufbauen und eine virtuelle Dateisystemdarstellung der Anwendung und ihrer Komponenten darstellen. Ein Docker Image dient als Vorlage für das Erstellen von Containern.

Was ist eine Docker Compose File?

Eine Docker Compose-Datei ist eine Konfigurationsdatei im YAML-Format, die verwendet wird, um mehrere Docker-Container gleichzeitig zu definieren, zu konfigurieren und zu starten. Docker Compose erleichtert das Management von Anwendungen, die aus mehreren Diensten oder Komponenten bestehen, indem es die Konfiguration dieser Dienste in einer einzigen Datei ermöglicht.

Was ist ein Docker Container?

Ein Docker Container ist eine ausgeführte Instanz eines Docker Images. Er stellt eine isolierte Umgebung dar, in der eine Anwendung und alle benötigten Ressourcen laufen. Container sind leichtgewichtig, portierbar und teilen das Betriebssystem des Hosts, wodurch sie schnell gestartet und beendet werden können. Jeder Container verfügt über sein eigenes Dateisystem und seine eigene Netzwerkumgebung.

Wie hängen Dockerfile, Docker Image und Docker Container zusammen?

- Erstelle ein Dockerfile, um die Konfiguration und die Schritte zum Erstellen eines Docker Images zu definieren.
- Das Docker Image wird mit dem Befehl „docker build" aus dem Dockerfile erstellt. Dieses Image enthält alles, was benötigt wird, um deine Anwendung in einem isolierten Container auszuführen.
- Der Docker Container wird mit dem Befehl „docker run" aus einem Docker Image erstellt und gestartet. Er nutzt die Dateisystem- und Netzwerkschichten des Images, um die Anwendung zu betreiben.
