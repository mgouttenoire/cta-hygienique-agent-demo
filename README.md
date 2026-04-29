# CTA Hygiénique — Agent de dimensionnement

> **Quand l'expertise HVAC rencontre l'IA — un outil de dimensionnement CTA hygiénique pensé pour le terrain.**

[![Version](https://img.shields.io/badge/version-15.5-0d7c66)](./CHANGELOG.md)
[![License](https://img.shields.io/badge/license-Proprietary-blue)](./LICENSE)
[![Démo](https://img.shields.io/badge/démo-en%20ligne-brightgreen)](https://mgouttenoire.github.io/cta-hygienique-agent-demo/cta_hygienique_agent_v15_5.html)
[![Normes](https://img.shields.io/badge/normes-NF%20S%2090--351%20%C2%B7%20EN%201886%20%C2%B7%20ISO%2014644-success)](#normes-respectées)

---

## 🔗 Démo en ligne

**👉 [Lancer l'agent dans votre navigateur](https://mgouttenoire.github.io/cta-hygienique-agent-demo/cta_hygienique_agent_v15_5.html)**

Aucune installation. Aucun compte. L'agent fonctionne dans n'importe quel navigateur moderne (Chrome, Firefox, Safari, Edge).

---

## Présentation

Cet agent web autonome dimensionne les Centrales de Traitement d'Air (CTA) hygiéniques destinées aux **environnements régulés** : blocs opératoires, salles de réveil, services de soins intensifs, stérilisation, industries pharmaceutique et agroalimentaire, laboratoires.

Conçu et développé par un ingénieur d'affaires HVAC, il intègre les retours d'expérience terrain et les exigences normatives applicables en France et en Europe.

### Captures d'écran

> _Captures d'écran à venir : vue d'ensemble, bloc opératoire, diagramme Mollier._

---

## Pourquoi cet outil ?

Le dimensionnement d'une CTA hygiénique implique de croiser **8 à 10 contraintes simultanées** : débit, classe ISO, taux de renouvellement d'air, température et hygrométrie soufflées, surpression, étanchéité du caisson, niveau de filtration, récupération d'énergie, choix du fluide frigorigène, dimensionnement acoustique.

Beaucoup de bureaux d'études manipulent ces calculs dans des feuilles Excel maison, fragiles et non documentées, ou font appel à des configurateurs constructeurs orientés vente. Cet agent propose une **alternative indépendante, transparente et conforme aux normes**.

### Cas d'usage typiques

- Vérifier rapidement un dimensionnement reçu d'un BE
- Dégrossir une étude de faisabilité avant chiffrage détaillé
- Comparer plusieurs typologies sur un même projet (bloc + soins intensifs + stérilisation)
- Documenter un choix de conception dans un dossier technique
- Former un ingénieur junior à la méthode de dimensionnement

---

## Fonctionnalités

### Typologies d'environnements régulés (8)

- 🏥 **Bloc opératoire** (ISO 5 / ISO 7 / ultra-propre)
- 🩺 **Salle de réveil / SSPI** (PACU)
- 💊 **Stérilisation centrale**
- 🔬 **Laboratoire de microbiologie**
- 🧪 **Pharma — zone classée** (A / B / C / D)
- 🐟 **Agroalimentaire** (zones froides, salles blanches)
- 🛏️ **Chambre d'isolement** (immunodéprimé / contagieux)
- 🧬 **Salle propre industrielle** (ISO 6 à ISO 8)

### Calculs et exports

- **Calculs** : débit d'air, taux de renouvellement, batterie chaude/froide, récupérateur, encombrement, niveau sonore, consommation énergétique
- **Diagramme de l'air humide (Mollier)** interactif et exportable
- **Exports** : PDF rapport technique, PDF synthèse projet, Excel détaillé, IFC pour BIM, SketchUp .rb
- **Mode multi-CTA** : comparer plusieurs configurations sur un même projet
- **Bilingue** Français / Anglais

### Architecture technique

- **Mono-fichier HTML** autonome (~1.2 Mo) — fonctionne hors-ligne par double-clic
- **Aucune dépendance externe en runtime** — tout est embarqué
- **Vanilla JavaScript** — pas de framework, pas de build, pas de dépendance npm
- **SheetJS embarqué** pour la génération XLSX (Apache 2.0)

---

## Normes respectées

| Norme | Domaine | Application |
|-------|---------|-------------|
| **NF S 90-351** | Établissements de santé | Classification des zones, taux de renouvellement, surpression |
| **EN 1886** | Caissons CTA | Étanchéité, classe mécanique, performance thermique |
| **ISO 14644** | Salles propres | Classification particulaire, qualification |
| **EU F-Gas 2024/573** | Fluides frigorigènes | GWP, fluides autorisés, calendrier d'élimination |

---

## Méthodologie

Cet agent a été développé en mobilisant des **outils d'IA ciblés sur les problématiques techniques et scientifiques** : génération de code, vérification d'équations, structuration documentaire. La logique métier, les choix normatifs et les algorithmes de calcul reflètent l'expertise de l'auteur en CTA hygiénique. L'IA a accéléré la phase d'implémentation et de documentation, sans se substituer au jugement d'ingénieur.

Cette démarche illustre une approche que je propose en mission : **identifier où l'IA apporte une vraie valeur sur des problèmes techniques précis**, et où elle ne remplace pas l'expertise humaine.

---

## À propos de l'auteur

**Mikael Gouttenoire** — Ingénieur d'affaires HVAC, désormais consultant IA × HVAC, basé à Lyon.

Spécialisé dans les **environnements régulés** (santé, pharma, agroalimentaire), j'accompagne les bureaux d'études, maîtres d'ouvrage et industriels sur leurs projets de traitement d'air les plus exigeants.

Mon parcours en ingénierie d'affaires m'a confronté à la complexité réelle des projets — celle qui n'apparaît pas dans les manuels. Mon engagement dans les outils IA me permet aujourd'hui de proposer un accompagnement plus rapide, plus rigoureux et plus documenté.

---

## Services proposés

Pour tout projet en environnement régulé, je propose les missions suivantes :

### 🔍 Audit de conception CTA existante
Revue indépendante d'un dimensionnement réalisé par un BE, vérification de conformité normative, identification des optimisations possibles. Mission courte, livrable structuré.

### 📐 Dimensionnement CTA hygiénique
Étude de dimensionnement complète pour un projet ponctuel : bloc opératoire, zone pharma, agroalimentaire, laboratoire. Inclut diagramme Mollier, note de calcul, synthèse exécutive.

### 📚 Conseil normatif
Accompagnement sur l'application des normes NF S 90-351, EN 1886, ISO 14644, EU F-Gas 2024/573 dans un projet précis. Pour les équipes qui veulent sécuriser un point de conformité.

### 🤝 Sparring partner ingénierie
Mode collaboratif sur durée moyenne (3 à 12 mois), pour BE ou maître d'ouvrage souhaitant un avis externe régulier sur leurs études CTA hygiéniques en cours.

### 🎓 Formation équipe
Transfert de méthode aux ingénieurs juniors / dessinateurs / chargés d'affaires : dimensionnement CTA hygiénique, lecture de norme, utilisation d'outils IA pour le métier. Format demi-journée à 2 jours, sur site ou en visio.

**📩 Contact** : [LinkedIn](https://www.linkedin.com/in/mikael-gouttenoire-5ba9b7100/) · [Email](mailto:buffets-cinquiemes.7c@icloud.com)

---

## ⚠️ Précautions d'usage

Cette démonstration est fournie **à titre d'évaluation uniquement**. Les résultats produits ne constituent pas une étude d'ingénierie validée et ne doivent pas être utilisés tels quels pour la conception, le chiffrage ou la mise en œuvre d'une installation.

Pour un usage en projet réel, un engagement professionnel formel est requis (mission de conseil, contrat d'étude, validation par un ingénieur signataire).

---

## FAQ technique

<details>
<summary><b>L'agent fonctionne-t-il hors-ligne ?</b></summary>

Oui. Le fichier HTML embarque toutes les ressources nécessaires (CSS, JS, librairies, catalogues). Une fois téléchargé, il s'ouvre par double-clic dans n'importe quel navigateur moderne, sans connexion Internet.
</details>

<details>
<summary><b>Pourquoi un mono-fichier HTML et pas une application web classique ?</b></summary>

Trois raisons :
- **Portabilité** : un seul fichier à archiver, partager, joindre à un mail
- **Pérennité** : pas de dépendance à un serveur, un cloud, ou une stack technique qui peut être obsolète dans 3 ans
- **Auditabilité** : tout le code est lisible dans un seul fichier — important pour un outil métier où la transparence des calculs compte

Le format mono-fichier est aussi adapté à l'archivage en dossier technique de projet : on garde la version utilisée pour le calcul, on n'a pas à se poser de questions sur l'environnement.
</details>

<details>
<summary><b>Les calculs sont-ils traçables ?</b></summary>

Oui. Chaque résultat est associé à une référence normative et à une formule explicite, exportables en PDF ou Excel. La logique de calcul est documentée dans le code source, accessible depuis n'importe quel navigateur (clic droit → Afficher la source).
</details>

<details>
<summary><b>L'agent peut-il être adapté à mon contexte (typologie spécifique, normes locales) ?</b></summary>

Oui, dans le cadre d'une mission de conseil. Les algorithmes et les catalogues sont conçus pour être étendus. Les adaptations courantes : ajout d'une typologie spécifique (par exemple BSL-3, salle de cryoconservation), intégration de catalogues constructeurs spécifiques, ajustement des seuils selon des cahiers des charges internes.
</details>

<details>
<summary><b>Pourquoi pas un SaaS ?</b></summary>

Le format mono-fichier offline est volontaire. La plupart des bureaux d'études HVAC ont des contraintes de confidentialité fortes (secret professionnel, projets stratégiques) qui rendent un SaaS cloud difficile à déployer. Un fichier HTML local respecte naturellement ces contraintes — pas de données envoyées vers un serveur tiers, pas de question RGPD, pas de dépendance à la disponibilité d'un service externe.
</details>

<details>
<summary><b>Et le code source ?</b></summary>

Le code source de l'agent est **propriétaire** (voir [LICENSE](./LICENSE)). Cette démonstration est librement consultable et utilisable à des fins d'évaluation. Pour un usage commercial, une intégration dans un environnement métier, ou un développement sur mesure, contactez-moi.
</details>

---

## Versions

L'agent évolue régulièrement. Voir le [CHANGELOG](./CHANGELOG.md) pour le détail des versions.

**Version actuelle : 15.5** — Menu déroulant exports (regroupement UX), variables CSS Apple-clinique pour design system futur.

---

## Licence

Logiciel propriétaire — tous droits réservés. Voir [LICENSE](./LICENSE) pour les conditions complètes d'utilisation.

Inclut SheetJS (xlsx.full.min.js v0.18.5) sous licence Apache 2.0.

---

<div align="center">

**Vous êtes BE, maître d'ouvrage, industriel, et vous avez un projet CTA hygiénique en cours ?**

[💬 Me contacter sur LinkedIn](https://www.linkedin.com/in/mikael-gouttenoire-5ba9b7100/)

</div>
