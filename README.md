# tyndor.github.io

Entwickler-Seite von SJR App Development, ausgeliefert über GitHub Pages unter
<https://tyndor.github.io/>.

Zweck:

* **Übersicht der Apps** (`index.html`) — je App ein `<article class="app">`.
  Eine weitere App ist ein kopierter Block, keine neue Seite.
* **Impressum** (`impressum.html`) — gilt für die Seite und alle Apps.
* **Datenschutz dieser Seite** (`datenschutz.html`) — nur das Hosting. Die
  Datenschutzerklärungen der Apps liegen getrennt davon, für Bürofauna unter
  <https://tyndor.github.io/buerofauna-legal/datenschutz.html>.
* **`app-ads.txt`** — muss in der WURZEL der Domain liegen, sonst findet der
  Crawler sie nicht. Die Datei gilt für alle Apps, deren Store-Eintrag auf
  diese Website zeigt; sie nennt Anzeigenquellen, keine Apps.

Keine Build-Schritte, keine Abhängigkeiten: reines HTML und eine CSS-Datei.
Die Bilder unter `bilder/` sind herunterskalierte Fassungen aus dem
App-Repository (`store/screenshots/`, `store/feature-grafik-1024x500.png`).

Die acht `schuss-*.png` werden nicht von Hand skaliert, sondern im
App-Repository erzeugt:

```
dart run tool/make_web_screenshots.dart <pfad-zu-diesem-repo>/bilder
```

Das Werkzeug nimmt den kompletten Satz aus `store/screenshots/`, bringt ihn
auf 380 px Breite und benennt ihn nach der Reihenfolge der Motive um. Nach
einem neuen Screenshot-Satz also einmal laufen lassen und die
Bildbeschreibungen in `index.html` gegenlesen — sie beschreiben, was zu sehen
ist, und veralten genauso wie die Bilder.
