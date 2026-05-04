# VéloRépare — Association de Réparation de Vélo

> **Réparer, ne pas jeter.**

Site web éco-conçu pour une association citoyenne dédiée à la réparation collaborative de vélos à Paris.  
Réalisé dans le cadre du mini-projet hackathon **TI616 Numérique Durable** — EFREI Paris 2025–2026.

---

## 🌐 Site en ligne

**[https://royta-creator.github.io/velovert/](https://royta-creator.github.io/velovert/)**

---

## 👥 Équipe projet

| Nom | Rôle |
|-----|------|
| **TAMWO Roy** | Chef de projet, déploiement GitHub Pages |
| **SEKHARA Arnaud** | Développement front-end, diagrammes UML |
| **VALLAT Hippolyte** | CRUD admin, authentification, données démo |
| **TADRIST Fahed** | Tests, empreinte carbone, rapport PDF |

Coordinateur du module : **Yvan GUIFO**

---

## ⚙️ Stack technique

| Couche | Technologie | Justification Green IT |
|--------|-------------|------------------------|
| Front-end | HTML5 · CSS3 · JS vanilla | 0 dépendance, 0 bundle, −200 Ko vs React |
| Illustrations | SVG inline | 0 requête image externe, −800 Ko estimés |
| Données | localStorage (navigateur) | 0 requête serveur, 0 latence réseau |
| Auth | sessionStorage (navigateur) | Session temporaire, pas de token persisté |
| Hébergement | GitHub Pages | Énergie 100 % renouvelable (Green Web Foundation) |

---

## 📊 Métriques Green IT (mesurées le 4 mai 2026)

| Indicateur | Valeur |
|------------|--------|
| Poids de la page | **167 Ko** |
| Requêtes HTTP | **5** |
| Score EcoIndex | **B — 76/100** |
| Score Lighthouse Performance | **99 / 100** |
| First Contentful Paint | **0,8 s** |
| Largest Contentful Paint | **0,8 s** |
| Total Blocking Time | **0 ms** |
| Classement EcoIndex | Top 17 % mondial (100 769 / 594 930) |

---

## 🚀 Installation et lancement en local

### Prérequis
Aucune dépendance — le site est un fichier HTML statique pur.

### Cloner le dépôt
```bash
git clone https://github.com/Royta-creator/velovert.git
cd velovert
```

### Lancer en local
```bash
# Option 1 — Ouvrir directement dans le navigateur
open index.html   # Mac
start index.html  # Windows

# Option 2 — Serveur local (recommandé pour éviter les restrictions CORS)
npx serve .
# puis ouvrir http://localhost:3000
```

### Accès admin (démo)
- Email : `admin@velorepare.fr`
- Mot de passe : `velovert2025`

---

## 🗂️ Structure du dépôt

```
velovert/
├── index.html                  # Site complet (HTML + CSS + JS, monofichier)
├── README.md                   # Ce fichier
├── diagrammes/
│   ├── diag_usecase.png        # Diagramme de cas d'utilisation (UML)
│   ├── diag_class.png          # Diagramme de classes / MLD
│   └── diag_seq.png            # Diagramme de séquence
├── empreinte carbone/
│   ├── empreinte carbone 1.png # Capture EcoIndex
│   └── empreinte carbone 2.png # Capture PageSpeed Insights
└── docs/
    └── VeloRepare-Rapport.pdf  # Rapport PDF du projet
```

---

## 🌿 Principes Green IT appliqués

- **Zéro image externe** — toutes les illustrations sont en SVG inline
- **Zéro framework JS** — JavaScript vanilla uniquement, pas de npm
- **Zéro requête API** — données persistées en localStorage côté client
- **Animations sobres** — CSS uniquement, aucune librairie d'animation
- **Hébergement vert** — GitHub Pages certifié Green Web Foundation
- **DOM minimal** — 480 éléments vs ~900 pour un site moyen

---

## 📝 Conventions de commits

```
feat: nouvelle fonctionnalité
fix: correction de bug
docs: modification de documentation
style: changement de style (CSS, mise en forme)
refactor: refactorisation de code
test: ajout ou modification de tests
```

---

## 🔗 Liens utiles

- [EcoIndex](https://www.ecoindex.fr) — mesure de l'empreinte environnementale
- [PageSpeed Insights](https://pagespeed.web.dev) — performance Lighthouse
- [Green Web Foundation](https://www.thegreenwebfoundation.org) — certification hébergement vert
- [Référentiel GR491](https://gr491.isit-europe.org) — guide Green IT

---

© 2026 VéloRépare — Association loi 1901 · EFREI Paris TI616
