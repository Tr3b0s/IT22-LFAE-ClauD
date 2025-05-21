### Infoblatt: Docker Compose 

#### Was ist Docker Compose?

Docker Compose ist ein Werkzeug, das es ermöglicht, Multi-Container-Docker-Anwendungen zu definieren und auszuführen. Mit einem einzigen Befehl können alle Dienste einer Anwendung gestartet werden, die in einem YAML-Format beschrieben sind. Es vereinfacht die Verwaltung komplexer Anwendungen, indem es die Konfiguration und den Startprozess automatisiert.

#### Warum Docker Compose verwenden?

1. **Vereinfachte Verwaltung von Container-Anwendungen**: Mit Docker Compose können mehrere Container gleichzeitig gestartet, gestoppt und verwaltet werden.
2. **Portabilität**: Anwendungen können auf verschiedenen Umgebungen (Entwicklung, Test, Produktion) mit denselben Konfigurationen ausgeführt werden.
3. **Automatisierung**: Reduzierter manueller Aufwand durch automatische Erstellung und Verwaltung von Netzwerken und Volumes.
4. **Schnelles Setup**: Entwicklungsumgebungen können schnell eingerichtet werden.

#### Grundlegende Konzepte

- **YAML-Datei (`docker-compose.yml`)**: Eine Textdatei im YAML-Format definiert die Services, Netzwerke und Volumes der Anwendung.
- **Services**: Jeder Service entspricht einem Container oder einer Gruppe von Containern mit derselben Konfiguration.
- **Netzwerke**: Ermöglichen die Kommunikation zwischen Containern.
- **Volumes**: Persistente Speicherorte zur Datenspeicherung außerhalb des Containers.

#### Grundstruktur einer `docker-compose.yml`

```yaml
version: '3'
services:
  web:
    image: nginx
    ports:
      - "80:80"
  db:
    image: mysql
    environment:
      MYSQL_ROOT_PASSWORD: example
```

Dieser einfache Aufbau definiert zwei Services – einen Webserver (nginx) und eine Datenbank (MySQL).

#### Wichtige Befehle

- `docker-compose up`: Startet alle im YAML definierten Services. Mit dem Flag `-d` wird im Hintergrundmodus gestartet.
- `docker-compose down`: Stoppt alle laufenden Services und entfernt Container sowie Netzwerke, aber nicht definierte Volumes.
- `docker-compose ps`: Zeigt den Status der laufenden Services an.
- `docker-compose logs`: Zeigt Logs der laufenden Container an.

#### Best Practices

1. **Modularisierung der Konfigurationen**:
   - Trennen Sie Entwicklungs-, Test- und Produktionskonfigurationen in verschiedene Dateien oder verwenden Sie Variablen für dynamische Werte.
   
2. **Verwendung von Umgebungsvariablen**:
   - Sensible Informationen wie Passwörter sollten über Umgebungsvariablen gesteuert werden.

3. **Netzwerkisolation**:
   - Nutzen Sie separate Netzwerke für unterschiedliche Teile Ihrer Anwendung zur Erhöhung der Sicherheit.

4. **Persistenz beachten**:
   - Verwenden Sie Volumes für persistente Daten, um Datenverlust beim Neustart von Containern zu vermeiden.

5. **Versionierung der Compose-Datei**:
   - Nutzen Sie eine Versionskontrolle für Ihre `docker-compose.yml`, um Änderungen nachvollziehbar zu machen.

#### Fazit

Docker Compose ist ein mächtiges Werkzeug zur Verwaltung komplexer Anwendungen in Containern. Durch seine Fähigkeit, mehrere Dienste gleichzeitig zu starten, ermöglicht es eine effizientere Entwicklungspipeline und erleichtert das Deployment in unterschiedlichen Umgebungen erheblich.