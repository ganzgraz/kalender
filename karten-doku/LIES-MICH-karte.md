# ganzgraz-Karte – Kurzanleitung (Stand 09.11.2026)

Live: https://ganzgraz.github.io/kalender/karte.html (gleiches Passwort wie die Bildsuche)

## Was sie kann
- **Ein Ort**: Platz, Straße, Adresse oder Gebäude eingeben → Karte im CI mit Marker, Titel-Pille, Logo-Band. Fertig in ca. 1 s (Daten liegen als Kacheln im Repo, kein Overpass nötig).
- **Mehrere Orte** („Mehr“ aufklappen): einer pro Zeile → nummerierte Marker 1, 2, 3 … in Eingabereihenfolge. Optional `Ort | Beschriftung` (z. B. `Hauptbahnhof | Treffpunkt 18 Uhr`).
- **Strecke hervorheben**: ganze Straßen per Namen (`Annenstraße` oder `Keplerstraße, Wienerstraße`) oder eine Route `von Hauptbahnhof bis Jakominiplatz` – der Weg wird über das Grazer Straßennetz gesucht (kürzester Weg über benannte Straßen, keine Fußwege). Länge steht in der Infozeile. Mit `Annenstraße: von A bis B` nur über diese Straße.
- **Fläche hervorheben**: Bezirk (`Gries`, `Innere Stadt`), Park (`Stadtpark`, `Augarten`), Platz, Friedhof, Gewässer; mehrere mit Komma. Bezirksgrenzen aus OpenStreetMap.
- **Ausschnitt automatisch**: sobald mehr als ein Element im Spiel ist, wird der Ausschnitt so gewählt, dass alles drauf ist. Bei sehr weitem Ausschnitt (> 1,3 km) werden Gebäude automatisch weggelassen.

## Dateien
- `bildsuche/karte.html` = Live-Datei (Kopie in `karten/karte.html`), im Repo `ganzgraz/kalender` als `karte.html`.
- Repo-Ordner `kacheln/`: `t_i_j.json` (305 Kartenkacheln), `idx_namen.json` (Straßen, Orte, Adressen), `strassen.json` (Straßenzüge für Strecken), `flaechen.json` (Bezirke, Parks, Plätze …).
- Erzeugt aus `Graz.osm.pbf` (BBBike-Export) mit `karten/kacheln-bau/kacheln_bauen.py` und `extras_bauen.py` (brauchen `osmpbf.py` daneben, ~1 min). Bei einer OSM-Aktualisierung: neues PBF laden, beide Skripte laufen lassen, Ordner `kacheln/` hochladen.

## Regeln
- Keine Karten bei Unfallopfern oder Privatadressen.
- Unter der Karte im Newsletter: „Grafik: ganzgraz · Kartendaten: © OpenStreetMap-Mitwirkende“ (steht auch im Logo-Band).
- Immer prüfen, ob Marker/Strecke am richtigen Ort sitzen – Namensdoppelungen (z. B. „Hauptplatz“) nimmt die Suche nach Rang (Platz vor Gebäude).
