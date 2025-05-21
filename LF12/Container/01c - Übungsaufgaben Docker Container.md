### Aufgabe 1: Einfaches Dockerfile erstellen

**Ziel:** Erstelle ein einfaches Dockerfile, das ein Basis-Image verwendet und eine einfache Textdatei in den Container kopiert.

1. **Erstelle ein Verzeichnis** für dein Projekt, z.B. `mein-erster-container`.
2. **Erstelle eine Datei** namens `Dockerfile` in diesem Verzeichnis.
3. Wähle ein Basis-Image aus, z.B. `alpine`, indem du die Zeile `FROM alpine` in das Dockerfile schreibst.
4. Erstelle eine einfache Textdatei namens `info.txt` mit einem beliebigen Inhalt.
5. Füge dem Dockerfile eine Zeile hinzu, die diese Datei in den Container kopiert:
   ```dockerfile
   COPY info.txt /info.txt
   ```
6. Baue das Docker-Image mit dem folgenden Befehl:
   ```bash
   docker build -t mein-erster-container .
   ```
7. Starte einen Container aus dem Image und überprüfe den Inhalt der Datei:
   ```bash
   docker run mein-erster-container cat /info.txt
   ```

### Aufgabe 2: Einfache Anwendung im Container

**Ziel:** Führe ein einfaches Python-Skript innerhalb eines Containers aus.

1. **Erweitere dein Verzeichnis** um eine Python-Datei namens `app.py`.
2. Schreibe ein kleines Skript in `app.py`, das „Hello, World!“ ausgibt.
3. Aktualisiere das Dockerfile:
   - Verwende ein Image mit Python-Unterstützung: `FROM python:3-alpine`
   - Kopiere `app.py` in den Container:
     ```dockerfile
     COPY app.py /app.py
     ```
   - Definiere den Standardbefehl zum Starten des Containers:
     ```dockerfile
     CMD ["python", "/app.py"]
     ```
4. Baue und starte das Image erneut wie zuvor und überprüfe die Ausgabe.

### Aufgabe 3: Umgebungskonfiguration

**Ziel:** Verwende Umgebungsvariablen im Container.

1. Ändere dein Python-Skript so, dass es eine Umgebungsvariable liest und deren Wert ausgibt:
   ```python
   import os
   
   message = os.getenv("MESSAGE", "Hello, World!")
   print(message)
   ```
2. Aktualisiere dein Dockerfile nicht direkt, sondern übergebe die Umgebungsvariable beim Start des Containers:
3. Starte den Container mit einer Umgebungsvariable:
    ```bash
    docker run -e MESSAGE="Hallo von Docker!" mein-erster-container
    ```

### Aufgabe 4: Eigenes Image auf Basis eines anderen erweitern

**Ziel:** Erstelle ein eigenes Image basierend auf einem bereits existierenden.

1. **Verwende das vorherige Image** als Basis für ein neues Projekt.
2. Ändere das Dockerfile so ab, dass es auf deinem bestehenden Image basiert:
   ```dockerfile
   FROM mein-erster-container
   ```
3. Füge einen neuen Schritt hinzu, der ein weiteres Skript oder einen zusätzlichen Befehl im Container startet oder installiert (z.B., installiere curl).
4. Baue dieses neue Image unter einem anderen Namen und teste es entsprechend.
