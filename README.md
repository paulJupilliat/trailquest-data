# trailquest-data

Données statiques des maquettes de trail, servies par GitHub Pages à l'app iOS (le code de l'app est dans un repo privé).

## Structure prévue

```
hex/index.json              liste des hexagones disponibles
hex/<id-h3>/dem.png         relief (encodage terrarium)
hex/<id-h3>/sat.jpg         orthophoto
hex/<id-h3>/trails.json     sentiers éligibles et lieux (tampons)
```

Un hexagone = une cellule H3 de résolution 6. Couverture : France métropolitaine.

## Sources et licences

- Sentiers et lieux : © contributeurs OpenStreetMap, sous licence [ODbL](https://opendatacommons.org/licenses/odbl/). Les fichiers `trails.json` sont des données dérivées d'OSM et restent sous ODbL.
- Orthophotos : © IGN, [Licence Ouverte Etalab 2.0](https://www.etalab.gouv.fr/licence-ouverte-open-licence/).
- Relief : © IGN (RGE ALTI), Licence Ouverte Etalab 2.0, ou AWS Terrain Tiles selon les zones (attribution des sources indiquée dans `hex/index.json`).

L'app affiche ces attributions.
