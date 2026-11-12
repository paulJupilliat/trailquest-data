# trailquest-data

Données statiques des maquettes de trail, servies par GitHub Pages à l'app iOS (le code de l'app est dans un dépôt privé).

Adresse de base : `https://pauljupilliat.github.io/trailquest-data/hex7/` (hexagones de 2,8 km, résolution H3 7).
L'ancienne adresse `…/hex/` (hexagones de 7,3 km, résolution 6) reste servie pour les versions de l'app qui l'utilisent encore.

## Structure

```
hex7/index.json             liste des hexagones disponibles (nom, centre, km de sentiers, altitudes)
hex7/<id-h3>/trails.json    sentiers éligibles découpés en tronçons, et lieux à tamponner
hex7/<id-h3>/meta.json      fenêtre de relief : {"half": mètres, "dem": points par côté, "low": m, "top": m}
hex7/<id-h3>/dem.bin        relief : entiers 16 bits non signés petit-boutistes, altitude = valeur / 10 − 1000
hex7/<id-h3>/sat.jpg        orthophoto de la même fenêtre, nord en haut
```

Un hexagone est une cellule [H3](https://h3geo.org) de résolution 7 (environ 5 km², 2,8 km de large). Le relief (256 points par côté) et l'orthophoto (1024 pixels) couvrent une fenêtre carrée centrée sur l'hexagone, de `half` mètres de chaque côté. Un hexagone qui a moins de 1,5 km de sentiers éligibles n'est pas publié.

Couverture actuelle : 909 hexagones.

- 28 km autour du Grand-Bornand (Haute-Savoie) : 497 hexagones
- 25 km autour d'Orléans (Loiret) : 412 hexagones

## Sources et licences

- **Sentiers et lieux** (`trails.json`) : © les contributeurs d'OpenStreetMap, sous licence [ODbL](https://opendatacommons.org/licenses/odbl/). Ces fichiers sont des données dérivées d'OpenStreetMap et restent sous ODbL.
- **Relief et orthophotos** (`dem.bin`, `sat.jpg`) : © IGN, [Licence Ouverte Etalab 2.0](https://www.etalab.gouv.fr/licence-ouverte-open-licence/), via la Géoplateforme.

L'app affiche ces attributions sur chaque maquette.
