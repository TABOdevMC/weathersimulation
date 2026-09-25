# 🌦️ Weather Simulation

Sandbox météo 3D interactive permettant de modifier le terrain et l'atmosphère et d'observer leurs interactions.

## 🚀 Démo

**GitHub Pages :** https://tabodevmc.github.io/weathersimulation/

## ✨ Fonctionnalités

### 🌍 Terrain 3D
- Monde 3D interactif avec caméra orbitale
- Relief généré procéduralement
- Sculpture du terrain à la souris
- Outils **Élever**, **Creuser** et **Lisser**
- Taille de pinceau réglable
- Montagnes et vallées
- Eau visible et animée
- Végétation 3D

### 🌤️ Simulation météo

Paramètres modifiables en temps réel :
- 🌡️ Température
- 💧 Humidité
- 💨 Vitesse du vent
- 🌊 Présence de l'eau

Les biomes appliquent leurs propres effets sur les conditions atmosphériques :

| Biome | Température | Humidité | Vent |
|---|---:|---:|---:|
| 🌾 Plaine | +1°C | +5% | +0 km/h |
| ⛰️ Montagne | -6°C | +12% | +18 km/h |
| 🌲 Forêt | -2°C | +18% | -8 km/h |
| 🏜️ Désert | +9°C | -28% | +12 km/h |
| 🌊 Océan | +2°C | +32% | +25 km/h |
| 🏙️ Ville | +4°C | -5% | +5 km/h |

### ⛰️ Physique du relief

Le relief influence directement la simulation : le vent rencontre une pente, l'air est forcé de monter, l'ascendance favorise la condensation et les précipitations sur le versant exposé. Après la crête, l'air redescend et s'assèche, créant une **ombre pluviométrique**.

La hauteur et la pente du terrain sont utilisées pour calculer l'influence orographique.

### ☁️ Nuages et vent

- Nuages 3D animés
- Déplacement contrôlé par la vitesse du vent
- Réaction des nuages au relief
- Variation de hauteur et de densité au-dessus des reliefs
- Simulation continue avec pause/reprise

### 🎬 Scénarios

| Scénario | Conditions |
|---|---|
| ☀️ **Canicule** | 38°C, air chaud et sec |
| 🌪️ **Tempête** | 95 km/h, forte humidité |
| 🌧️ **Front pluvieux** | 12°C, humidité très élevée |
| 🏔️ **Barrière montagneuse** | Relief + vent + humidité |
| 🏜️ **Sécheresse** | 32°C, humidité très faible |
| 🌧️ **Mousson** | Chaleur + humidité + vent |
| ⚙️ **Mode libre** | Paramètres entièrement personnalisables |

## 🖱️ Contrôles

| Action | Contrôle |
|---|---|
| Élever le terrain | Sélectionner **Élever**, puis cliquer/glisser |
| Creuser | Sélectionner **Creuser**, puis cliquer/glisser |
| Lisser | Sélectionner **Lisser**, puis cliquer/glisser |
| Modifier le pinceau | Curseur **Taille** |
| Explorer le terrain | Caméra orbitale |
| Modifier la météo | Curseurs atmosphériques |
| Pause | Bouton **Pause** |

## 🛠️ Technologies

- **React**
- **Vite**
- **Three.js**
- **JavaScript / ES Modules**
- **GitHub Actions**
- **GitHub Pages**

## 💻 Installation locale

```bash
git clone https://github.com/TABOdevMC/weathersimulation.git
cd weathersimulation
npm install
npm run dev
```

Build de production :

```bash
npm run build
```

Prévisualisation du build :

```bash
npm run preview
```

## 📦 Déploiement

Le projet est configuré pour GitHub Pages avec GitHub Actions. Chaque push sur `main` déclenche le workflow de build et de déploiement.

Le site utilise le chemin `/weathersimulation/`.

## 📁 Structure

```text
weathersimulation/
├── .github/
│   └── workflows/
│       └── deploy-pages.yml
├── src/
│   ├── main.jsx
│   └── style.css
├── index.html
├── package.json
└── vite.config.js
```

## 🎯 Objectif

Le projet sert de laboratoire interactif pour expérimenter les relations entre :

**terrain → vent → ascendance → condensation → nuages → précipitations → zone sèche**

L'objectif est de faire évoluer progressivement cette sandbox vers une simulation météo et environnementale plus complète.

## 📄 Licence

Aucune licence open source spécifique n'est actuellement déclarée.
