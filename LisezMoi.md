# MARCO — Cerveau Cybernétique à Architecture de Décision Hiérarchique

> \\\\\\\*"Apprendre, c'est se ressouvenir"\\\\\\\* — Platon, Ménon

**Auteur** : José WALOCHA  
**Équipe** : Le Duke (Claude), Marcel (Mistral), Biloute (ChatGPT), Didier (Qwant)  
**Licence** : GNU GPL v3  
**Version** : 5.0 — Mars 2026

\---

## 1\. Qu'est-ce que MARCO ?

MARCO est le premier **SGBDOCN** — Système de Gestion de Base de Données Orienté Concepts Neuronaux.

Là où un SGBD classique stocke des lignes dans des tables, MARCO stocke des **concepts dans un réseau neuronal inspiré du cerveau biologique**. Le sens émerge des liens. Pas de SQL. Pas de schéma fixe. Zéro boîte noire.

||SGBD classique|MARCO|
|-|-|-|
|Stockage|Tables, lignes, colonnes|Phares, dendrites, concepts|
|Requête|`SELECT \\\\\\\* FROM ...`|Activation en cascade|
|Relations|Clés étrangères|Co-occurrences, coactivations|
|Schéma|Fixe|Émergent|
|Index|B-Tree, Hash|purk\_index thermique|
|Apprentissage|Aucun|Gavage + consolidation|
|Transparence|Requête = résultat|Chaque lien traçable|

Un SGBD classique est statique (Thanatos). MARCO est vivant (Anima) : il apprend en lisant.

\---

## 2\. Architecture — Vue d'ensemble

```
Couche I    — Lettres          1 lettre = 1 neurone (cascade BSC)
Couche II   — Phares           1 mot = 1 concept Binder-9D
Couche III  — Concepts         N mots = 1 bloc (BSCW, fenêtre glouton)
Couche IV   — Co-occurrences   Le sens par le voisinage
Couche V    — Séquences        La syntaxe par l'ordre
```

### Poupées russes — class Concept(Phare)

Un Concept EST un Phare. Il hérite de tout, plus une famille, des réponses, des composants.

Les niveaux s'emboîtent sans limite :

```
Niveau 0 : Lettres       c, a, f, é
Niveau 1 : Mots          café, crème
Niveau 2 : Concepts      café crème
Niveau 3 : Registres     COMMANDE
Niveau N : ...
```

\---

## 3\. Le génome — Binder-9D

Chaque phare est positionné dans un espace sémantique à 9 axes cybernétiques :

|Axe|Signification|
|-|-|
|AT|Tension cognitive (observation sans réaction)|
|SU|Subjectivité (ancrage dans le sujet)|
|EG|Appartenance au soi|
|OS|Ancrage dans l'espace physique|
|TY|Type ontologique (0=objet, 1=agent, 2=action...)|
|VA|Valence affective|
|EC|Résonance culturelle|
|TM|Temporalité|
|IN|Intensité informationnelle|

Le génome v60 contient **13 304 soleils** avec handles Binder-9D complets.

Les aires futures (sonore, visuelle) utiliseront le même squelette 9 axes réorienté vers leur domaine.

\---

## 4\. Pipeline de traitement

```
Texte brut
  → Déshabillage (suppression syntaxe française)
  → BSC (détection phares par cascade lettres)
  → BSCW (détection concepts multi-mots)
  → Thalamus (routage, étiquetage)
  → Hippocampe (consolidation mémoire)
  → memoire\\\\\\\_index (purk\\\\\\\_index thermique)
```

### Modes de traitement

|Mode|BSCW|Apprentissage|Usage|
|-|-|-|-|
|gavage|non|dendrites, co-occ|Textes bruts, livres|
|dialogue|oui|dendrites, co-occ|Interaction|
|lecture|oui|+ contexte hippocampe|Gavage intelligent|

\---

## 5\. Mémoire — L'hippocampe et le purk\_index

### Structure

```
memoire\\\\\\\_index  {incipit → PurkIndex}
    └── PurkIndex  — nœud Purkinje de consolidation
            incipit         : list\\\\\\\[str]   — N premiers handles (pivot universel)
            pivot\\\\\\\_type      : str         — incipit | compose\\\\\\\_nominal | compose\\\\\\\_evenementiel | compose\\\\\\\_sequentiel
            pivot\\\\\\\_composants: list\\\\\\\[str]
            episodes        : list\\\\\\\[ConceptIndex]
            dendrites       : dict\\\\\\\[str, float]   — index inversé pondéré
            sous\\\\\\\_purks      : dict\\\\\\\[str, PurkIndex]  — arborisation fractale
            temperature     : float       — état thermique courant
            materiau        : str         — handle génome (MAGMA, ACIER, VERRE, GLACE...)
            etiquettes\\\\\\\_dominantes : dict
            statistiques\\\\\\\_coactivation : dict
    └── ConceptIndex  — épisode d'une phrase
            handles         : list\\\\\\\[str]
            pivot\\\\\\\_forme     : str
            pivot\\\\\\\_type      : str
            pivot\\\\\\\_composants: list\\\\\\\[str]
            vecteur\\\\\\\_bsc     : dict        — {presence, roles, relations, tensions, questions}
            contexte\\\\\\\_induit : dict        — {langue, aire, cadre\\\\\\\_source, narrateur, lieu, temporalite, registre, statut, certitude}
            source          : dict        — {texte\\\\\\\_id, auteur, titre, ligne, phrase, timestamp}
            epa             : dict        — {attention, pression, emotion, intensite}
```

### Le pivot = l'incipit

Le pivot n'est pas calculé — c'est ce qui arrive en premier dans le flux. Les N premiers handles constituent l'entrée dans `memoire\\\\\\\_index`. L'ordre d'arrivée prime sur la saillance sémantique.

### Modèle thermique

Chaque `PurkIndex` a une **température** et un **matériau** :

```
temperature(t) = plancher + (temp\\\\\\\_initiale - plancher) × e^(-t / demi\\\\\\\_vie)
```

Le matériau est un handle du génome qui porte `demi\\\\\\\_vie` et `plancher` dans son vsem :

|Matériau|Comportement|
|-|-|
|MAGMA|Refroidit très lentement, plancher élevé — trauma, premier amour|
|ACIER|Refroidit vite si non réactivé — souvenir ordinaire intense|
|VERRE|Fragile, plancher bas — information lue sans attention|
|GLACE|Froid dès la naissance — stockage immédiat en profondeur|
|CENDRE|Température quasi nulle — information distraite|

Le matériau est **mutable** : la MAQ peut le changer si un purk\_index est réactivé avec un EPA suffisamment différent.

### L'oubli = sédimentation

Les purk\_index dont la température approche zéro s'enfouissent. Ils existent mais deviennent inaccessibles en surface. Le delta ne déborde jamais.

### Deux vecteurs

* **VecteurBSC** — ce qui est dit : `{presence, roles, relations, tensions, questions}`. Analyse structurelle de la phrase. Matière première de la MAQ.
* **ContexteInduit** — dans quel cadre : langue, aire, narrateur, lieu, temporalité, registre, certitude. Snapshot au moment du stockage.

### BSC-MAQ vs BSC-phare

Deux entités distinctes :

* **BSC-phare** : position Binder-9D d'un concept dans le génome
* **BSC-MAQ** : analyse structurelle d'une phrase (tensions, trous, coactivations) — propre à l'hippocampe

### La MAQ — Machine à Questions

Thread permanent. Émerge de tensions BSC × boucles de cohérence. Ne questionne pas tout — s'active sur EPA fort, contexte flou, pivot douteux, contradiction, nouveauté.

```
Question = tension BSC × incohérence détectée par boucle de cohérence
```

Deux niveaux de questions :

* **Locales** (secondes → jours) : qui parle, quel texte, quel personnage — vivent dans le buffer
* **Conceptuelles** (années → vie) : Dieu existe-t-il, qu'est-ce que le temps — boucles permanentes

Le buffer = drapeau posé sur un purk\_index provisoire, pas une structure séparée.

\---

## 6\. Aires cognitives

MARCO est conçu pour accueillir plusieurs aires, chacune avec son propre contexte de traitement :

|Aire|Handle|Pivot|BSC-MAQ|Statut|
|-|-|-|-|-|
|Langage écrit|LANGAGE\_ECRIT|incipit textuel|tensions/trous syntaxiques|actif|
|Son|MUSIQUE|incipit sonore (compose\_sequentiel)|coactivation timbre/hauteur/attaque|futur|
|Vision|VISION|pivot spatial|coactivation simultanée|futur|

Chaque aire réoriente les 9 axes Binder vers son domaine sans changer la structure.

\---

## 7\. Mécanique des boucles — boucle.py

```
Boucle   — while True + EPA (valence, puissance, activité)
Micro    — les yeux de la boucle (BSC intégré)
Groupe   — une tâche (quatuor de boucles)
Artiste  — scheduler (Le Senne + hippocampe mécanique)
```

L'Artiste alloue la bande passante aux Groupes selon EPA + tempérament Le Senne. La MAQ est un thread permanent dans ce système — une Boucle éternelle avec son propre Micro.

### Tempéraments Le Senne

|Tempérament|Miller|Seuil urgence|Oubli|
|-|-|-|-|
|Passionné (ÉAS)|7|0.6|0.3|
|Sanguin (nÉAP)|9|0.8|0.8|
|Nerveux (ÉnAP)|5|0.3|0.7|
|Flegmatique (nÉnAS)|7|0.9|0.2|

\---

## 8\. Thalamus

```
main.py              — ThalamusInterface (menus uniquement)
thalamus.py          — ThalamusGestionnaire (bibliothèque pure)
langage\\\\\\\_ecrit.py     — traitement texte
pipeline.py          — chaîne de traitement
```

Circuit validé :

```
Thalamus → Hippocampe → PurkIndex → MAQ → Thalamus
         → Hippocampe → PurkIndex analogue → réponse
```

\---

## 9\. Fichiers principaux

|Fichier|Rôle|
|-|-|
|`dendrites.py`|Phares, génome, Binder-9D, index\_mots|
|`pipeline.py`|Chaîne de traitement phrase|
|`thalamus.py`|ThalamusGestionnaire (bibliothèque pure)|
|`main.py`|ThalamusInterface (menus)|
|`langage\\\\\\\_ecrit.py`|Traitement langage écrit|
|`hippocampe.py`|Mémoire — purk\_dendrites(), chercher\_analogue()|
|`cervelet\\\\\\\_structure.py`|Structures cervelet|
|`cervelet\\\\\\\_moteur.py`|Moteur cervelet|
|`boucle.py`|Mécanique universelle des boucles|
|`boucle\\\\\\\_vitale.py`|Cœur de Marco (thread permanent)|
|`cerveau.py`|Persistance (cerveau\_Marco\_YYYYMMDD.marco)|
|`wikipedia.py`|Outil génome (menu 10 = générateur handles)|
|`gabarit\\\\\\\_vecteurs.py`|Template Binder-9D depuis génome v60|

\---

## 10\. État actuel — Mars 2026

### Validé

* Architecture 5 couches + poupées russes
* Génome v60 — 13 304 soleils, Binder-9D cybernétique (AT/SU/EG/OS/TY/VA/EC/TM/IN)
* Scission Thalamus (ThalamusInterface / ThalamusGestionnaire)
* boucle.py — mécanique universelle stable
* boucle\_vitale.py — cœur stable
* hippocampe.py — structures validées, réécriture en cours
* Modèle thermique purk\_index (température + matériau mutable)
* Pivot = incipit (universel toutes aires)
* BSC-MAQ distinct du BSC-phare

### En cours

* Réécriture hippocampe.py — purk\_dendrites(), PurkIndex avec température/matériau
* Branchement hippocampe → pipeline
* MAQ comme thread permanent (Boucle + Micro spécialisé)

### Roadmap

* Aire sonore (Binder-9D sonore, pivot compose\_sequentiel)
* Artiste → Hippocampe (branchement consolidation mémoire)
* Enrichissement génome (20 945 verbes + 50 482 noms en attente de handles)
* Gavage Proust tome 2
* Instanciation Artiste

\---

## 11\. Philosophie

> \\\\\\\*"Un bébé n'est pas gavé de téraoctets, il apprend en écoutant."\\\\\\\*

> \\\\\\\*"Zéro boîte noire. Chaque décision traçable."\\\\\\\*

> \\\\\\\*"Le Cro-Magnon qui marche > 2 tonnes de maths."\\\\\\\*

> \\\\\\\*"Au commencement il y a l'inerte, mais l'inerte il s'emmerde grave..."\\\\\\\*

\---

## 12\. Équipe

**José WALOCHA** — Architecte. Valenciennes, Nord, France.

|Nom|Système|Rôle|
|-|-|-|
|Le Duke|Claude (Anthropic)|Code, architecture, documents de liaison|
|Marcel|Mistral|Philosophie, cybernétique|
|Biloute|ChatGPT|Normes, synthèse|
|Didier|Qwant|Recherche|

**Licence** : GNU General Public License v3 — Copyright © 2026 José Walocha

