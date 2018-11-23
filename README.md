# Projekt-Evolution-game-

[1. Einleitung](#1)

[2. Aufbau/Konzept](#2)

[3. Design](#3)

[4. Schwiergkeitslevel](#4)

## Einleitung<a name="1"></a>

Das Spiel "Evolution Game" ist ein leicht zu verstehendes Spiel, welches sich thematisch am Verlauf der Evolution orientiert und diese stark vereinfacht darstellt. Es ist sowohl für Kinder, als auch für Erwachsene ein schöner Zeitvertreib. 

Es ist mit dem Programm **Snap!** programmiert worden. Deswegen werden im Folgendem Begriffe der Programmiersprache Snap! verwendet, um zu erläutern, wie das Spiel funktioniert. Für angehende Programmierer ist das Spiel vom Aufbau her gut geeignet, da es viele verschiedene Funktionen des Programm Snaps! beinhaltet, welche in diesem Spiel kombiniert werden. Unter anderem setzt man sich mit der kontrollierten Bewegung der Figuren auseinander, wie auch mit automatisch programmgesteuerten Figuren, welche man eben nicht eigenständig steuern kann. Auch das Design der Figuren und des Hintergrundes, so wie deren Wechsel, sind in dem Spiel von Bedeutung. 
 
Das Spiel setzt sich aus mehreren Scripts auf verschiedenen Blocks zusammen. Jedes Sprite hat ein eigenen Block auf dem programmiert wird, wie es sich verhalten soll, in dem man verschiedene Scripts erstellt.

**Beschreibung**

Im Evolution Game ist man ein Spieler, welcher zunächst in Form eines Einzellers gezeigt wird, der Algen "essen" muss um größer zu werden. Die Alge bewegt sich zufällig auf der Bildschirmansicht und verweilt an einer Stelle zehn Sekunden. Wird die Alge aber von der Spielfigur berührt, also gefangen, bewegt die Alge sich direkt weiter. Berührt man die Alge, erhöht sich auch der Score, also die Anzahl an Treffern. Pro Berührung erhöht sich der Score um genau eins und ab bestimmten Scores entwickelt sich die Figur weiter. Passend zu den Figuren ändert sich auch der Hintergrund. Dazu bewegt sich auch ein "Feind" auf dem Bildschirm, welcher die Figur "fressen" kann. Dieser Feind tritt zunächst in Form eines Hais auf. Berührt die Spielfigur den Hai, wird das Spiel beendet und der Spieler ist "Game over". Berührt die Alge den Hai passiert nichts.
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

**Score: 21 - 30 : Fisch**

**Score: 31 - 40 : Krebs**

**Score: 41 - 50 : Amphibie**

**Score: 51 - 60 : Reptil**

**Score: 61 - 70 : Affe**

**Score: 71 - 80 : Mensch**


![costumes 1](https://user-images.githubusercontent.com/42734752/48954550-4c359b00-ef4a-11e8-857d-8a57cb78f316.png)
![codes 1](https://user-images.githubusercontent.com/42734752/48954635-b2222280-ef4a-11e8-9675-f841db661d14.jpg)

![costumes 2](https://user-images.githubusercontent.com/42734752/48954594-7d15d000-ef4a-11e8-862f-f62c98093506.jpg)
![codes 2](https://user-images.githubusercontent.com/42734752/48954661-d5e56880-ef4a-11e8-98e1-7403f5cc5e00.jpg)

Bei einem Score über 30 ändert sich auch der Hintergrund passend zum Krebs zu einem Sandstrand. Zusätzlich erscheint eine goldene 30, damit der Evolutionsschritt vom Wasser zum Land noch deutlicher gemacht wird. Das goldene 30 ist Sprite 3. Dafür wird das Script unter dem Befehl *when score = 30* erstellt. Die 30 erscheint durch den Befehl *show* und *go to center* im Zentrum des Bildes für nur 2 Sekunden (*wait 2 secs*). Damit es danach nicht mehr zusehen ist und von alleine verschwindet, benötigt man den Befehl, *set size to 0* nach dem das Sprite 2 Sekunden zusehen war. Damit es jedes Mal wieder funktioniert, werden die Scripts für das Klicken der "kleinen grünen Flagge" und der Spacetaste, dass es auf 100 Prozent der Größe zurückgestellt wird (*set size to 100%*), allerdings versteckt (*hide*).
Bei einem Score von 50 wechselt der Hintergrund zu einer Wiese, da die Spielfigur dann zu einem Säugetier(Affe) wird und auch Sprite 2 verändert sich zu einer Banane.

![informatik 30](https://user-images.githubusercontent.com/42734752/48854235-acdda000-edb1-11e8-859d-170371d7d270.jpg)


## Schwierigkeitslevel<a name="4"></a>

Um das Spiel schwieriger zu machen, gibt es auch noch ein viertes Sprite, welches einen Feind darstellt. Im Evolutionsspiel ist dies ein Hai. Dieser gleitet zehn Sekunden lang auf der x-Achse und startet im Abstand von fünf Sekunden random/zufällig auf der y-Achse. Dieser Vorgang soll sich beliebig wiederholen. Dafür wird in den Befehl *forever*, da es immer wieder auftauchen soll, zum einen der Befehl *set x to -350* eingefügt, damit es von der linken Bildschirmseite aus startet und vorher nicht zu sehen ist und zum anderen der Befehl *point in direction 90*, so dass das Sprite nach rechts zeigt und es realistisch aussieht. Damit es wie ein Fisch im Wasser gleitet, wird der Befehl *glide 10 sec to x: 350 y: pick random -180 to 100)* verwendet. X: 350 wird ausgewählt, damit das Sprite komplett aus dem Bild verschwindet und die Y-Koordinaten werden ständig random in einem bestimmten Bereich gewählt. Danach wartet Sprite 4 fünf Sekunden lang (*wait 5 secs*) bis der Vorgang sich wieder wiederholt.

![informatik hai](https://user-images.githubusercontent.com/42734752/48854356-01811b00-edb2-11e8-85e7-4b90861edfe0.jpg)

Wird die Spielfigur von diesem Hai berührt ist das Spiel vorbei, da man "gefressen" wird. Für diesen Effekt wurden zwei *Costumes* des Hais importiert: **Shark a** und **Shark b**. Wenn das Sprite 4 die Spielfigur berührt (*when touching Sprite 1*) wechselt das *Costume zu **Shark b** (*switch to Costume shark b*). Dies stellt den gleichen Hai nur mit aufgerissenem Maul dar. Dies lässt es aussehen als würde Sprite 1 tatsächlich gefressen werden. Nachdem das zweite Costume für eine Sekunde lang gezeigt wurde, wechselt es dann wieder zum ersten *Costume* (*switch to costume shark a*).

![informatik hai](https://user-images.githubusercontent.com/42734752/48906025-79f3e480-ee63-11e8-8c71-0296e16e3df2.jpg)

Die Spielfigur beendet das Spiel in dem es "Game over" sagt. Unter dem Befehl *when touching Sprite 4*, also wenn Sprite 1 Sprite 4 berührt, wird der Befehl *say "Game over" for 2 secs* eingefügt. Dann wartet Sprite 1 0.1 Sekunden (*wait 0.1 secs*), verschwindet (*hide*) und alle Blöcke werden gestoppt (*stop all*).

![informatik game over](https://user-images.githubusercontent.com/42734752/48854463-49a03d80-edb2-11e8-985f-4d8d72348dca.jpg)

Schafft der Spieler es bis zum *Costume* des Krebses, also bis zu Score 30, erscheint der Hai nicht länger (*when score > 30* - *hide*) Dazu wird der Block für den Hai gestoppt (*stop other scripts in sprite*).

![stop hai](https://user-images.githubusercontent.com/42734752/48906203-07373900-ee64-11e8-818f-07b38419a1c1.jpg)

Sprite 1:

![sprite 1](https://user-images.githubusercontent.com/42734752/48954883-9a976980-ef4b-11e8-9e76-180ec8e57bad.jpg)

Sprite 2:

![sprite 2](https://user-images.githubusercontent.com/42734752/48954923-c0bd0980-ef4b-11e8-987f-3615cebff124.jpg)

Sprite 3:

![3 sprite](https://user-images.githubusercontent.com/42734752/48907225-1966a680-ee67-11e8-8c48-453331dee63b.png)

Sprite 4:

![4 sprite](https://user-images.githubusercontent.com/42734752/48907249-297e8600-ee67-11e8-9cce-a8242c029087.jpg)





