# 🗺️ GUIDE D'UTILISATION - WebSIG Pro Tivaouane

## 📋 Table des Matières
1. [Interface Générale](#interface-générale)
2. [Outils de Localisation](#outils-de-localisation)
3. [Requêtes Spatiales](#requêtes-spatiales)
4. [Analyses et Statistiques](#analyses-et-statistiques)
5. [Dépannage](#dépannage)

---

## 🎨 Interface Générale

### Barre Supérieure (Navbar)
```
┌──────────────────────────────────────────────────────────────┐
│ [LOGO] WebSIG Pro     [COUCHES] [DONNÉES] [STATS] [ANALYSE]  │
│                                  Lat: 14.95 | Lon: -14.97    │
└──────────────────────────────────────────────────────────────┘
```

### Boutons Principaux
- 🗺️ **COUCHES** - Afficher/masquer les données
- 📊 **DONNÉES** - Catalogue complet des fichiers
- 📈 **STATS** - Graphiques et statistiques
- 🔧 **ANALYSE** - Outils géospatiaux avancés

---

## 🎯 Outils de Localisation

### 1. **Recherche Rapide**
```
┌─ Barre de recherche en haut ─────────────┐
│ 🔍 Rechercher... [Tapez un nom]         │
│   → Écoles, Localités, Routes            │
│   → Zoom automatique sur le résultat     │
└──────────────────────────────────────────┘
```

**Exemple** :
- Tapez "Cité" → Localise toutes les localités contenant "Cité"
- Tapez "École" → Affiche toutes les écoles

### 2. **Affichage des Coordonnées**
```
En temps réel (en haut à droite) :
   Lat: 14.95234 | Lon: -14.97456

→ Mise à jour avec le mouvement de la souris
```

### 3. **Zoom et Navigation**
- **Zoom +/-** : Contrôles en haut à droite
- **Scroll** : Rouler pour zoomer/dézoomer
- **Glisser** : Maintenir clique gauche pour se déplacer
- **Double-clic** : Zoom sur un point
- **Carte miniature** : En bas à gauche pour orientation

---

## ⚡ Requêtes Spatiales

### Accès au Panel
```
Cliquez sur 🔧 ANALYSE dans la barre supérieure
```

### A. **Créer un Buffer (Zone de Protection)**

**Objectif** : Créer une zone circulaire autour d'une forme

**Étapes** :
```
1. Allez dans l'onglet ANALYSE
2. Entrez la distance (ex: 2 km)
3. Utilisez les outils de DESSIN (sur la carte) :
   - Cliquez sur le crayon pour activer le dessin
   - Dessinez un polygone, ligne ou point
4. Cliquez le bouton [Buffer]
5. ✅ Vous voyez la zone de protection en cyan

Résultat : Zone pointillée en cyan avec transparence
```

**Exemple de distance** :
```
- 0.5 km : Zone très restreinte (école)
- 1 km : Zone de proximité
- 5 km : Zone administrative
- 10 km : Région d'influence
```

### B. **Calculer des Statistiques**

**Objectif** : Analyser les données d'une couche

**Étapes** :
```
1. Allez dans l'onglet ANALYSE
2. Sélectionnez une couche :
   - Départements
   - Arrondissements
   - Routes
   - Écoles
   - Localités
3. Cliquez [📊 Statistiques]
4. ✅ Une boîte affiche les résultats

Résultats affichés :
  - Nombre total d'objets
  - Types de géométrie
  - Étendue spatiale (Bounding Box)
```

**Exemple** :
```
STATISTIQUES - Routes
Total d'objets: 2
Types: {"LineString": 2}
Étendue: -14.98, 14.92, -14.89, 14.98
```

### C. **Trouver l'Objet le Plus Proche**

**Objectif** : Distance minimale entre un point et une couche

**Étapes** :
```
1. Allez dans l'onglet ANALYSE
2. Sélectionnez une couche (ex: Écoles)
3. DESSINEZ un point sur la carte :
   - Cliquez sur l'outil Marqueur
   - Cliquez sur la carte pour créer le point
4. Cliquez [📍 Plus proche]
5. ✅ Affiche le nom et la distance

Résultat :
   "Objet le plus proche trouvé!
    Distance: 2.45 km
    Nom: École Primaire Central"
```

**Cas d'usage** :
- Trouver l'école la plus proche d'une maison
- Trouver la localité la plus proche d'une route
- Analyser les services de proximité

### D. **Créer une Carte de Chaleur**

**Objectif** : Visualiser la densité des points

**Étapes** :
```
1. Allez dans l'onglet ANALYSE
2. Sélectionnez une couche AVEC POINTS :
   - Écoles ✅
   - Localités ✅
   - Routes ❌ (pas de points)
3. Cliquez [🔥 Carte de Chaleur]
4. ✅ Apparition de l'heatmap

Résultat :
  - Zones bleues = Peu de points
  - Zones vertes = Points modérés
  - Zones rouges = Forte concentration
```

**Interprétation** :
```
Rouge intense  → Zone très dense en écoles
Orange         → Zone moyenne
Bleu           → Zone peu peuplée
```

---

## 📊 Analyses et Statistiques

### 1. **Onglet Statistiques**

```
┌─ STATISTIQUES ──────────────────────┐
│ [Cartes Statistiques]               │
│  📚 Écoles: 0                       │
│  🏠 Localités: 0                    │
│  🛣️ Routes: 0                      │
│  📊 Total: 0                        │
│                                     │
│ [Graphique Doughnut]                │
│ Répartition par type                │
│                                     │
│ [Graphique Bar]                     │
│ Comparaison des couches             │
│                                     │
│ [Graphique Ligne]                   │
│ Évolution temporelle (exemple)      │
└─────────────────────────────────────┘
```

### 2. **Catalogue de Données**

```
┌─ DONNÉES ───────────────────────────┐
│ Couche │ Type    │ Objets │ Action  │
├────────┼─────────┼────────┼─────────┤
│ Routes │ LINE    │   2    │ [Voir]  │
│ Écoles │ POINT   │   0    │ [Voir]  │
│ ...    │  ...    │  ...   │  ...    │
└─────────────────────────────────────┘
```

Cliquez sur **[Voir]** pour zoomer sur la couche

### 3. **Légende Interactive**

```
En bas à gauche de la carte :
┌─ LÉGENDE ──────────────────┐
│ ● Écoles (Vert)           │
│ ● Localités (Rouge)       │
│ ─ Routes (Orange)         │
│ ▭ Arrondissements (Violet)│
│ ▭ Départements (Gris)     │
└────────────────────────────┘
```

---

## 🛠️ Outils de Dessin

### Accès
1. Cliquez sur 🔧 ANALYSE
2. Utilisez les outils sur la **carte** :

### Formes Disponibles
```
🔷 Polygone     → Cliquez pour chaque point (double-clic pour terminer)
━ Polyline      → Ligne/chemin (double-clic pour terminer)
▭ Rectangle     → Cliquez deux coins opposés
⭕ Cercle        → Cliquez centre, puis rayon
📍 Marqueur     → Simple clic sur la carte
```

### Mesurer
```
Cliquez sur 📏 Mesures sur la carte
→ Mesurez distances et surfaces
→ Affichage dynamique en km/m²
```

---

## 📥 Exporter des Données

### Télécharger vos Dessins

```
1. Dessinez vos formes sur la carte
2. Allez dans ANALYSE
3. Cliquez [⬇️ Télécharger] (si visible)
4. ✅ Fichier GeoJSON téléchargé

Fichier généré :
  tivaouane_export_2024-12-19.geojson
  
Utilisable dans :
  - QGIS
  - ArcGIS
  - Autres logiciels SIG
```

---

## 🐛 Dépannage

### Problème 1 : Aucune donnée n'apparaît

**Solution** :
```
1. Ouvrez la console (F12)
2. Vérifiez les messages d'erreur
3. Assurez-vous que :
   - Les fichiers *.geojson existent
   - Vous avez internet (cartographie OSM)
   - Les fichiers sont valides (test JSON)
```

### Problème 2 : Certains objets n'apparaissent pas

**Solution** :
```
1. Vérifiez l'onglet COUCHES
2. Les couches doivent être COCHÉES (✓)
3. Décochez/recochez pour rafraîchir
```

### Problème 3 : La recherche ne fonctionne pas

**Solution** :
```
1. Seulement les POINTS peuvent être recherchés
2. Seuls les noms définis sont trouvés
3. Essayez avec d'autres mots-clés
```

### Problème 4 : Buffer n'apparaît pas

**Solution** :
```
1. Dessinez d'abord une forme valide
2. La forme doit être un polygone, ligne ou point
3. Vérifiez que Turf.js est chargé (console)
4. Essayez une distance plus grande (> 0.1 km)
```

### Problème 5 : Performance lente

**Solution** :
```
1. Décochez les couches inutiles
2. Réduisez le rayon du buffer
3. Zoomez sur la zone d'intérêt
4. Fermez les autres onglets
```

---

## 🎓 Tutoriels Avancés

### Workflow 1 : Analyser la Couverture Scolaire

```
Objectif : Voir combien d'écoles dans un rayon de 2km

1. Allez dans ANALYSE
2. Sélectionnez "Écoles"
3. Entrez 2 km comme rayon
4. Dessinez un point (zone d'habitat)
5. Cliquez Buffer
6. Cliquez "Plus proche"
→ Distance et école trouvées !
```

### Workflow 2 : Importer des Données Personnalisées

```
Si vous avez un fichier GeoJSON :

1. Placez-le dans /data/
2. Modifiez la config du code :
   { id: 'monlayer', url: 'data/monlayer.geojson', ... }
3. Rechargez la page
→ Votre couche apparaît !
```

---

## 📞 Support

**Questions fréquentes** :
- Q: Puis-je modifier les couleurs?  
  R: Oui, dans le code (section `config`)

- Q: Puis-je ajouter plus de couches?  
  R: Oui, ajoutez à la config + fichier GeoJSON

- Q: Comment partager la carte?  
  R: Générez un lien vers votre serveur web

---

**Version** : 2.1 Pro  
**Dernière mise à jour** : 19 Décembre 2024  
**Support** : Consultez le code source ou AMELIORATIONS.md
