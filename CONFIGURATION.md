# ⚙️ CONFIGURATION - WebSIG Pro

Ce fichier explique comment personnaliser votre WebSIG Pro.

---

## 🎨 Configuration des Couleurs

### Localisation dans le code

Dans `index.html`, cherchez la section `:root` du CSS :

```css
:root {
    --primary: #06b6d4;      /* Couleur principale (cyan) */
    --secondary: #8b5cf6;    /* Couleur secondaire (violet) */
    --success: #22c55e;      /* Succès (vert) */
    --danger: #ef4444;       /* Danger (rouge) */
    --warning: #f97316;      /* Attention (orange) */
    --info: #3b82f6;         /* Info (bleu) */
    --dark: #0f172a;         /* Fonds sombre */
    --light: #f8fafc;        /* Texte clair */
}
```

### Exemples

**Changer la couleur principale en rouge :**
```css
--primary: #FF0000;  /* rouge */
```

**Changer en bleu :**
```css
--primary: #0066FF;  /* bleu */
```

**Palette couleurs recommandée :**
```css
/* Sombre - Professionnel */
--dark: #000000;
--primary: #1E90FF;  /* Dodger Blue */

/* Clair - Coloré */
--primary: #00CCFF;
--secondary: #FF00FF;

/* Naturel - Terre */
--primary: #8B6914;
--secondary: #DAA520;
```

---

## 🗺️ Ajouter des Couches de Données

### 1. Préparer votre GeoJSON

**Format requis :**
```json
{
  "type": "FeatureCollection",
  "features": [
    {
      "type": "Feature",
      "geometry": {
        "type": "Point",
        "coordinates": [-14.95, 14.95]
      },
      "properties": {
        "nom": "Exemple",
        "type": "Type d'objet",
        ...
      }
    }
  ]
}
```

**Validez votre GeoJSON :** https://geojson.io

### 2. Placer le fichier

```
geo-sn/data/
├── ma_couche.geojson  ← Votre fichier ici
├── departements.geojson
└── ...
```

### 3. Ajouter à la Configuration

Dans `index.html`, cherchez `config:` et ajoutez :

```javascript
config: [
    // Couches existantes...
    
    // NOUVELLE COUCHE :
    {
        id: 'ma_couche',           // Identifiant unique
        url: 'data/ma_couche.geojson',  // Chemin
        type: 'point',             // point, line, ou poly
        name: 'Ma Couche',         // Affichage UI
        color: '#FF5733',          // Couleur (hex)
        category: 'custom',        // Catégorie (admin, infra, custom)
        cluster: true              // Clustering (true pour points)
    }
]
```

### 4. Recharger

F5 dans le navigateur → Votre couche apparaît !

---

## 🎯 Configuration par Type Géométrie

### Points (Points d'intérêt)

```javascript
{
    id: 'mes_points',
    url: 'data/mes_points.geojson',
    type: 'point',
    name: 'Points d\'Intérêt',
    color: '#22c55e',
    category: 'infra',
    cluster: true  // Regroupe les points proches
}
```

**Affichage** :
- Cercles colorés avec bordure blanche
- Cluster dynamique avec compteur
- Popup au clic

**Propriétés recommandées** :
```json
{
    "nom": "Nom du point",
    "type": "Type",
    "description": "Description détaillée",
    "population": 5000,
    "contact": "Infos contact"
}
```

### Lignes (Routes, chemins)

```javascript
{
    id: 'mes_routes',
    url: 'data/mes_routes.geojson',
    type: 'line',
    name: 'Réseau Routier',
    color: '#f97316',
    category: 'infra',
    cluster: false  // Les lignes ne se clusterisent pas
}
```

**Affichage** :
- Ligne colorée avec épaisseur 4px
- Surbrillance au survol (orange)
- Popup avec détails

**Propriétés recommandées** :
```json
{
    "nom": "Route N1",
    "type": "Route Nationale",
    "etat": "Bon / Moyen / Mauvais",
    "longueur_km": 45.5,
    "largeur_m": 7
}
```

### Polygones (Zones, limites)

```javascript
{
    id: 'mes_zones',
    url: 'data/mes_zones.geojson',
    type: 'poly',
    name: 'Zones Administratives',
    color: '#8b5cf6',
    category: 'admin',
    cluster: false
}
```

**Affichage** :
- Polygone avec bordure et remplissage transparent
- Surbrillance au survol
- Popup avec infos

**Propriétés recommandées** :
```json
{
    "nom": "Arrondissement 1",
    "type": "Zone administrative",
    "population": 50000,
    "superficie_km2": 125.5,
    "code": "ARR001"
}
```

---

## 🔧 Personnaliser les Popups

### Localisation du code

Cherchez dans `createLayer()` :
```javascript
if (id === 'ecoles') {
    popupContent += `
        <div class="info-row">
            <span class="info-label">📚 Type:</span>
            <span class="info-value">${props.type || 'N/A'}</span>
        </div>
    `;
}
```

### Ajouter vos champs

```javascript
else if (id === 'ma_couche') {
    popupContent += `
        <div class="info-row">
            <span class="info-label">📍 Localité:</span>
            <span class="info-value">${props.localite || 'N/A'}</span>
        </div>
        <div class="info-row">
            <span class="info-label">📊 Population:</span>
            <span class="info-value">${props.population || 'N/A'}</span>
        </div>
        <div class="info-row">
            <span class="info-label">📞 Contact:</span>
            <span class="info-value">${props.contact || 'N/A'}</span>
        </div>
    `;
}
```

### Ajouter des icônes

```javascript
<div class="info-row">
    <span class="info-label">🏥 Hôpital:</span>
    <span class="info-value">${props.hopital || 'Non'}</span>
</div>

<div class="info-row">
    <span class="info-label">🏫 École:</span>
    <span class="info-value">${props.ecole || 'Non'}</span>
</div>

<div class="info-row">
    <span class="info-label">🚰 Eau:</span>
    <span class="info-value">${props.eau || 'Non'}</span>
</div>
```

---

## 📊 Personnaliser les Graphiques

### Localisation

Cherchez `initCharts()` dans le JavaScript.

### Modifier les Statistiques Affichées

```javascript
// Avant :
const statsContainer = document.getElementById('stat-cards');
statsContainer.innerHTML = `
    <div class="col-md-6 mb-3">
        <div class="stat-box">
            <div class="stat-number">${data[3] || 0}</div>
            <div class="stat-text">Écoles</div>
        </div>
    </div>
`;

// Après (ajouter nouvelle stat) :
statsContainer.innerHTML = `
    ...
    <div class="col-md-6 mb-3">
        <div class="stat-box" style="border-color: #FFD700;">
            <div class="stat-icon"><i class="bi bi-hospital"></i></div>
            <div class="stat-number">5</div>
            <div class="stat-text">Hôpitaux</div>
        </div>
    </div>
`;
```

### Ajouter des Graphiques Personnalisés

```javascript
// Nouveau graphique personnalisé :
this.charts.custom = new Chart(document.getElementById('chartCustom'), {
    type: 'pie',
    data: {
        labels: ['Rural', 'Urbain', 'Semi-urbain'],
        datasets: [{
            data: [40, 35, 25],
            backgroundColor: ['#22c55e', '#ef4444', '#f97316'],
            borderWidth: 2,
            borderColor: '#0f172a'
        }]
    },
    options: {
        responsive: true,
        maintainAspectRatio: false,
        plugins: {
            legend: {
                labels: { color: 'white' }
            }
        }
    }
});
```

---

## 🌍 Changer les Fonds de Carte

### Localisation

```javascript
const osm = L.tileLayer('https://tile.openstreetmap.org/{z}/{x}/{y}.png', {
    attribution: '© OpenStreetMap',
    maxZoom: 19
});

const satellite = L.tileLayer('https://mt1.google.com/vt/lyrs=y&x={x}&y={y}&z={z}', {
    attribution: '© Google',
    maxZoom: 20
});
```

### Autres Fonds Disponibles

**Cartodb Positron** (minimaliste) :
```javascript
L.tileLayer('https://{s}.basemaps.cartocdn.com/light_all/{z}/{x}/{y}{r}.png', {
    attribution: '© CartoDB'
})
```

**ESRI World Imagery** (satellite HD) :
```javascript
L.tileLayer('https://server.arcgisonline.com/ArcGIS/rest/services/World_Imagery/MapServer/tile/{z}/{y}/{x}', {
    attribution: '© ESRI'
})
```

**Stamen Terrain** (relief) :
```javascript
L.tileLayer('https://stamen-tiles-{s}.a.ssl.fastly.net/terrain/{z}/{x}/{y}{r}.png', {
    attribution: '© Stamen Design'
})
```

### Implémenter

```javascript
// Ajouter à baseMaps :
this.baseMaps = {
    "Plan": osm,
    "Satellite": satellite,
    "Cartodb": L.tileLayer('...'),  // Nouveau
    "Terrain": L.tileLayer('...')   // Nouveau
};

L.control.layers(this.baseMaps, null, { position: 'topright' }).addTo(this.map);
```

---

## 🎯 Configurer le Zoom Initial

### Localisation

```javascript
this.map = L.map('map', {
    center: [14.95, -14.97],  // [Latitude, Longitude]
    zoom: 10                    // Niveau de zoom
});
```

### Exemples

**Vue mondiale** :
```javascript
center: [20, 0],
zoom: 2
```

**Vue pays** :
```javascript
center: [14, -15],  // Sénégal
zoom: 6
```

**Vue ville** :
```javascript
center: [14.95, -14.97],  // Tivaouane
zoom: 12
```

**Vue rue** :
```javascript
zoom: 16-18
```

---

## 📱 Responsive Design

### CSS Breakpoints

```css
/* Desktop (> 1200px) */
@media (max-width: 1200px) {
    .sidebar-width: 320px;
}

/* Tablette (768px - 1199px) */
@media (max-width: 768px) {
    .navbar-height: 60px;
    .sidebar-width: 280px;
}

/* Mobile (< 767px) */
@media (max-width: 480px) {
    .sidebar-width: 100%;
    .tool-btn { width: 40px; }
}
```

---

## 🔐 Sécurité & Performance

### CORS (Cross-Origin)

Pour serveur distant, ajouter headers :
```javascript
// Node.js Express
app.use((req, res, next) => {
    res.header('Access-Control-Allow-Origin', '*');
    next();
});

// Apache .htaccess
Header set Access-Control-Allow-Origin "*"
```

### Cache

```javascript
// Activer le cache navigateur
fetch('data/ma_couche.geojson', {
    headers: { 'Cache-Control': 'max-age=86400' }
})
```

### Compression

Serveur local avec gzip :
```bash
# Python
python -m gzip index.html > index.html.gz

# Nginx
gzip on;
gzip_min_length 1000;
```

---

## 🐛 Déboguer

### Console Développeur (F12)

```javascript
// Afficher toutes les couches
console.log(app.layers);

// Afficher toutes les données
console.log(app.layersData);

// Tester un buffer
app.spatialTools.createBuffer();

// Afficher les coordonnées
app.map.on('click', (e) => {
    console.log(e.latlng);
});
```

### Validation GeoJSON

```bash
# Ligne de commande
npm install -g geojson-validation
geojson-validate data/ma_couche.geojson

# Online
https://geojson.io
```

---

## ✅ Checklist de Configuration

- [ ] Fichier GeoJSON créé et validé
- [ ] Fichier placé dans `/data/`
- [ ] Configuration ajoutée à `config:[]`
- [ ] ID unique défini
- [ ] Couleur choisie
- [ ] Type géométrie correct (point/line/poly)
- [ ] Catégorie assignée
- [ ] Clustering configé (si applicable)
- [ ] Popups personnalisées
- [ ] Graphiques mis à jour
- [ ] Tests sur tous navigateurs
- [ ] Responsive design vérifié

---

## 📚 Ressources

- **GeoJSON Spec** : https://geojson.org/
- **Leaflet API** : https://leafletjs.com/reference.html
- **Turf.js** : https://turfjs.org/docs/
- **Color Picker** : https://htmlcolorcodes.com/

---

*Configuration Guide v2.1*  
*Mise à jour : 19 Décembre 2024*
