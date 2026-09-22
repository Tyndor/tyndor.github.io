# tyndor.github.io

Entwickler-Seite von SJR App Development, ausgeliefert über GitHub Pages unter
<https://tyndor.github.io/>.

Zweck:

* **Übersicht der Apps** (`index.html`) — je App ein `<article class="app">`
  mit Banner, einem Absatz und einem Verweis. Mehr steht dort nicht.
* **Eine Seite je App** (`buerofauna.html`, `stapelhaus.html`) — Text,
  Bildschirmfotos, Store-Abzeichen, Verweis auf ihre Datenschutzerklärung.

  **Stapelhaus trägt statt der Abzeichen die Marke „In Arbeit"**
  (`<span class="bald">`): Die App ist noch nicht veröffentlicht, ein
  Abzeichen führte ins Leere, und Bildschirmfotos aus einer App, die sich noch
  ändert, wären am Tag der Veröffentlichung falsch. Ihre
  Datenschutzerklärung steht trotzdem schon — die muss vor dem ersten
  Store-Eintrag da sein, nicht danach.

  **Bis zum 2026-09-21 war beides dasselbe** (Nutzer-Wunsch): Die Startseite
  WAR die Seite von Bürofauna. Mit der zweiten App wäre daraus eine Seite
  geworden, die man erst durchscrollt, um die zweite zu finden. Eine weitere
  App ist jetzt eine kopierte Datei plus ein Block in der Übersicht.
* **Impressum** (`impressum.html`) — gilt für die Seite und alle Apps.
* **Datenschutz dieser Seite** (`datenschutz.html`) — nur das Hosting. Die
  Datenschutzerklärungen der Apps liegen getrennt davon, für Bürofauna unter
  <https://tyndor.github.io/buerofauna-legal/datenschutz.html>.
* **`app-ads.txt`** — muss in der WURZEL der Domain liegen, sonst findet der
  Crawler sie nicht. Die Datei gilt für alle Apps, deren Store-Eintrag auf
  diese Website zeigt; sie nennt Anzeigenquellen, keine Apps.

## Drei Anzüge

`stil.css` trägt den Hausstil in `:root` und je App eine Klasse, die
DIESELBEN Variablen übersteuert — kein zweites Regelwerk, nur andere Werte.
Wo die Klasse hängt, entscheidet, wie weit der Anzug reicht:

| Seite | Klasse an | Wirkung |
|---|---|---|
| `buerofauna.html`, `stapelhaus.html` | `<body>` | die ganze Seite im Look der App |
| `index.html` | `<article class="app …">` | nur ihr Block; der Rahmen bleibt Hausstil |
| `impressum.html`, `datenschutz.html` | nichts | Hausstil — sie gehören dem Entwickler, nicht einer App |

Die Werte stammen aus den Apps selbst (Farben, Schrift, Rundung, Gewicht der
Überschriften) und stehen genauso auf den beiden Rechtstext-Seiten. Verbunden
sind die drei Orte nur durch diesen Satz: Wer eine Farbe in der App ändert,
ändert sie hier mit.

Keine Build-Schritte, keine Abhängigkeiten: reines HTML und eine CSS-Datei.
Die Bilder unter `bilder/` sind herunterskalierte Fassungen aus dem
App-Repository (`store/screenshots/`, `store/feature-grafik-1024x500.png`).
Je App ein Banner: `banner.png` ist Bürofaunas Vorstellungsgrafik,
`banner-stapelhaus.png` die von Stapelhaus — unverändert übernommen, denn sie
ist bereits 1024 × 500 und gilt als fertig geliefert.

Die acht `schuss-*.png` werden nicht von Hand skaliert, sondern im
App-Repository erzeugt:

```
dart run tool/make_web_screenshots.dart <pfad-zu-diesem-repo>/bilder
```

Das Werkzeug nimmt den kompletten Satz aus `store/screenshots/`, bringt ihn
auf 380 px Breite und benennt ihn nach der Reihenfolge der Motive um. Nach
einem neuen Screenshot-Satz also einmal laufen lassen und die
Bildbeschreibungen in `buerofauna.html` gegenlesen — sie beschreiben, was zu
sehen ist, und veralten genauso wie die Bilder.
