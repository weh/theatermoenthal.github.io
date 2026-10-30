# Personen und Produktionen pflegen

Personen sind zentrale, wiederverwendbare Datensätze in `data/people.yaml`. Der Schlüssel ist die unveränderliche Personen-ID. Namen und Porträts werden nur dort gepflegt.

```yaml
people:
  anna-muster:
    name: Anna Muster
    image: images/people/anna-muster.jpg
    imageAlt: Porträt von Anna Muster
```

Lege das Porträt unter `themes/theater-moenthal/static/images/people/anna-muster.jpg` ab. `image` und `imageAlt` sind optional; ohne Bild zeigt die Website einen neutralen Platzhalter.

## Eine Person einer Produktion zuordnen

In `data/current-play.yaml` und in jedem Eintrag von `data/archive.yaml` verwendet `credits` dieselbe Struktur. `person` verweist auf die ID aus `people.yaml`; `role` ist bewusst Teil der Produktion. Dadurch kann dieselbe Person in einer anderen Saison mit einer anderen Rolle auftauchen.

```yaml
credits:
  - heading: Besetzung
    entries:
      - person: anna-muster
        role:
          name: Frau Müller
          description: Optionale Beschreibung der Figur
  - heading: Hinter der Bühne
    entries:
      - person: ben-beispiel
        role:
          name: Regie
```

Weitere Gruppen sind möglich, etwa `Technik`, `Maske` oder `Musik`. Eintrag und Gruppe werden nur angezeigt, wenn die referenzierte Personen-ID existiert.
