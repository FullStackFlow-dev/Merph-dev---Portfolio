# 🚀 Portfolio Merphy Mademba — HTML Pure

> Développeur Full Stack | Cybersécurité | DevOps | Data | IA  
> Dakar, Sénégal

---

## 📋 À propos

Portfolio professionnel développé en **HTML pur** — sans framework, sans dépendances. Design moderne avec animations, responsive, et entièrement commenté pour faciliter la compréhension et la maintenance.

**URLs :**
- **Production :** [merph-dev.vercel.app](https://merph-dev.vercel.app)
- **Netlify (ancien) :** [merphdev-portfolio.netlify.app](https://merphdev-portfolio.netlify.app)

---

## ✨ Fonctionnalités

### Design & Interface
- ✅ Design moderne sombre avec accent vert néon
- ✅ Animations fluides (fade-in, hover effects)
- ✅ Responsive (desktop, tablette, mobile)
- ✅ Menu hamburger fonctionnel sur mobile
- ✅ Typographie distinctive (Playfair Display, Sora, IBM Plex Mono)
- ✅ Texture de bruit (noise) pour effet premium

### Sections
- ✅ **Hero** — Nom, description, tags de compétences, CTA
- ✅ **À propos** — Présentation, informations de contact
- ✅ **Compétences** — 6 domaines (Web, Cybersec, Linux, Data, IA, DevOps)
- ✅ **Certificats** — Anthropic, CompTIA (avec badges académiques)
- ✅ **Formation** — Timeline académique (Licence → Master 2028)
- ✅ **Projets** — 5 projets dont ArtéNova Shop (featured), liens Vercel
- ✅ **Contact** — Formulaire fonctionnel avec Formspree ⭐ **NOUVEAU**
- ✅ **Footer** — Liens réseaux sociaux, copyright

### Techniques
- ✅ Code entièrement commenté (chaque section, chaque style)
- ✅ HTML5 sémantique
- ✅ CSS3 avec variables CSS (maintenabilité)
- ✅ JavaScript vanilla (menu mobile, scroll fluide)
- ✅ Performance optimisée (1 seul fichier, pas de dépendances)

---

## 🆕 Dernière mise à jour majeure : Formulaire de contact

**Date :** 3 février 2025  
**Fonctionnalité :** Intégration de Formspree pour recevoir les messages

### Pourquoi ?

Le portfolio affichait un formulaire de contact, mais il ne fonctionnait pas réellement. Les visiteurs ne pouvaient pas m'envoyer de message directement.

### Solution

**Formspree** a été intégré — un service qui transmet les messages du formulaire vers ma boîte email sans nécessiter de backend.

### Bénéfices

**Pour les visiteurs :**
- ✅ Formulaire fonctionnel (nom, email, sujet, message)
- ✅ Envoi simple et rapide
- ✅ Confirmation immédiate
- ✅ Pas de compte requis

**Pour moi :**
- ✅ Notification email instantanée
- ✅ Dashboard Formspree pour voir tous les messages
- ✅ Anti-spam intégré
- ✅ Gratuit (50 messages/mois)

### Problème rencontré & résolu

**Problème initial :**  
Le formulaire avait `onsubmit="event.preventDefault()"` qui bloquait complètement l'envoi, même avec Formspree configuré.

**Cause :**
```html
<!-- ❌ AVANT : bloquait l'envoi -->
<form onsubmit="event.preventDefault()">
  <input type="text" placeholder="Nom" />
</form>
```

**Correction appliquée :**
```html
<!-- ✅ APRÈS : fonctionne -->
<form action="https://formspree.io/f/mdadyejk" method="POST">
  <input type="text" name="name" placeholder="Nom" />
</form>
```

**Changements effectués :**
1. ❌ Suppression de `onsubmit="event.preventDefault()"`
2. ✅ Ajout de `action="https://formspree.io/f/mdadyejk"`
3. ✅ Ajout de `method="POST"`
4. ✅ Ajout de `name="..."` sur tous les champs
5. ✅ Configuration de `_next` (redirection) et `_subject` (sujet email)

**Tests effectués :**
- ✅ Local : message envoyé et reçu
- ✅ Production : message envoyé et reçu
- ✅ Validation des champs (required, email format)
- ✅ Anti-spam activé

**Documentation complète :** Voir [FEATURE-FORMSPREE.md](./FEATURE-FORMSPREE.md)

---

## 🗂️ Structure du projet

```
portfolio/
├── index.html                      ← Fichier principal unique
├── README.md                       ← Ce fichier
├── FEATURE-FORMSPREE.md           ← Documentation ajout formulaire
├── GUIDE-AJOUT-IMAGE.md           ← Guide pour ajouter photo de profil
├── FORMSPREE-FIX.md               ← Résolution du problème formulaire
└── COMPARAISON-PORTFOLIOS.md      ← Analyse vs autres portfolios
```

**Note :** Tout le CSS et JavaScript est inclus dans `index.html` pour maximiser la simplicité et la performance (1 seul fichier = 1 seule requête HTTP).

---

## 🚀 Installation & Déploiement

### Option 1 : Ouvrir localement

```bash
# 1. Télécharge ou clone le fichier
git clone https://github.com/FullStackFlow-dev/portfolio.git

# 2. Ouvre index.html dans ton navigateur
# Double-clic sur le fichier OU
open index.html  # macOS
start index.html # Windows
```

**C'est tout !** Pas d'installation, pas de `npm install`, pas de build.

---

### Option 2 : Déployer sur Vercel

#### Via l'interface Vercel

1. Va sur [vercel.com](https://vercel.com)
2. **New Project** → **Import Git Repository**
3. Sélectionne ton repo GitHub
4. **Framework Preset :** Other
5. **Build Command :** (laisse vide)
6. **Output Directory :** `.` (juste un point)
7. **Deploy**

#### Via Vercel CLI

```bash
# 1. Installe Vercel CLI
npm install -g vercel

# 2. Déploie
vercel

# 3. Suis les instructions
```

---

### Option 3 : Déployer sur Netlify

#### Via drag & drop

1. Va sur [app.netlify.com](https://app.netlify.com)
2. Glisse-dépose le dossier du projet
3. Netlify déploie automatiquement

#### Via Netlify CLI

```bash
# 1. Installe Netlify CLI
npm install -g netlify-cli

# 2. Déploie
netlify deploy --prod

# 3. Glisse le dossier quand demandé
```

---

## 🎨 Personnalisation

### Couleurs

Modifie les variables CSS (ligne ~10) :

```css
:root {
  --bg: #0a0c0f;           /* Fond principal */
  --accent: #00e5a0;       /* Couleur d'accent (vert néon) */
  --text: #e2e8f0;         /* Texte principal */
  /* ... */
}
```

### Polices

Modifie le lien Google Fonts (ligne ~8) et les variables (ligne ~25) :

```css
:root {
  --font-display: 'Playfair Display', Georgia, serif;
  --font-body: 'Sora', sans-serif;
  --font-code: 'IBM Plex Mono', monospace;
}
```

### Ajouter une photo de profil

Voir le guide complet : [GUIDE-AJOUT-IMAGE.md](./GUIDE-AJOUT-IMAGE.md)

**Résumé rapide :**
1. Place ton image (`photo.jpg`) dans le même dossier que `index.html`
2. Dans le Hero (ligne ~1168), change :
   ```html
   <img src="votre-photo.jpg" ... />
   ```
   en :
   ```html
   <img src="photo.jpg" ... />
   ```

### Modifier les projets

Les projets sont dans la section `<section id="projects">` (ligne ~1440).

**Exemple — ajouter un projet :**

```html
<div class="project-card">
  <h4>Titre du projet</h4>
  <p>Description courte du projet</p>
  <div class="project-tags">
    <span>React</span>
    <span>Node.js</span>
  </div>
  <div class="project-links">
    <a href="https://demo.com" target="_blank">↗ Demo Live</a>
    <a href="https://github.com/..." target="_blank">↗ GitHub</a>
  </div>
</div>
```

### Configurer le formulaire de contact

Le formulaire utilise Formspree avec l'ID `mdadyejk`.

**Pour utiliser ton propre compte Formspree :**

1. Crée un compte sur [formspree.io](https://formspree.io)
2. Crée un nouveau formulaire
3. Copie ton Form ID (exemple : `abc123xyz`)
4. Dans `index.html` (ligne ~1640), change :
   ```html
   <form action="https://formspree.io/f/mdadyejk" method="POST">
   ```
   en :
   ```html
   <form action="https://formspree.io/f/TON_FORM_ID" method="POST">
   ```

Documentation complète : [FEATURE-FORMSPREE.md](./FEATURE-FORMSPREE.md)

---

## 🧪 Tests

### Vérifications avant déploiement

- [ ] Tous les liens fonctionnent (projets, réseaux sociaux)
- [ ] Menu hamburger s'ouvre/ferme sur mobile
- [ ] Formulaire de contact envoie des emails
- [ ] Images se chargent correctement
- [ ] Responsive sur mobile (tester avec DevTools)
- [ ] Pas d'erreurs dans la console navigateur

### Tester le formulaire localement

1. Ouvre `index.html` dans le navigateur
2. Va dans la section Contact
3. Remplis le formulaire avec tes vraies données
4. Clique sur "Envoyer"
5. Vérifie ton email (`merphy97@gmail.com`)

---

## 📊 Performance

| Métrique | Valeur | Note |
|---|---|---|
| **Taille fichier** | ~35 KB | ✅ Très léger |
| **Requêtes HTTP** | 2 (HTML + fonts) | ✅ Minimal |
| **Temps de chargement** | <500ms | ✅ Ultra-rapide |
| **Mobile-friendly** | Oui | ✅ 100% responsive |
| **Accessibility** | Sémantique HTML5 | ✅ Accessible |

**Lighthouse Score (estimé) :**
- Performance : 95-100
- Accessibility : 90-95
- Best Practices : 95-100
- SEO : 90-95

---

## 📚 Documentation

| Fichier | Description |
|---|---|
| `README.md` | Ce fichier — aperçu général |
| `FEATURE-FORMSPREE.md` | Documentation complète de l'ajout formulaire |
| `FORMSPREE-FIX.md` | Guide de résolution du problème formulaire |
| `GUIDE-AJOUT-IMAGE.md` | Guide pour ajouter une photo de profil |
| `COMPARAISON-PORTFOLIOS.md` | Analyse comparative avec d'autres portfolios |

---

## 🤝 Contribution

Ce portfolio est personnel, mais les suggestions sont bienvenues.

**Pour signaler un bug :**
1. Ouvre une issue sur GitHub
2. Décris le problème
3. Ajoute des captures d'écran si possible

**Pour proposer une amélioration :**
1. Fork le repo
2. Crée une branche (`git checkout -b feature/amelioration`)
3. Commit tes changements
4. Ouvre une Pull Request

---

## 📜 Changelog

### [1.2.0] - 2025-02-03

**Ajouté :**
- ✨ Formulaire de contact fonctionnel avec Formspree
- 📧 Notifications email pour chaque message reçu
- 📸 Support pour photo de profil dans le Hero
- 📝 Documentation complète (5 fichiers .md)

**Corrigé :**
- 🐛 `event.preventDefault()` qui bloquait l'envoi du formulaire
- 🐛 Attributs `name` manquants sur les champs du formulaire
- 🐛 Menu hamburger ne s'affichait pas sur mobile
- 🐛 Réseaux sociaux manquants dans le footer

**Amélioré :**
- 💬 Commentaires détaillés dans tout le code
- 📱 Responsive amélioré pour mobile
- 🎨 Animations plus fluides

### [1.1.0] - 2025-02-01

**Ajouté :**
- 🎓 Section Formation académique avec timeline
- 🏆 Section Certificats avec badges académiques
- 🚀 Projets déployés avec badges Vercel CI/CD

### [1.0.0] - 2025-01-30

**Initial :**
- 🎉 Première version du portfolio
- 🎨 Design moderne sombre
- 📱 Responsive complet
- 🔗 5 projets déployés

---

## 📞 Contact

**Merphy Mademba**

- 📧 Email : merphy97@gmail.com
- 💼 LinkedIn : [linkedin.com/in/merph-dev](https://linkedin.com/in/merph-dev)
- 💻 GitHub : [github.com/FullStackFlow-dev](https://github.com/FullStackFlow-dev)
- 🌐 Portfolio : [merph-dev.vercel.app](https://merph-dev.vercel.app)

---

## 📄 Licence

© 2025 Merphy Mademba. Tous droits réservés.

Ce portfolio est un projet personnel. Tu peux t'en inspirer, mais ne le copie pas tel quel.

---

**Version :** 1.2.0  
**Dernière mise à jour :** 3 février 2025  
**Statut :** ✅ En production
