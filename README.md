# tyndor.github.io

Entwickler-Seite von SJR App Development, ausgeliefert über GitHub Pages unter
<https://tyndor.github.io/>.

Zweck:

* **Übersicht der Apps** (`index.html`) — je App ein `<article class="app">`
  mit Banner, einem Absatz und einem Verweis. Mehr steht dort nicht.
* **Eine Seite je App** (`buerofauna.html`) — Text, Bildschirmfotos,
  Store-Abzeichen, Verweis auf ihre Datenschutzerklärung.

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
Bildbeschreibungen in `buerofauna.html` gegenlesen — sie beschreiben, was zu
sehen ist, und veralten genauso wie die Bilder.
