# Java Lernzettel 📌

Dies ist der Lernzettel für die IT Klausur - Basierend auf dem herausgegebenen Lernzettel von Herrn Lam und mit vielen Ergänzungen, Übungsaufgaben und Empfehlungen von Dennis.

## Inhalt

1. [🏐 Objektorientierte Programmierung](#kap1)
2. [🎫 Konzepte von Greenfoot](#kap2)
3. [🎢 Java Grundlagen](#kap3)
4. [🎰 Datentypen](#kap4)
5. [👨‍💻 Rechnen mit Variablen](#kap5)
6. 🔩 Klassen und Objekte
7. 🔗 Bedingungen
8. 🌠 Schleifen
9. 🐫 Ausgaben
10. ✨ Sauberen Code schreiben!
11. 👓 Übungsaufgaben

### Legende

| Markierung | Bedeutung                                                    |
| ---------- | ------------------------------------------------------------ |
| ❕          | Besonders *wichtiger* Abschnitt.                             |
| 🔁          | Kurze *Zusammenfassung*.                                     |
| 💫          | *Zusatzinfos*, die beim Verständnis helfen können, aber nicht notwendig sind. |



## 🏐 Objektorientierte Programmierung <a name="kap1"></a>

Java ist eine der größten sogenannten *Objektorientierten Programmiersprachen* und Greenfoot verwendet Java als Programmiersprache. Deshalb ist es wichtig, überhaupt zu verstehen, womit wir arbeiten.

### Was ist das überhaupt?

In der klassischen Programmierung geht es darum, einen *Ablaufplan* zu erstellen, dessen Befehle einfach chronologisch vom jeweiligen Gerät abgearbeitet werden.

Im Gegensatz dazu versucht die *Objektorientierte Programmierung* so viele Programmteile wie möglich zu **Modularisieren**, dadurch kann der Code sehr viel kürzer werden, da Wiederverwendungen vermieden werden. Dieser kürzere Code ist im Zweifel auch leichter zu verstehen, zu testen und zu warten.

### Konzepte der Modularisierung

Um einen modularen Code zu erreichen, werden Codeabschnitte in **Objekte** unterteilt. Diese Objekte können mehrfach erzeugt werden und bleiben gespeichert, solange das Programm läuft (Oder bis sie im Programm gelöscht werden). Objekte können festgelegte Eigenschaften haben (**Attribute** genannt) und eigene Funktionen besitzen (**Methoden** genannt). Um ein Objekt zu erzeugen, muss zuvor eine Art Bauplan erstellt werden, der alle verfügbaren Attribute und Methoden eines Objektes festlegen kann. Ein solcher Bauplan heißt **Klasse**.

Um dieses Konzept besser zu verstehen, hier ein **Beispiel**:

Es gibt eine Klasse namens *Auto*. In der Klasse ist festgelegt, dass alle Autos eine *Marke* haben. Außerdem kann jedes Auto *fahren*, Autos haben also eine Funktion namens *fahren()*.

Dann wird das Programm ausgeführt und ein *Auto* wird erzeugt. Dieses spezielle *Auto* ist jetzt also gebaut worden und existiert jetzt als *Objekt*. Dieses Auto bekommt die *Marke* "Lada" zugewiesen und es soll drei Mal *fahren*, diese Funktion wird also 3 Mal ausgeführt.

### 💫Advanced Stuff

Viele Programmiersprachen unterstützen außerdem das Konzept der *Vererbung*. So kann man in Java Beispielsweise eine Klasse "Auto" erstellen und die Klasse "VW" erbt dann alle Eigenschaften und Funktionen der "Auto"-Klasse, wird aber z.B. um die Eigenschaften "Modell" und "PS" erweitert.

Objekte sind grundsätzlich von der Außenwelt *abgekapselt* und können nicht ohne weiteres von außen beeinflusst werden (es sei denn, man will das). Objekte entscheiden grundsätzlich selbst über ihr Verhalten. Mehr dazu im Kapitel [Variablen](change me).

## 🎫 Konzepte von Greenfoot <a name="kap2"></a>

Greenfoot ist eine sogenannte **IDE** (Integrated Development Environment). Zu Deutsch, es handelt sich um eine Entwicklungsumgebung, also ein Programm, in dem man Programmiercode schreiben kann. Deshalb nimmt Greenfoot dem Entwickler etwas Arbeit ab, indem dieser den Code nicht selbst zu Maschinencode umwandeln muss. Was Greenfoot außerdem tut, ließt Du hier:

### Actor und World

In Greenfoot gibt es sogenannte **Actors**. Im Prinzip ist das nur eine festgelegte Oberklasse, aus der all deine selbst-erstellten Actors erben. Alle Actors können *act()* ausführen, das passiert in Greenfoot bei jedem Tick / Frame. Außerdem haben sie ein Anzeigebild, das man in Greenfoot vereinfacht durch Rechtsklick auf den Actor verändern kann.

Außerdem gibt es **World**s, dies sind auch nur festgelegte Klassen, in denen Objekte generiert und platziert werden können. Jede World wird also beim Ausführen auch nur als ein Objekt erstellt, das dann die anderen (Actor-)Objekte erstellt und dadurch weiterhin auf diese zugreifen kann.

## Oberfläche

Die **Oberfläche** von Greenfoot enhält ein großes Fenster, in dem live (als Vorschau) eine Welt geladen werden kann, außerdem können *act()* Zyklen simuliert werden. Ein Klick auf "Run" simuliert diese Zyklen im Loop.

An der rechten Leiste sind alle Klassen des Spiels aufgelistet. Dort können neue Actors und Worlds erstellt werden.

## 🎢 Java Grundlagen <a name="kap3"></a>

Java ist eine *Objektorientierte Programmiersprache*, die auf vielen Geräten und Systemen ausführbar ist. Java-Code wird als Programm in einen **Zwischencode** umgewandelt ("compiled"), der dann von je nach System / Gerät in den jeweiligen Maschinencode **interpretiert** wird. Dies übernimmt der *Java Interpreter*. Der große Vorteil von Java ist, dass es auf so vielen Systemen funktioniert. Der Nachteil ist, dass solcher *interpretierter Code* etwas langsamer ist, Spiele laufen in Java generell langsamer als z.B. in C++.

### Die main()-Methode

Da Java zu 100% Objektorientiert ist, ist selbst das Programm nur ein Objekt. Jedes Programm hat eine *main()*-Funktion, die als Einstiegspunkt dient, damit der *Interpreter* weiß, was zu tun ist.

Um das zu veranschaulichen, hier das bekannte "Hello-World!" Beispiel:

```java
public class HelloWorld
{
    public static void main(String[] args)
    {
        System.out.println("Hello World!");
    }
}
```

- Die Hauptklasse des Programms heißt *HelloWorld*.
- Diese Klasse besitzt die Funktion *main()* mit folgenden Eigenschaften:
  - Sie ist *public*, kann also von einem anderen Objekt ausgeführt werden.
  - Sie ist *static*, d.h. existiert pro Klasse nur einmal.
  - Sie ist *void*, d.h. sie gibt keinen Wert zurück, bzw. hat kein festes Ergebnis.
  - Sie heißt *"main"*
  - Der *"(String[] args)"*-Parameter kann weitere Argumente beim Ausführen an die Funktion weitergeben, d.h. wenn das Programm in der Konsole mit "helloworld.exe -f -j" gestartet wird, ist die Variable "args" gleich ['-f','-j'], also ein Array aus mehreren Strings.
  - In der Funktion wird der Befehl *System.out.println("Hello World!");* ausgeführt, der einfach *Hello World* in der Konsole ausgibt.

 

### Syntax

Der **Syntax**, also wie Code in Java strukturiert und artikuliert werden muss, ist recht eindeutig:

- Befehle werden immer als *befehl();* geschrieben, also mit Klammern und einem Semikolon.
- Funktionsblöcke werden immer in *{}* gefasst.
- Arrays stehen in *[ ]* Klammern.
- Es kann eingerückt und verschoben werden, wie nur möglich, aber die {} und ; Zeichen müssen gesetzt werden.
- Einzeilige Kommentare werden mit // und mehrzeilige mit /* und */ geschrieben.

### Alles weitere

...wird in den folgenden Abschnitten detailliert erklärt.

## 🎰 Datentypen <a name="kap4"></a>

Wann immer etwas neues im **Speicher** abgelegt werden soll, müssen dessen Zugriffsrechte und der Datentyp festgelegt werden.

### Zugriffsrechte

Bei der Erstellung muss mithilfe eines **Zugriffsmodifikators** festgelegt werden, von wo auf die Daten zugegriffen werden kann. Sie können festgelegt werden für *Klassen, Variablen & Methoden* - Folgendes ist Möglich:

| Code           | Beschreibung                                        |
| -------------- | --------------------------------------------------- |
| *Standardwert* | Sichtbar für das Programmpaket.                     |
| `public`       | Sichtbar für alle.                                  |
| `private`      | Sichtbar innerhalb der eigenen Klasse.              |
| `protected`    | Sichtbar für das Programmpaket und alle Subklassen. |

### 💫Modifikatoren

Abseits der Zugriffsmodifikatoren können sogenannte **Nicht-Zugriffs Modifikatoren** festgelegt werden.

| Code       | Gilt für                        | Beschreibung                                                 |
| ---------- | ------------------------------- | ------------------------------------------------------------ |
| `static`   | *Klassen, Methoden*             | Begrenzt die Erstellung auf ein Exemplar pro Klasse          |
| `final`    | *Klassen, Methoden & Variablen* | Verhindert eine Änderung nach der Erstellung.                |
| `abstract` | *Klassen, Methoden*             | Verhindert Initialisierung (Erstellung) als Objekt, Subklassen können aber noch initialisiert werden. |

### Datentypen

Bei der Erstellung von **Variablen** muss der Typ festgelegt werden, also was gespeichert werden soll.

| Code       | Wertebereich                                       | Beschreibung                                                 |
| ---------- | -------------------------------------------------- | ------------------------------------------------------------ |
| ❕`boolean` | `true` oder `false`                                | Ist wie ein Schalter - kann nur aktiviert oder deaktiviert werden. |
| `byte`     | `-128` bis `127`                                   | Speichern von kleineren ganzen Zahlen.                       |
| `short`    | `-32768` bis `32767`                               | Speichern von etwas größeren Ganzzahlen.                     |
| ❕`int`     | `-2147483648` bis `2147483647`                     | Speichern von großen Ganzzahlen, wird am häufigsten verwendet. |
| `long`     | `-9223372036854775808` bis `9223372036854775808`   | Speichern von sehr großen Ganzzahlen.                        |
| ❕`float`   | `3.4e−038` bis `3.4e+038`                          | Speichern von Kommazahlen.                                   |
| `double`   | `1.7e−308` bis `1.7e+038`                          | Speichern von sehr kleinen Kommazahlen.                      |
| `char`     | Buchstabe / Zeichen                                | Speichern einzelner Buchstaben / Zeichen.                    |
| ❕`String`  | `Array` mehrerer `char`'s                          | Speichern von längeren Sätzen oder Wörtern.                  |
| `[]`       | `Array` enthält *Variablen, Objekte, Arrays, etc.* | Speichern beliebiger Daten an einem Ort. Kann gut durch Loops erstellt und abgerufen werden. |

### Beispiel

```java
// Erstelle zwei Integers, die gleich einem Wert zugewiesen werden.
int posX = 89;
int posY = -1200;

// Erstelle einen Boolean und setzte ihn danach auf true.
boolean schalter1;
schalter1 = true;

// Erstelle eine Kommazahl, die noch keinen Wert hat.
double preis = 0.93127;

// Erstelle einen String, der festgelegt wird.
String name = "Abigall";

// Gebe alle Daten in der Konsole aus, zum Testen:
System.out.println("posX: " + posX);
System.out.println("poxY: " + posY);
System.out.println("schalter1: " + schalter1);
System.out.println("preis: " + preis);
System.out.println("name: " + name);

```

*Kopiere diesen Code ruhig in Greenfoot und führe ihn aus! z.B. könntest Du ihn in den Konstruktur (nach dem super(); ) der aktuellen Welt einfügen und dann per*`Rechtsklick > new MyWorld()` *auf die Welt den Code ausführen.*

## 👨‍💻 Rechnen mit Variablen <a name="kap5"></a>

Mithilfe des `=` Operators lässt sich eine **Variable zuweisen**. Das lässt sich nutzen. Auf der rechten Seite kann deshalb auch eine Rechnung stehen, die wird vom Programm dann zuerst ausgerechnet und dann ganz normal zugewiesen. Normale Rechenoperatoren wie `+ - * / ()` werden ganz normal verstanden.

Außerdem lassen sich spezielle Mathe-Funktionen zur Berechnung nutzen.

### Beispiel

```java
// Erstelle eine Variable
int ergebnis;

// Berechnung irgendeiner Formel
// Das Ergebnis wird der Variable zugewiesen
ergebnis = (6+3)*2-1;

// Gebe das Ergebnis aus:
// Erwartungswert: 6+3 = 9 und 9*2 = 18 und 18-1 = 17.
System.out.println("Ergebnis: " + ergebnis);

// Eine weitere Rechnung:
double einViertel = 1/4;
double zweiViertel = 1*0.5;

// Ausgabe:
System.out.println("einViertel: " + einViertel + " zweiViertel: " + zweiViertel);
```

