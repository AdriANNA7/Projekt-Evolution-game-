# Projekt-Evolution-game-

[1. Einleitung](#1)

[2. Aufbau/Konzept](#2)

[3. Design](#3)



## Einleitung<a name="1"></a>

  Das Spiel "Evolution Game" ist ein leicht zu verstehendes Spiel, welches sich mit der Evolution auseinandersetzt. Es ist sowohl für Kinder, als auch für Erwachsene ein schöner Zeitvertreib. Auch für angehende Programmierer ist das Spiel gut geeignet, da es viele verschiedene Funktionen des Programm Snaps! beinhaltet, welche in diesem Spiel kombiniert werden. 
Unter anderem setzt man sich mit der kontrollierten Bewegung der Figuren auseinander, wie auch mit automatisch ablaufenden Figuren, welche man nicht eigenständig steuern kann. Auch das Design der Figuren und des Hintergrundes, so wie dessen Wechsels, sind in dem Spiel von Bedeutung. 
 
 Das Spiel setzt sich aus mehreren Scripts auf verschiedenen Blocks zusammen. Jedes Sprite hat ein eigenen Block auf dem programmiert wird, wie es sich verhalten soll, in dem man verschiedene Scripts erstellt.

**Beschreibung**

In dem Evolution Game ist man ein Spieler, welcher zunächst in Form eines Einzellers gezeigt wird, der Algen "essen" muss um größer zu werden. Pro Alge erhöht sich der Score um 1 und ab bestimmten Scores entwickelt sich die Figur weiter. Passend zu den Figuren ändert sich auch der Hintergrund. Dazu bewegt sich auch ein "Feind" auf dem Bildschirm, welcher die Figur "fressen" kann. Damit wird ist das Spiel Game over. Am Anfang stellt der sogenannte Feind einen Hai dar. 
Gewonnen ist das Spiel, wenn man sich bis zu einem Menschen entwickelt hat. 
 
 ## Aufbau/Konzept<a name="2"></a>

**Start:**
Wenn die "kleine grüne Flagge" geklickt wird, startet das Spiel. Dadurch erscheint die erste Spielfigur (Sprite 1) im Zentrum des Bildschirms durch die Befehle *show* und *go to center* in einer passenden Größe *set size to 25%*. Dieser letzte Befehl wird je nach Figur unterschiedlich eingestellt, um es möglichst angenehm für den Benutzer zu machen.

Zusätzlich wird die selbsterstellte Variable "Score" auf 0 gestellt durch *set score to 0*. "Score" zeigt in dem Spiel das Ergebnis an.

![1 1](https://user-images.githubusercontent.com/42734752/48783533-f01c0e00-ece0-11e8-90b4-d0068def0e3b.jpg)

Das gleiche passiert, wenn man die *Spacetaste* drückt. Allerdings gibt es hier die erweiterte Funktion, dass zum Anfangsdesign gewechselt wird, was später noch erläutert wird.

![1 2](https://user-images.githubusercontent.com/42734752/48783732-691b6580-ece1-11e8-8b5e-8f577458cee8.jpg)

Dies ist unser erstes Sprite mit dem ersten Script. Dieser wird mit den Pfeiltasten gesteuert, sodass er sich über den Bildschirm bewegt.
![sprite bewegung](https://user-images.githubusercontent.com/42734752/48779370-c0b4d380-ecd7-11e8-8cb2-51cf34407c0c.jpg)
