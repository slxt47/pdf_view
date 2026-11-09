# pdf_view

Eine Mini-Webseite, die ein PDF bildschirmfüllend im Browser anzeigt, mit Leiste für
„In neuem Tab“ und „Herunterladen“. Ich nutze sie z. B. für ein Schul-Handout.

## Aufbau

```
index.html
dokument.pdf      ← Standard-Datei
favicon.ico       ← optional
```

## Benutzen

- PDF als `dokument.pdf` neben die `index.html` legen, **oder**
- eine andere Datei über die Adresse wählen: `https://example.org/?pdf=handout.pdf`
  (auch in Unterordnern: `?pdf=docs/plan.pdf`).

Aus Sicherheitsgründen werden nur `.pdf`-Dateien von derselben Seite angenommen, keine
fremden Adressen und kein `..`.

Läuft mit jedem statischen Webserver, z. B.:

```bash
docker run -d -p 8080:80 -v "$PWD":/usr/local/apache2/htdocs:ro httpd:2.4
```

> Tipp: Safari auf dem iPhone zeigt PDFs in einem eingebetteten Rahmen oft nur mit der ersten
> Seite. Dafür gibt es oben „In neuem Tab“.

## Änderungen (Oktober 2026)

- Datei frei wählbar (`?pdf=`) statt fest eingebautem Dateinamen; Titel = Dateiname.
- Leiste mit „In neuem Tab“ / „Herunterladen“ (wichtig fürs iPhone).
- `lang="de"`, Viewport für Handys, README passt wieder zum Code.
