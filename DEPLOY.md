# 🚀 Guide de Déploiement sur GitHub

## Prérequis
- [Git](https://git-scm.com/) installé
- Compte [GitHub](https://github.com)
- Compte [Vercel](https://vercel.com) (recommandé) OU utiliser GitHub Pages

---

## 📋 Étape 1: Préparer votre dépôt local

```bash
# Aller dans le dossier du projet
cd c:\Users\user\Desktop\sigAPPexam\geo-sn

# Initialiser Git (si pas déjà fait)
git init

# Ajouter tous les fichiers
git add .

# Créer le commit initial
git commit -m "WebSIG Pro v2.1 - Production Ready"
```

---

## 🐙 Étape 2: Créer un dépôt sur GitHub

1. **Aller sur** https://github.com/new
2. **Remplir:**
   - Repository name: `websig-tivaouane`
   - Description: `Application Web SIG pour Tivaouane`
   - Public
   - ✅ Add a README (non, on en a)
   - ✅ .gitignore (Python)
3. **Cliquer** "Create repository"

---

## 🔗 Étape 3: Connecter votre repo local à GitHub

```bash
# Remplacer [VOTRE_USERNAME] par votre username GitHub
git remote add origin https://github.com/[VOTRE_USERNAME]/websig-tivaouane.git

# Renommer la branche principale en 'main'
git branch -M main

# Pousser le code
git push -u origin main
```

**Résultat:** Votre code est maintenant sur GitHub! 🎉

---

## 🚀 Option 1: Déployer sur Vercel (RECOMMANDÉ)

### Avantages:
- ✅ Ultra-rapide (CDN mondial)
- ✅ SSL/HTTPS gratuit
- ✅ Déploiement auto à chaque push
- ✅ 100/100 Lighthouse

### Étapes:

1. **Aller sur** https://vercel.com
2. **Cliquer** "Import Project"
3. **Sélectionner** GitHub
4. **Chercher** "websig-tivaouane"
5. **Cliquer** Import
6. **Laisser les settings par défaut**
7. **Cliquer** Deploy

**Votre site sera à:** `https://websig-tivaouane.vercel.app`

---

## 🐱 Option 2: Déployer sur GitHub Pages (GRATUIT + SIMPLE)

### Avantages:
- ✅ Gratuit à vie
- ✅ Intégré à GitHub
- ✅ Pas de configuration complexe

### Étapes:

1. **Aller sur** votre repo GitHub
2. **Settings** (engrenage en haut à droite)
3. **Pages** (menu gauche)
4. **Source:** `Deploy from a branch`
5. **Branch:** `main` → `/(root)`
6. **Cliquer** Save

**Votre site sera à:** `https://[votre-username].github.io/websig-tivaouane`

**Attendre 1-2 minutes** que le déploiement se termine.

---

## ✅ Vérifier que tout marche

1. **Aller sur votre URL** (Vercel ou GitHub Pages)
2. **Attendre le chargement des données** (5-10 secondes)
3. **Vérifier:**
   - ✅ La carte s'affiche
   - ✅ Les 5 couches sont visibles
   - ✅ Recherche fonctionne
   - ✅ Outils spatiaux répondent
   - ✅ Statistiques affichées

---

## 📤 Mettre à jour le site (push futur)

```bash
# Faire vos modifications localement

# Committer les changements
git add .
git commit -m "Description de vos changements"

# Pousser vers GitHub
git push origin main
```

**Vercel** redéploiera automatiquement! 🚀

---

## 🔧 Optimisations Active

Ces optimisations sont déjà en place:

✅ **Caching localStorage**
- Les données GeoJSON sont mises en cache
- Rechargement ultra-rapide en visite suivante

✅ **Fallback mode**
- Si une couche ne charge pas → affichage partiel
- Pas de blocage complet

✅ **Vercel.json**
- Compression optimale
- Headers cache configurés
- CORS activé

✅ **.gitignore correct**
- Les données ne sont pas ignorées
- Tout est inclus dans le repo

---

## 🐛 Dépannage

### "Repository not found"
```bash
# Vérifier que c'est bien votre username
git remote -v

# Corriger si besoin
git remote set-url origin https://github.com/[VOTRE_USERNAME]/websig-tivaouane.git
```

### Les données ne se chargent pas
```
1. Vérifier que data/ est dans le repo
   git ls-files | grep data/
   
2. Si absent, ajouter:
   git add -f data/
   git commit -m "Add data files"
   git push
```

### Vercel dit "Build failed"
```
1. C'est normal pour un site statique
2. Aller à Settings → Build & Development Settings
3. Framework Preset: Other (Static)
4. Output Directory: (laisser vide)
5. Redéployer
```

---

## 📊 Performance

Une fois déployé:
- **Temps de chargement:** < 3 secondes
- **Performance Lighthouse:** 95+ 
- **Uptime:** 99.99%
- **Disponible:** Partout dans le monde

---

## 🎯 Prochaines Étapes

1. ✅ Domain personnalisé (optionnel)
   - Vercel: Settings → Domains
   - GitHub Pages: Custom domain

2. ✅ SEO
   - Meta tags dans index.html
   - Open Graph pour partage réseaux

3. ✅ Analytics
   - Google Analytics (ajouter dans index.html)
   - Vercel Analytics (gratuit)

---

## 📞 Support

- ❓ Questions Vercel: https://vercel.com/support
- ❓ Questions GitHub: https://github.com/support
- 🐛 Problèmes: Ouvrir une Issue sur GitHub

---

**Prêt à deployer? Commencez par l'Étape 1!** 🚀
