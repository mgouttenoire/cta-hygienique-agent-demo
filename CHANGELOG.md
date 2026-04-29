# Changelog

Toutes les évolutions notables de ce projet sont documentées dans ce fichier.
Format basé sur [Keep a Changelog](https://keepachangelog.com/fr/1.1.0/), versioning [SemVer](https://semver.org/lang/fr/).

---

## [15.5] — 2026-04-28

### Ajouté
- **Menu déroulant exports (Phase 1b)** : les ~10 boutons d'export éparpillés dans l'action bar et l'export bar sont regroupés dans un seul bouton `Exports ▾` par CTA, ouvrant un menu déroulant accessible.
  - 5 groupes : Rapports (PDF) · Données · BIM & 3D · Descriptif · Visualiser.
  - Navigation clavier complète : `↑`/`↓` wrap-around, `Home`/`End`, `Escape`, `Tab`.
  - ARIA complet : `aria-haspopup="menu"`, `aria-expanded`, `role="menu"`, `role="menuitem"`, `role="separator"`.
  - Fermeture au clic en dehors via event delegation (résistant aux rebuilds de panel lors du switch de langue).
  - Styles via variables CSS Apple-clinique (`--accent`, `--bg-primary`, `--border-subtle`, `--radius-*`, `--focus-ring`, etc.) introduites en v15.4.
- Nouvelles clés i18n dans `T.fr`/`T.en` et `LANG_EN` : `btn_exports`, `exp_group_pdf`, `exp_group_data`, `exp_group_bim`, `exp_group_desc`, `exp_group_nav`.

### Modifié
- L'export bar (`.export-bar`) est supprimée du HTML généré par `buildCTAPanelHTML`. Le span `export-status` est conservé inline dans l'action bar.
- `initCTAHandlers(ctaId)` appelle désormais `initExportsMenu(ctaId)`.
- Fichier renommé `cta_hygienique_agent_v15_4.html` → `cta_hygienique_agent_v15_5.html`.
- Harmonisation numéros de version v15.4 → v15.5 (title, topbar, footers PDF ×3, IFC `FILE_NAME`, Ruby SketchUp, canvas SVG ×2, i18n EN, descriptif, banner JS).

### Notes de conception
- La fonction `initExportsMenu` utilise l'event delegation sur `document` (handlers globaux, mis en place une seule fois) afin de rester opérationnelle après le rebuild de panel lors du switch de langue — sans modifier `setLang()`.
- Les boutons "Voir Encombrement" et "Graphiques analytiques" (navigation) sont inclus dans le groupe "Visualiser" du menu, conformément à l'instruction de regrouper **tous** les boutons de l'export bar.
- `exportSynthesisPDF()` est une action globale (non liée à une CTA spécifique) ; son inclusion dans le menu per-CTA suit le groupement demandé dans l'issue.

---

## [15.4] — 2026-04-27

### Ajouté
- **Design tokens CSS Apple-clinique (Phase 1a)** : bloc `:root` introduit en tête du `<style>` global avec 29 variables CSS (fonds, bordures, texte, accent teal médical, statuts métier, focus ring, rayons). Aucune variable consommée dans cette version — fondation pour Phase 1b (menu exports) et Phase 4 (refonte CSS globale).

### Modifié
- Fichier renommé `cta_hygienique_agent_v15_3.html` → `cta_hygienique_agent_v15_4.html`.
- Harmonisation numéros de version v15.3 → v15.4 (title, topbar, footers PDF ×3, IFC `FILE_NAME` + `IFCAPPLICATION`, Ruby SketchUp, canvas SVG ×2, i18n EN, descriptif, banner JS).

---

## [15.3] — 2026-04-22

### Corrigé
- **Fin de la dépendance CDN XLSX**. La bibliothèque `xlsx.full.min.js` v0.18.5 (SheetJS) est désormais **embarquée inline** dans le HTML. L'export Excel fonctionne en `file://` **sans aucune connexion réseau**. Le fichier passe de 619 Ko à 1,18 Mo (compromis assumé pour l'offline complet).
- Intégrité vérifiée : JS syntaxiquement valide (`node --check` OK), byte-identique à la source npm, fonctions `XLSX.utils` / `XLSX.write` opérationnelles après chargement jsdom.

### Modifié
- **Harmonisation numéros de version v14 → v15.3** partout où la référence concerne la version applicative :
  - `<title>` HTML
  - Sous-titre topbar
  - Pied de page rapport PDF (rapport technique, rapport dimensionnement, budget)
  - Métadonnées IFC (`FILE_NAME` et `IFCAPPLICATION`)
  - En-tête script Ruby SketchUp
  - Labels canvas (SVG `AGENT v15`, `SIZING AGENT v15`)
  - Dictionnaire i18n (`LANG_EN`) pour le titre EN
- Les commentaires de code `// Clés ajoutées v15` / `// Labels additionnels v15` sont **conservés** comme annotations historiques d'ajout dans le dictionnaire i18n — ce ne sont pas des références de version applicative.

### Sécurité / autonomie
- Confirmation : plus aucune balise `<script src="https://...">` externe dans le fichier. Le HTML est 100 % autonome.

---

## [15.2] — 2026-04

### Ajouté
- Internationalisation complète FR ↔ EN via moteur DOM post-rendu (`LANG_EN` + `_i18nNode`), sans modification du code métier.
- Bascule langue instantanée via bouton `🇬🇧 EN` / `🇫🇷 FR` dans la barre d'onglets.
- Bouton golden case `🏥 OR Montbrison ×2` pour créer automatiquement deux CTA blocs opératoires pré-câblées.
- Panneau réseau AN (`🔗 Réseau AN`) avec visualisation des flux entre CTA source / dépendantes / autonomes.
- Bilan capacités sources AN avec calcul automatique du débit extrait centralisé (∑ Q_souf − Q_AN des zones dépendantes).

### Modifié
- Catalogue ROBATHERM étendu : GX-1000 à GX-20000.
- Catalogue Flakt Group Clinicair ajouté : CAH-800 à CAH-20000.

### Corrigé
- Récupération plaques / rotatif désactivés d'office quand `pct_an ≥ 100 %` (protection contamination croisée).
- Restauration des liens `dep_an` entre sessions via index `ctaList` plutôt que par ID volatile.

### Problèmes connus (résolus en v15.3)
- ~~Dépendance CDN à `xlsx.full.min.js` (Cloudflare) → exports Excel impossibles sans connexion au premier chargement.~~ ✅ Résolu v15.3
- ~~Mélange `v14` / `v15` dans le HTML.~~ ✅ Résolu v15.3

---

## [15.0]

### Ajouté
- Architecture multi-CTA (jusqu'à 10).
- Projets mémorisés localStorage (`ctahyg_projects`, max 50 entrées).
- Mode Simplifié / Expert avec persistance.
- Diagramme de Mollier SVG interactif.
- Bilan CO₂ par pays (21 mix électriques).
- Export IFC 4 (buildingSMART IFC4 ADD2 TC1).
- Export SketchUp Ruby (.rb).
- Calcul PA disponible à 50 % d'encrassement (EN 779).
- Classes SFP ErP 1-7.

---

## [14.0]

### Ajouté
- Synthèse projet multi-CTA (tableau de bord + prescriptions).
- Export descriptif technique format UNITAIR.
- Plan d'encombrement A3 technique professionnel avec vues multiples.

---

## [10.0]

### Ajouté
- Polyfill `ctx.roundRect()` pour compatibilité Edge / Firefox anciens.
- Version "offline-safe" : Google Fonts retirées (bloquées par Edge en `file://`).
- Polices système uniquement (Consolas, Segoe UI).

### Corrigé
- Crash `showTab(null)` sur onglet absent.
- Champ "débit" redondant retiré (auto-calculé à partir surface × hauteur × brassage).

---

## Format des entrées

Chaque release doit utiliser ces sections dans l'ordre si elles s'appliquent :
- **Ajouté** — nouvelles fonctionnalités
- **Modifié** — évolutions de comportement
- **Déprécié** — fonctionnalités qui seront retirées
- **Retiré** — fonctionnalités supprimées
- **Corrigé** — correctifs de bugs
- **Sécurité** — vulnérabilités corrigées
- **Problèmes connus** — limitations identifiées non corrigées dans cette version

## À venir (v15.6 et au-delà)

- Suite de tests JSON snapshot automatisée pour les 5 cas de référence du `CLAUDE.md` §9.
- Complétion du dictionnaire `LANG_EN` pour tous les libellés récents (Réseau AN, Prescriptions, boutons Mode Expert).
- Refonte export IFC pour schéma IFC4X3 (évolution buildingSMART).
- Wizard multi-étapes (Phase 4) — à évaluer sur mockup HTML/SVG avant implémentation.
