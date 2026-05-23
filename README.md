# Stellantis / PSA - DS Automobiles Trip Analyser

<img width="1143" height="375" alt="image" src="https://github.com/user-attachments/assets/16e05a46-f3cd-4dba-bc33-53292d4cb61c" />

Outil web **100 % frontend** pour visualiser, filtrer et analyser les exports CSV des trajets du système **myDS** (Testé et validé pour DS7 Crossback, application myDS 1.53.1).
- Format français supporté nativement (`;` comme séparateur, dates `DD/MM/YY`, virgules décimales)
- Aucun backend, tout tourne dans le navigateur
- Données 100 % privées (aucun upload)

## Aperçu des fonctionnalités

<img width="1401" height="775" alt="image" src="https://github.com/user-attachments/assets/dfe6f30e-755a-44a8-bfa3-113ff61643ee" />
<img width="1400" height="535" alt="image" src="https://github.com/user-attachments/assets/8c7b90bc-6f0d-4289-919c-45984ea63b5c" />
<img width="1398" height="643" alt="image" src="https://github.com/user-attachments/assets/015cae77-c9bd-4a86-853b-575cc8a847d8" />


- **KPIs globaux** : nombre de trajets, km total, distance/conso/vitesse moyennes, coût total
- **Filtres avancés** :
  - Période (date départ / arrivée)
  - Catégories (Professionnel / Loisirs / Sans catégorie)
  - Plage de distance (**minimum ET maximum**)
  - Recherche texte dans les adresses
- **Tableau interactif** :
  - Tri par colonne (date, distance, vitesse, coût…)
  - Pagination configurable
  - Détails complets d’un trajet en modal
- **Graphiques** (Chart.js) :
  - Tendance mensuelle (trajets + km)
  - Répartition par catégorie (donut)
  - Consommation moyenne mensuelle (L/100 km)
  - Vitesse moyenne mensuelle (km/h)
  - Kilométrage cumulé
- **Vitesses moyenne** calculées automatiquement (distance / durée)
- **Export CSV filtré** (garde uniquement les trajets visibles)

## Comment l’utiliser

### 1. Export depuis myDS

1. Va sur l’application myDS des propriétaires DS Automobiles (https://play.google.com/store/apps/details?id=com.psa.mym.myds&hl=fr&pli=1)
2. Exporte l’historique des trajets au format CSV (séparateur `;` attendu)
3. Dans Mon compte -> Paramètres -> Données de conduite -> Exportez vos trajets
4. Le nom du fichier ressemble généralement à : `myDS-trips-05-22-2026.csv`
5. Plus d'info sur les services connectés DS Automobiles : https://www.dsautomobiles.fr/votreds/votreds-et-vous/myds-app-connected-services.html

### 2. Visualisation locale (recommandé)

1. Clone ou télécharge uniquement `index.html` + `demo-trips.csv`
2. Ouvre `index.html` avec n’importe quel navigateur moderne
3. Glisse-dépose ton fichier CSV dans la zone prévue
   - ou clique pour sélectionner le fichier

Tout est stocké en local. Tu peux même le déconnecter d’Internet.

### 3. Version démo

Le fichier `demo-trips.csv` contient une vingtaine de trajets fictifs réalistes (mêmes colonnes + format).  
Tu peux l’ouvrir directement pour tester l’interface sans données personnelles.

## Structure du dépôt

```
DS7_Trip_Analyser/
├── index.html          # Application complète (HTML + Tailwind + Chart.js)
├── demo-trips.csv      # Données fictives pour démonstration
├── README.md
└── .gitignore
```

**Important :**  
Ton véritable export (`myDS-trips-*.csv` ou tout autre CSV contenant tes trajets) **ne doit jamais** être commit sur GitHub.

→ voir le `.gitignore` fourni.

## Personnalisation rapide

- Largeur maximale des sliders distance → 300 km (modifiable directement dans le code si tu fais des trajets plus longs)
- Page size par défaut = 25 (modifiable dans la balise `<select id="page-size">`)

## Dépendances (CDN – aucune installation)

- Tailwind CSS (via CDN)
- Chart.js v4
- Font Awesome 6

## Licence

MIT – fais ce que tu veux avec le code.

---

**Made by [esquiiom](https://github.com/eskiiom)** – Retrouve le projet ici : https://github.com/eskiiom/DS-Automobiles-Trip-Analyser

**Bon road-trip !** 🚗
