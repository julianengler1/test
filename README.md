# 3 in 1 Schreinerei St. Gallen &ndash; Website

Modernisierte, statische Website (reines HTML/CSS/JS, kein Build-Schritt nötig).

## Struktur

```
index.html              Startseite
dienstleistungen.html   Beraten / Planen / Bauen
produkte.html           Fenster, Bodenbeläge, Möbel, Reparatur ...
referenzen.html         Projektgalerie
ueber-uns.html          Team, Firmengeschichte, Partner
kontakt.html            Adressen, Karten, Kontaktdaten
css/style.css           Gesamtes Styling (Design-System, responsive)
js/main.js              Mobile-Navigation, Header-Scroll-State
assets/images/          Platzhalter-Grafiken (SVG)
sitemap.xml, robots.txt SEO-Basics
```

## Deployment

Alle Dateien sind statisch und können direkt auf jeden Webspace/Hosting
(z.B. bestehendes Hosting von dreiineins.ch), Netlify, Vercel oder GitHub
Pages hochgeladen werden. Kein Server-Rendering, keine Datenbank nötig.

Domain in `sitemap.xml`, `robots.txt` sowie den `canonical`/`og:*`-Tags ist
aktuell auf `https://www.dreiineins.ch` gesetzt &ndash; bei einer anderen
Ziel-Domain bitte in allen HTML-Dateien sowie `sitemap.xml`/`robots.txt`
anpassen.

## Bilder ersetzen

Die Referenz- und Team-Bilder unter `assets/images/` sind aktuell abstrakte,
markenfarbene Platzhalter-Grafiken (SVG), da die Original-Fotos der
bestehenden Website hier nicht verfügbar waren. `referenzen.html` und
`ueber-uns.html` verlinken bereits auf die künftigen echten Foto-Dateien im
`.jpg`-Format und fallen automatisch auf den Platzhalter zurück, solange die
Datei fehlt (`onerror`) &ndash; es reicht also, die Fotos mit exakt diesen
Dateinamen in `assets/images/` hochzuladen (z.B. per Drag & Drop im
GitHub-Webinterface), keine weitere Code-Änderung nötig:

```
assets/images/team-rolf-messmer.jpg
assets/images/team-sven-messmer.jpg
assets/images/team-beat-faessler.jpg
assets/images/team-gioele-gotadoro.jpg
assets/images/team-maurizio-heeb.jpg

assets/images/ref-fenster.jpg
assets/images/ref-wittenbach-bad.jpg
assets/images/ref-herisau-kueche.jpg
assets/images/ref-abtwil-tisch.jpg
assets/images/ref-stgallen-tv.jpg
assets/images/ref-stgallen-schrank.jpg
assets/images/ref-herisau-buero.jpg
```

Die beiden Firmenlogos (weru, UNILUX) sind aktuell als reine Text-Badges
gesetzt &ndash; bei Bedarf durch die offiziellen Partner-Logo-Dateien ersetzen.

## Kontaktformular

`kontakt.html` enthält ein echtes Kontaktformular (Name, E-Mail, Telefon,
Nachricht), das ohne eigenen Server über
[FormSubmit](https://formsubmit.co) direkt an `info@dreiineins.ch`
zustellt. Kein Account, keine Kosten. Einziger Schritt: **Bei der ersten
echten Formular-Einsendung** schickt FormSubmit eine
Aktivierungs-E-Mail an `info@dreiineins.ch` &ndash; dort einmal auf den
Bestätigungslink klicken, danach werden alle weiteren Anfragen automatisch
zugestellt. Ein verstecktes Honeypot-Feld reduziert Spam.

## Kontakt-E-Mail

Die E-Mail-Adresse `info@dreiineins.ch` ist eine Annahme basierend auf der
Domain, da auf der bestehenden Seite nur ein "Mail"-Link ohne sichtbare
Adresse vorhanden war. Bitte in `kontakt.html` und `index.html`/Footer aller
Seiten (`mailto:` und Klartext) durch die tatsächliche Adresse ersetzen,
falls abweichend.

## SEO

- Ein `<h1>` pro Seite, saubere H2/H3-Hierarchie
- Eigene, sprechende Permalinks je Unterseite (z.B. `/kontakt.html`)
- `<link rel="canonical">`, Open-Graph- und Twitter-Card-Tags je Seite
- JSON-LD (`schema.org/HomeAndConstructionBusiness`) inkl. Adressen,
  Telefonnummer und Breadcrumbs auf jeder Seite
- `sitemap.xml` und `robots.txt` im Root-Verzeichnis
