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
- [ ] Partie 6 - Diagramme circulaire (Pie Chart)
- [ ] Partie 7 - Plusieurs courbes sur un même graphique
- [ ] Partie 8 - Sauvegarde des graphiques
- [ ] Partie 9 - Bonus
