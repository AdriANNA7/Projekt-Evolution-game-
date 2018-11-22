# Projekt-Evolution-game-

[1. Einleitung](#1)

[2. Aufbau/Konzept](#2)

[3. Design](#3)

[4. Schwiergkeitslevel](#4)

## Einleitung<a name="1"></a>

Das Spiel "Evolution Game" ist ein leicht zu verstehendes Spiel, welches sich thematisch am Verlauf der Evolution orientiert und diese stark vereinfacht darstellt. Es ist sowohl für Kinder, als auch für Erwachsene ein schöner Zeitvertreib. 
Auch für angehende Programmierer ist das Spiel vom Aufbau her gut geeignet, da es viele verschiedene Funktionen des Programm Snaps! beinhaltet, welche in diesem Spiel kombiniert werden. Unter anderem setzt man sich mit der kontrollierten Bewegung der Figuren auseinander, wie auch mit automatisch programmgesteuerten Figuren, welche man eben nicht eigenständig steuern kann. Auch das Design der Figuren und des Hintergrundes, so wie deren Wechsel, sind in dem Spiel von Bedeutung. 
 
Das Spiel setzt sich aus mehreren Scripts auf verschiedenen Blocks zusammen. Jedes Sprite hat ein eigenen Block auf dem programmiert wird, wie es sich verhalten soll, in dem man verschiedene Scripts erstellt.

**Beschreibung**

Im Evolution Game ist man ein Spieler, welcher zunächst in Form eines Einzellers gezeigt wird, der Algen "essen" muss um größer zu werden. Pro Alge erhöht sich der Score um eins und ab bestimmten Scores entwickelt sich die Figur weiter. Passend zu den Figuren ändert sich auch der Hintergrund. Dazu bewegt sich auch ein "Feind" auf dem Bildschirm, welcher die Figur "fressen" kann. Damit wird das Spiel beendet und der Spieler ist "Game over". Am Anfang stellt der sogenannte Feind einen Hai dar. 
Gewonnen ist das Spiel, wenn man sich bis zu einem Menschen entwickelt hat. 
 
 ## Aufbau/Konzept<a name="2"></a>

**Start:**
Wenn die "kleine grüne Flagge" geklickt wird, startet das Spiel. Dadurch erscheint die erste Spielfigur (Sprite 1) im Zentrum des Bildschirms und zwar durch die Befehle *show* und *go to center* in einer passenden Größe *set size to 25%*. Dieser letzte Befehl wird je nach Figur unterschiedlich eingestellt, um es visuell möglichst angenehm für den Benutzer zu machen.

Zusätzlich wird die selbsterstellte Variable "Score" auf 0 gestellt durch *set score to 0*. "Score" zeigt in dem Spiel das Ergebnis an.

![1 1](https://user-images.githubusercontent.com/42734752/48783533-f01c0e00-ece0-11e8-90b4-d0068def0e3b.jpg)

Das gleiche passiert, wenn man die *Spacetaste* drückt. Dies dient dazu, das Spiel wieder neu anfangen zu können. Allerdings gibt es hier die erweiterte Funktion, dass zum Anfangsdesign gewechselt wird (*switch to costume [...]*).

![1 2](https://user-images.githubusercontent.com/42734752/48783732-691b6580-ece1-11e8-8b5e-8f577458cee8.jpg)

Dies ist unser erstes Sprite mit dem ersten Script. Dieser wird mit den Pfeiltasten gesteuert, sodass er sich über den Bildschirm bewegt. Damit sich das Sprite bewegt, wird für die jeweiligen Pfeiltasten der Befehl *change y by [20]* eingefügt. Die Zahl 20 besagt, wie weit nach vorne sich der Pfeil bewegt.
Dazu dreht sich das Sprite bei den Pfeiltasten links und rechts in die jeweilige Richtung mit , um es realistischer aussehen zu lassen.
Deswegen ist nur bei *arrow left* und *arrow right* der zusätzliche Befehl *point in direction[...]* vorhanden. In das freie Feld werden die passende Gradzahl reingeschreiben. 
Links: 0° Rechts: 180° 

![sprite bewegung](https://user-images.githubusercontent.com/42734752/48779370-c0b4d380-ecd7-11e8-8cb2-51cf34407c0c.jpg)

Dazu gibt es ein zweites Sprite, welches random/zufällig auf dem Bildschirm erscheint. Jedesmal bevor es wieder auftaucht, verschwindet es und wird dann an seiner neuen Position sichtbar. Dieser Ablauf wird unter anderem durch den Befehl *go to random position* gewährleistet. Dann sollte er eine Sekunde warten (Befehl:*wait 1 secs*), bis er dann wieder durch den Befehl *show* sichtbar wird. Er ist dann fünf Sekunden lang sichtbar (Befehl: *wait 5 secs*) ist, damit man das zweite Sprite mit dem ersten Sprite fangen kann. Das ganze sollte sich ständig (unendlich) wiederholen, weshalb dieses Script mit dem Befehl *forever* umschlossen ist. Das gleiche wird auch durch drücken der Spacetaste erreicht.

![informatik sprite 2](https://user-images.githubusercontent.com/42734752/48852438-a3523900-edad-11e8-9562-d56518b6a22c.jpg)

Wird Sprite 2 von Sprite 1 berührt (*when touching sprite 1*), wartet es einen kurzen Augenblick (0,05 sek./* wait 0.05 secs*) und geht dann durch den Befehl *go to random position* wieder auf eine zufällige Position. Zusätzlich wird dadurch der Score um genau 1 erhöht (*change score by 1*). Die kurze Wartezeit verhindert eine lange Berührung der beiden Sprites, um den Score nicht mehrfach zu erhöhen. 

![informatik beruhrung von 1 und 2](https://user-images.githubusercontent.com/42734752/48852650-1eb3ea80-edae-11e8-8b24-9a577bcf86d3.jpg)

## Design<a name="3"></a>

Da es sich um ein Evolutionsspiel handelt, ist Sprite 1 zunächst in Gestalt eines Einzellers zusehen. Der Hintergrund ist eine Unterwasserwelt und Sprite 2 stellt eine Art Alge dar. Die grafische Darstellung (*Costumes* und *Stages*) wurden aus dem Internet importiert.

![design informatik](https://user-images.githubusercontent.com/42734752/48853002-d5b06600-edae-11e8-82bf-9fb7bde57aa2.jpg)

Bildlich erklärt muss die Spielfigur/der Spieler die Alge (Sprite 2) fangen und "fressen". Dadurch wird der Einzeller vorläufig größer und entwickelt sich dann weiter. Die Spielfigur wechselt also ihr Aussehen in dem die *Costumes* geändert werden.
Bei unterschiedlichen Scores befindet sich die Spielfigur in unterschiedlichen Etappen.
Um einen begrenzten Score-Bereich für das jeweilige *Costume* zu programmieren, musste der Befehl *when score > [...] and < [...]* mit dem Befehl *switch to costume* kombiniert werden. Für den freien Bereichen werden die jeweiligen Werte der Anfangs- und Endscores, in denen das passende *Costume* auftreten soll, geschrieben.

**Score: 11 - 20 : Qualle**

**Score: 21 - 30 : Tintenfisch**

**Score: 31 - 40 : Krebs**

![kostume informatik](https://user-images.githubusercontent.com/42734752/48853495-eb725b00-edaf-11e8-9ca4-6227a05b5ef4.jpg) ![informatik befehle kostume](https://user-images.githubusercontent.com/42734752/48853600-21174400-edb0-11e8-8602-d249c0f0dff9.jpg)

Bei einem Score über 30 ändert sich auch der Hintergrund passend zum Krebs zu einem Sandstrand. Zusätzlich erscheint eine goldene 30, damit der Evolutionsschritt vom Wasser zum Land noch deutlicher gemacht wird. Das goldene 30 ist Sprite 3. Dafür wird das Script unter dem Befehl *when score = 30* erstellt. Die 30 erscheint durch den Befehl *show* und *go to center* im Zentrum des Bildes für nur 2 Sekunden (*wait 2 secs*). Damit es danach nicht mehr zusehen ist und von alleine verschwindet, benötigt man den Befehl, *set size to 0* nach dem das Sprite 2 Sekunden zusehen war. Damit es jedes Mal wieder funktioniert, werden die Scripts für das Klicken der "kleinen grünen Flagge" und der Spacetaste, dass es auf 100 Prozent der Größe zurückgestellt wird (*set size to 100%*), allerdings versteckt (*hide*).

![informatik 30](https://user-images.githubusercontent.com/42734752/48854235-acdda000-edb1-11e8-859d-170371d7d270.jpg)


## Schwierigkeitslevel<a name="4"></a>

Um das Spiel schwieriger zu machen, gibt es auch noch ein viertes Sprite, welches einen Feind darstellt. Im Evolutionsspiel ist dies ein Hai. Dieser gleitet im Abstand von zehn Sekunden auf der X-Achse an beliebigen Stellen der Y-Achse entlang.

![informatik hai](https://user-images.githubusercontent.com/42734752/48854356-01811b00-edb2-11e8-85e7-4b90861edfe0.jpg)

Wird die Spielfigur von diesem Hai berührt ist das Spiel vorbei, da man "gefressen" wird. Die Spielfigur beendet das Spiel in dem es "Game over" sagt.

![informatik game over](https://user-images.githubusercontent.com/42734752/48854463-49a03d80-edb2-11e8-985f-4d8d72348dca.jpg)
