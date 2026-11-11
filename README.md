# trailquest-data

Données statiques des maquettes de trail, servies par GitHub Pages à l'app iOS (le code de l'app est dans un dépôt privé).

Adresse de base : `https://pauljupilliat.github.io/trailquest-data/hex/`

## Structure

```
hex/index.json              liste des hexagones disponibles (nom, centre, km de sentiers, altitudes)
hex/<id-h3>/trails.json     sentiers éligibles découpés en tronçons, et lieux à tamponner
hex/<id-h3>/meta.json       fenêtre de relief : {"half": mètres, "dem": points par côté, "low": m, "top": m}
hex/<id-h3>/dem.bin         relief : entiers 16 bits non signés petit-boutistes, altitude = valeur / 10 − 1000
hex/<id-h3>/sat.jpg         orthophoto de la même fenêtre, nord en haut
```

Un hexagone est une cellule [H3](https://h3geo.org) de résolution 6 (environ 35 km²). Le relief et l'orthophoto couvrent une fenêtre carrée centrée sur l'hexagone, de `half` mètres de chaque côté.

Couverture actuelle : 28 km autour du Grand-Bornand (Haute-Savoie), soit 71 hexagones.

## Sources et licences

- **Sentiers et lieux** (`trails.json`) : © les contributeurs d'OpenStreetMap, sous licence [ODbL](https://opendatacommons.org/licenses/odbl/). Ces fichiers sont des données dérivées d'OpenStreetMap et restent sous ODbL.
- **Relief et orthophotos** (`dem.bin`, `sat.jpg`) : © IGN, [Licence Ouverte Etalab 2.0](https://www.etalab.gouv.fr/licence-ouverte-open-licence/), via la Géoplateforme.

L'app affiche ces attributions sur chaque maquette.
