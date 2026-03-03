## Link zur Webseite: https://codecobra3.vercel.app/

## 🚀 Projekt starten

Es gibt zwei Möglichkeiten, dieses Projekt zu nutzen: Als fertigen Docker-Container (empfohlen für die Ausführung) oder durch lokale Entwicklung mit Node.js (für die Bearbeitung des Codes).

---

### 1. Als Docker-Container

Diese Methode startet die fertig gebaute Anwendung in einem isolierten Nginx-Webserver. Das Image wird automatisch bei jedem Push auf `main` auf Docker Hub erstellt.

#### 📋 Voraussetzungen

Um dieses Projekt als Docker-Container auszuführen, wird nur eine Software benötigt:

* **Docker Desktop:** Du musst [Docker Desktop](https://www.docker.com/products/docker-desktop/) (oder eine andere Docker-Umgebung) auf deinem Computer installiert haben und es muss ausgeführt werden.

#### 🐳 Docker Image & Schnellstart

- **Link zum Repository:**
  [https://hub.docker.com/repository/docker/abcakir/codecobra-docker/general](https://hub.docker.com/repository/docker/abcakir/codecobra-docker/general)

# Container starten
Starten sie "Docker Desktop" und führe diesen Befehl in deinem Terminal aus. Docker lädt das Image automatisch herunter und startet es unter dem Namen `CodeCobra-TZR`.

```bash
docker run -d -p 8080:8080 --name CodeCobra-TZR abcakir/codecobra-docker:latest
``` 

- Öffne deinen Browser und gehe auf: http://localhost:8080

#### 🔄 Container aktualisieren (Update)

Da der Container mit einem festen Namen (`CodeCobra-TZR`) läuft, muss er gestoppt und neu erstellt werden, um das neueste Image von Docker Hub zu verwenden.

### 1. Das neueste Image herunterladen (Pull)
```bash
docker pull abcakir/codecobra-docker:latest
```

### 2. Alten Container stoppen
```bash
docker stop CodeCobra-TZR
```
### 3. Alten Container löschen
```bash
docker rm CodeCobra-TZR
```
### 4. Neuen Container mit dem neuen Image starten
```bash
docker run -d -p 8080:8080 --name CodeCobra-TZR abcakir/codecobra-docker:latest
```



---

### 2. Mit Node.JS v24.11.0 oder höher (Empfohlene Methode für Entwickler)

[https://nodejs.org/en/download](https://nodejs.org/en/download)

- Im **teilzeit-ausbildungsrechner** Ordner (einmalig) folgendes eingeben:

```bash
npm install
```

Dann

```bash
npm run dev
```

- Öffne deinen Browser und gehe auf: http://localhost:5173/



---

## Einbettung als iFrame

Die Anwendung kann als iFrame in andere Seiten eingebettet werden. Im ausgelieferten Build liegt dafür `public/embed.html`, das die App vollflächig in einem iFrame rendert.

### iFrame-Snippet

```html
<iframe
  src="https://IHRE-DOMAIN.de/embed.html"
  style="border:0;width:100%;min-height:1480px;"
  loading="lazy"
  allowfullscreen
></iframe>
```

 #### Hinweis: Ersetzen Sie die URL durch die Domain, auf der Sie den Teilzeit-Ausbildungsrechner hosten.
- Bei lokalem Dev-Server: `src` auf `http://localhost:5173/embed.html` setzen.
- Bei Docker/Nginx: `src` auf `http://localhost:8080/embed.html` setzen.
- Hoehe/Breite nach Bedarf anpassen, ggf. `min-height` erhohen, damit das Formular ohne Scrollen sichtbar ist.
