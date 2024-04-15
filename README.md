GameTheory API
==============

Übersicht
---------

Die GameTheory API bietet Endpunkte für die Verwaltung von Spielen, Spielern und Spielzügen. Dieses OpenAPI-Spezifikationsdokument beschreibt die verfügbaren Ressourcen, Operationen und Schemata.

API-Server
----------

Der API-Server ist unter [http://localhost:30167](http://localhost:30167/) verfügbar.

Ressourcen
----------

### Spiel (/games)

-   GET /games: Gibt eine Liste aller Spiele zurück.
-   POST /games: Erstellt ein neues Spiel.
-   GET /games/{gameId}: Gibt ein Spiel anhand seiner ID zurück.
-   PATCH /games/{gameId}: Ändert ein vorhandenes Spiel.
-   DELETE /games/{gameId}: Löscht ein Spiel anhand seiner ID.

### Spieler (/games/{gameId}/players)

-   GET /games/{gameId}/players: Gibt eine Liste aller Spieler in einem Spiel zurück.
-   POST /games/{gameId}/players: Fügt dem Spiel einen neuen Spieler hinzu.

### Spielzüge (/games/{gameId}/moves)

-   GET /games/{gameId}/moves: Gibt alle Spielzüge in einem Spiel zurück.
-   GET /games/{gameId}/moves/turns/{turnNumber}: Gibt alle Züge eines bestimmten Spielzugs zurück.
-   POST /games/{gameId}/players/{playerId}/moves: Erstellt einen Zug für einen Spieler in einem Spiel.
-   GET /games/{gameId}/players/{playerId}/moves: Gibt alle Züge eines Spielers in einem Spiel zurück.
-   GET /games/{gameId}/players/{playerId}/moves/turns/{numTurn}: Gibt den Zug eines Spielers in einem bestimmten Spielzug zurück.
-   POST /games/{gameId}/players/{playerId}/moves/turns/{numTurn}: Erstellt einen Zug für einen Spieler in einem bestimmten Spielzug.

Schemata
--------

### Spiel (game)

Ein Spiel hat folgende Eigenschaften:

-   id: Die eindeutige ID des Spiels.
-   name: Der Titel des Spiels zur Anzeige ggü dem Dozenten.
-   numTurns: Die Anzahl der Spielzüge im Spiel.
-   currentTurn: Der aktuelle Spielzug.
-   players: Eine Liste der Spieler im Spiel.
-   cardHandValue: Der Wert einer roten Karte auf der Hand eines Spielers.
-   cardPotValue: Der Wert einer roten Karte im öffentlichen Gütertopf, festgelegt vom Spielleiter.
-   potCards: Die Anzahl der roten Karten im öffentlichen Gütertopf.

### Spieler (player)

Ein Spieler hat folgende Eigenschaften:

-   id: Die eindeutige ID des Spielers.
-   name: Der Name des Spielers.
-   moves: Eine Liste der vom Spieler gemachten Züge.
-   score: Die Punktzahl des Spielers.

### Spielzug (move)

Ein Zug hat folgende Eigenschaften:

-   numTurn: Der Spielzug, zu dem der Zug gehört.
-   numRedCards: Die Anzahl der roten Karten, die der Spieler spielt (0, 1 oder 2).
