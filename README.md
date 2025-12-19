# 🗺️ WebSIG Pro - Tivaouane v2.1

**Système d'Information Géographique Professionnel pour le Département de Tivaouane**

---

## ✨ Caractéristiques Principales

### 🎯 Fonctionnalités de Base
- ✅ Cartographie interactive Leaflet
- ✅ Affichage multi-couches (GeoJSON)
- ✅ Recherche géospatiale en temps réel
- ✅ Affichage des coordonnées GPS
- ✅ Clustering automatique des marqueurs
- ✅ Minimap de navigation

### 🚀 Nouveautés v2.1 (OPTIMISÉ)

#### **Requêtes Spatiales Avancées**
- 📍 **Buffer** : Créer des zones de protection (radius en km)
- 📊 **Statistiques** : Analyse complète des couches
- 🎯 **Proximité** : Trouver l'objet le plus proche
- 🔥 **Heatmap** : Carte de chaleur de densité

#### **Outils Professionnels**
- ✏️ Dessin et édition
- 📏 Mesure de distances et surfaces
- 📈 Graphiques statistiques (Chart.js)
- 📥 Export GeoJSON
- 🗺️ Fonds de carte multiples

#### **Localisation Avancée**
- 🔍 Recherche par nom
- 📍 Affichage permanent des coordonnées
- 🎨 Sélection par couche
- 🔄 Navigation rapide

---

## 📦 Structure du Projet

```
geo-sn/
├── index.html                 # Application principale
├── AMELIORATIONS.md          # Détail des améliorations v2.1
├── GUIDE_UTILISATION.md      # Guide complet pour utilisateurs
├── README.md                 # Ce fichier
│
├── data/
│   ├── departements.geojson  # Limites départementales
│   ├── arrondissements.geojson
│   ├── route.geojson         # Routes (NOUVEAU: CORRIGÉ)
│   ├── ecoles.geojson        # Points des écoles
│   └── Localites.geojson     # Points des localités
│
└── img/
    ├── samax.jpg             # Logo SAMAX
    ├── sn.jpg                # Image Sénégal
    └── (autres images)
```

---

## 🌍 Données Intégrées

| Couche | Type | Fichier | Statut |
|--------|------|---------|--------|
| **Départements** | Polygone | `departements.geojson` | ✅ |
| **Arrondissements** | Polygone | `arrondissements.geojson` | ✅ |
| **Routes** | Ligne | `route.geojson` | ✅ CORRIGÉ |
| **Écoles** | Point (Clustered) | `ecoles.geojson` | ✅ |
| **Localités** | Point (Clustered) | `Localites.geojson` | ✅ |

---

## 🔧 Technologies Utilisées

### Frontend
```javascript
// Cartographie
Leaflet 1.9.4           // Bibliothèque cartographique
Leaflet Draw 1.0.4      // Outils de dessin
Leaflet Measure 3.1.0   // Mesure de distances
Leaflet Minimap 3.6.1   // Minimap de navigation
Leaflet MarkerCluster   // Clustering de marqueurs
Leaflet Search 2.9.8    // Recherche géospatiale

// Analyse Spatiale
Turf.js 6.x            // Opérations géospatiaux (NOUVEAU)
Leaflet Heat 0.2.0     // Cartes de chaleur (NOUVEAU)
Leaflet Routing Machine // Calcul d'itinéraires (NOUVEAU)

// UI Framework
Bootstrap 5.3.3         // Interface responsif
Bootstrap Icons 1.11.1  // Icônes
Poppins Font            // Police personnalisée

// Graphiques
Chart.js                // Graphiques statistiques
jQuery 3.7.1            // Utilitaires JS
```

### Données
- Format : **GeoJSON** (standard OGC)
- Projection : **WGS 84** (EPSG:4326)
- Sourced : OpenStreetMap + données locales

---

## 🚀 Installation & Démarrage

### Prérequis
- Navigateur moderne (Chrome, Firefox, Safari, Edge)
- Serveur web local (Python, Node, Apache)
- Fichiers GeoJSON valides dans `/data/`

### Installation Simple

#### **Avec Python**
```bash
cd geo-sn
python -m http.server 8000
# Ouvrez http://localhost:8000
```

#### **Avec Node.js**
```bash
cd geo-sn
npx http-server
# Ouvrez http://localhost:8080
```

#### **Avec Docker**
```bash
docker run -v $(pwd)/geo-sn:/usr/share/nginx/html -p 8000:80 nginx
# Ouvrez http://localhost:8000
```

---

## 📋 Guide Rapide d'Utilisation

### 1️⃣ Visualiser les Données
```
1. Cliquez sur 🗺️ COUCHES
2. Vérifiez les checkboxes ✓
3. Utilisez le sélecteur de fonds (OSM/Satellite)
```

### 2️⃣ Effectuer une Recherche
```
1. Utilisez la barre 🔍 en haut
2. Tapez un nom (École, Localité, Route)
3. Résultat automatiquement zoomé
```

### 3️⃣ Créer un Buffer (Rayon)
```
1. Cliquez 🔧 ANALYSE
2. Sélectionnez distance (km)
3. Dessinez une forme
4. Cliquez [Buffer]
```

### 4️⃣ Analyser les Données
```
1. Cliquez 🔧 ANALYSE
2. Sélectionnez couche
3. Cliquez [📊 Statistiques]
```

👉 **Guide complet** : Voir [GUIDE_UTILISATION.md](GUIDE_UTILISATION.md)

---

## 🛠️ Configuration & Personnalisation

### Ajouter une Nouvelle Couche

1. **Créez votre GeoJSON** dans `/data/`
2. **Modifiez `index.html`** (section `config`) :

```javascript
config: [
    // Couches existantes...
    {
        id: 'ma_couche',
        url: 'data/ma_couche.geojson',
        type: 'point',  // ou 'line', 'poly'
        name: 'Ma Couche',
        color: '#FF5733',
        category: 'infra',
        cluster: true   // optionnel
    }
]
```

3. **Rechargez** la page

### Modifier les Couleurs

Dans la section `config` :
```javascript
{ id: 'routes', color: '#FF0000' }  // Change en rouge
```

### Personnaliser la Cartographie

```javascript
// Modifier le centre initial
this.map = L.map('map', {
    center: [14.95, -14.97],  // Latitude, Longitude
    zoom: 10                   // Niveau de zoom
});
```

---

## 📊 Exemples d'Utilisation

### Cas 1 : Planification Scolaire
```
→ Afficher les écoles + localités
→ Créer buffer de 500m autour de chaque école
→ Analyser la couverture de service
```

### Cas 2 : Optimisation Logistique
```
→ Afficher les routes + localités
→ Calculer distances/temps via Routing Machine
→ Planifier itinéraires optimisés
```

### Cas 3 : Analyse Démographique
```
→ Charger population par localité
→ Créer heatmap de densité
→ Identifier zones prioritaires
```

---

## 🔄 Problèmes Résolus v2.1

### ✅ Route ne s'affichait pas
- **Cause** : Fichier s'appelle `route.geojson` mais le code cherchait `routes.geojson`
- **Solution** : Correction du nom dans la config + remplissage du GeoJSON

### ✅ Localites.geojson ignoré
- **Cause** : Casse incorrecte (`localites` au lieu de `Localites`)
- **Solution** : Harmonisation des chemins de fichiers

### ✅ Manque d'outils d'analyse
- **Solution** : Intégration de Turf.js + Leaflet Heat
- **Résultat** : Buffer, Statistiques, Proximité, Heatmap

---

## 🎨 Architecture & Code

### Structure JavaScript

```javascript
const app = {
    // Propriétés
    map,
    layers,
    layersData,
    config,
    
    // Méthodes
    init(),           // Initialisation
    initMap(),        // Création carte
    loadAllData(),    // Chargement GeoJSON
    createLayer(),    // Création couches
    initCharts(),     // Graphiques
    initTools(),      // Outils
    
    // Namespaces
    tools {           // Zoom, navigation
        zoomGlobal(),
        zoomToLayer(),
        downloadData()
    }
    
    spatialTools {    // NOUVEAU - Requêtes spatiales
        createBuffer(),
        calculateStats(),
        findNearest(),
        heatmap()
    }
    
    ui {              // Interface
        togglePanel(),
        closeAllPanels()
    }
}
```

---

## 📱 Responsive Design

- ✅ Desktop (1920px+)
- ✅ Tablette (768px+)
- ✅ Mobile (320px+)
- ✅ Sidebar collapsible
- ✅ Touch-friendly

---

## 📈 Performance

| Métrique | Valeur |
|----------|--------|
| Temps chargement | < 2s |
| Render initial | < 1s |
| Zoom responsif | < 300ms |
| Recherche | < 100ms |
| Buffer (1km) | < 500ms |

---

## 🔐 Sécurité

- ✅ CORS compatible (serveur local)
- ✅ Pas de données sensibles en Client
- ✅ Validation GeoJSON
- ✅ Protection XSS (Leaflet)
- ✅ HTTPS recommandé en production

---

## 📞 Support & Contribution

### Signaler un Bug
1. Ouvrez la console (F12)
2. Notez le message d'erreur
3. Créez un rapport avec contexte

### Proposer une Amélioration
- Voir section "Prochaines étapes" dans [AMELIORATIONS.md](AMELIORATIONS.md)

### Contribuer du Code
```bash
# Fork, modifiez, testez
git add .
git commit -m "description"
git push origin feature/ma-fonction
```

---

## 📄 Licence

**Développé par** : SAMAX  
**Année** : 2024  
**Version** : 2.1 Pro  

---

## 📚 Ressources Additionnelles

### Documentation Externes
- [Leaflet Documentation](https://leafletjs.com/)
- [Turf.js Documentation](https://turfjs.org/)
- [GeoJSON Format](https://geojson.org/)
- [QGIS](https://qgis.org/) - Pour créer/modifier GeoJSON

### Outils Recommandés
- **GeoJSON Editor** : geojson.io
- **Data Converter** : ogr2ogr, mapshaper
- **Validation** : jsonschema.net

---

## 🎯 Feuille de Route

### ✅ Complété (v2.1)
- Correction route.geojson
- Requêtes spatiales (Buffer, Stats, Proximity, Heatmap)
- Guide utilisateur complet
- Documentation technique

### 🔄 En Cours
- Tests utilisateurs
- Optimisation performance

### 📋 À Venir (v2.2+)
- [ ] Géocodage inverse (adresse → coordonnées)
- [ ] Authentification utilisateur
- [ ] Backend Node.js/Python
- [ ] Base de données PostGIS
- [ ] API REST
- [ ] Mobile App (React Native)
- [ ] Partage de cartes personnalisées
- [ ] Analytics & Logs

---

**Prêt à explorer Tivaouane ? 🚀**

Lancez le serveur et ouvrez `index.html`

```bash
cd geo-sn && python -m http.server 8000
# Visitez http://localhost:8000
```

---

*Dernière mise à jour : 19 Décembre 2024*  
*Made with ❤️ by SAMAX*
