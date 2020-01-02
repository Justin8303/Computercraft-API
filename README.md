# Computercraft-API

## Module
- logisticPipes
  - Items auslesen und abfragen

## Laden der Module

1. Importiere die API mit
    ```os.loadAPI("japi")```
    
2. Lade das Modul, was du haben möchtest, alle Module sind oben aufgelistet.
    ```module = getModule(MODUL)```
    
    
    
### Verwendung des Logistic Pipes Modul

|Bereich|Funktion      |Argumente                               |Beschreibung                   |
|---    |---           |---                                     |---                            |
|request|setRequestSide|1) string: left, right, top, down, bottom, front|Setzt die Seite der Requestpipe|
|request|initPipe      |keine                                   |Muss ausgeführt werden, damit die Pipe benutzt werden kann. Die Seite muss aber vorher definiert sein!|
|request|getItems      |1) boolean: mit nbtdaten 2) boolean: mit damagedaten|Gibt alle Items im Logistic Pipes netzwerk zurück.|
|convert|getSpecificItem|1) alle Items von getItems 2) die ItemID, des gewünschten Items|Gibt das Item zurück.
|convert|getEnchantments|1) item, welches bei getSpecificItem zurückgegeben wird|Gibt alle enchantments in einer Table zurück.|

#### Item

- item
  - .id ist die Minecraft ID des Items
  - .value ist die Menge der Items im System
  - .nbt sind die NBT Daten des Items. Diese werden aber nur gespeichert, wenn bei getItems das erste Argument auf true ist.
  - .damage ist der Damage Wert des Items. Dieser wird aber nur gespeichert, wenn bei getItems das zweite Argument auf true ist.
