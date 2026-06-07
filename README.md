# JF Visual — Guide de déploiement

Site avec animations 3D WebGL (Three.js) + panneau d'administration sans code (Decap CMS).

## 📦 Structure du projet

```
jfvisual/
├── index.html              ← Le site principal (Three.js, animations)
├── content/
│   └── content.json        ← Contenu du site (textes, services, projets)
├── admin/
│   ├── index.html          ← Interface admin (Decap CMS)
│   └── config.yml          ← Configuration des champs modifiables
├── netlify.toml            ← Configuration de déploiement
└── README.md               ← Ce fichier
```

## 🚀 Déploiement — Étape par étape

### Étape 1 — Créer un compte GitHub (5 min)

Si tu n'en as pas déjà un :

1. Va sur **github.com**
2. Crée un compte gratuit
3. Confirme ton email

### Étape 2 — Créer le repository (5 min)

1. Une fois connecté à GitHub, clique sur **"New repository"** (bouton vert en haut à droite)
2. Nom du repo : **`jfvisual-site`**
3. Mets-le en **Public**
4. Clique **"Create repository"**

### Étape 3 — Uploader les fichiers (5 min)

Sur la page du repo vide :

1. Clique **"uploading an existing file"**
2. **Glisse-dépose** tous les fichiers du projet (index.html, dossier admin/, dossier content/, netlify.toml)
3. En bas, clique **"Commit changes"**

### Étape 4 — Connecter à Netlify (10 min)

Netlify héberge ton site **gratuitement** et gère l'authentification de l'admin.

1. Va sur **netlify.com**
2. Crée un compte (utilise ton compte GitHub pour aller plus vite)
3. Une fois connecté, clique **"Add new site" → "Import an existing project"**
4. Sélectionne **GitHub** et autorise l'accès
5. Choisis ton repo **`jfvisual-site`**
6. Laisse les paramètres par défaut, clique **"Deploy"**
7. Attends 1-2 minutes, ton site est en ligne ! 🎉

L'URL temporaire ressemblera à : `random-name-12345.netlify.app`

### Étape 5 — Activer l'authentification admin (10 min)

Pour que tu puisses te connecter à `/admin` :

1. Dans ton tableau de bord Netlify, va dans **"Site configuration" → "Identity"**
2. Clique **"Enable Identity"**
3. Dans **Registration preferences** → mets **"Invite only"** (pour que seul toi puisses te connecter)
4. Toujours dans Identity, scroll vers **"Services" → "Git Gateway"** → clique **"Enable Git Gateway"**

### Étape 6 — Créer ton compte admin

1. Toujours dans Identity, clique **"Invite users"**
2. Entre ton email
3. Tu vas recevoir un email d'invitation
4. Clique le lien, crée ton mot de passe

### Étape 7 — Connecter ton domaine jfvisual.com (15 min)

1. Dans Netlify : **"Site configuration" → "Domain management"**
2. Clique **"Add custom domain"**
3. Entre **jfvisual.com**
4. Netlify te donne des **serveurs DNS** à configurer
5. Va chez ton registrar (où tu as acheté le domaine) et configure les DNS selon les instructions Netlify
6. Attends 1-24h pour la propagation DNS

## ✏️ Comment modifier le contenu

Une fois tout configuré :

1. Va sur **`tonsite.netlify.app/admin/`** (ou **`jfvisual.com/admin/`**)
2. Connecte-toi avec ton email/mot de passe
3. Tu vois un panneau avec tous les champs modifiables :
   - Tagline du hero
   - Titres
   - Services (ajouter/supprimer/modifier)
   - Projets portfolio
   - Email/téléphone de contact
4. Modifie ce que tu veux
5. Clique **"Publish"** en haut à droite
6. Le site se met à jour automatiquement en 1-2 minutes

## 🎨 Personnalisation avancée (si tu veux toucher au code)

**Changer la couleur rouge** : ouvre `index.html`, cherche `--red:#e63946` et change le code hex

**Changer les polices** : modifie la ligne `<link href="https://fonts.googleapis.com/...">`

**Modifier les animations 3D** : tout est dans la balise `<script type="module">` à la fin du HTML

## ❓ Problèmes fréquents

**"Je ne peux pas me connecter à /admin"** → Vérifie que Git Gateway est activé dans Netlify Identity

**"Les changements ne s'affichent pas"** → Attends 1-2 minutes, Netlify reconstruit le site à chaque modification

**"Le site est blanc"** → Vérifie la console du navigateur (F12), il y a probablement une erreur JavaScript

## 💰 Coûts

- **GitHub** : Gratuit
- **Netlify** : Gratuit (jusqu'à 100GB de bande passante/mois)
- **Decap CMS** : Gratuit (open source)
- **Domaine jfvisual.com** : ~15$/an

**Total : ~15$/an** pour un site pro avec admin sans code.

---

Bonne chance avec JF Visual ! 🚀
