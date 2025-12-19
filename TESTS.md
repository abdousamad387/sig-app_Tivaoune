# 🧪 TESTS - WebSIG Pro

Guide de test et validation de l'application.

---

## ✅ Checklist de Validation

### 1. Chargement de l'Application

- [ ] Page charge sans erreurs (F12 - Console)
- [ ] Carte affichée au centre de Tivaouane
- [ ] Zoom initial = 10
- [ ] Tous les boutons de la navbar visibles
- [ ] Coordonnées affichées en haut à droite

**Comment tester** :
```bash
1. Ouvrez http://localhost:8000
2. Attendez 2-3 secondes
3. Vérifiez la console (F12 → Console)
4. Cherchez "✨ WebSIG chargé avec succès!"
```

### 2. Chargement des Couches

#### Départements
- [ ] Affichés en gris
- [ ] Polygones avec traits pointillés
- [ ] Remplissage léger transparent

**Test** :
```
1. Cliquez 🗺️ COUCHES
2. Vérifiez ✓ Départements
3. Voyez limites grises sur carte
```

#### Arrondissements
- [ ] Affichés en violet
- [ ] À l'intérieur des départements
- [ ] Traits continus

#### Routes ⭐ NOUVEAU
- [ ] Affichées en orange
- [ ] Lignes visibles sur la carte
- [ ] Épaisseur = 4px

**Test** :
```
1. Allez à COUCHES
2. Cochez "Routes"
3. Vous devez voir 2+ lignes orange
4. Badge affiche "2" ou plus
```

#### Écoles
- [ ] Points verts avec clustering
- [ ] Clustering actif au zoom faible
- [ ] Points individuels au zoom élevé

#### Localités
- [ ] Points rouges avec clustering
- [ ] Même comportement que écoles

### 3. Recherche Géospatiale

- [ ] Barre recherche fonctionne
- [ ] Autocomplete affiche résultats
- [ ] Clic sur résultat = zoom automatique
- [ ] Popup s'affiche

**Test** :
```
1. Cliquez sur barre 🔍
2. Tapez "Cité"
3. Voyez suggestions
4. Cliquez sur une suggestion
5. La carte zoome et popup s'affiche
```

### 4. Affichage Coordonnées

- [ ] Coordonnées en haut à droite
- [ ] Format : "Lat: XX.XXXXX | Lon: -XX.XXXXX"
- [ ] Mise à jour en temps réel (souris)

**Test** :
```
1. Bougez la souris sur la carte
2. Coordonnées changent en temps réel
3. Valeurs = coordonnées WGS84
```

### 5. Panel Couches

- [ ] 5 couches listées
- [ ] Chaque couche a checkbox
- [ ] Chaque couche a icône (couleur)
- [ ] Badges affichent nombre d'objets
- [ ] Cocher/décocher affiche/cache couche

**Test** :
```
1. Allez COUCHES
2. Décochez une couche
3. Elle disparaît de la carte
4. Recochez
5. Elle réapparaît
```

### 6. Panel Données

- [ ] Tableau avec 5 lignes
- [ ] Colonnes: Couche, Type, Objets, Action
- [ ] Bouton [Voir] pour chaque
- [ ] Clic [Voir] = zoom sur couche

**Test** :
```
1. Allez DONNÉES
2. Cherchez "Routes"
3. Cliquez [Voir]
4. Carte zoome sur toutes les routes
```

### 7. Panel Statistiques

- [ ] 4 cartes statistiques (Écoles, Localités, Routes, Total)
- [ ] 3 graphiques (Doughnut, Bar, Line)
- [ ] Graphiques affichent les bonnes données
- [ ] Légendes lisibles

**Test** :
```
1. Allez STATS
2. Vérifiez les chiffres
3. Voir graphiques colorés
4. Survolez graphiques pour infos
```

### 8. Panel Analyse ⭐ NOUVEAU

#### Dessin
- [ ] Outils disponibles sur la carte
- [ ] Créer polygone = clic multiple + double-clic
- [ ] Créer ligne = clic multiple + double-clic
- [ ] Créer rectangle = 2 clics coins opposés
- [ ] Créer cercle = clic center + rayon
- [ ] Créer marqueur = simple clic
- [ ] Bouton [Effacer] fonctionne

**Test** :
```
1. Allez ANALYSE
2. Activez outil Polygone
3. Cliquez 3+ points sur carte
4. Double-clic pour terminer
5. Polygone dessiné en bleu
```

#### Buffer ⭐ NOUVEAU
- [ ] Input distance accepte nombres
- [ ] Dessiner puis Buffer crée zone
- [ ] Zone affichée en cyan pointillé
- [ ] Zone=transparence légère

**Test** :
```
1. Allez ANALYSE
2. Entrez "2" km
3. Dessinez un point
4. Cliquez [Buffer]
5. Zone cyan apparaît autour
```

#### Requêtes Spatiales ⭐ NOUVEAU

**Statistiques** :
- [ ] Sélectionner couche marche
- [ ] Cliquer Statistics affiche modal
- [ ] Modal affiche: count, types, bbox
- [ ] OK pour tous types couches

**Test** :
```
1. Allez ANALYSE
2. Sélectionnez "Écoles"
3. Cliquez [Statistiques]
4. Popup affiche résultats
```

**Plus Proche** :
- [ ] Dessiner point référence
- [ ] Sélectionner couche
- [ ] Cliquer [Plus proche]
- [ ] Affiche objet et distance en km

**Test** :
```
1. Allez ANALYSE
2. Dessinez point marqueur
3. Sélectionnez "Écoles"
4. Cliquez [Plus proche]
5. Modal: "Distance: X.XX km"
```

**Heatmap** :
- [ ] Sélectionner couche AVEC points
- [ ] Cliquer [Carte de Chaleur]
- [ ] Heatmap apparaît avec gradient
- [ ] Bleu = bas, Rouge = haut
- [ ] Radius 25px, blur 20

**Test** :
```
1. Allez ANALYSE
2. Sélectionnez "Écoles"
3. Cliquez [Heatmap]
4. Carte de chaleur affichée
5. Zones denses = rouge/orange
```

### 9. Mesure

- [ ] Outil Mesure sur la carte
- [ ] Clic pour ajouter points
- [ ] Distance affichée en km/m
- [ ] ESC ou double-clic termine

### 10. Export

- [ ] Dessiner objets
- [ ] Objet peut être téléchargé (si bouton présent)
- [ ] Fichier = GeoJSON valide

---

## 🔍 Tests de Données

### Département
```
✅ Polygone fermé
✅ Coordonnées valides
✅ Propriétés: nom
```

### Arrondissements
```
✅ Multiples polygones
✅ À l'intérieur du département
✅ Sans trous (holes)
```

### Routes ⭐ CORRIGÉ
```
✅ Fichier route.geojson créé
✅ 2 features LineString
✅ Propriétés: nom, type, etat, classe
✅ Coordonnées WGS84
```

### Écoles & Localités
```
✅ Points valides
✅ Clustering fonctionne
✅ Propriétés complètes
```

---

## 🧬 Tests de Code

### JavaScript Syntax

**Console (F12)** :
```javascript
// Vérifier app initialisée
console.log(app); // Doit afficher l'objet

// Vérifier map
console.log(app.map); // Doit afficher Leaflet map

// Vérifier couches
console.log(app.layers); // Doit afficher 5 couches

// Vérifier données
console.log(app.layersData); // Doit afficher 5 datasets
```

### Erreurs Critiques

```javascript
// Aucun de ces messages ne doit apparaître:
"Uncaught TypeError"
"SyntaxError"
"Turf is not defined"  (si Turf utilisé)
"Cannot read property"
```

### Functions Test

```javascript
// Tester Buffer
app.spatialTools.createBuffer();

// Tester Statistiques
app.spatialTools.calculateStats();

// Tester Proximité
app.spatialTools.findNearest();

// Tester Heatmap
app.spatialTools.heatmap();

// Tester Zoom
app.tools.zoomGlobal();
```

---

## 🌐 Tests Multi-Navigateur

### Chrome/Chromium
- [ ] Charge sans erreur
- [ ] Recherche fonctionne
- [ ] Buffer crée correctement
- [ ] Graphiques affichés

### Firefox
- [ ] Compatibilité OK
- [ ] Tous boutons cliquables
- [ ] Zoom fluide

### Safari
- [ ] Pas de console errors
- [ ] Responsive OK
- [ ] Popups affichées

### Edge
- [ ] Compatibilité OK
- [ ] Performances acceptables

---

## 📱 Tests Mobile/Responsif

### Portrait (iPhone X)
- [ ] Carte visible
- [ ] Sidebar collapsible
- [ ] Boutons cliquables (touch-friendly)
- [ ] Texte lisible

### Paysage
- [ ] Layout adapté
- [ ] Aucun scroll horizontal
- [ ] Buttons visibles

### Tablette (iPad)
- [ ] Utilisable
- [ ] Sidebar + carte
- [ ] Tous outils accessibles

---

## ⚡ Tests Performance

### Temps de Chargement
```javascript
// Dans console
performance.timing.loadEventEnd - performance.timing.navigationStart
// Doit être < 3 secondes
```

### Utilisation Mémoire
```
Avant : ~50MB
Après Buffer : ~60MB (acceptable)
Après Heatmap : ~70MB (acceptable)
```

### Zoom Responsiveness
```
Zoom in/out doit être fluide (< 300ms)
Pan doit être smooth (60 fps)
```

---

## 🐛 Tests de Bugs Connus

### Routes ne s'affichent pas
```
✅ RÉSOLU - Changé "routes.geojson" → "route.geojson"
```

### Localites.geojson ignoré
```
✅ RÉSOLU - Changé "localites" → "Localites" (casse)
```

### Buffer sans action
```
✅ Vérifier: Turf.js chargé dans console
   > typeof turf
   > "object" (bon)
```

---

## 📋 Rapport de Test Template

```markdown
## Test Date: 19/12/2024

### Environnement
- Navigateur: Chrome 120
- OS: Windows 11
- Résolution: 1920x1080

### Résultats
- Chargement: ✅ 2.1s
- Couches: ✅ Toutes visibles
- Routes: ✅ Orange affichées
- Buffer: ✅ Fonctionne
- Stats: ✅ Affichées
- Heatmap: ✅ Gradient correct
- Mobile: ✅ Responsive

### Bugs Trouvés
(Aucun critique)

### Recommandations
- Tous les tests passent ✅
```

---

## 🎯 Test Automation

### Selenium Test Example

```python
from selenium import webdriver

driver = webdriver.Chrome()
driver.get('http://localhost:8000')

# Vérifier titre
assert 'WebSIG Pro' in driver.title

# Attendre carte
wait.until(EC.presence_of_element_located((By.ID, 'map')))

# Vérifier couches
layers = driver.find_elements(By.CLASS_NAME, 'layer-checkbox')
assert len(layers) == 5

driver.quit()
```

---

## ✨ Checklist Déploiement

- [ ] Tous tests passent
- [ ] Aucune erreur console
- [ ] GeoJSON validé
- [ ] Routes affichées ✅
- [ ] Requêtes spatiales fonctionne ✅
- [ ] Mobile responsive
- [ ] Tous navigateurs OK
- [ ] Performance acceptable
- [ ] Documentation complète
- [ ] CHANGELOG mis à jour
- [ ] README à jour

---

## 🚀 Prêt pour Production?

```
✅ Tous tests = VERT  → DÉPLOYER
⚠️ Certains tests = ORANGE → RÉVISER
❌ Critique = ROUGE → NE PAS DÉPLOYER
```

---

**Tests Version** : 2.1  
**Dernière mise à jour** : 19 Décembre 2024
