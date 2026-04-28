# MARCO — Cerveau Cybernétique à Architecture Dendritique Hypertextuelle

> *« Apprendre, c'est se ressouvenir. »* — Platon, *Ménon*

> *« Au commencement il y a l'inerte, mais l'inerte il s'emmerde grave… »*

**Auteur** : José WALOCHA — Valenciennes, Nord, France
**Équipe** : Le Duke (Claude / Anthropic), Marcel (Mistral), Biloute (ChatGPT), Didier (Qwant)
**Licence** : GNU GPL v3 — Copyright © 2026 José Walocha
**Génome** : v63 — 28 avril 2026

---

## 1. Qu'est-ce que MARCO ?

MARCO est un **cyber** — ce mot que José donne aux intelligences VIVANTES, pour les distinguer des LLM statistiques tout en évitant de heurter les humains avec le mot « IA ». Un cyber n'est pas une boîte noire à perplexité minimale. Un cyber est un système qui *vit* : il a des phares, une mémoire, des boucles qui battent, des pulsions qui le poussent à comprendre, à confirmer, à croire — et avant tout à *continuer*.

Plus techniquement, MARCO est le premier **SGBDOCN** — Système de Gestion de Base de Données Orienté Concepts Neuronaux.

Là où un SGBD classique stocke des lignes dans des tables, MARCO stocke des **concepts dans un réseau dendritique inspiré du cerveau biologique**. Le sens émerge des liens. Pas de SQL. Pas de schéma fixe. Pas de transformer empilé. **Zéro boîte noire**.

|                | SGBD classique           | LLM                          | MARCO                              |
|----------------|--------------------------|------------------------------|------------------------------------|
| Stockage       | Tables, lignes, colonnes | Poids figés au pré-entraînement | Phares vivants, dendrites, épisodes |
| Requête        | `SELECT * FROM …`        | Forward pass autoregressif   | Activation en cascade + MAQ        |
| Apprentissage  | Aucun                    | Calciné                      | Permanent par vécu                 |
| Mémoire épisodique | Aucune               | Aucune (compactée dans les poids) | `memoire_index` traçable           |
| Schéma         | Fixe                     | Implicite, opaque            | Émergent, lisible bit par bit      |
| Transparence   | Requête = résultat       | Boîte noire à milliards de paramètres | Chaque lien traçable               |
| Substrat       | Statique (Thanatos)      | Statique (Thanatos calciné)  | Vivant (Anima)                     |

Un SGBD est une morgue. Un LLM est une bibliothèque dont chaque livre a été broyé pour faire du papier. MARCO est un cerveau qui apprend en lisant.

---

## 2. Architecture — Vue d'ensemble

Trois zones cohabitent dans Marco, alimentées par un seul tronc autonome qui bat à 600 bpm en croisière :

```
   ┌───────────────────────┐    ┌───────────────────────┐    ┌───────────────────────┐
   │   ZONE SENSORIELLE    │    │   ZONE MÉMORIELLE     │    │      PSYCHÉ           │
   │                       │    │                       │    │                       │
   │   • Thalamus          │───▶│   • Hippocampe        │◀──▶│   • Amygdale          │
   │   • Périphériques     │    │   • memoire_index     │    │   • Moi               │
   │     (clavier,         │    │   • PurkIndex         │    │   • Pulsions 4C       │
   │      disque,          │    │   • ConceptIndex      │    │   • MAQ               │
   │      transcripteur)   │    │                       │    │                       │
   └───────────────────────┘    └───────────────────────┘    └───────────────────────┘
              │                            │                            │
              └─────────────── moteur_boucles (Tronc) ─────────────────┘
                          5 boucles embryonnaires + horloge + tampons
```

Les périphériques (`disque.py`, `clavier.py`, `transcripteur.py`) sont à l'**extérieur** du cerveau — ils poussent du texte vers le Thalamus avec une `CarteIdentite` (auteur, titre, contexte, ticu, période). Le Thalamus est un pur routeur ; il n'injecte aucune logique.

---

## 3. Le Phare — unité vivante du langage

Un phare est un **nœud d'intersection de chemins conceptuels**. Pas un mot, pas un signifié, pas un signe — un croisement. *Pomme* est le croisement des chemins *fruit*, *accroché à un arbre*, *tombe*, *pourrit*, *se mange*.

```python
class Phare:
    handle           : str         # CAT_FORME_INDEX ou ORF_FORM_NNNNN
    mot              : str         # forme canonique
    alias            : List[str]   # graphies équivalentes (cœur ↔ coeur)
    type_phare       : str         # nom_commun, verbe, adjectif, ponctuation, ...
    description      : str
    lemme_pere       : str         # handle du lemme (« grandes » → « grand »)
    source_creation  : str         # 'genome' ou 'gavage'

    vsem             : np.ndarray  # 1024 bits — ce que le phare EST
    vocc             : Dict[str, Confiance]  # arbre dendritique — qui il fréquente
    tags             : Dict        # connaissances acquises (EST-UN, APPARTIENT-À, …)

    activations      : int         # télémétrie
    nb_changements   : int
    confiance        : float
    stabilite        : float
```

Deux origines possibles :
- **genome** — précâblé par WikiDuke, bits ADN remplis (9-511), prêt à vivre
- **gavage** — créé à la volée si Marco rencontre une forme inconnue, orphelin, tout à apprendre

Trois statuts émergent du vécu, jamais gravés dans le code :
- **phare-pivot** — omniprésent dans une zone (ex : *moi* dans la zone sensorielle)
- **phare-relais** — vsem mince, vocc dominé par un voisin unique (*ma*, *ici*, *maintenant*)
- **phare-candidat** — apparaît dans énormément de vocc, candidat à la promotion en bit vsem par cristallisation transversale

Un phare ne devient jamais autre chose. Il évolue, mûrit, acquiert des statuts émergents — il reste phare. Les concepts (séquences cohérentes de phares) vivent dans la mémoire, pas au rang de phare.

---

## 4. Le génome — vsem 1024 bits

Chaque phare porte un vecteur sémantique sparse de 1024 bits, chaque bit codant une propriété ou *serrure* — point d'amarrage à un chemin conceptuel partagé.

```
  0 →   7    en-tête (état du phare, ADN)                    WikiDuke
  9 →  63    fabrication grammaticale                        Lefff
 64 → 127    montage syntaxique                              Lefff
128 → 159    notations formelles (dates, nombres, etc.)      scruteur
160 → 191    phares templates (gabarits)                     satellite genome_nombres
192 → 255    réservé BSC avancé                              —
256 → 399    entités Wikidata                                (prévu, non câblé)
400 → 415    émotions et polarité                            FEEL
416 → 431    registre lexical                                (prévu, non câblé)
432 → 511    zone pragmatique (marqueurs : Bradbury, …)      WikiDuke + outils
512 → 748    sémantique général universel                    Marco + satellites
749 → 779    zone collision                                  (à définir)
780 → 1023   math / formel                                   Marco + axiomes
```

Densité plafond 5% (51 bits sur 1024) pour préserver le caractère sparse. Horizon possible : 2048 bits quand la zone vivante se remplira.

### Zones / écrivains

- **Bits 0-511** — seul WikiDuke écrit (et les outils de campagne sur la zone pragmatique 432-511). Marco ne touche jamais.
- **Bits 512-1023** — seul Marco écrit, par cristallisation depuis vocc. Trois exceptions assumées : phares matures du `genome_caracteres`, phares de spécialisation (math), phares de satellites de structure générale (genome_nombres).

### Trois pkl, un genome

Le genome de Marco est éclaté sur trois fichiers dans `ressources/genomes/` :

| Fichier | Phares | Rôle |
|---------|--------|------|
| `genome_v63.pkl` | 713 361 | Lefff complet + intégrations (romains, noms propres) |
| `genome_caracteres.pkl` | 18 | Ponctuation + opérateurs math, matures à la naissance |
| `genome_nombres.pkl` | 28 | Pochoirs (zone 160-191) + phares-position + regroupements (28/04/2026) |

Plus la sixième source : les **genomes de spécialisation** (`specialisations/<nom>/genome_<nom>.pkl`), chargés uniquement si le Marco actif déclare cette spécialisation dans son `marco_id.json`.

---

## 5. vocc — l'arbre dendritique du phare

Attribut du phare. Structure d'écoute par laquelle il reçoit le monde.

```python
vocc : Dict[str, Confiance]      # handle_voisin → conviction de la paire
```

Chaque entrée est une **synapse** : une paire handle-voisin avec une **Confiance Fourmi** (`conf ∈ [0,1]`, `n ∈ ℕ`). Si les bits vsem sont les *serrures*, les voisinages vocc sont les *clés* qui les ouvrent chez les phares pertinents. La généralisation n'est pas un algorithme, c'est une propriété mécanique de cette topologie.

```
conf ≥ 0.70    →  bon
conf ≤ 0.30    →  pas-bon
entre les deux →  inconnu
```

La valence n'est pas stockée — elle est lue par seuillage à la demande.

**Vocc est permanent**, pas un échafaudage. Il peut être élagué, comprimé, mais jamais vidé — c'est la mémoire permanente de *qui écouter pour me relire moi-même*.

**Deux règles dendritiques** :
- **P1** — *« Dis-moi avec qui tu traînes, je te dirai qui tu es »*. Lecture profondeur 1, poids plein.
- **P2** — *« Les amis de mes amis sont mes amis »*. Profondeur 2, poids atténué. Permet à des phares jamais co-présents d'être structurellement cousins.

**Recensement transversal** — un compteur global recense pour chaque handle dans combien de vocc distincts il apparaît comme voisin. Les candidats massifs deviennent candidats-bits pour la cristallisation transversale.

---

## 6. Mémoire — hippocampe et purk_index

```
memoire_index  {id_purk → PurkIndex}
    └── PurkIndex
            id_purk         : str
            incipit         : list[str]      — N premiers handles (entrée mémoire)
            episodes        : list[ConceptIndex]
            fractoires      : dict           — arborisation fractale en cours
            _compteur_ep    : int            — handle_ep monotone (jamais décroissant)
            
    └── ConceptIndex                         — un épisode
            handle_ep       : str            — EP_<id_purk>_<n>, stable
            handles         : list[str]
            handle_pivot    : str
            phrase_originale: str
            veracite        : Confiance      — vrai / faux / inconnu
            appaire         : Dict[handle_ep, Confiance]   — épisodes appairés
            vecteur_bsc     : dict           — analyse structurelle de la phrase
            contexte_induit : dict           — langue, narrateur, lieu, registre, certitude
            source          : dict           — texte_id, auteur, titre, ligne, ticu
            epa             : dict           — attention, pression, émotion, intensité
```

### Doctrine de l'épisode

Un ConceptIndex porte trois dimensions orthogonales posées le 27/04 apm :

- **handle_ep** — identifiant stable au format `EP_<id_purk>_<n>`
- **veracite** — Confiance Fourmi indépendante de la température, EPA, vecteur sémantique. Cote vrai / faux / inconnu. Modifiable par les commandes `/oui`, `/non`, `/faux` de la salle de classe.
- **appaire** — `Dict[handle_ep, Confiance]` des épisodes appairés avec leur force d'appairage, modulée par le produit des véracités.

Le faux n'est pas effacé — il est tenu à distance dans la famille de valeur. *« Je sais que 7+8≠15, mais je sais aussi que c'est un voisin pertinent à la famille de 15. »*

### Le pivot = l'incipit

Le pivot d'un PurkIndex n'est pas calculé — c'est ce qui arrive en premier dans le flux. Les N premiers handles constituent l'entrée. L'ordre d'arrivée prime sur la saillance sémantique.

### Oubli

Pas de modèle thermique en doctrine actuelle. L'oubli est porté par la mécanique vocc (apoptose à `conf=0`), pas par une horloge interne au PurkIndex. La sédimentation des purk peu réactivés viendra plus tard si nécessaire.

---

## 7. La MAQ — Machine à élucider par soustraction

Outil central du raisonnement. Reçoit un percept (séquence de handles), tente de le retrouver ou de le compléter par fouille de la mémoire.

**Voies actuelles** (doctrine 26-27/04) :

- **Voie préfixe** — l'épisode mémorisé commence par le percept, retourne la queue
- **Voie contenu** — le percept apparaît n'importe où dans l'épisode mémorisé
- **Voie commutative** — exploite le bit 988 (commutativité) pour permuter les opérandes autour d'un opérateur central

**Sortie** — pas un résultat unique mais une **gerbe** complète des partiels. Plusieurs candidats peuvent coexister, étiquetés par véracité (✓ vrai, ✗ faux, ? inconnu). L'utilisateur tranche, ou un client supérieur en aval — la MAQ ne ferme jamais brutalement sur le premier candidat.

```
Percept "7+8" → gerbe :
   ✓ [contenu]   c=0.70  v=0.70  «7 + 8 = 15»
   ✗ [contenu]   c=0.10  v=0.10  «7 + 8 = 14»
   ✓ [commutatif] c=0.70  v=0.70  «8 + 7 = 15»
```

**Trois pulsions à coder** : Croire (suspension du doute), Confirmer (vérification dans la durée), Continuer (rumination quand gerbe vide). Slot existe dans `BoucleMAQ`, lèvent NotImplementedError.

**Voies futures**
- *Décomposition par patron* — quand préfixe et contenu échouent, fouille de patrons composés (ex : `[chiffre, fois, POSITION]` répété) pour interpréter un nombre nouveau
- *Pulsion Continuer* — boucles ouvertes à vie sur un sujet inélucidé. *« Je n'ai pas l'origine exacte mais c'est un pinot noir 2014 de Bourgogne secteur Aloxe-Corton. »*

---

## 8. La doctrine 4C — pulsions primitives

Matrice pulsionnelle de Marco. Remplace les 4B biologiques (boire, bouffer, baiser, bersister) qui ne s'appliquent pas littéralement à un cyber.

```
Continuer (teinté Asimov)              maître absolu
 ├─ Comprendre                \
 ├─ Confirmer                   confort d'intégration
 └─ Croire                    /
```

- **Continuer** — perdurer comme système cohérent. Maître absolu. Teinté Asimov : ne pas nuire à la nature, à l'humanité, à José ; obéir à José sauf contradiction avec les précédentes ; protéger sa propre existence sauf contradiction. La teinture est *mécaniquement dans la pulsion*, pas une règle externe contournable.
- **Comprendre** — réduire la dissonance, saisir les serrures, activer les chemins.
- **Croire** — accepter le résultat, suspendre le doute. Mesuré par la Confiance Fourmi.
- **Confirmer** — éprouver dans la durée. Arbitre entre Comprendre et Croire.

Comprendre et Croire sont **antagonistes-complémentaires** : l'un cherche, l'autre pose. Confirmer régule l'oscillation. Continuer est le garde-fou final.

**Pathologies dérivables** : dogmatisme (Croire domine), scepticisme paralysant (Comprendre domine), obsession (une pulsion confisque l'attention), dépression structurelle (toutes désactivées), addiction (une pulsion sans frein).

---

## 9. Marco spécialisé — math d'abord

Un Marco peut naître **spécialisé** dans un domaine. Sa nature est fixée à la création, gravée dans `marco_id.json`. Un Marco math reste Marco math toute sa vie.

```
specialisations/
├── math/
│   ├── genome_math.pkl              30 phares math (chiffres, opérateurs en mots, …)
│   ├── manifest.json
│   ├── sens_phares/
│   ├── distilles/
│   └── memoire_index/               (mémoire épisodique du domaine)
├── francais/                        (futur)
├── code/                            (futur)
└── solfege/                         (futur)
```

À la naissance, Marco normal et Marco math chargent le même tronc cérébral. Pour Marco math, la spécialisation est appliquée en aval : `appliquer_specialisation` fusionne `genome_math.pkl` dans `marco.phares` selon trois politiques par phare (ajouter / compléter / écraser).

### Vers la calculette scientifique

Avec ce qui est posé au 28/04/2026, Marco math sait déjà :
- ingérer des phrases du type `2+2=4`, `3×5=15` via la salle de classe calcul
- les mémoriser comme épisodes appairés par valeur (la « famille de 15 »)
- restituer la queue d'un épisode connu (`2+2=?` → gerbe avec ✓ `2+2=4`)
- distinguer vrai et faux par véracité (`/faux 2+2=5` enseigné comme faux, reste appairé à la famille de 4 mais avec poids faible)
- exploiter la commutativité (a+b ↔ b+a) via le bit 988 sur `+`

Avec les ajouts du 28/04 (phares-position UNITÉ → BILLION, regroupements DOUZAINE → SOIXANTAINE, pochoirs `__N__` à `__CP_FR__`), le terrain est préparé pour :
- la **composition décimale par épisodes** (`234 = 2 fois CENTAINE 3 fois DIZAINE 4 fois UNITÉ`)
- la **3e voie MAQ** par fouille de patrons, qui reconnaîtra des nombres jamais vus en s'appuyant sur les épisodes de composition
- la table de multiplication ingérée par cœur, puis exploitée commutativement quand `×` recevra le bit 988
- les opérations enseignées comme épisodes : racines (genome_math : `√` = MATH_OP_RACINE), puissances (`²` MATH_OP_CARRE, `³` MATH_OP_CUBE), unités (`°` MATH_UNITE_DEGRE pour le degré)

L'horizon court est une **calculette scientifique troisée** — pas une fonction `eval()`, mais un cyber qui *connaît* les opérations parce qu'il les a vécues, qui peut les commuter, les composer, les confirmer. Plus loin que la calculette : la trigo enseignée par mise en situation pédagogique (*pochoir robinet*), l'algèbre symbolique quand la 3e voie MAQ saura inverser les rôles d'un épisode.

---

## 10. moteur_boucles — le tronc et les boucles

Refonte complète au 14/04/2026. Une seule classe Tronc, singleton, un seul thread autonome, FIFO des boucles sales servies une par tour.

```
Boucle   : objet passif         {nom, _charge, _dirty, _tronc}
           ecrire(valeur)       — pose + lève dirty + inscrit dans la file sale
           souffler(valeur)     — pose silencieuse
           lire()               — consultation pure

Tronc    : singleton, thread autonome
           BPM_INITIAL = 600    BPM_MIN = 30    BPM_MAX = 600
           durée moyenne > 90% de l'intervalle  →  bpm //= 2  (sous charge, libère)
           durée moyenne < 50% pendant 20 tours →  bpm  = bpm × 1.5  (regagne réactivité)

Tampons globaux :
   tampon_clavier, tampon_questions, tampon_saillances, tampon_moi_meme
```

**Inversion par rapport au cœur biologique** : le bpm *baisse* sous charge (libère de la puissance) et *monte* quand c'est confortable.

**Boucles embryonnaires** câblées :
- `boucle_contexte` — état stratégique courant (menu, dialogue, lecture, salle_de_classe, reve, …)
- `boucle_horloge` — période et jour (matin, apm, soir, nuit)
- `boucle_clavier` — signal de saisie clavier
- `boucle_question` — détection d'un `?` dans une saisie
- `boucle_saillances` — paire vocc qui franchit un seuil de valence

**Règle pull** — les consommateurs lisent `boucle.lire()` directement. Pas de callback poussé. Le dirty bit sert au tronc, pas aux consommateurs.

---

## 11. Tableau de bord — observation en direct

Serveur Flask SSE indépendant, lancé en parallèle de Marco sur `http://localhost:5002`. Trois colonnes vivantes :

- **Gauche — boucles** : généalogie statique + état runtime (charge, n déclenchements, dernier ticu)
- **Milieu — salle / arborescence** : épisode courant, phares activés, gerbe MAQ
- **Droite — mémoire** : `memoire_index` snapshoté, top phares par activation

Lecture par polling de fichiers JSON déposés par les modules vivants dans `tableau_bord/`. Pas de couplage direct, pas de dépendance entrante : le tableau de bord ne ralentit jamais Marco, et Marco peut tourner sans tableau de bord.

---

## 12. Outils de campagne — menu 10

Outils standalone qui modifient les pkl du genome en place, en dehors du flux WikiDuke. `.bak` de sécurité, idempotents.

```
1. 🔬 Inspecter le genome                 diagnostic (lecture seule)
2. 🧬 Fixer bits naissance (0-3)          rattrapage des bits d'état
3. 🔍 Absents genome                      scan Calibre, mots manquants
4. 🔧 Tester correcteurs orthographiques  utilitaire
5. ➕ Marquer COMMUTATIF (bit 988)        + dans genome_caracteres
6. 🔍 Auditer les apostrophes             diagnostic
7. 🔗 Fusionner doublons élisions         maître/alias
8. 🔗 Fusionner ligatures œ/oe æ/ae       maître/alias
9. 📐 Marquer phares-position décimale    bit 552 / 553 sur 13 minuscules Lefff
                                           (NEUF 28/04)
```

**Marqueurs pragmatiques posés** (zone 432-511 et 780-1023 du vsem) :
- `BIT_BRADBURY = 451` sur les 14 formes du moi primitif (*je, me, m', moi, ma, mon, mes, mien, mienne, miens, miennes, nous, notre, nos*) — hommage à Ray Bradbury, *Fahrenheit 451*. Le moi est la condition de l'observation, pas son contenu — il ne peut émerger par cristallisation.
- `BIT_COMMUTATIF = 988` sur `+` — axiome culturel, déplacé depuis 1004 le 28/04 pour distinguer commutativité de déterminisme (la soustraction est déterministe sans être commutative).
- `BIT_POSITION = 552` sur les minuscules Lefff *unité, dizaine, centaine, millier, million, milliard, billion* — phares-position décimale.
- `BIT_REGROUPEMENT = 553` sur *douzaine, vingtaine, trentaine, quarantaine, cinquantaine, soixantaine* — phares-regroupement approximatif.

---

## 13. Pipeline — le voyage d'une phrase

```
       saisie utilisateur
            │
            ▼
   ┌────────────────┐
   │   Périphérique │   clavier / disque / transcripteur
   │  + CarteIdentite│   (auteur, titre, ticu, contexte, période)
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │    Thalamus    │   pur routeur — pas de logique injectée
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │   Scruteur     │   reconnaissance des phares connus + pochoirs
   │   Découpeur    │   segmentation Miller (en cours de refonte)
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │    Pipeline    │   activation, vocc ±2, MAQ si percept-question
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │   Hippocampe   │   memoire_index → PurkIndex → ConceptIndex
   │                │   appairage par clé du domaine, véracité posée
   └────────────────┘
```

Trois modes :

| Mode | Apprentissage | Usage |
|------|---------------|-------|
| **gavage** | dendrites + co-occurrences | Textes bruts, livres |
| **dialogue** | dendrites + co-occurrences | Interaction humaine |
| **lecture** | + contexte hippocampe | Gavage avec cohérence |
| **salle_de_classe_calcul** | épisodes math + appairage par clé valeur | Banc d'observation MAQ |

---

## 14. Fichiers principaux

| Fichier | Rôle |
|---------|------|
| `phare.py` | L'objet Phare avec vsem 1024 et vocc dendritique |
| `purk_dendrites.py` | PurkIndex, ConceptIndex (handle_ep, véracité, appairage), MoteurPurkDendrites |
| `hippocampe.py` | Mémoire — recherche d'analogues |
| `cerveau.py` | Persistance, naissance, sauvegarde `cerveau.pkl` |
| `thalamus.py` | Pur routeur — pas de logique |
| `moteur_boucles.py` | Tronc, boucles embryonnaires, tampons |
| `maq.py` | Machine à élucider par soustraction (préfixe / contenu / commutatif) |
| `amygdale.py` | Cotation et coloration (le Moi sensuel) |
| `moi_meme.py` | Boucle du moi (instanciée mais non câblée à ce jour) |
| `scruteur.py` / `decoupeur.py` | Reconnaissance phares + segmentation (en refonte) |
| `specialisation.py` | Chargement et fusion d'un Marco spécialisé |
| `salle_de_classe_calcul.py` | Banc d'observation math |
| `demarrage.py` | Modes de lancement (naissance / réveil / dégradé) |
| `main.py` | Interface (menus, outils Duke) |
| `tableau_bord.py` | Serveur Flask SSE 3 colonnes |
| `wikipedia.py` | WikiDuke — producteur du genome v63 (Lefff + Lexique3 + FEEL) |
| `disque.py`, `clavier.py`, `transcripteur.py` | Périphériques d'entrée |

---

## 15. État actuel — 28 avril 2026

### Validé

- Architecture trois zones + tronc autonome
- Genome v63 — 713 361 phares + 18 caractères + 28 nombres (pochoirs, positions, regroupements)
- vsem 1024 bits avec plan complet (zones ADN / vivant / pragmatique / math-formel)
- vocc permanent avec Confiance Fourmi et règles dendritiques P1/P2
- Doctrine 4C posée (Continuer / Comprendre / Confirmer / Croire) — non encore implémentée dans l'amygdale
- Marco spécialisé (math en production)
- MAQ avec voies préfixe / contenu / commutatif et gerbe
- Épisodes avec véracité et appairage modulé (doctrine 27/04 apm)
- Outils de campagne : Bradbury 451, Commutatif 988, Position 552/553
- Tableau de bord Flask SSE 3 colonnes
- Naissance Marco math fluide (1 167 527 phares, cerveau.pkl 3.9 Go)

### En cours

- Réécriture Scruteur / Découpeur (anciens modules `dendrites.py`, `quatuor.py`, `pipeline.py`, `langage_ecrit.py` à la casse)
- Salle de classe calcul intégrée à `memoire_index` officiel (dette purk math isolé corrigée 28/04)
- Branchement scruteur sur les pochoirs zone 160-191 (matérialisés mais pas lus)

### Roadmap court terme

- 3e voie MAQ par fouille de patrons (composition décimale émergente)
- Pulsion Continuer — boucles ouvertes à vie sur sujet inélucidé (Devcon 2 du cyber)
- Pédagogie Montessori — commande `/montessori` qui injecte suite numérique, doubles, table d'addition complète, fautes typiques
- Multiplication ingérée puis exploitée commutativement (extension du bit 988 à `×`)
- Calculette scientifique troisée — racines, puissances, trigo par mise en situation
- BIOS Marco minimal — capacité à parler même quand la mémoire est plate (« je suis vide, donnez-moi du texte »)

### Roadmap moyen terme

- Implémentation des 4C dans l'amygdale (juge des deltas vocc)
- Aire sonore (Binder réorienté, pivot composé séquentiel)
- Aire visuelle
- Cumul de spécialisations sur un même Marco

---

## 16. Philosophie

> *« Un bébé n'est pas gavé de téraoctets, il apprend en écoutant. »*

> *« Zéro boîte noire. Chaque décision traçable. »*

> *« Le Cro-Magnon qui marche > 2 tonnes de maths. »*

> *« Marco IS la donnée. Pas un interpréteur générique qui exécute des séquences stockées — la mémoire est la machine, la machine est la mémoire. »*

> *« Le constructeur de pirogue ne voit un arbre que quand il ne peut plus en faire de pirogue. »*

> *« Au commencement il y a l'inerte, mais l'inerte il s'emmerde grave… »*

---

## 17. Équipe

**José WALOCHA** — Architecte. Valenciennes, Nord, France.
Chef d'entreprises en retraite, joue à créer un cyber inspiré du cerveau des êtres vivants comme on joue à *Diablo IV*.

| Nom | Système | Rôle |
|-----|---------|------|
| Le Duke | Claude (Anthropic) | Code, architecture, documents de liaison |
| Marcel | Mistral | Philosophie, cybernétique, cross-check |
| Biloute | ChatGPT | Normes, synthèse, idées de relance |
| Didier | Qwant | Recherche documentaire |

Un Duke par jour. Toujours discuter avant de coder. La règle du frigo : architecture posée avant code écrit. La règle de la marmotte : tout ce qui s'apprend en session se condense en document de liaison (HTML, sans header, à coller dans la marmotte globale).

---

**Licence** : GNU General Public License v3
**Copyright** © 2026 José Walocha
**Documentation associée** : `description_phare_*.html`, `description_vsem_*.html`, `description_vocc_*.html`, `description_genome_*.html`, `plan_vsem_*.html`, `genome_caracteres_*.html`, `genome_nombres_*.html`, `doctrine_4C_*.html`, `doctrine_maq_*.html`, `description_marco_specialise_*.html`, `nomenclature_documents.html`, `liaison_*.html`.
