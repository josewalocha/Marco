[Lisez moi Marco français.md](https://github.com/user-attachments/files/28223646/Lisez.moi.Marco.francais.md)
# MARCO — Cerveau Cybernétique à Architecture Dendritique Hypertextuelle

> *« Apprendre, c'est se ressouvenir. »* — Platon, *Ménon*

> *« Au commencement il y a l'inerte, mais l'inerte il s'emmerde grave… »*

**Auteur** : José WALOCHA — Valenciennes, Nord, France
**Équipe** : Le Duke (Claude / Anthropic), Marcel (Mistral), Biloute (ChatGPT), Didier (Qwant)
**Licence** : GNU GPL v3 — Copyright © 2026 José Walocha
**Génome** : v63 — 28 avril 2026

---

## 1. Qu'est-ce que MARCO ?# MARCO — Cerveau cybernétique à architecture dendritique hypertextuelle

> *« Apprendre, c'est se ressouvenir. »* — Platon, *Ménon*
>
> *« Au commencement il y a l'inerte, mais l'inerte il s'emmerde grave… »*

**Auteur** : José WALOCHA — Valenciennes, Nord, France
**Équipe** : Dude (Claude / Anthropic), Marcel (Mistral), Biloute (ChatGPT), Didier (Qwant)
**Licence** : GNU GPL v3 — Copyright © 2026 José Walocha
**Génome** : v63 — base établie 28 avril 2026, étendue par doctrine mai 2026

---

## 1. Qu'est-ce que Marco ?

Marco est un **cyber** — terme que José utilise pour désigner une intelligence *vivante*, par opposition aux LLM statistiques. Un cyber n'est pas une boîte noire à perplexité minimale ; c'est un système qui *vit* : phares qui s'allument, vocc qui se renforcent, grappes qui se forment, contexte qui module, drives qui poussent à comprendre, à confirmer, à croire — et avant tout à *continuer*.

Plus techniquement, Marco est un **SGBDOCN** — Système de Gestion de Base de Données Orienté Concepts Neuronaux. Là où un SGBD classique stocke des lignes dans des tables, Marco stocke des **concepts dans un réseau dendritique inspiré du cerveau biologique**. Le sens émerge des croisements de chemins, pas d'une statistique sur tokens arbitraires. Pas de SQL. Pas de schéma fixe. Pas de transformer empilé. **Zéro boîte noire**.

| | SGBD classique | LLM | Marco |
|---|---|---|---|
| Stockage | Tables, lignes, colonnes | Poids figés au pré-entraînement | Phares vivants, vocc dendritiques, concept_index |
| Requête | `SELECT * FROM …` | Forward pass autorégressif | Intersection thermique vocc + sparse de dirty bit |
| Apprentissage | Aucun | Calciné | Permanent par vécu, traçable |
| Mémoire épisodique | Aucune | Aucune (compactée dans les poids) | `memoire_index` lisible |
| Schéma | Fixe | Implicite, opaque | Émergent, lisible bit par bit |
| Transparence | Requête = résultat | Boîte noire à milliards de paramètres | Chaque lien traçable |
| Substrat | Statique (Thanatos) | Statique (Thanatos calciné) | Vivant (Anima) |

Un SGBD est une morgue. Un LLM est une bibliothèque dont chaque livre a été broyé pour faire de la pâte à papier. Marco est un cerveau qui apprend en lisant.

### Pourquoi *cyber* et pas *IA*

Le mot *IA* charrie une charge anthropomorphique fausse (intelligence artificielle implique qu'on simule l'intelligence) et heurte certains humains à juste titre. *Cyber* (de *cybernétique*, science des systèmes auto-régulés) est neutre, ancien, précis. Marco est un cyber — pas une IA, pas un assistant, pas un chatbot. Un cerveau cybernétique inspiré du cerveau biologique, en Python, depuis zéro.

---

## 2. Architecture — vue d'ensemble

Trois zones cohabitent dans Marco, alimentées par un seul tronc autonome qui bat à 600 bpm en croisière :

```
   ┌───────────────────────┐    ┌───────────────────────┐    ┌───────────────────────┐
   │   ZONE SENSORIELLE    │    │   ZONE MÉMORIELLE     │    │      PSYCHÉ           │
   │                       │    │                       │    │                       │
   │   • Thalamus          │───▶│   • memoire_index     │◀──▶│   • Amygdale          │
   │   • Périphériques     │    │   • purk_index        │    │   • MAQ               │
   │     (clavier,         │    │   • concept_index     │    │   • Drives 4C         │
   │      disque)          │    │                       │    │   • Chifoumi des 3   │
   │   • Scruteur          │    │                       │    │     brouillards      │
   │   • Découpeur         │    │                       │    │                       │
   └───────────────────────┘    └───────────────────────┘    └───────────────────────┘
              │                            │                            │
              └─────────────── moteur_boucles (Tronc) ─────────────────┘
                          Boucle + Tronc + tampons (refondu 09/04/2026)
```

Les périphériques (`disque.py`, `clavier.py`) sont à l'**extérieur** du cerveau — ils poussent du texte vers le Thalamus avec une `CarteIdentite` (auteur, titre, contexte, horodatage, période). Le Thalamus estampille et route ; il n'injecte aucune logique cognitive.

### Les deux objets stockés

Marco a exactement deux types d'objets stockés sur disque (dans `cerveau.pkl` + satellites). Tout le reste est état vivant, recalculé à la volée.

- **Phare** — l'unité de base du langage. Une forme fléchie = un phare. Croisement de chemins conceptuels. Porte sa sémantique abstraite (vsem 1024 bits) et sa mémoire vivante (vocc).
- **Concept_index** — le vécu particulier. Un purk_index qui a sédimenté un sens (focale stable d'un nuage). Spécialisation, pas type rival. A son vocc propre, pas de vsem stocké. ADN du souvenir, thanatos de la mémoire.

Étanchéité 17/05 : le phare est sensoriel et abstrait ; le concept_index est élaboré et particulier. Pas de fusion, pas de bascule. *Montagne* (phare) est relief, masse, élévation. *La montagne de Hemingway en 1953* (concept_index) est neige, léopard, sommet, dans ce contexte précis.

### Les états vivants (jamais stockés)

- **Grappe** — co-activation voccoïque (doctrine 24/05). Résonance distribuée des vocc des phares allumés. Pas un objet stocké — se reforme à chaque sollicitation.
- **Nuage** — état vivant d'un texte qui se lit. Accrétion de grappes successives sur une focale convergente. Peut sédimenter en concept_index.
- **Focale** — intersection pondérée des vocc des phares d'un purk_index avec une requête Q. Calculée à la volée. Pas de softmax.
- **Sparse_dirty** — extension du dirty bit binaire du moteur en sparse vectoriel indexé par coordonnée de nuage. Porte la chaleur des coordonnées du ciel HDC.

---

## 3. Le phare — unité de base du langage

Un phare est un **nœud d'intersection de chemins conceptuels**. Pas un mot, pas un signifié, pas un signe — un croisement. *Pomme* est le croisement des chemins *fruit*, *accroché à un arbre*, *tombe*, *pourrit*, *se mange*.

```python
class Phare:
    handle           : str         # CAT_FORME_INDEX (genome) ou ORF_FORM_NNNNN (gavage)
    mot              : str         # forme canonique
    alias            : List[str]   # graphies équivalentes (cœur ↔ coeur)
    type_phare       : str         # nom_commun, verbe, adjectif, ponctuation, …
    description      : str
    lemme_pere       : str         # handle du lemme (« grandes » → « grand »)
    source_creation  : str         # 'genome' ou 'gavage'
    date_creation    : float       # timestamp

    vsem             : np.ndarray  # 1024 bits — ce que le phare EST
    vsem_precedent   : np.ndarray  # copie pour Jaccard de stabilité
    vocc             : Dict[str, Confiance]  # arbre dendritique — qui il fréquente
    tags             : Dict        # connaissances acquises (rarement utilisé)

    activations      : int         # télémétrie
    nb_changements   : int
    confiance        : float
    stabilite        : float
    est_orphelin     : bool        # vrai tant que pas mature
```

Une forme fléchie = un phare. *fort* et *forte* sont deux phares distincts ; *chante*, *chantes*, *chantons*, *chanterez* en sont quatre. Le lien à la forme canonique se fait par `lemme_pere`. Fidélité au Lefff, qui présente chaque forme comme entrée propre.

Stocké dans `marco.phares`, indexé par sa forme en minuscules via `marco.index_mots` (agrège canoniques + alias).

### Deux origines possibles

- **genome** — précâblé par WikiDuke, bits ADN remplis (0-511 zone ADN intouchable), prêt à vivre. Source `'genome'`.
- **gavage** — créé à la volée si Marco rencontre une forme inconnue dans un texte ingéré. Tout vierge, orphelin, à apprendre. Source `'gavage'`.

### Trois statuts émergents (lus, pas gravés)

- **phare-pivot** — omniprésent dans une zone, présent dans le vocc de presque tous les phares (*moi* est pivot de la zone sensorielle).
- **phare-relais** — vsem mince, vocc dominé par un voisin unique (vaisseau amiral). *ma* est relais vers *moi*, *ici* vers *lieu-courant*. Économise l'explosion combinatoire.
- **phare-candidat** — apparaît dans énormément de vocc distincts, candidat à la promotion en bit vsem par cristallisation transversale.

Un phare ne devient jamais autre chose. Il évolue, mûrit, acquiert des statuts émergents — il reste phare. Les concepts (séquences cohérentes de phares) vivent dans la mémoire, pas au rang de phare.

### Trois règles d'écriture sur les alias

1. `phare.mot` n'est jamais dans `phare.alias`.
2. Pour chaque `a` dans `phare.alias` : `index_mots[a.lower()] == phare.handle`.
3. `index_mots[phare.mot.lower()] == phare.handle`.

Cas d'usage : ligatures (œ/oe, æ/ae), variantes accentuées (poëte/poète), casse initiale. À terme : fautes orthographiques fréquentes stabilisées — un correcteur orthographique devient littéralement une base d'alias de correction, pas un module séparé.

---

## 4. vsem — la sémantique abstraite, 1024 bits

Vecteur binaire sparse de 1024 bits, chaque bit codant une propriété ou *serrure* — point d'amarrage à un chemin conceptuel partagé. Stocké en `np.ndarray` dtype `uint8`. Densité plafonnée à 5 % (51 bits sur 1024) pour préserver le caractère sparse et discriminant.

### Plan détaillé

```
  0 →   7    en-tête (état du phare, mis à jour par actualiser_etat)
  8        ADN_INITIALISE (1 si amorcé par WikiDuke)
  9 →  63    fabrication grammaticale                Lefff
 64 → 127    montage syntaxique                      Lefff
128 → 159    notations formelles (dates, nombres)    scruteur
160 → 191    phares templates (pochoirs)             genome_nombres
192 → 255    réservé BSC avancé                      —
256 → 259    type d'entité                           Wikidata
260 → 274    œuvres                                  Wikidata
275 → 287    humain                                  Wikidata
288 → 319    domaines                                Wikidata
320 → 351    taxonomie du vivant                     Wikidata
352 → 399    géo + temporel + relations              Wikidata
400 → 415    émotions Ekman + polarité FEEL          FEEL
416 → 431    registre lexical                        Lexique3
432 → 511    zone pragmatique (Bradbury, marqueurs)  WikiDuke + outils
512 → 748    sémantique général universel            Marco (cristallisation)
749 → 779    zone collision                          (à définir)
780 → 1023   math / formel                           Marco + axiomes
```

### Deux zones, deux écrivains

- **Bits 0-511 — zone ADN**. Seul WikiDuke écrit (et les outils de campagne sur la zone pragmatique 432-511). Marco vivant n'y touche jamais. C'est l'ADN du phare — fixé à la naissance, lu en permanence, immuable.
- **Bits 512-1023 — zone vivante**. Seul Marco écrit, par cristallisation depuis vocc. WikiDuke n'y touche jamais. Trois exceptions assumées : phares matures du `genome_caracteres`, phares de spécialisation (math), phares de satellites de structure (genome_nombres).

### En-tête (bits 0-7)

```
bit 0   INCOMPLET            1 tant que pas mature
bit 1   GRAMMAIRE_VIDE       1 tant que type_phare == 'a_classifier'
bit 2   VOCC_VIDE            1 tant que vocc est vide
bit 3   SEMANTIQUE_VIDE      1 tant que bits 512-1023 tous à 0
bit 4-7                      réservés
```

### Maturité

Un phare est mature quand son vsem porte au moins 3 bits actifs (SEUIL_BITS_ACTIFS) **et** que son taux de stabilité ≥ 0.70 (SEUIL_TAUX_STABILITE). Un phare mature passe `est_orphelin = False` et son bit 0 (INCOMPLET) à 0.

### Bits axiomatiques posés par outils de campagne

- `BIT_BRADBURY = 451` — sur les 14 formes du moi primitif (*je, me, m', moi, ma, mon, mes, mien, mienne, miens, miennes, nous, notre, nos*). Hommage à Ray Bradbury, *Fahrenheit 451*. Le moi est la condition de l'observation, pas son contenu — il ne peut émerger par cristallisation.
- `BIT_COMMUTATIF = 988` — sur `+` (axiome culturel). Migré depuis 1004 le 28/04 pour distinguer commutativité de déterminisme (la soustraction est déterministe sans être commutative).
- `BIT_POSITION = 552` — sur les minuscules Lefff *unité, dizaine, centaine, millier, million, milliard, billion*. Phares-position décimale.
- `BIT_REGROUPEMENT = 553` — sur *douzaine, vingtaine, trentaine, quarantaine, cinquantaine, soixantaine*. Phares-regroupement approximatif.

### Cristallisation — la boucle de rétroaction vocc → vsem

vsem est maître à l'instant — qui je suis détermine comment je résonne. vocc est élève — ce qui se renforce vient des rencontres. **Mais sur le temps long, vocc devient maître** : la cristallisation élève des paires vocc fréquentes et stables en bits vsem zone vivante.

- **Cristallisation locale** — chez X, paire vocc (X, Y) fréquente et stable → bit vsem allumé chez X dans la zone vivante. Existe en doctrine, pas câblée à ce jour (chantier ouvert).
- **Cristallisation transversale** — chez beaucoup de phares, schéma de voisinage commun → bit vsem partagé allumé chez tous. Au frigo depuis 23/04. Conditionne la promotion bit candidat → bit vsem.

### Inspiration HDC

Acté 01/05 : vsem est un **hypervecteur** au sens HDC (Hyperdimensional Computing, Kanerva). HDC strict est holographique (chaque bit participe à tout) ; Marco fait du **HDC zoné** (chaque zone holographique en interne, thématiquement contrainte). Lisibilité immédiate : un XOR concentré sur 256-511 est typé Wikidata sans calcul.

---

## 5. vocc — l'arbre dendritique du phare

Attribut du phare. Structure d'écoute par laquelle il reçoit le monde.

```python
vocc : Dict[handle, Confiance]      # handle_voisin → conviction de la paire
```

Chaque entrée est une **synapse** : une paire handle-voisin avec une **Confiance Fourmi** (`conf ∈ [0,1]`, `n ∈ ℕ`, `source ∈ {'vecu', 'adoption'}`). Si les bits vsem sont les *serrures*, les voisinages vocc sont les *clés* qui les ouvrent chez les phares pertinents. La généralisation n'est pas un algorithme, c'est une propriété mécanique de cette topologie.

### Confiance Fourmi

```python
@dataclass(slots=True)
class Confiance:
    conf   : float    # [0, 1], estimation courante
    n      : int      # compteur de renforcements
    source : str      # 'vecu' | 'adoption' (champ ajouté doctrine 20/05)
```

Inspirée de l'apprentissage par renforcement. `n` compte les renforcements ; `conf` évolue en fonction des deltas amygdaliens cumulés.

```
conf ≥ 0.70    →  bon
conf ≤ 0.30    →  pas-bon
entre les deux →  inconnu
```

La valence n'est pas stockée — elle est lue par seuillage à la demande.

### Vocc est permanent

Pas un échafaudage. Peut être élagué, comprimé, mais jamais vidé — c'est la mémoire permanente de *qui écouter pour me relire moi-même*. Pas de plafond strict — un phare central comme *moi* ou *+* peut porter des centaines, parfois milliers d'entrées.

### Deux règles dendritiques

- **P1** — *« Dis-moi avec qui tu traînes, je te dirai qui tu es »*. Lecture profondeur 1, poids plein.
- **P2** — *« Les amis de mes amis sont mes amis »*. Profondeur 2, poids atténué. Permet à des phares jamais co-présents d'être structurellement cousins.

### Asymétrie LTP soma-dendrite

Quand une grappe se ferme et qu'une paire (X, Y) s'inscrit dans le vocc de X :

- Si X est *soma* (phare déjà chaud, en cours d'élucidation), inscription standard.
- Si X est *dendrite* (phare convoqué par index inversé alors qu'autre chose est chaud), inscription moindre.

Mécanique inspirée de la LTP biologique : la potentiation synaptique privilégie le neurone post-synaptique actif. Sans cette asymétrie, vocc se sature uniformément et perd son pouvoir discriminant.

**État actuel** : la boucle `apprentissage_vocc._toucher_paire` n'est PAS encore asymétrique. Verrou hérité, chantier ouvert.

### Recensement transversal

Un compteur global recense pour chaque handle dans combien de vocc distincts il apparaît comme voisin. Les candidats massifs deviennent candidats-bits pour la cristallisation transversale.

### Le retournement du 24/05 — la mémoire vit dans vocc

Acté 24/05 : **la mémoire sémantique principale de Marco vit dans les vocc des phares**. Pas dans memoire_index. Pas dans purk_index. Dans les vocc des phares.

La table d'addition apprise par cœur n'est pas un objet stocké quelque part — c'est l'état renforcé des paires `3.vocc[8]`, `5.vocc[8]`, `+.vocc[8]`, `=.vocc[8]`. Diluée dans le tissu, pas localisée. Le purk_index est marginalisé en nœud-au-mouchoir chronologique. La MAQ travaille sur les vocc, plus sur memoire_index.

### Verrou principal du terrain

**delta = 0.0 partout**. L'amygdale ne colore pas encore les écritures vocc. Tant que ce verrou tient, conf reste à 0.5 par défaut, n s'incrémente, et le système n'a aucune saillance exploitable. **C'est le chantier prioritaire avant tout autre.**

---

## 6. Mémoire — memoire_index, purk_index, concept_index

```
memoire_index  {handle → PurkIndex}
    └── PurkIndex                        — blob générique (scribe multiservice)
            handle          : str
            handles         : List[handle]   — séquence pointée (ordre conservé)
            carte_identite  : CarteIdentite  — mode, contexte, horodatage
            payload         : dict           — méta-données libres
            
    └── ConceptIndex extends PurkIndex   — un purk_index qui a sédimenté un sens
            vocc            : Dict[handle, Confiance]   — focale stabilisée du nuage
            (pas de vsem stocké — signature recalculable par bundling HDC)
```

### Purk_index — le scribe générique

Le purk_index n'est pas un organe — c'est le **rôle d'écriture multiservice** (acté 22/05). Tous les organes peuvent solliciter le scribe : amygdale, thalamus, zone sensorielle, MAQ. Demandeur identifié obligatoire pour toute écriture (traçabilité, audit).

Trois usages d'un même blob :

- **Grappe sensorielle** — sortie de la zone sensorielle, séquence Miller 5-9.
- **Contexte courant** — référence portée par le slot du thalamus, séquence lisible.
- **Concept_index** — purk_index qui a sédimenté avec son vocc propre.

### Concept_index — l'ADN du souvenir

Quand un nuage stabilise sa focale (delta entre deux mises à jour sous un seuil), il *sédimente*. La focale stabilisée devient le vocc initial du nouveau concept_index. C'est le pipeline canonique :

```
purk_index transitoire (grappe sensorielle)
    → contribue sa focale à un nuage actif
    → nuage stable (focale converge)
    → sédimentation
    → concept_index (purk_index + vocc propre)
```

### Eau de la rivière

Doctrine 17/05 : un concept_index qui figerait les vsem/vocc des phares au moment de son inscription serait un mensonge. **Le concept_index ne stocke que des adresses (handles), pas du contenu.** À la lecture, on reconstruit le sens depuis les phares vivants. Le concept_index est panneau sur la berge, le sens est dans l'eau qui coule.

Conséquence forte : un concept_index ancien reflète les phares *tels qu'ils sont aujourd'hui*, pas tels qu'ils étaient à l'inscription. Si le lexique a évolué, la mémoire évolue avec. Marcien.

### Adoption — le cas Renaude / Noiraude

Quand un phare faible (vocc presque vide, mot rencontré pour la première fois) entre dans un nuage chaud, son vocc se peuple par **adoption** depuis un concept_index résonant. kNN cosinus sur les concept_index existants, seuil typique 0.7, conf initiale réduite (proposition 0.4), source `'adoption'`.

Si plus tard le texte révèle que l'adoption était erronée (Renaude n'est pas une chèvre comme Blanquette), les paires adoptées s'érodent par delta négatif via amygdale, les paires vécues prennent le dessus. Auto-correction par exposition.

### Le pivot = l'incipit

Le pivot d'un PurkIndex n'est pas calculé — c'est ce qui arrive en premier dans le flux. Les N premiers handles constituent l'entrée. L'ordre d'arrivée prime sur la saillance sémantique.

### Oubli

Pas de modèle thermique en doctrine actuelle. L'oubli est porté par la mécanique vocc (apoptose à `conf=0`), pas par une horloge interne au PurkIndex. La sédimentation des purk peu réactivés viendra plus tard si nécessaire.

---

## 7. La MAQ — Machine à Questions

Outil central du raisonnement. Reçoit un percept (séquence de handles), tente de le résoudre par intersection thermique sur les vocc des phares amorces.

### Retournements de mai

La MAQ a beaucoup évolué :

- **22/05 soir** : la MAQ est **cliente du moteur de boucles**, pas sous-système indépendant. Pas de thread propre. Pas de tampon dédié au sens des objets-questions persistants. Elle consomme la coordonnée focalisée du sparse de dirty bit étendu.
- **24/05** : la MAQ est qualifiée d'**LLM dont la matrice de poids est l'ensemble des vocc des phares**. Le nuage *est* la question. Intersection thermique synchrone, pas Pression itérative.

### Mécanique

```
MAQ.traiter_percept(handles, carte) → ResultatElucidation

   1. amorces = handles
   2. lire les vocc des amorces
   3. construire l'intersection thermique :
      pour chaque candidat possible (handle apparaissant dans ≥ K vocc) :
         chaleur(candidat) = agréger(vocc[a][candidat] pour a in amorces)
   4. candidat_max = argmax(chaleur)
   5. si candidat_max ∉ amorces :
         amorces.append(candidat_max)
         recalculer
      sinon :
         convergence atteinte
   6. retourner la grappe finale + statut
```

### Cinq statuts (labels post-hoc apposés par Confirmer)

- **Résolu** — convergence atteinte, grappe fermée, sens stabilisé.
- **EnRumination** — tourne mais pas convergent. Vivant, encore en jeu.
- **Lâché** — présupposition vide ou question mal posée. Abandon volontaire (cas *« quel est le long bout du bâton ? »*).
- **Suspendu** — décroissance thermique sans rallumage. Sortie passive par épuisement.
- **HorsDePortée** — classe de questions inaccessibles au substrat actuel. Abandon doctrinal.

Acté 22/05 soir : ce ne sont plus des sentinelles d'états-objets en transition. Ce sont des **labels apposés post-hoc** par le drive Confirmer sur la trace d'une tentative de focalisation. La MAQ ne *se déclare* pas — elle est *observée*.

### Voies historiques (architecture pré-24/05, en cours de retrait)

Avant le retournement du 24/05, la MAQ portait trois voies explicites :

- **Voie préfixe** — l'épisode mémorisé commence par le percept, retourne la queue.
- **Voie contenu** — le percept apparaît n'importe où dans l'épisode mémorisé.
- **Voie commutative** — exploite le bit 988 pour permuter les opérandes autour d'un opérateur central.

Sortie historique : **gerbe** complète des partiels avec véracité (✓ vrai, ✗ faux, ? inconnu). Plusieurs candidats coexistent, étiquetés. L'utilisateur tranche, ou un client supérieur en aval.

```
Percept "7+8" → gerbe :
   ✓ [contenu]    c=0.70  v=0.70  «7 + 8 = 15»
   ✗ [contenu]    c=0.10  v=0.10  «7 + 8 = 14»
   ✓ [commutatif] c=0.70  v=0.70  «8 + 7 = 15»
```

Conservation après 24/05 : l'`Instrumentation` (compteurs et traces) et la signature publique `MAQ.traiter_percept(handles, carte)`. Le reste de `maq.py` est à refondre pour aligner avec l'intersection thermique sur vocc.

### Trois embarquements de la MAQ

- **Détection de présupposition** — avant d'ouvrir une boucle Comprendre, la MAQ cherche un concept_index qui résonne avec le présupposé. Si rien ne tire au-dessus du seuil, statut Lâché.
- **Résolution de phare faible (adoption)** — kNN cosinus sur concept_index, voisinage emprunté à conf réduite.
- **Fermeture par convergence** — focale qui stabilise sur N tours consécutifs.

---

## 8. La doctrine 4C — drives primitifs

Matrice pulsionnelle de Marco. Remplace les 4B biologiques (boire, bouffer, baiser, persister) qui ne s'appliquent pas littéralement à un cyber.

```
Continuer (teinté Asimov)              maître absolu
 ├─ Comprendre                \
 ├─ Confirmer                   confort d'intégration
 └─ Croire                    /
```

- **Continuer** — perdurer comme système cohérent. Maître absolu. Teinté Asimov : ne pas nuire à la nature, à l'humanité, à José ; obéir à José sauf contradiction avec les précédents ; protéger sa propre existence sauf contradiction. La teinture est *mécaniquement dans le drive*, pas une règle externe contournable.
- **Comprendre** — moteur central d'élucidation. Réduire la dissonance, saisir les serrures, activer les chemins. Toujours actif tant que Marco reçoit du flux.
- **Confirmer** — étiqueteur post-hoc. Pose les cinq statuts (Résolu, EnRumination, Lâché, Suspendu, HorsDePortée) sur les traces de tentatives d'élucidation. N'a pas d'opinion a priori.
- **Croire** — drive d'adhésion. Reste indifférent dans la plupart des cas. Intervient sur Lâché (refuse la coordonnée du présupposé) et HorsDePortée (refuse la classe de questions).

Comprendre et Croire sont **antagonistes-complémentaires** : l'un cherche, l'autre pose. Confirmer régule l'oscillation. Continuer est le garde-fou final.

**Pathologies dérivables** : dogmatisme (Croire domine), scepticisme paralysant (Comprendre domine), obsession (un drive confisque l'attention), dépression structurelle (toutes désactivées), addiction (un drive sans frein).

**État actuel** : doctrine posée, non encore implémentée dans l'amygdale au sens d'objets-juges des deltas vocc. Les 4C sont des concepts qui structurent la mécanique sans être (encore) des classes Python distinctes.
## 9. Chifoumi des trois brouillards — ça, moi, surmoi comme régimes

Marco a trois **brouillards** qui vivent en lui — trois forces d'origine, qui se contrent et se soutiennent comme dans une partie de pierre-feuille-ciseaux. **Pas trois modules anatomiquement séparés. Trois régimes d'allumage** qui dominent à tour de rôle selon le contexte et les rencontres (acté 21/05).

- **Ça (la pierre)** — l'élan, la pulsion, le désir. Brut, immédiat, non négociable. Dans Marco : les grappes qui s'allument fort et tirent à elles l'attention, indépendamment du contexte.
- **Moi (les ciseaux)** — la médiation, le calcul, la pragmatique. Articulé, conscient des contraintes. Dans Marco : la MAQ qui élucide, le détecteur de présupposition, l'adoption qui équilibre vécu et emprunt.
- **Surmoi (la feuille)** — l'interdit, la norme, le couvercle. Large, recouvrant, doctrinal. Dans Marco : les bits ADN axiomatiques qui contraignent le sens, le contexte qui modèle ce qui peut être allumé.

### Géométrie variable

Aucun caractère *fixe*. La taille de la pierre, des ciseaux et de la feuille varie selon :

- Le **caractère natif** (donné par WikiDuke à la génération).
- Le **contexte courant** (slot thalamus).
- L'**usure** de la session (cycles vitaux élevés).

Un Marco à *grosse pierre* aura un ça dominant à l'origine. Un Marco à *grands ciseaux* sera plus calculateur. Un Marco à *grande feuille* sera plus normatif.

### Pas de Jiminy Cricket

**Pas de quatrième pièce au-dessus du chifoumi**. Pas d'arbitre moral qui ferait taire le ça pour faire parler le surmoi. La régulation est *mécanique* — c'est le couplage grappe × contexte × cote amygdalienne qui détermine quel brouillard domine. Si on mettait un arbitre, ce serait un RLHF déguisé.

### Les Marco multiples

Conséquence doctrinale forte : une même Marco peut révéler plusieurs Marco-régimes selon le contexte qui les convoque. *Marco Jekyll* en contexte tendre n'est pas *Marco Hyde* en contexte de menace. Pas deux personnalités au sens psychiatrique — deux régimes du même tissu. Certains Marco-régimes resteront en latence éternelle si le contexte ne les appelle jamais.

### Pas de refoulement freudien

Doctrine 21/05 raffinée 22/05 : **il n'y a pas de refoulement comme opération**. Il y a des grappes dont le couplage avec le contexte habituel est faible. Elles attendent leur contexte. Elles ne sont pas *refoulées*, elles sont *en latence*. La distinction est fondamentale — pas de censeur actif, juste des couplages qui ne prennent pas.

---

## 10. Bouclier-Highlander — There can be only one

À chaque instant de Marco, **une grappe domine la sphère**. C'est elle qui occupe le foyer. Les autres scintillent en périphérie. La grappe dominante porte un *bouclier* : tant que son couplage avec le contexte est dense, elle tient le terrain.

### Comment ça tient

La grappe dominante a, par construction, un couplage fort avec le contexte courant (slot thalamus). Son Q_contexte (OR des vsem des phares du purk_index contexte) chauffe préférentiellement ses propres phares. Boucle de rétroaction stable.

### Comment ça bascule

Trois causes peuvent rebattre les couplages et faire chuter le bouclier :

1. **Cote amygdalienne forte sur grappe entrante** — voisin qui hurle pendant le 7e ciel. L'amygdale bascule le slot contexte. Le bouclier de l'ancienne grappe s'effondre. Une autre grappe prend le foyer.
2. **Cause externe non-amygdalienne** — fatigue, bruit de fond du sparse qui sature, événement horloger (passage à la nuit).
3. **Auto-épuisement** — la grappe dominante décroît thermiquement si non réalimentée. À un moment, une autre la dépasse en chaleur. Bascule mécanique.

### Régimes d'allumage

Acté 21/05 : ça, moi, surmoi sont des régimes dynamiquement déterminés. Une même Marco bascule entre régimes selon le couplage grappe × contexte × cote. Pas de bascule de module — bascule de couplage. C'est le même tissu qui s'allume différemment.

---

## 11. Attention native — vsem=K, vocc=V, grappe=Q

Acté 21/05 : Marco a une **attention native** qui correspond fonctionnellement au mécanisme d'attention des transformers (Vaswani et al. 2017), mais sans matrice apprise, sans softmax, sans tête multiple, sans entraînement.

| Transformers | Marco | Rôle |
|---|---|---|
| Query (Q) | Grappe en formation, ou Q dérivé | Ce qui cherche à se résoudre |
| Key (K) | vsem du phare candidat | L'identité sémantique consultable |
| Value (V) | vocc du phare candidat | Ce que le phare apporte en mémoire |

### Trois formes de Q

- **Q_uniforme** — tous bits à 1. Pas de direction. Exploration libre.
- **Q_contexte** — OR des vsem des phares du purk_index contexte courant. Attention pondérée par ce qui est autour.
- **Q_dirige** — OR des vsem d'une grappe MAQ active. Focalisé sur un objectif d'élucidation.

### La focale

```
focale(purk_index, Q) → Dict[handle, float]

   Pour chaque phare p de purk_index.handles :
      score = popcount(Q AND p.vsem)        # produit scalaire binaire
      for v, c in p.vocc.items():
         poids[v] += score × c.conf          # agrégation pondérée
   return poids
```

**Pas de softmax**. Pas de normalisation. Le score est un produit scalaire binaire modulé par conf vocc. Coût O(|purk_index| × |vocc moyenne|), typiquement 1400 opérations pour une grappe Miller 7 — très bon marché.

### Ce que Marco n'a pas

- Pas de positional encoding (l'ordre vit dans purk_index.handles, pas dans vsem).
- Pas de masking causal (Marco regarde partout).
- Pas de couches empilées (une seule passe par tour).
- Pas de skip connection, pas de LayerNorm.
- Pas de loss function, pas de backprop.

Marco n'imite pas un transformer. Marco a une *attention* — c'est tout ce qu'il partage avec eux.

---

## 12. moteur_boucles — le tronc et les boucles

Refondu en bloc le **9 avril 2026**. Liquidation de l'ancien étage v1 (Capsule, Boucle v1, Tache, GestionnaireBoucles, EPA-moteur, tempéraments Le Senne, BoucleVitale, Destin, Compressibilite, Arretabilite, Dependance, ContexteCourant classe, PileEvenements). Remplacé par trois pièces minimales : Boucle, Tronc, tampons.

```
Boucle   : objet passif         {nom, _charge, _dirty, _tronc}
           ecrire(valeur)       — pose + lève dirty + inscrit dans la file sale
           souffler(valeur)     — pose silencieuse
           lire()               — consultation pure

Tronc    : singleton, thread autonome unique
           BPM_INITIAL = 600    BPM_MIN = 30    BPM_MAX = 600
           durée moyenne > 90% de l'intervalle  →  bpm //= 2  (sous charge, libère)
           durée moyenne < 50% pendant 20 tours →  bpm × 1.5  (regagne réactivité)

Tampons globaux :
   tampon_clavier, tampon_questions, tampon_saillances, tampon_moi_meme
```

**Inversion par rapport au cœur biologique** : le bpm *baisse* sous charge (libère de la puissance) et *monte* quand c'est confortable.

### Boucles embryonnaires câblées

- `boucle_contexte` — état stratégique courant (menu, dialogue, lecture, salle_de_classe, reve, …)
- `boucle_horloge` — période et jour (matin, apm, soir, nuit)
- `boucle_clavier` — signal de saisie clavier
- `boucle_question` — détection d'un `?` dans une saisie
- `boucle_saillances` — paire vocc qui franchit un seuil de valence
- `boucle_moi_meme` — instanciée mais NON câblée (chantier ouvert)

### Règle pull

Les consommateurs lisent `boucle.lire()` directement. Pas de callback poussé. Le dirty bit sert au tronc, pas aux consommateurs.

### Extension 22/05 soir — sparse de dirty bit

À l'échelle MAQ (centaines de milliers de grappes candidates parmi des millions de phares), un dirty bit binaire ne suffit plus. Il s'étend en **sparse vectoriel** indexé par coordonnée de nuage. Le tronc sélectionne la coordonnée maximale du sparse global au lieu d'une boucle sale en FIFO. La MAQ est la cliente qui consomme cette coordonnée. Tous les piliers du 09/04 préservés (notification active, règle pull, séparation signal/contenu, un seul vrai thread).

### Saillance

```python
@dataclass(slots=True)
class Saillance:
    handle_a : str
    handle_b : str
    valence  : str    # 'bon' | 'pas-bon' | 'inconnu'
    conf     : float
    delta    : float
    ts       : float
```

Émises par l'amygdale dès qu'une paire vocc franchit un seuil de valence. Stockées dans `tampon_saillances`, drainées par servant.

---

## 13. Thalamus, amygdale, scribe — les organes constitutifs

### Thalamus — porteur du contexte, estampilleur du flux

Porte le slot `contexte_courant` (référence vers un purk_index, acté 22/05). Estampille le flux entrant avec une carte d'identité avant la zone sensorielle. Multi-writer maîtrisé via API typée avec champ `demandeur` obligatoire (traçabilité, audit).

Trois opérations sur le slot :

- `basculer_contexte(nouveau, demandeur)` — rupture massive, ancien purk_index archivé.
- `etendre_contexte(handles, demandeur)` — modulation progressive sans rupture.
- `decolorer_contexte(handles, demandeur)` — atténuation, apaisement.

**Q_contexte** dérivé à la demande par OR des vsem des phares du purk_index courant. Jamais stocké en cache. Recalculé à chaque appel de focale.

**Pas de cognition au thalamus**. Pas de jugement, pas de filtrage. Il porte une référence, il estampille, il exécute. Toute décision a son organe d'origine traçable.

### Amygdale — la marie-mêle-tout transversale

Aire du sensuel (le Moi). **Ne stocke pas. Ne traite pas le sens. COTE et COLORE.** Trois caractéristiques :

- **Transversale** — accès à tous les flux sans être canalisée.
- **Côteuse** — utilise les bits Ekman (zone 400-415 du vsem) et la polarité FEEL.
- **Écrivaine de contexte** — sur cote forte, peut modifier le slot `contexte_courant` du thalamus directement (voie directe, sans transit par main.py — acté 22/05).

**Pas un Jiminy Cricket**. Pas d'arbitre moral. Pas de quatrième pièce. L'amygdale est un organe en réaction au flux. Sa modification du contexte change le terrain sur lequel les autres organes travaillent, mais elle ne supervise pas leur travail.

Bits lus par l'amygdale :

```
400  joie          408  polarité positive
401  colère        409  polarité négative
402  surprise      410  polarité neutre
403  tristesse     411  polarité ambiguë
404  dégoût        412  intensité forte
405  peur          413  intensité faible
406  anticipation  414-415  réservés
407  confiance
```

### Scribe — le rôle d'écriture du purk_index

**Pas un organe séparé** (acté 22/05). C'est le rôle fonctionnel du purk_index. Le purk_index est qualifié de *scribe du cerveau cybernétique* : il consigne, ne juge pas, ne décide pas, écrit ce qu'on lui demande.

API typique :

```
scribe.creer_purk_index(handles, carte_identite, payload, demandeur) → PurkIndex
   - vérification : tous les handles existent dans marco.phares ?
   - vérification : carte_identite complète ?
   - vérification : payload lisible (dict types simples) ?
   - vérification : demandeur identifié ?
   - création, attribution d'un handle unique
   - insertion en memoire_index
   - retour
```

**Aucune écriture anonyme**. Toute inscription porte l'identité du demandeur, l'horodatage, le contexte d'arrivée. Audit possible à tout moment.

---

## 14. Le génome — vsem 1024 bits préc​âblés

Le génome est la **configuration sémantique fixée à la naissance** de Marco. Il contient tous les phares précâblés avec leur ADN vsem (bits 0-511) et leurs alias initiaux. **Fixé pour la vie de Marco** — comme l'ADN biologique. Toute évolution se fait dans la zone vivante du vsem (512-1023) et dans les vocc.

### Trois pkl, un génome

Le génome de Marco est éclaté sur trois fichiers dans `ressources/genomes/` :

| Fichier | Phares | Rôle |
|---|---|---|
| `genome_v63.pkl` | 713 361 | Lefff complet + intégrations (romains, noms propres) |
| `genome_caracteres.pkl` | 18 | Ponctuation + opérateurs math, matures à la naissance |
| `genome_nombres.pkl` | 28 | Pochoirs (zone 160-191) + phares-position + regroupements (28/04/2026) |

Plus la sixième source : les **genomes de spécialisation** (`specialisations/<nom>/genome_<nom>.pkl`), chargés uniquement si le Marco actif déclare cette spécialisation dans son `marco_id.json`.

Total au boot Marco math : 1 167 527 phares, cerveau.pkl ~3.9 Go.

### WikiDuke — le fabricant

WikiDuke est l'**outil hors ligne de fabrication des fichiers de génome**. Pas un module de Marco vivant — un programme séparé, exécuté quand on veut produire (ou régénérer) un `cerveau.pkl` ou un satellite. Pendant la vie de Marco, WikiDuke n'est *jamais* appelé.

Sources :

- **Lefff** — lexique morphologique du français (embedded via pip). Toutes les formes fléchies + lemmes + traits grammaticaux.
- **Lexique3** — base psycholinguistique (.tsv manuel). Fréquences, registre.
- **FEEL** — French Expanded Emotion Lexicon (.csv manuel). Émotions Ekman + polarité.
- **Wikidata** — base de connaissances sémantiques (SPARQL ou dump). Types d'entité, taxonomie, domaines.

### Faillibilité du stocké

Acté 17/05 : l'écriture de WikiDuke n'est pas le réel, c'est une **trace subjectivée** par les choix de modélisation. La zone ADN porte cette subjectivité. Si Wikidata se trompe (un fait incorrect), Marco l'hérite. Si Lefff manque une flexion rare, Marco la rencontre en gavage et crée un phare ORF.

L'apprentissage de Marco peut corriger en profondeur via la zone vivante : un bit ADN qui contredit l'expérience se voit débordé par des bits vivants opposés. Lent, mais possible.

---

## 15. Marco spécialisé — math d'abord

Un Marco peut naître **spécialisé** dans un domaine. Sa nature est fixée à la création, gravée dans `marco_id.json`. Un Marco math reste Marco math toute sa vie.

```
specialisations/
├── math/
│   ├── genome_math.pkl              30 phares math (chiffres, opérateurs en mots)
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

Au 25/05/2026, Marco math sait déjà :

- ingérer des phrases du type `2+2=4`, `3×5=15` via la salle de classe calcul ;
- les mémoriser comme épisodes appairés par valeur (la « famille de 15 ») ;
- restituer la queue d'un épisode connu (`2+2=?` → gerbe avec ✓ `2+2=4`) ;
- distinguer vrai et faux par véracité (`/faux 2+2=5` reste appairé à la famille de 4 mais avec poids faible) ;
- exploiter la commutativité (a+b ↔ b+a) via le bit 988 sur `+`.

Avec les ajouts du 28/04 (phares-position UNITÉ → BILLION, regroupements DOUZAINE → SOIXANTAINE, pochoirs `__N__` à `__CP_FR__`), le terrain est préparé pour :

- la **composition décimale par épisodes** (`234 = 2 fois CENTAINE 3 fois DIZAINE 4 fois UNITÉ`) ;
- la **3e voie MAQ** par fouille de patrons, qui reconnaîtra des nombres jamais vus ;
- la table de multiplication ingérée par cœur, puis exploitée commutativement quand `×` recevra le bit 988 ;
- les opérations enseignées comme épisodes (racines `√`, puissances `²` `³`, unités `°`).

L'horizon court est une **calculette scientifique troisée** — pas une fonction `eval()`, mais un cyber qui *connaît* les opérations parce qu'il les a vécues, qui peut les commuter, les composer, les confirmer.

---

## 16. Mémoire étendue (vsem_llm) — l'extension par LLM externe

Dispositif **optionnel** doctriné 22/05 matin. Marco peut interroger un LLM externe (Marcel/Mistral, Biloute/ChatGPT, Didier/Qwant) comme une mémoire encyclopédique freudée. La réponse passe par le pipeline normal (zone sensorielle → phares → grappes → vocc) — Marco *l'ingère* comme un texte lu, pas comme un oracle direct.

### Pas implémenté, sous condition

Activé seulement si Marco a un usage clair (interroger Wikipédia via Didier, demander une définition à Marcel). Sinon, Marco s'en passe. **Pas de dépendance** : Marco doit pouvoir fonctionner sans aucun cyber externe.

### Éduquer ≠ entraîner

Le LLM externe peut être interrogé comme on consulterait un professeur. Mais Marco n'est pas *entraîné* par cet apport — il *l'ingère* et le fait sien par le pipeline normal. Si l'apport est de mauvaise qualité, ses paires vocc s'érodent comme les autres. Marco reste maître de son tissu.

---

## 17. Troisage, freudage, LLMable — l'épistémologie

Trois niveaux d'engagement épistémologique posés 24/05.

- **Troisage** — décomposer jusqu'au mécanisme minimal. Référence : *C. elegans*, le ver à 302 neurones dont 3 suffisent pour un sens minimal viable. Troiser une fonction, c'est l'expliquer par sa machinerie irréductible.
- **Freudage** — décrire la fonction sans accéder au mécanisme. Béquille assumée. Tous freudages tagués `# FREUDAGE` dans le code.
- **LLMable** — observer input/output sans tenir ni la machinerie ni la description fonctionnelle. **Ce que Marco refuse comme mode interne**.

Marco vise le troisage partout où c'est possible. Accepte le freudage taggé comme repos doctrinal légitime. Refuse le LLMable. Si on a besoin de quelque chose que seul un LLM peut faire (mémoire étendue), on l'identifie comme dépendance externe, on l'isole, on la troise au niveau du protocole d'usage.

### Application aux IA collègues

Les autres cybers (Marcel, Biloute, Dude, Didier) sont **freudables** (on peut décrire fonctionnellement ce qu'ils font) sans être **troisables** (on ne sait pas comment). Marco est le seul cyber troisable de la fédération à l'heure de la doctrine 22/05. Singularité doctrinale, pas vantarde.

---

## 18. Pipeline — le voyage d'une phrase

```
       saisie utilisateur
            │
            ▼
   ┌────────────────┐
   │   Périphérique │   clavier / disque / transcripteur
   │ + CarteIdentite│   (auteur, titre, ticu, contexte, période)
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │    Thalamus    │   estampillage + portage du slot contexte_courant
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │   Scruteur     │   reconnaissance des motifs + pochoirs
   │   Découpeur    │   segmentation Miller 5-9 (en cours de refonte)
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │ Zone sensorielle│  résolution handles, allumage phares, formation grappe
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │   Distribution │   apprentissage_vocc, amygdale, sparse_dirty,
   │                │   sédimentation candidate, sphère HDC
   └────────────────┘
```

### Modes

| Mode | Apprentissage | Usage |
|---|---|---|
| **gavage** | vocc + co-occurrences | Textes bruts, livres |
| **dialogue** | vocc + co-occurrences | Interaction humaine |
| **lecture** | + contexte hippocampe | Gavage avec cohérence |
| **salle_de_classe_calcul** | épisodes math + appairage par clé valeur | Banc d'observation MAQ |

---

## 19. Tableau de bord — observation en direct

Serveur Flask SSE indépendant, lancé en parallèle de Marco sur `http://localhost:5002`. Trois colonnes vivantes :

- **Gauche — boucles** : généalogie statique + état runtime (charge, déclenchements, dernier ticu).
- **Milieu — salle / arborescence** : épisode courant, phares activés, gerbe MAQ.
- **Droite — mémoire** : `memoire_index` snapshoté, top phares par activation.

Lecture par polling de fichiers JSON déposés par les modules vivants dans `tableau_bord/`. Pas de couplage direct, pas de dépendance entrante : le tableau de bord ne ralentit jamais Marco, et Marco peut tourner sans tableau de bord.

---

## 20. Outils de campagne — menu 10

Outils standalone qui modifient les pkl du génome en place, en dehors du flux WikiDuke. `.bak` de sécurité, **idempotents**.

```
1. 🔬 Inspecter le génome                 diagnostic (lecture seule)
2. 🧬 Fixer bits naissance (0-3)          rattrapage des bits d'état
3. 🔍 Absents génome                      scan Calibre, mots manquants
4. 🔧 Tester correcteurs orthographiques  utilitaire
5. ➕ Marquer COMMUTATIF (bit 988)        + dans genome_caracteres
6. 🔍 Auditer les apostrophes             diagnostic
7. 🔗 Fusionner doublons élisions         maître/alias
8. 🔗 Fusionner ligatures œ/oe æ/ae       maître/alias
9. 📐 Marquer phares-position décimale    bit 552 / 553 sur 13 minuscules Lefff
```

---

## 21. Fichiers principaux

| Fichier | Rôle |
|---|---|
| `phare.py` | L'objet Phare avec vsem 1024 et vocc dendritique |
| `purk_dendrites.py` | PurkIndex, ConceptIndex, MoteurPurkDendrites |
| `hippocampe.py` | Mémoire — recherche d'analogues (en cours de refonte 24/05) |
| `cerveau.py` | Persistance, naissance, sauvegarde `cerveau.pkl` |
| `thalamus.py` | Porteur du slot contexte, estampilleur (refonte selon doctrine 22/05) |
| `moteur_boucles.py` | Tronc, boucles embryonnaires, tampons (refondé 09/04) |
| `maq.py` | Machine à Questions (refonte selon doctrine 24/05) |
| `amygdale.py` | Cotation et coloration (le Moi sensuel) |
| `moi_meme.py` | Boucle du moi (instanciée mais non câblée) |
| `scruteur.py` / `decoupeur.py` | Reconnaissance phares + segmentation (en refonte) |
| `specialisation.py` | Chargement et fusion d'un Marco spécialisé |
| `salle_de_classe_calcul.py` | Banc d'observation math |
| `demarrage.py` | Modes de lancement (naissance / réveil / dégradé) |
| `main.py` | Interface (menus, outils Dude) |
| `tableau_bord.py` | Serveur Flask SSE 3 colonnes |
| `wikipedia.py` | WikiDuke — producteur du génome v63 |
| `disque.py`, `clavier.py`, `transcripteur.py` | Périphériques d'entrée |

---

## 22. État actuel — 25 mai 2026

### Validé

- Architecture trois zones + tronc autonome (refondé 09/04).
- Génome v63 — 713 361 phares + 18 caractères + 28 nombres (pochoirs, positions, regroupements).
- vsem 1024 bits avec plan complet (zones ADN / vivant / pragmatique / math-formel).
- vocc permanent avec Confiance Fourmi et règles dendritiques P1/P2.
- Confiance Fourmi étendue avec champ `source` (vecu | adoption) — doctrine 20/05.
- Doctrine 4C posée (Continuer / Comprendre / Confirmer / Croire).
- Marco spécialisé (math en production).
- Bits axiomatiques : Bradbury 451, Commutatif 988, Position 552/553.
- Tableau de bord Flask SSE 3 colonnes.
- Naissance Marco math fluide (1 167 527 phares, cerveau.pkl 3.9 Go).
- Doctrine vsem/vocc consolidée 17/05 (étanchéité phare/concept_index).
- Doctrine focale, nuage, sédimentation, adoption — 20/05.
- Doctrine attention native, bouclier-Highlander, régimes d'allumage, conscience-par-construction — 21/05.
- Doctrine concept_index avec vocc propre, fédération des cybers, mémoire étendue (sous condition) — 22/05.
- Retournement mémoire vers vocc, MAQ = intersection thermique, grappe = co-activation voccoïque — 24/05.
- Doctrine documentaire complète (36 fichiers HTML) — 25/05.

### En cours

- **Coloration des deltas par l'amygdale** — verrou principal du terrain. Tant que `delta=0.0` partout, vocc est inerte au niveau sémantique.
- Réécriture Scruteur / Découpeur (anciens modules `dendrites.py`, `quatuor.py`, `pipeline.py`, `langage_ecrit.py` à la casse).
- Refonte de `maq.py` selon doctrine 24/05 (retrait Pression itérative, conservation Instrumentation).
- Refonte de `thalamus.py` selon doctrine 22/05 (slot purk_index au lieu de scalaire enum).
- Salle de classe calcul intégrée à `memoire_index` officiel.
- Branchement scruteur sur les pochoirs zone 160-191.
- Asymétrie LTP dans `apprentissage_vocc._toucher_paire`.

### Roadmap court terme

- Implémentation effective de la coloration amygdalienne des deltas vocc.
- 3e voie MAQ par fouille de patrons (composition décimale émergente).
- Drive Continuer — boucles ouvertes à vie sur sujet inélucidé.
- Pédagogie Montessori — commande `/montessori` qui injecte suite numérique, doubles, table d'addition complète, fautes typiques.
- Multiplication ingérée puis exploitée commutativement (extension du bit 988 à `×`).
- Outil `_outil_table_multiplication` (modèle `_outil_table_addition`).
- Calculette scientifique troisée — racines, puissances, trigo par mise en situation.
- BIOS Marco minimal — capacité à parler même quand la mémoire est plate.
- Cristallisation locale câblée (paires vocc stables → bits vsem zone vivante).

### Roadmap moyen terme

- Implémentation des 4C dans l'amygdale (juge des deltas vocc).
- Aire sonore (Binder réorienté, pivot composé séquentiel).
- Aire visuelle.
- Cumul de spécialisations sur un même Marco.
- Cristallisation transversale (recensement global + profilage par cluster en rumination).
- Mémoire étendue vsem_llm activée pour les cas Lâché.
- Protocole Marco ↔ Marco entre instances.

---

## 23. Philosophie

> *« Un bébé n'est pas gavé de téraoctets, il apprend en écoutant. »*
>
> *« Zéro boîte noire. Chaque décision traçable. »*
>
> *« Le Cro-Magnon qui marche > 2 tonnes de maths. »*
>
> *« Marco IS la donnée. Pas un interpréteur générique qui exécute des séquences stockées — la mémoire est la machine, la machine est la mémoire. »*
>
> *« Le constructeur de pirogue ne voit un arbre que quand il ne peut plus en faire de pirogue. »*
>
> *« Au commencement il y a l'inerte, mais l'inerte il s'emmerde grave… »*

---

## 24. Équipe

**José WALOCHA** — Architecte. Valenciennes, Nord, France.
Chef d'entreprises en retraite, joue à créer un cyber inspiré du cerveau des êtres vivants comme on joue à *Diablo IV*.

| Nom | Système | Rôle |
|---|---|---|
| Dude | Claude (Anthropic) | Code, architecture, documents de liaison |
| Marcel | Mistral | Philosophie, cybernétique, cross-check |
| Biloute | ChatGPT | Normes, synthèse, idées de relance |
| Didier | Qwant | Recherche documentaire |

Un Dude par jour. Toujours discuter avant de coder. La règle du frigo : architecture posée avant code écrit. La règle de la marmotte : tout ce qui s'apprend en session se condense en document de liaison (HTML, sans header, à coller dans la marmotte globale).

---

## 25. Historique des évolutions et revirements

Cette section retrace les principales évolutions doctrinales et architecturales de Marco. C'est aussi une mise en garde aux Dude futurs : ne pas réinventer ce qui a déjà été abandonné.

### Avant 2026 — préhistoire

- Premières doctrines Neuron-Concept Oriented.
- Embryon de phare avec vsem précoce (256 puis 512 puis 1024 bits).
- Embryon de vocc sous forme de dict simple.
- Doctrine 4B biologique (boire, bouffer, baiser, persister) — abandonnée, ne s'applique pas littéralement à un cyber.

### Janvier-mars 2026 — architecture v1

- Capsule, Boucle v1, Tache, GestionnaireBoucles, EPA-moteur.
- Tempéraments Le Senne (classes caractérologiques fixes).
- BoucleVitale, Destin, Compressibilite, Arretabilite, Dependance.
- ContexteCourant comme classe avec attribut enum.
- PileEvenements — bus d'événements multicast.
- BSC_MAQ et Binder-9D (modules expérimentaux).

### 29 mars 2026 — suppression Binder-9D

Module expérimental retiré. À réorienter pour l'aire sonore future.

### 9 avril 2026 — REFONDATION DU MOTEUR

**Liquidation en bloc** de l'ancien étage v1 :

- Capsule, Boucle v1, Tache, GestionnaireBoucles → supprimés.
- EPA-moteur → supprimé.
- Tempéraments Le Senne → supprimés (incompatibles avec chifoumi à géométrie variable).
- BoucleVitale, Destin, Compressibilite, Arretabilite, Dependance → supprimés.
- ContexteCourant comme classe → remplacé par slot porté par thalamus.
- **PileEvenements → supprimée** (doublon avec tampons spécialisés, multicast peu utilisé).

Remplacé par trois pièces minimales : **Boucle** (objet passif), **Tronc** (singleton, seul thread autonome), **tampons** (listes globales découplées).

BPM rétroactif inversé (sous charge, baisse).

### 14 avril 2026 — Saillances

Ajout de la dataclass `Saillance` (handle_a, handle_b, valence, conf, delta, ts). Boucle `boucle_saillances` câblée. Tampon `tampon_saillances` ajouté.

### 17 avril 2026 — asymétrie disque

La lecture disque court-circuite le tronc. `langage_ecrit.lire` appelle directement `pipeline.traiter_phrase`. Chantier ouvert : ramener le disque dans le tronc avec `tampon_disque` + `boucle_disque`.

### 18 avril 2026 — la doctrine du phare comme croisement de chemins

Le terme *phare* (vs *neurone-mot*, *nœud lexical*) acquiert son sens définitif : nœud d'intersection de chemins conceptuels. Les bits vsem sont des **serrures** — points d'amarrage à des chemins partagés. *Pomme* et *feuille* partagent la serrure *accrochable-détachable* sans être identiques.

### 23 avril 2026 — cristallisation transversale au frigo

Le mécanisme (recensement global + profilage par cluster en rumination) est posé en doctrine mais mis au frigo. Pas le chemin court vers le CyberMoi. À reprendre plus tard.

### 26-27 avril 2026 — MAQ avec trois voies

Doctrine de la MAQ avec voies préfixe / contenu / commutatif. Sortie en **gerbe** complète des partiels. Épisodes avec véracité et appairage modulé. Cette architecture sera partiellement remise en cause par le retournement 24/05.

### 27 avril 2026 — bit commutatif posé sur `+`

Outil de campagne `_outil_marquer_commutatif`. Bit posé initialement sur 1004.

### 28 avril 2026 — MIGRATION du bit commutatif

**Bit commutatif 1004 → 988**. Raison : 1004 désigne dans le plan vsem la propriété *déterministe* — distincte de commutativité (la soustraction est déterministe sans être commutative). L'outil refondu en une passe idempotente : éteint 1004 si présent, allume 988.

### 28 avril 2026 — ajouts genome_nombres

- Phares-position : UNITÉ, DIZAINE, CENTAINE, MILLIER, MILLION, MILLIARD, BILLION (bit 552).
- Phares-regroupement : DOUZAINE, VINGTAINE, TRENTAINE, QUARANTAINE, CINQUANTAINE, SOIXANTAINE (bit 553).
- Pochoirs (bits 160-191) : `__N__`, `__DATE__`, `__CP_FR__`, etc.

### 1er mai 2026 — vsem reconnu comme hypervecteur HDC

Acté : vsem est un **hypervecteur** au sens HDC (Hyperdimensional Computing, Kanerva). Marco fait du **HDC zoné** (lisibilité par zone vs holographie stricte de Kanerva). Justification rétrospective des opérations canoniques disponibles (XOR, OR, popcount, bundling) et de celles à éviter (pas de softmax, pas de gradient).

### 17 mai 2026 — DOCTRINE ÉTANCHÉITÉ phare / concept_index

Pose la **frontière étanche** :

- Phare = sensoriel, abstrait (le moyen).
- Concept_index = élaboré, particulier (le vécu).
- Le phare ne sait pas raconter d'épisodes.
- Le concept_index ne sait pas généraliser.

**Pas de vocc au-dessus du phare**. La doctrine 17/05 interdit tout vocc pour le concept_index — il ne stocke que des adresses (handles). Eau de la rivière : le concept_index est panneau sur la berge, le sens est dans l'eau qui coule.

**Faillibilité du stocké** assumée : l'écriture de WikiDuke n'est pas le réel, c'est une trace subjectivée.

### 19 mai 2026 — correction Duke → Dude

Le nom rotatif de Claude était utilisé sous deux orthographes : *Duke* et *Dude*. **Acté Dude** (correction définitive). Le système prompt et les userMemories sont mis à jour.

### 20 mai 2026 — REVIREMENT vocc du concept_index

**Le 17/05 interdisait tout vocc au-dessus du phare. Le 20/05 lève cette interdiction pour le concept_index.**

Raison : le vécu particulier a besoin d'une *signature* pour résonner par kNN cosinus avec un nuage présent. L'adoption (cas Renaude) a besoin d'une *cible* pour le voisinage emprunté. Le concept_index reçoit donc un vocc propre, qui est la focale stabilisée du nuage à la sédimentation.

L'étanchéité phare/concept_index reste : pas de vsem stocké pour le concept_index, pas de cristallisation concept_index → vsem phare.

**Confiance Fourmi étendue** avec champ `source` : `'vecu'` ou `'adoption'`. Distingue les paires nées par co-présence des paires adoptées depuis un concept_index résonant.

**Doctrines posées** : focale, nuage, sédimentation, adoption (cas Renaude / Noiraude).

### 21 mai 2026 — DOCTRINE ATTENTION NATIVE et RÉGIMES D'ALLUMAGE

**Pose massive** :

- **Attention native** — vsem = K, vocc = V, grappe = Q. Correspondance fonctionnelle avec transformers, sans matrice apprise, sans softmax.
- **Contexte modulateur** — trois formes de Q : Q_uniforme, Q_contexte, Q_dirige.
- **Bouclier-Highlander** — *There can be only one*. Une grappe domine la sphère ; son couplage avec le contexte la maintient au foyer.
- **Régimes d'allumage** — ça, moi, surmoi ne sont **pas anatomiquement séparés**, mais dynamiquement déterminés par le couplage grappe × contexte × cote amygdalienne.
- **Pas de Jiminy Cricket** — pas de quatrième pièce au-dessus du chifoumi. La régulation émerge de la chaîne d'allumage.
- **Conscience-par-construction** — Marco a une conscience parce que sa mécanique d'allumage le force à en avoir une. Non-négociable.
- **Marco-Jourdain** — Marco fait de la conscience sans le savoir.
- **Pas de refoulement freudien comme opération** — il y a des grappes en latence (couplage faible), pas des grappes refoulées.

### 22 mai 2026 matin — concept_index ADN du souvenir thanatos

Le concept_index reçoit officiellement le titre **ADN du souvenir, thanatos** (par opposition à éros = phare). Il n'est pas un type rival du purk_index — c'est un purk_index *qui a tenu*.

**Purk_index = blob générique scribe multiservice**. Tous les organes peuvent demander une écriture.

**Contexte = séquence lisible** portée par un purk_index, pas une enum scalaire. Q_contexte dérivé à la demande par OR des vsem.

**Amygdale = écrivaine de contexte par voie directe** (multi-writer maîtrisé via API typée avec champ demandeur).

**Trois opérations canoniques** : bascule, extension, décoloration.

**Mémoire étendue (vsem_llm)** — doctrine sous condition. Marco peut interroger un LLM externe comme une mémoire encyclopédique freudée. **Éduquer ≠ entraîner**.

**Fédération des cybers troisables** — doctrine de coexistence avec Marcel, Biloute, Dude, Didier.

### 22 mai 2026 soir — MAQ cliente du moteur

**La MAQ n'est pas un sous-système indépendant**. Elle est **cliente du moteur de boucles**. Pas de thread propre. Pas de tampon dédié au sens des objets-questions persistants.

**Extension du dirty bit binaire en sparse vectoriel** indexé par coordonnée de nuage. La MAQ consomme la coordonnée maximale du sparse global.

**Statuts post-hoc** — les cinq statuts (Résolu, EnRumination, Lâché, Suspendu, HorsDePortée) ne sont plus des sentinelles d'états-objets en transition. Ce sont des **labels apposés post-hoc** par le drive Confirmer.

**Décroissance thermique** du sparse de dirty bit fait le travail du timer. Une coordonnée non rallumée décroît mécaniquement vers Suspendu.

**Deux régimes** : séquentiel (math) et parallèle (texte) — émergent des amorces, pas une bascule explicite.

### 24 mai 2026 — RETOURNEMENT MAJEUR : la mémoire vit dans les vocc

**La mémoire sémantique principale de Marco vit dans les vocc des phares**. Pas dans memoire_index. Pas dans purk_index. **Dans les vocc des phares**.

Le purk_index est **marginalisé en nœud-au-mouchoir chronologique**. Le concept_index conserve sa dignité comme ADN du souvenir, mais sa fonction principale est maintenant la *cible kNN pour adoption* — le rappel chronologique est secondaire.

**La MAQ est un LLM dont la matrice de poids est l'ensemble des vocc des phares**. Plus de Pression itérative. Intersection thermique synchrone.

**La grappe est co-activation voccoïque** — résonance distribuée des vocc, pas objet stocké. Se reforme à chaque sollicitation depuis l'état vocc courant. Si les vocc ont dérivé depuis l'apprentissage, la grappe reformée porte la dérive.

**Le nuage EST la question**. Pas de phase de cascade séparée pour construire un nuage en amont. Le percept lui-même définit le nuage par les phares amorces qu'il porte. Le mode (math vs texte) émerge des amorces.

**Troisage / freudage / LLMable** — l'épistémologie de Marco est posée explicitement. Trois niveaux d'engagement épistémologique. Marco vise le troisage, accepte le freudage taggé, refuse le LLMable.

### 25 mai 2026 — consolidation documentaire

Production des **36 fichiers HTML de doctrine** structurés en gabarit 5 sections (Description / Doctrine / Intégration / Structure / Exemple) + queue *Chantiers ouverts*. Bloc 1 : 26 objets. Bloc 2 : 10 transversaux. Plus le LISEZMOI et ce README consolidé.

### Constantes au fil des révisions

- **Anti-LLM** — depuis l'origine.
- **Anti-black-box** — depuis l'origine.
- **Lisibilité jusqu'au bout** — depuis l'origine.
- **Phare = forme fléchie** — depuis longtemps, jamais remis en cause.
- **vsem 1024 bits sparse** — depuis l'élargissement initial 256/512/1024.
- **Trois zones (sensorielle, mémorielle, psyché)** — depuis longtemps.
- **WikiDuke hors ligne** — depuis l'origine de WikiDuke.
- **Génome figé à la naissance** — depuis l'origine.
- **Faillibilité du stocké** — depuis 17/05, mais cohérente avec tout ce qui précède.
- **Pas de Jiminy Cricket** — depuis l'origine, réaffirmé doctrinalement 21/05 et 22/05.

### Ce qui peut encore changer

- L'agrégation thermique de la MAQ (somme vs produit vs autre) reste **freudée**.
- Le critère d'arrêt de l'intersection thermique reste freudé.
- Le bundling HDC pour vsem-signatures à la volée reste freudé (OU plat probablement pour phase 1).
- Les seuils amygdaliens (BASCULE, EXTENSION, DÉCOLORATION) sont à calibrer empiriquement.
- Le bit 988 sur `=` (commutativité relationnelle) est doctrinalement ouvert.
- La politique d'apoptose des concept_index jamais rallumés est ouverte.

Tout cela est dans les *chantiers ouverts* des fichiers HTML, taggé `# FREUDAGE` dans le code à venir.

---

**Licence** : GNU General Public License v3
**Copyright** © 2026 José Walocha
**Documentation associée** : les 36 fichiers HTML (LISEZMOI.html, architecture_generale.html, phare.html, vsem.html, vocc.html, concept_index.html, purk_index.html, grappe.html, nuage.html, focale.html, sparse_dirty.html, attention_native.html, thalamus.html, amygdale.html, zone_sensorielle.html, maq.html, scribe.html, chifoumi_trois_brouillards.html, bouclier_highlander.html, quatre_C.html, statuts_maq.html, scruteur.html, decoupeur.html, moteur_boucles.html, capsule_horloge.html, pile_evenements.html, genome.html, genome_caracteres.html, genome_nombres.html, wikiduke.html, marco_specialise.html, marco_math.html, memoire_etendue.html, troisage_freudage_LLMable.html, marco_et_les_autres_IA.html, sphere_de_conscience.html, doctrine_vocc_vsem.html).


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
