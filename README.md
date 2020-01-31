# Computercraft-API

## Download über Pastebin
- https://pastebin.com/6zmgx9db

## Module
- logisticPipes
  - Items auslesen und abfragen
- appliedEnergistics
  - Items auslesen und abfragen

## Laden der Module

1. Importiere die API mit
    ```os.loadAPI("japi")```
    
2. Lade das Modul, was du haben möchtest, alle Module sind oben aufgelistet.
    ```module = japi.getModule(MODUL)```
    
    
    
### Verwendung des Logistic Pipes Modul

|Bereich|Funktion      |Argumente                               |Beschreibung                   |
|---    |---           |---                                     |---                            |
|request|setRequestSide|1) string: left, right, top, down, bottom, front|Setzt die Seite der Requestpipe|
|request|initPipe      |keine                                   |Muss ausgeführt werden, damit die Pipe benutzt werden kann. Die Seite muss aber vorher definiert sein!|
|request|getItems      |1) boolean: mit nbtdaten 2) boolean: mit damagedaten|Gibt alle Items im Logistic Pipes netzwerk zurück.|
|convert|getSpecificItem|1) alle Items von getItems 2) die ItemID, des gewünschten Items|Gibt das Item zurück.
|convert|getEnchantments|1) item, welches bei getSpecificItem zurückgegeben wird|Gibt alle enchantments in einer Table zurück.|

#### Aufbau des Items

- item
  - .id ist die Minecraft ID des Items
  - .value ist die Menge der Items im System
  - .nbt sind die NBT Daten des Items. Diese werden aber nur gespeichert, wenn bei getItems das erste Argument auf true ist.
  - .damage ist der Damage Wert des Items. Dieser wird aber nur gespeichert, wenn bei getItems das zweite Argument auf true ist.




### Verwendung des Applied Energistics Modul
|Bereich|Funktion      |Argumente                               |Beschreibung                   |
|---    |---           |---                                     |---                            |
|sensor|setSensorSide|1) string: left, right, top, down, bottom, front|Setzt die Seite des Sensors|
|sensor|initSensor      |int: x Koordinate, int: y Koordinate, int z Koordinate                                   |Muss ausgeführt werden, damit der Sensor benutzt werden kann. Die Seite muss aber vorher definiert sein! Wenn man mehrere Accesspoints vom Me System hat, kann man die x,y und z Koordinaten als Argument angeben.|
|request|getItems      |keine|Gibt alle Items im ME System zurück.|
|convert|getSpecificItem|1) alle Items von getItems 2) der Name (in Englisch) des gewünschten Items|Gibt das Item zurück. 3) true oder false, jenachdem ob es mehrere Items mit dem gleichen Namen im ME System gibt.

#### Aufbau des Items

- item
  - .RawName ist der interne Name des Items
  - .Name ist der Anzeigename des Items
  - .MaxStack ist die Maximale anzahl in einem Stack also z.b. 64
  - .Size ist die Menge der Items im System
  - .DamageValue ist der Damage Wert des Items
