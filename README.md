# 🌦️ AeroSim 2D — Simulation météo interactive

Sandbox météo 2D interactive permettant de modifier le terrain et l'atmosphère, puis d'observer leurs interactions en temps réel.

## 🚀 Démo

**GitHub Pages :** https://tabodevmc.github.io/weathersimulation/

Le projet fonctionne directement dans le navigateur et ne nécessite pas de serveur backend.

## ✨ Fonctionnalités

### 🗺️ Carte de simulation

La simulation repose sur une grille 2D de **90 × 60 cellules** avec plusieurs couches d'affichage :

- 🌍 Vue réaliste / composite
- 📡 Radar des précipitations
- ⛰️ Élévation
- 🌡️ Température
- 💧 Humidité
- 💨 Vent
- 🏭 Pollution

### 🌤️ Variables météorologiques

La simulation fait évoluer notamment :

- Température
- Humidité
- Vent horizontal
- Nuages
- Précipitations
- Pollution atmosphérique

Les variables interagissent entre elles : la température influence l'humidité, le vent transporte les propriétés atmosphériques et le relief modifie localement le vent, l'humidité et les précipitations.

### ⛰️ Influence du relief

Le relief intervient directement dans la météo simulée :

- pente et différence d'altitude utilisées pour modifier le vent ;
- accélération du vent sur les zones exposées ;
- ralentissement sous le vent ;
- influence de l'altitude sur la température ;
- influence du relief sur l'humidité ;
- soulèvement orographique favorisant les nuages ;
- précipitations renforcées lorsque l'humidité et la couverture nuageuse sont suffisantes.

L'objectif est de reproduire progressivement des mécanismes comme l'effet orographique et l'ombre pluviométrique.

### 💨 Vent

Le vent possède une échelle de couleurs dédiée permettant de distinguer les vitesses élevées :

| Vitesse | Couleur indicative |
|---:|---|
| 0–10 km/h | Bleu nuit |
| 10–25 km/h | Turquoise |
| 25–40 km/h | Cyan |
| 40–60 km/h | Bleu |
| 60–80 km/h | Orange |
| 80–100 km/h | Rouge |
| 100–120 km/h | Magenta |
| 120+ km/h | Blanc |

La carte conserve ainsi du contraste au-dessus de 80 km/h.

Le vent est également représenté par des particules animées et son comportement est influencé par le relief.

### 🌧️ Nuages et précipitations

La formation des nuages et de la pluie est progressive :

- l'humidité élevée favorise la formation nuageuse ;
- le soulèvement lié au relief augmente l'humidité effective ;
- la pluie augmente progressivement lorsque les nuages sont suffisamment chargés ;
- les précipitations consomment progressivement de l'humidité ;
- la température influence également le comportement des précipitations.

### 🧰 Outils de simulation

La barre d'outils permet notamment d'agir directement sur la simulation :

- **Élever** le terrain
- **Abaisser** le terrain
- **Chauffer**
- **Refroidir**
- **Humidifier**
- **Assécher**
- **Polluer**
- **Nettoyer**
- **Source de vent**
- **Station météo**
- **Dépression**
- **Anticyclone**
- **Orage**
- **Blizzard**
- **Inspection**

Les actions peuvent être utilisées pendant la simulation afin d'observer leurs effets.

### 📍 Stations météo

Des stations peuvent être placées sur la carte pour suivre localement :

- température ;
- humidité ;
- vitesse du vent ;
- pollution.

Un historique est conservé pour les mesures et affiché avec des graphiques.

### 📊 Statistiques

L'interface affiche notamment :

- température moyenne ;
- couverture nuageuse ;
- taux de précipitations ;
- qualité moyenne de l'air.

Les mises à jour des statistiques et des graphiques sont limitées afin de réduire les pics de calcul et les micro-saccades.

## ⏯️ Simulation

La boucle principale utilise `requestAnimationFrame` pour l'affichage et exécute les pas de simulation séparément. La simulation peut être mise en pause et sa vitesse peut être ajustée depuis l'interface.

## ⚡ Performances

Plusieurs optimisations ont été mises en place :

- grille compacte de 5 400 cellules ;
- télémétrie des stations limitée en fréquence ;
- graphiques mis à jour moins fréquemment que le rendu ;
- échelle de couleurs du vent réutilisée au lieu d'être recréée pour chaque cellule ;
- redimensionnement du canvas effectué uniquement lorsque ses dimensions changent.

## 🛠️ Technologies

Le prototype météo actuel est principalement basé sur :

- **HTML**
- **CSS**
- **JavaScript**
- **Canvas 2D**
- **Chart.js**
- **GitHub Pages**

Le fichier principal de la simulation est `index.html`.

## 💻 Installation locale

Le prototype actuel est autonome et peut être ouvert directement dans un navigateur.

Pour récupérer le projet :

~~~bash
git clone https://github.com/TABOdevMC/weathersimulation.git
cd weathersimulation
~~~

Puis ouvrir `index.html` dans un navigateur, ou utiliser un serveur statique local.

## 📦 Déploiement

Le projet est publié avec **GitHub Pages**.

**URL de production :**

https://tabodevmc.github.io/weathersimulation/

Le dépôt contient également la configuration historique Vite/React du projet ; le prototype météo actuellement déployé est une version autonome centrée sur `index.html`.

## 📁 Structure actuelle

~~~text
weathersimulation/
├── .github/
│   └── workflows/
├── index.html          # Application météo 2D autonome
├── package.json        # Configuration du projet
├── vite.config.js
└── README.md
~~~

## 🎯 Objectif

Le projet sert de laboratoire pour expérimenter progressivement les relations :

**terrain → vent → ascendance → humidité → nuages → précipitations → transport atmosphérique**

L'objectif est d'enrichir progressivement la simulation pour obtenir une météo 2D plus cohérente et interactive, tout en conservant une expérience fluide dans le navigateur.

## 📄 Licence

Aucune licence open source spécifique n'est actuellement déclarée.
