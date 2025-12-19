# ⚡ QUICKSTART - Démarrage en 5 Minutes

**Pour les pressés! 🏃‍♂️**

---

## 1️⃣ Lancer l'Application (1 min)

### Avec Python (Recommandé)
```bash
cd c:\Users\user\Desktop\sigAPPexam\geo-sn
python -m http.server 8000
```

### Avec Node.js
```bash
npx http-server
```

### Ouvrir dans le Navigateur
```
http://localhost:8000
```

✅ **C'est fait!** La carte s'affiche!

---

## 2️⃣ Explorer les Couches (1 min)

### Afficher/Masquer les Données
1. Cliquez sur **🗺️ COUCHES** (navbar)
2. Cochez ✓ les couches que vous voulez
3. Les couches apparaissent/disparaissent

### Résumé
- 🟢 **Écoles** (verts, groupés)
- 🔴 **Localités** (rouges, groupés)
- 🟠 **Routes** (orange - NOUVEAU!)
- 🟣 **Arrondissements** (violet)
- ⚫ **Départements** (gris)

---

## 3️⃣ Rechercher un Lieu (1 min)

### Utiliser la Barre de Recherche
1. Cliquez sur **🔍** en haut
2. Tapez un nom (ex: "Cité", "École")
3. Cliquez sur le résultat
4. La carte zoome automatiquement! 📍

---

## 4️⃣ Créer un Buffer (1 min)

### Créer une Zone de Protection

1. Cliquez sur **🔧 ANALYSE** (navbar)
2. Entrez la distance: `2` km
3. Sur la carte, **Dessinez un point** (clic simple)
4. Cliquez le bouton **[Buffer]**
5. ✅ Zone cyan pointillée apparaît!

---

## 5️⃣ Analyser les Données (1 min)

### Voir les Statistiques

1. Allez dans **🔧 ANALYSE**
2. Sélectionnez une couche (ex: "Écoles")
3. Cliquez **[📊 Statistiques]**
4. ✅ Popup affiche le nombre total et les types

### Visualiser la Densité

1. Allez dans **🔧 ANALYSE**
2. Sélectionnez une couche (ex: "Écoles")
3. Cliquez **[🔥 Carte de Chaleur]**
4. ✅ Zones rouges = densité élevée

---

## 🎯 Commandes Rapides

| Action | Bouton | Résultat |
|--------|--------|----------|
| Afficher couches | 🗺️ COUCHES | Voir liste |
| Chercher lieu | 🔍 | Zoom automatique |
| Analyser | 🔧 ANALYSE | Panel analyse |
| Voir graphiques | 📊 STATS | Statistiques |
| Catalogue | 📋 DONNÉES | Tableau |

---

## ⌨️ Raccourcis Clavier

```
SUPPR     → Effacer les dessins
ESC       → Annuler action en cours
CTRL+F    → Rechercher sur la page
F12       → Ouvrir console (pour debug)
```

---

## 🎨 Navigation Carte

| Action | Comment |
|--------|---------|
| **Zoom avant** | `+` en haut à droite ou molette souris |
| **Zoom arrière** | `-` en haut à droite ou molette souris |
| **Se déplacer** | Glisser la souris (cliquer + traîner) |
| **Double-clic** | Zoom sur ce point |
| **Voir orientation** | Minimap en bas à gauche |

---

## 🆘 Problèmes Rapides

### La carte ne charge pas
```
❌ Fermez le terminal
✅ Relancez: python -m http.server 8000
✅ Rafraîchissez F5
```

### Routes n'apparaissent pas
```
✅ Allez COUCHES
✅ Cochez "Routes"
✅ Attendez quelques secondes
```

### Aucune donnée n'apparaît
```
✅ Ouvrez la console (F12)
✅ Cherchez messages d'erreur
✅ Vérifiez que tous fichiers existent en /data/
```

### Lent/Bloqué
```
✅ Décochez les couches inutiles
✅ Zoomez sur une zone restreinte
✅ Fermez les autres onglets
```

---

## 📚 En Savoir Plus

### Pour Guides Détaillés
→ Voir [GUIDE_UTILISATION.md](GUIDE_UTILISATION.md) (15 min)

### Pour Personnaliser
→ Voir [CONFIGURATION.md](CONFIGURATION.md) (20 min)

### Pour Tout Savoir
→ Voir [README.md](README.md) (5 min)

---

## 🆕 Nouvelles Fonctionnalités v2.1

### ✨ 4 Outils Géospatiaux Nouveaux

1. **Buffer** - Zone autour d'objets
2. **Statistiques** - Compter et analyser
3. **Plus Proche** - Distance minimale
4. **Heatmap** - Visualiser densité

### ✨ Routes Affichées!
Le problème v2.0 où les routes ne s'affichaient pas est **RÉSOLU** ✅

---

## ✅ Checklist Rapide

- [ ] Serveur lancé
- [ ] Carte chargée (2-3s)
- [ ] Toutes couches visibles
- [ ] Routes affichées en orange
- [ ] Recherche fonctionne
- [ ] Buffer crée zone
- [ ] Statistiques affiche résultats
- [ ] Heatmap affiche gradient

**Si tout ✅ → Prêt à utiliser! 🚀**

---

## 🎓 Cas Simple d'Usage

### Je veux voir les écoles autour d'un point

```
1. Ouvrez http://localhost:8000
2. Cliquez 🗺️ COUCHES
3. Cochez "Écoles"
4. Allez 🔧 ANALYSE
5. Sélectionnez "Écoles"
6. Dessinez un point
7. Cliquez [📍 Plus proche]
8. ✅ Voir distance et nom
```

### Je veux voir les zones denses d'écoles

```
1. Ouvrez http://localhost:8000
2. Allez 🔧 ANALYSE
3. Sélectionnez "Écoles"
4. Cliquez [🔥 Heatmap]
5. ✅ Zones rouges = denses
```

---

## 🚀 Prêt!

**Vous savez maintenant comment:**
- ✅ Démarrer l'appli
- ✅ Voir les données
- ✅ Rechercher des lieux
- ✅ Créer des zones
- ✅ Analyser des données

**Que voulez-vous faire maintenant?**

| Objectif | Allez à |
|----------|---------|
| Maîtriser tous les outils | [GUIDE_UTILISATION.md](GUIDE_UTILISATION.md) |
| Ajouter vos données | [CONFIGURATION.md](CONFIGURATION.md) |
| Changer les couleurs | [CONFIGURATION.md#configuration-des-couleurs](CONFIGURATION.md) |
| Tester tout | [TESTS.md](TESTS.md) |
| Comprendre les changements | [CHANGELOG.md](CHANGELOG.md) |

---

## 💬 Questions Fréquentes

**Q: C'est gratuit?**  
A: Oui! Code open source, fichiers inclus.

**Q: Je peux modifier les couleurs?**  
A: Oui, voir [CONFIGURATION.md](CONFIGURATION.md)

**Q: Je peux ajouter mes données?**  
A: Oui, voir [CONFIGURATION.md#ajouter-des-couches-de-données](CONFIGURATION.md)

**Q: Ça marche sur mobile?**  
A: Oui! Interface responsive.

**Q: Ça marche hors ligne?**  
A: Oui une fois chargé, sauf les fonds de carte (besoin internet).

---

**Durée totale:** ⏱️ 5 minutes  
**Difficulté:** 🟢 Très facile  
**Résultat:** 🎉 Application fonctionnelle!

---

🗺️ **Bon voyage à Tivaouane!**

**Besoin d'aide?** Consultez [INDEX.md](INDEX.md) pour la navigation complète.
