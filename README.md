# Atelier Matplotlib - Mesures capteurs IoT

## Contexte

Une entreprise possède plusieurs bâtiments équipés de capteurs IoT. Chaque capteur collecte
régulièrement des informations sur la température, l'humidité, la pression, la consommation
énergétique et l'état du capteur.

Ce projet représente graphiquement ces données avec Matplotlib afin d'identifier des tendances,
des différences entre bâtiments et des anomalies.

## Structure du projet

```
atelier_matplotlib_iot/
│
├── data/
│   └── mesures_capteurs.csv
│
├── notebooks/
│   └── atelier_matplotlib_iot.ipynb
│
└── exports/
    ├── temperature.png
    └── temperature.pdf
```

## Installation

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Utilisation

```bash
source .venv/bin/activate
jupyter notebook notebooks/atelier_matplotlib_iot.ipynb
```

## Avancement

- [x] Structure du projet, environnement virtuel, `requirements.txt`, `.gitignore`
- [x] Partie 1 - Graphique linéaire (Line Plot)
- [x] Partie 2 - Diagramme en barres (Bar Chart)
- [x] Partie 3 - Histogramme
- [x] Partie 4 - Nuage de points (Scatter Plot)
- [x] Partie 5 - Diagramme à moustache (Box plot)
- [x] Partie 6 - Diagramme circulaire (Pie Chart)
- [x] Partie 7 - Plusieurs courbes sur un même graphique
- [x] Partie 8 - Sauvegarde des graphiques
- [x] Partie 9 - Bonus (dashboard récapitulatif avec subplots)

## Détail des parties

### Partie 1 - Graphique linéaire (Line Plot)

Évolution de la température en fonction du temps (titre, labels, légende, grille).
Deux anomalies clairement visibles : un pic proche de **58°C** et un creux proche de **-18°C**,
très en dehors de la plage normale (~15-35°C).

### Partie 2 - Diagramme en barres (Bar Chart)

Calcul de `consommation_batiment` (consommation moyenne par bâtiment), puis comparaison en
barres verticales et horizontales. **B004** est le bâtiment le plus énergivore (~283), **B003**
le moins énergivore (~153). Discussion sur les cas où l'orientation horizontale est plus lisible
(catégories nombreuses ou aux noms longs, lecture en classement, contrainte d'espace).

### Partie 3 - Histogramme

Distribution des températures (20 classes, grille horizontale uniquement) : concentration entre
~20°C et ~30°C, forme globalement symétrique en cloche, avec les mêmes valeurs aberrantes déjà
repérées en Partie 1. Distribution de la consommation testée avec 10, 20 et 30 classes : moins
de classes lisse la tendance générale, plus de classes révèle davantage de détails (dont un
outlier proche de 875) mais rend le graphique plus bruité.

### Partie 4 - Nuage de points (Scatter Plot)

Nuage de points température vs consommation. Pas de relation linéaire nette visuellement ;
coefficient de corrélation calculé ≈ **0.32** (corrélation positive mais faible).

### Partie 5 - Diagramme à moustache (Box plot)

Box plots séparés pour la température et la consommation (valeurs manquantes supprimées, grille
horizontale uniquement). Les points hors moustaches représentent les valeurs extrêmes
(> 1.5×IQR). Comparaison des deux box plots : médianes centrées dans leur boîte, boîte et
moustaches nettement plus larges pour la consommation. Coefficient de variation ≈ 35 % pour la
consommation contre ≈ 16 % pour la température : la consommation est relativement plus dispersée.

### Partie 6 - Diagramme circulaire (Pie Chart)

Répartition des états des capteurs : **OK 94.3 %**, **ALERTE 4.8 %**, **ERREUR 0.8 %**. Le parc
de capteurs est donc majoritairement fiable, avec une part d'alertes à surveiller et une part
d'erreurs marginale mais non nulle.

### Partie 7 - Plusieurs courbes sur un même graphique

Évolution de la température des 4 bâtiments (B001 à B004) sur un même graphique. Les deux
anomalies de température repérées en Partie 1 (pic ~58°C, creux ~-18°C) appartiennent toutes les
deux au bâtiment **B004**.

### Partie 8 - Sauvegarde des graphiques

Le graphique de la Partie 1 est exporté dans `exports/temperature.png` et `exports/temperature.pdf`.

### Partie 9 - Bonus : dashboard récapitulatif

Une figure unique à 4 sous-graphiques (`plt.subplots`) réunissant l'évolution de la température,
la consommation moyenne par bâtiment, la distribution des températures et la répartition des
états, pour une vue d'ensemble rapide du parc de capteurs.
