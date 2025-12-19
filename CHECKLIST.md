# ✅ Checklist de Déploiement

## 🎯 Avant de Pusher sur GitHub

### Code & Fichiers
- [ ] index.html valide et sans erreurs
- [ ] data/ contient tous les GeoJSON
- [ ] img/ contient les logos/images
- [ ] js/ contient les dépendances
- [ ] .gitignore correct (ne pas ignorer data/)
- [ ] Pas de fichiers temporaires (.tmp, ~, etc)

### Configuration
- [ ] vercel.json présent
- [ ] netlify.toml présent
- [ ] .github/workflows/deploy.yml présent
- [ ] DEPLOY.md rempli
- [ ] README.md à jour

### Tests Locaux
- [ ] Lancer `python -m http.server 8000`
- [ ] Ouvrir http://localhost:8000
- [ ] Données se chargent (5-10s)
- [ ] Pas d'erreur console (F12)
- [ ] Toutes les couches visibles
- [ ] Recherche fonctionne
- [ ] Outils spatiaux répondent
- [ ] Statistiques affichées
- [ ] Mobile responsive (F12)
- [ ] Cache localStorage fonctionne (rechargement rapide)

### Performance
- [ ] Lighthouse score > 90
- [ ] FCP < 2 secondes
- [ ] LCP < 3 secondes
- [ ] Pas de memory leaks
- [ ] Pas de warnings console

---

## 🚀 Déploiement sur GitHub

### Étape 1: Préparation Git
```bash
cd c:\Users\user\Desktop\sigAPPexam\geo-sn
git init
git add .
git commit -m "WebSIG Pro v2.1 - Production Ready"
```
- [ ] Commit créé

### Étape 2: Créer Repo GitHub
- [ ] Aller sur https://github.com/new
- [ ] Créer "websig-tivaouane"
- [ ] Public
- [ ] Copier l'URL (https://github.com/[user]/websig-tivaouane.git)

### Étape 3: Pousser le Code
```bash
git remote add origin https://github.com/[user]/websig-tivaouane.git
git branch -M main
git push -u origin main
```
- [ ] Code poussé sur GitHub
- [ ] Repo visible sur GitHub.com

### Étape 4: Vérifier le Repo
- [ ] Tous les fichiers visibles sur GitHub
- [ ] data/ avec tous les GeoJSON
- [ ] img/ avec les images
- [ ] js/ avec les dépendances
- [ ] Pas d'erreurs

---

## 🌐 Déploiement sur Vercel (RECOMMANDÉ)

### Étape 1: Créer Compte
- [ ] Aller sur https://vercel.com
- [ ] Sign up avec GitHub
- [ ] Autoriser Vercel

### Étape 2: Importer Projet
- [ ] Cliquer "Import Project"
- [ ] Chercher "websig-tivaouane"
- [ ] Cliquer "Import"

### Étape 3: Configuration
- [ ] Framework: Other (Static)
- [ ] Build Command: (laisser vide)
- [ ] Output Directory: (laisser vide)
- [ ] Environment Variables: (aucune)
- [ ] Cliquer "Deploy"

### Étape 4: Vérifier le Deploy
- [ ] Attend 2-3 minutes
- [ ] Status passe à "Ready"
- [ ] URL affichée (websig-tivaouane.vercel.app)
- [ ] Cliquer la URL pour tester

### Tests sur Vercel
- [ ] Carte s'affiche
- [ ] Données chargent (5-10s)
- [ ] Pas d'erreur console
- [ ] Performance bonne
- [ ] Mobile fonctionne

---

## 📱 Déploiement GitHub Pages (ALTERNATIVE)

### Étape 1: Activer Pages
- [ ] Aller sur votre repo GitHub
- [ ] Settings → Pages
- [ ] Source: "Deploy from a branch"
- [ ] Branch: "main" / "(root)"
- [ ] Save

### Étape 2: Attendre Deploy
- [ ] Attendre 1-2 minutes
- [ ] URL affichée ([user].github.io/websig-tivaouane)

### Tests sur GitHub Pages
- [ ] Carte s'affiche
- [ ] Données chargent
- [ ] Pas d'erreur (peut être plus lent que Vercel)

---

## 🧪 Tests Finaux

### Fonctionnalités Cartographie
- [ ] Basemaps switch (OSM → Satellite)
- [ ] Zoom/Pan réactif
- [ ] Couches toggle on/off
- [ ] Popup affichée au clic
- [ ] Minimap visible

### Recherche
- [ ] Taper un nom
- [ ] Résultats apparaissent
- [ ] Cliquer un résultat → zoom sur objet

### Outils Spatiaux
- [ ] Buffer: crée une zone tampon
- [ ] Stats: affiche les nombres
- [ ] Proximité: trouve l'objet proche
- [ ] Heatmap: affiche la densité

### Autres Outils
- [ ] Draw: dessiner polygone/ligne/point
- [ ] Measure: mesurer distance
- [ ] Print: imprimer la carte
- [ ] About: modal s'affiche

### Statistiques
- [ ] 4 cartes affichées (nombres)
- [ ] 3 tables visibles
- [ ] Pourcentages corrects
- [ ] Valeurs min/max/moyenne juste

### Mobile (F12 → Mobile)
- [ ] Layout responsive
- [ ] Boutons cliquables
- [ ] Texte lisible
- [ ] Pas de scroll horizontal

### Performance
- [ ] Lighthouse: F12 → Lighthouse
- [ ] Performance > 90
- [ ] Accesibilité > 85
- [ ] Best Practices > 90
- [ ] SEO > 80

---

## 🔄 Mettre à Jour le Site

### Faire une Modification
```bash
# Éditer index.html ou fichiers
nano index.html

# Tester localement
python -m http.server 8000

# Quand c'est bon:
git add .
git commit -m "Description du changement"
git push origin main
```

- [ ] Changement commit et push
- [ ] Vercel redéploie automatique
- [ ] Site mis à jour (1-2 min)

---

## 🆘 Dépannage Rapide

### "Les données ne chargent pas"
```bash
# Vérifier que data/ est dans le repo
git ls-files | grep data/

# Si absent:
git add data/
git commit -m "Add data"
git push
```

### "Erreur 404 sur Vercel"
```
1. Aller à Settings → Build & Development
2. Framework: Other
3. Build Command: (vide)
4. Output Directory: (vide)
5. Redéployer
```

### "Performance lente"
```
1. Vérifier la connexion réseau (F12)
2. Vérifier Lighthouse
3. Vérifier que c'est Vercel (pas GitHub Pages)
4. Vider le cache (Ctrl+Shift+Delete)
```

### "Console affiche erreurs"
```
1. Ouvrir F12 → Console
2. Lire les messages d'erreur
3. Vérifier les URLs dans index.html
4. Vérifier que data/ existe
```

---

## 📊 Monitoring Post-Deploy

### Semaine 1
- [ ] Vérifier qu'aucune erreur console
- [ ] Tester depuis différents appareils
- [ ] Tester depuis différents navigateurs
- [ ] Tester offline mode (si voulu)

### Mensuellement
- [ ] Vérifier Vercel Analytics
- [ ] Vérifier Core Web Vitals
- [ ] Mettre à jour les dépendances CDN si besoin
- [ ] Vérifier les logs d'erreur

---

## 🎉 Succès!

Si tout est ✅, c'est fini!

Votre application est maintenant:
- ✅ En ligne et accessible 24/7
- ✅ Optimisée pour la performance
- ✅ Disponible sur CDN mondial
- ✅ Déploiement automatique (à chaque push)
- ✅ HTTPS/SSL inclus
- ✅ Prêt pour la production

**Partager l'URL avec vos utilisateurs!** 🌍

---

**Besoin d'aide?** Ouvrir une Issue sur GitHub
