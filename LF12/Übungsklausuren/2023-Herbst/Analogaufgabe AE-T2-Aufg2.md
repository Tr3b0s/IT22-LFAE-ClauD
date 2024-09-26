### Ähnliche Aufgabe: Routenplanung für Lieferfahrzeuge

#### Aufgabenstellung:

Ein Logistikunternehmen plant die Routen für seine Lieferfahrzeuge, um die Effizienz der Auslieferungen zu maximieren. Jedes Fahrzeug muss eine bestimmte Anzahl von Lieferadressen anfahren, die in einem eindimensionalen Array `deliveryLocations` gespeichert sind. Jede Adresse ist ein Objekt der Klasse `DeliveryLocation` und enthält die folgenden Attribute:

- `latitude: double`
- `longitude: double`
- `deliveryTime: double` (Zeit in Stunden, die für die Lieferung an dieser Adresse benötigt wird)

Das Ziel ist es, die Reihenfolge der Anfahrten zu bestimmen, sodass das Fahrzeug immer die nächste Adresse ansteuert, die der aktuellen Position am nächsten liegt.

#### Vorgaben:

- Die aktuelle Position des Fahrzeugs wird als Ausgangspunkt genommen.
- Die anzufahrenden Adressen liegen in einem eindimensionalen Array `deliveryLocations`.
- Für Entfernungsberechnungen zwischen Adressen kann die Methode `calculateDistance` der Klasse `DistanceCalculator` verwendet werden:
    
    - Quellcode
    - Vorschau
    - Neu laden
    - Kopieren Kopiert!
    
    ```java
    DistanceCalculator + calculateDistance(loc1: DeliveryLocation, loc2: DeliveryLocation): double { static }
    ```
    
- Der Algorithmus soll das Ergebnis in einem Array `route` speichern und zurückgeben.
- Das Array `deliveryLocations` kann durch den Algorithmus verändert werden.
- Die Adresse mit dem Index 0 des Arrays `deliveryLocations` wird zur ersten aktuellen Position und kann aus dem Array gelöscht werden.
- Solange noch Adressen im Array `deliveryLocations` vorhanden sind, wird die Adresse mit der kürzesten Entfernung zur aktuellen Position ermittelt und gespeichert.

#### Aufgabenstellung:

- Vervollständigen Sie den Pseudocode zur Implementierung des Algorithmus `planRoute()`.


**Musterlösung: [[Analogaufgabe AE-T2-Aufg2 Musterlösung]]**
