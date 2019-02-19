# Filius Lernzettel 🖥

Die Lernsoftware **Filius** dient der Visualisierung von Netzwerken und dessen Konfiguration.

## Inhalt

1. 🎨 [Interface](#kap1)
2. 🎰 [Rechner](#kap2)
3. 🔌 Switch
4. 🔩 Router
5. 🔗 Modem

## 🎨 Interface <a name="kap1"></a>

##### Simulation

- Es ist möglich, zwischen dem "🔨 Baumodus" und dem "▶ Simulationsmodus" zu wechseln.
  - Der "🔨 Baumodus" dient dem Platzieren von Geräten, wie auch dem konfigurieren der Netzwerkoptionen dieser Geräte.
  - Der "▶ Simulationsmodus" ermöglicht den Zugriff auf die Software der Geräte und startet die Geräte. Man zieht außerdem, wann wo Daten fließen.
- Die Prozentanzeige ermöglicht die Simulationsgeschwindigkeit zu regeln.

##### Aufbau

- Im Hauptfenster können die Geräte platziert werden, ein Doppelklick auf ein Gerät öffnet dessen Konfiguration.
- Der "✏ Bleistift" ermöglicht das Kommentieren und Strukturieren des Netzwerkes.

##### Konfiguration

- Für jedes Gerät öffnet sich am unteren Rand ein Fenster mit allen Einstellungsmöglichkeiten.

## 🎰 Rechner <a name="kap2"></a>

**Rechner**, bzw. auch **Notebooks** *(Die Funktionalität ist dieselbe.)* können folgende Eigenschaften haben:

![1550586572144](../img/1550586572144.png)

| Option      | Beschreibung                                                 |
| ----------- | ------------------------------------------------------------ |
| Name        | Die Namen der Geräte werden im Hauptfenster angezeigt.<br />Sinnvoll, um klar den Zweck eines Gerätes zuordnen zu können. |
| MAC-Adresse | ***Kann nicht geändert werden!*** - Hardwaregebundene Adressen, um IP-Adressen (z.B. durch DHCP) zuordnen zu können. |
| IP-Adresse  | *Kann entweder manuell eingetragen werden oder per DHCP zugeordnet werden.*<br />⚠ **Wichtig:** Um ohne Gateway kommunizieren zu können, müssen die IP-Adressen im selben Subnetz liegen! (Siehe [Netzwerktechnik](NETZWERKE.md)) |
| Netzmaske   | *Wird im Falle eines DHCPs automatisch übermittelt.*<br />Gibt an, mit welchem Adressbereich das Gerät kommunizieren kann. (Siehe [Netzwerktechnik](NETZWERKE.md)) |
| Gateway     | *Wird im Falle eines DHCPs automatisch übermittelt.*<br />Gibt an, wohin Daten gesendet werden sollen, wenn der Empfänger nicht im selben (Sub-)Netz liegt. |
| DNS         | *Wird im Falle eines DHCPs automatisch übermittelt.*<br />Gibt an, wo die IP-Adressen zu Domains (z.B. "google.de") nachgeschaut werden sollen. |

##### Software

Auf jedem PC / Notebook können folgende Programme installiert werden:
*(Ein paar sind ausgelassen, die nicht verwendet werden.)*

| Name             | Beschreibung                                                 |
| ---------------- | ------------------------------------------------------------ |
| **Befehlszeile** | Per Befehl können vor allem (z.B. durch *ping* oder *traceroute*) Verbindungen getestet werden. |
| Bildbetrachter   | Im Dateisystem hinterlegte Bilder können hiermit angezeigt werden. |
| Datei-Explorer   | Ermöglicht den *Zugriff auf das Dateisystem*. Es ist auch möglich, Dateien in Filius zu importieren. |
| **DNS-Server**   | Ergänzt die *DNS-Funktionalität* in einem Rechner. Die IP des Rechners muss dann als DNS-Server andererorts eingetragen werden. |
| Firewall         | Ermöglicht das Blockieren von Ports auf dem System.          |
| Text-Editor      | Ermöglicht das Editieren von Dateien im Dateisystem.         |
| **Webserver**    | Ergänzt *HTTP-Server-Funktionalität* im Rechner. Die im Ordner "webserver" hinterlegten Dateien werden über die IP-Adresse fürs Netzwerk zugänglich gemacht. |
| **Webbrowser**   | Aufrufen von *Html-Seiten* über das Netzwerk.                |

##### Webserver

Jeder Webserver muss über das Fenster gestartet werden. Dort können auch "Virtuelle Hosts" aktiviert werden.

Im **Dateisystem** sehen die Server so aus:

```
> webserver
  > index.html
  > splashscreen-mini.png
```

- Die *Index*-Datei wird grundsätzlich immer aufgerufen, wenn in der Adresszeile keine spezielle Datei angegeben ist. Ein Aufruf von `http://192.168.0.10/datei.html` öffnet `datei.html`. Wenn in der URL keine Datei angegeben ist ( `http://192.168.0.10/` ), wird immer automatisch die `index.html` Datei aufgerufen.
- Die `splashscreen-mini.png` Datei wird in der HTML Datei verwendet, auch das ist möglich.

Es können außerdem sogenannte **virtuelle Server** erstellt werden. Dazu muss in der Software einfach der Haken gesetzt werden. Dann können zusätzliche Websites konfiguriert werden:

![1550590104607](../img/1550590104607.png)

In diesem Beispiel wird über den Link `http://192.168.0.10/yey` die Website `webserver/lol/index.html` aufgerufen. Oder wahlweise über `http://192.168.0.10/yey/web.html` die Seite `webserver/lol/web.html`. Das Dateisystem könnte mit virtuellen Server z.B. so aussehen:

```
> webserver
  > index.html
  > splashscreen-mini.png
  > doogle
    > index.html
    > suche.html
    > logo.png
  > github
    > index.html
    > awesome.html
```

