# Visualisation E

Globe 3D interactif qui répond à la question : **combien d'avions, de bateaux, de véhicules et d'usines y a-t-il dans le monde ?**

Tout tient dans un seul fichier HTML autonome (`visualisation-e-local.html`, ~13 Mo). Les bibliothèques et les données y sont intégrées. Il suffit de l'ouvrir dans un navigateur, sans serveur ni installation. Seules les polices Google Fonts sont chargées depuis Internet.

## Couches

| Couche | Contenu | Sources principales |
|---|---|---|
| **Avions** | Positions en vol (instantané partiel), pic sur 7 jours, décollages par jour | OpenSky Network, Flightradar24, AirNav Radar |
| **Bateaux** | Flotte marchande 2025 sur des routes types (positions simulées) | UNCTAD, *Review of Maritime Transport 2025* (112 500 navires) |
| **Voitures et camions non électriques** | Véhicules thermiques et hybrides, 1 point = 1 000 véhicules, répartis par région | Eurostat `tran_r_vehst` (NUTS 2), registres nationaux, OICA |
| **Usines** | Unités de production, 1 point = 100 unités | Eurostat `sbs_r_nuts2021` (NACE C) ; hors UE : estimation à partir de la valeur ajoutée manufacturière (Banque mondiale) |

Les valeurs estimées (hors UE notamment) sont signalées comme telles dans l'interface.

## Utilisation

- Ouvrir `visualisation-e-local.html` dans un navigateur récent.
- Faire tourner le globe et zoomer à la molette ou par pincement.
- Activer ou désactiver les couches dans le panneau de gauche (en bas sur mobile).
- Les compteurs « dans le champ » suivent la zone visible.

## Technique

- Rendu du globe : [globe.gl](https://github.com/vasturiano/globe.gl) / three.js
- Frontières : TopoJSON (pays + régions NUTS)
- Données embarquées en JSON dans la page (`d-countries`, `d-nuts`, `d-data`)
