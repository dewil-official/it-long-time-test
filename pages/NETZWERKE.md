# Netzwerktechnik Lernzettel 🌇

Dies ist der Lernzettel für die IT Klausur, basierend auf dem letzten Lernzettel für die Netzwerktechnik-Klausur!

## Inhalt

1. [Wdhl. Zahlensysteme](#kap1)
2. Das OSI-Modell
3. IP-Adressen und Subnetze

## Zahlensysteme (Wdhl.) <a name="kap1"></a>

**Zahlen** werden heutzutage an jeder Ecke verwendet, wenn eine Menge oder ein Wert *fest definiert*
werden muss. Im Alltag verwenden wir normalerweise das **Dezimalsystem**, in dem genau **Zehn
verschiedene Zustände** pro Ziffer darstellt werden können. Das ist dahingehend praktisch, da der
Mensch selbst 10 Finger besitzt und so diese Werte leicht nachvollziehen kann. Anstatt von 0 bis 9 zu zählen, gibt es aber noch andere Möglichkeiten. *(Siehe Tabelle unten)*

**Binär und Hexadezimal** sind die populärsten anderen Zahlensysteme, allerdings kann man beliebig viele Zahlensysteme selbst erstellen, denn das Grundprinzip ist immer dasselbe. Jedes System zeichnet sich dadurch aus, wie viele Zustände sich in einer Stelle darstellen lassen. Dezimalzahlen (10er), Binär (2er) und Hexadezimal (16er). - So fängt man in einem 2er System schon bei der Zahl 3 an, eine zweite Ziffer vorne anzuhängen, im Dezimalsystem ab der Zahl 10 und im Hexadezimalsystem ab der 16.

| Dezimal | Binär | Hexadezimal |
| ------- | ----- | ----------- |
| 0       | 0     | 0           |
| 1       | 1     | 1           |
| 2       | 10    | 2           |
| 3       | 11    | 3           |
| 4       | 100   | 4           |
| 5       | 101   | 5           |
| 6       | 110   | 6           |
| 7       | 111   | 7           |
| 8       | 1000  | 8           |
| 9       | 1001  | 9           |
| 10      | 1010  | A           |
| 11      | 1011  | B           |
| 12      | 1100  | C           |
| 13      | 1101  | D           |
| 14      | 1110  | E           |
| 15      | 1111  | F           |

Welchen Wert hat nun die *Binärzahl 100*?
$$
Binär 100 => 1*2^2 + 0*2^1 + 0*2^0 => 1*4 + 0 + 0 => 4 Dezimal
$$

##### Tipp für die Klausur:

Umrechnungen kann man sich meist **sehr vereinfachen** und da wir am PC
schreiben, bietet sich die Verwendung des **Windows-Taschenrechners** an.
Dieser hat im Tab „Programmieren“ eine Umrechnungsfunktion eingebaut.

## Das OSI-Modell

Das *„Open Systems Interconnection Model“* ist ein **Referenzmodell**, das seit 1984 durch die ISO
(International Organization for Standardization) anerkannt wurde. Es stellt die **Netzwerkprotokolle
als unabhängige Ebenen** dar, die ineinander verkapselt dann genau so in der Praxis verwendet
werden. So sieht es aus:

| Ebene         | Orientierung | DoD-Schicht | Einordnung                          | Protokolle                | Geräte                    |
| ------------- | ------------ | ----------- | ----------------------------------- | ------------------------- | ------------------------- |
| 7 Anwendungen | Anwendung    | Anwendung   | Ende zu Ende                        | HTTP, DNS, DHCP, XMPP ... | Gateway, Proxy ...        |
| 6 Darstellung | Anwendung    | Anwendung   | Ende zu Ende                        | HTTP, DNS, DHCP, XMPP ... | Gateway, Proxy ...        |
| 5 Sitzung     | Anwendung    | Anwendung   | Ende zu Ende                        | HTTP, DNS, DHCP, XMPP ... | Gateway, Proxy ...        |
| 4 Transport   | Transport    | Transport   | Ende zu Ende                        | TCP, UDP ...              | Gateway, Proxy ...        |
| 3 Vermittlung | Transport    | Internet    | Ende zu Ende                        | ICMP, IP ...              | Router                    |
| 2 Sicherung   | Transport    | Netzzugriff | Direkte Verbindung (Punkt zu Punkt) | Ethernet, MAC             | Bridge, (Normaler) Switch |
| 1 Physisch    | Transport    | Netzzugriff | Direkte Verbindung (Punkt zu Punkt) | -                         | Kabel, Repeater, Hub      |

**Weitere Erläuterungen dazu:**

| Begriff            | Erklärung                                                    |
| ------------------ | ------------------------------------------------------------ |
| DoD                | Abgekürztes Schichtenmodell                                  |
| Ende zu Ende       | Paket kann über viele Rechner springen, hat aber einen Start und ein Ziel. |
| Direkte Verbindung | Beide Geräte müssen direkt miteinander verbunden sein.       |

**Was machen die einzelnen Ebenen?**

| Schicht         | Erklärung                                                    |
| --------------- | ------------------------------------------------------------ |
| 7 Anwendungen   | Was-auch-immer-der-Nutzer-machen-möchte. z.B. Spiele oder Email-Clients |
| 6 Darstellungen | **Übersetzt und verschlüsselt** die Daten auf Anwendungsebene, damit der Nutzer sie lesen kann. |
| 5 Sitzung       | Erstellt und verwaltet Verbindungen auf *Anwendungsebene*. Es wird sichergestellt, dass eine **Verbindung zwischen Programmen** dauerhaft aufrecht erhalten wird. |
| 4 Transport     | Je nach Paketprotokoll sollen hier die **Pakete** erstellt und etikettiert werden. Dazu müssen Netzwerkdaten in Blöcke unterteilt werden und es wird ein **Port** zugeordnet. |
| 3 Vermittlung   | Diese Ebene sorgt dafür, dass "Pakete" also *etikettierte Datenblöcke* über viele Rechner hinweg reisen können.<br />Dazu werden unter anderem **IP-Adressen** verwendet. Man nennt sie auch die "Netzwerk-Schicht". Die Pakete aus Schicht 4 werden mit einer IP-Adresse versehen und so versandfähig gemacht. |
| 2 Sicherung     | Soll die Verbindung absichern, indem 3.-Schicht Daten in "Frames" also **kleinere Blöcke** geteilt und durch "[Prüfsummen](https://www.it-talents.de/blog/it-talents/was-sind-pruefsummen-checksums)" **mathematisch abgesichert** werden. |
| 1 Physisch      | Kabelverbindungen oder "dumme" Geräte, denen die gesendeten Daten egal sind. |

## IP-Adressen und Subnetze

...