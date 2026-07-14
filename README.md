# Nidexo — Landing Page

Landing page officielle de **Nidexo**, l'employé IA qui répond à vos clients, automatise vos ventes et gère vos commandes sur WhatsApp et Messenger.

🔗 Site en ligne : *(à ajouter après déploiement, ex. `https://nidexo.com` ou `https://username.github.io/nidexo`)*

## 📁 Structure du projet

```
nidexo-site/
├── index.html        # Page d'accueil complète (Hero, Pourquoi Nidexo, Comment ça marche,
│                      #   Démo multilingue, Voix de marque, Tableau de bord, Intégrations,
│                      #   Tarifs, Formulaire de démo, FAQ, CTA final, Footer)
├── style.css          # Tous les styles de la landing page (design tokens, composants, responsive)
├── app.js             # Sélecteur de langue (FR/AR/EN), démo multilingue animée,
│                      #   accordéon FAQ, animations au scroll
├── login.html         # Connexion / Création de compte (onglets, redirige vers onboarding.html)
├── onboarding.html    # Assistant de configuration en 6 étapes (premier lancement)
├── pricing.html       # Page tarifs autonome + tableau comparatif + FAQ tarifs
├── demo-chat.html     # Démo WhatsApp interactive (chat simulé, mots-clés → réponses)
├── ui-kit.html        # Référence des composants pour les développeurs (couleurs, typo, boutons…)
├── privacy.html       # Politique de confidentialité
├── terms.html         # Conditions d'utilisation
└── README.md
```

> `login.html`, `onboarding.html`, `pricing.html`, `demo-chat.html` et `ui-kit.html` sont autonomes (styles inline) pour rester faciles à déplacer ou tester isolément. Si le projet grandit, les fusionner dans `style.css` évitera la duplication de tokens.

## 🎨 Identité visuelle

Les couleurs, la typographie et les composants suivent le Brand Book officiel de Nidexo :

| Token       | Couleur   |
|-------------|-----------|
| Purple      | `#6C4DFF` |
| Blue        | `#0288FF` |
| Cyan        | `#00C2FF` |
| Green       | `#00D084` |
| Pink        | `#FF4D9D` |
| Warning     | `#FFB020` |
| Danger      | `#FF4D4F` |

**Police :** [Poppins](https://fonts.google.com/specimen/Poppins) (latin) + [Noto Kufi Arabic](https://fonts.google.com/noto/specimen/Noto+Kufi+Arabic) (arabe).

Tous les tokens de couleur sont définis en variables CSS dans `style.css` (`:root { --purple, --blue, ... }`), à modifier à un seul endroit si la charte évolue.

## 🌍 Multilingue

Le site propose un sélecteur **FR / عربي / EN** dans la barre de navigation. Les traductions sont gérées côté client dans `app.js` (objet `translations`), sans dépendance externe. Le passage en arabe bascule automatiquement la page en `dir="rtl"` et en police Noto Kufi Arabic.

> Il ne s'agit pas d'un système i18n de build (type next-intl / i18next) — volontairement, pour rester un site statique simple à héberger. Si le site grandit (plusieurs pages, contenu dynamique), migrer vers un vrai framework i18n est recommandé.

## 🚀 Déploiement sur GitHub Pages

1. Créer un repo GitHub (ex. `nidexo-landing`) et y pousser le contenu de ce dossier.
2. Aller dans **Settings → Pages**.
3. Sous **Source**, choisir la branche `main` et le dossier `/ (root)`.
4. Le site sera disponible sous `https://<votre-username>.github.io/nidexo-landing/`.

Pour un nom de domaine personnalisé (ex. `nidexo.com`), ajouter un fichier `CNAME` à la racine contenant le domaine, et configurer le DNS chez votre registrar (enregistrement `A` vers les IPs GitHub Pages ou `CNAME` vers `<username>.github.io`).

## ✏️ À personnaliser avant le lancement

- [ ] Remplacer le numéro dans le bouton flottant WhatsApp (`app.js` non concerné — lien direct dans `index.html`, chercher `wa.me/21600000000`)
- [ ] Brancher le formulaire de démo (`#lead`) à un vrai backend ou service (ex. Formspree, Airtable, Google Sheets)
- [ ] Confirmer et afficher les tarifs réels (actuellement « Coming Soon »)
- [ ] Ajouter les liens réels LinkedIn / Facebook dans le footer
- [ ] Faire relire `privacy.html` et `terms.html` par un professionnel du droit avant le lancement commercial
- [ ] Ajouter un favicon (`favicon.ico` / `favicon.png`) et les meta tags Open Graph pour le partage sur les réseaux

## 🛠️ Développement local

Aucune dépendance ni build requis — pur HTML/CSS/JS. Pour prévisualiser :

```bash
# Avec Python
python3 -m http.server 8000

# puis ouvrir http://localhost:8000
```

---

© 2026 Nidexo — Tunisie.
