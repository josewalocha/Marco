# MARCO — Cybernetic Brain with Hierarchical Decision Architecture

> \*"Learning is remembering"\* — Plato, Meno

**Author**: José WALOCHA  
**Team**: Le Duke (Claude), Marcel (Mistral), Biloute (ChatGPT), Didier (Qwant)  
**License**: GNU GPL v3  
**Version**: 5.0 — March 2026

\---

## 1\. What is MARCO?

MARCO is the world's first **NCODB** — Neuron-Concept Oriented Database System.

Where a classic DBMS stores rows in tables, MARCO stores **concepts in a neural network inspired by the biological brain**. Meaning emerges from connections. No SQL. No fixed schema. Zero black box.

||Classic DBMS|MARCO|
|-|-|-|
|Storage|Tables, rows, columns|Beacons, dendrites, concepts|
|Query|`SELECT \* FROM ...`|Cascade activation|
|Relations|Foreign keys|Co-occurrences, coactivations|
|Schema|Fixed|Emergent|
|Index|B-Tree, Hash|Thermal purk\_index|
|Learning|None|Feeding + consolidation|
|Transparency|Query = result|Every link traceable|

A classic DBMS is static (Thanatos). MARCO is alive (Anima): it learns by reading.

\---

## 2\. Architecture — Overview

```
Layer I    — Letters          1 letter = 1 neuron (BSC cascade)
Layer II   — Beacons          1 word = 1 Binder-9D concept
Layer III  — Concepts         N words = 1 block (BSCW, greedy window)
Layer IV   — Co-occurrences   Meaning through proximity
Layer V    — Sequences        Syntax through order
```

### Russian Dolls — class Concept(Beacon)

A Concept IS a Beacon. It inherits everything, plus a family, responses, components.

Levels nest without limit:

```
Level 0: Letters      c, o, f, f, e, e
Level 1: Words        coffee, cream
Level 2: Concepts     coffee cream
Level 3: Registers    ORDER
Level N: ...
```

\---

## 3\. The Genome — Binder-9D

Each beacon is positioned in a 9-axis cybernetic semantic space:

|Axis|Meaning|
|-|-|
|AT|Cognitive tension (observation without reaction)|
|SU|Subjectivity (anchoring in the subject)|
|EG|Self-belonging|
|OS|Physical space anchoring|
|TY|Ontological type (0=object, 1=agent, 2=action...)|
|VA|Affective valence|
|EC|Cultural resonance|
|TM|Temporality|
|IN|Informational intensity|

Genome v60 contains **13,304 suns** with complete Binder-9D handles.

Future cognitive areas (sound, vision) will use the same 9-axis skeleton reoriented toward their domain.

\---

## 4\. Processing Pipeline

```
Raw text
  → Stripping (French syntax removal)
  → BSC (beacon detection via letter cascade)
  → BSCW (multi-word concept detection)
  → Thalamus (routing, labeling)
  → Hippocampus (memory consolidation)
  → memoire\_index (thermal purk\_index)
```

### Processing Modes

|Mode|BSCW|Learning|Usage|
|-|-|-|-|
|feeding|no|dendrites, co-occ|Raw texts, books|
|dialogue|yes|dendrites, co-occ|Interaction|
|reading|yes|+ hippocampus context|Intelligent feeding|

\---

## 5\. Memory — The Hippocampus and purk\_index

### Structure

```
memoire\_index  {incipit → PurkIndex}
    └── PurkIndex  — Purkinje consolidation node
            incipit          : list\[str]   — first N handles (universal pivot)
            pivot\_type       : str         — incipit | compose\_nominal | compose\_evenementiel | compose\_sequentiel
            pivot\_composants : list\[str]
            episodes         : list\[ConceptIndex]
            dendrites        : dict\[str, float]   — weighted inverted index
            sous\_purks       : dict\[str, PurkIndex]  — fractal arborization
            temperature      : float       — current thermal state
            materiau         : str         — genome handle (MAGMA, ACIER, VERRE, GLACE...)
            etiquettes\_dominantes : dict
            statistiques\_coactivation : dict
    └── ConceptIndex  — episode of one sentence
            handles          : list\[str]
            pivot\_forme      : str
            pivot\_type       : str
            pivot\_composants : list\[str]
            vecteur\_bsc      : dict        — {presence, roles, relations, tensions, questions}
            contexte\_induit  : dict        — {langue, aire, cadre\_source, narrateur, lieu, temporalite, registre, statut, certitude}
            source           : dict        — {texte\_id, auteur, titre, ligne, phrase, timestamp}
            epa              : dict        — {attention, pression, emotion, intensite}
```

### The Pivot = The Incipit

The pivot is not calculated — it is what arrives first in the stream. The first N handles constitute the entry into `memoire\_index`. Arrival order takes precedence over semantic salience.

### Thermal Model

Each `PurkIndex` has a **temperature** and a **material**:

```
temperature(t) = floor + (initial\_temp - floor) × e^(-t / half\_life)
```

The material is a genome handle carrying `half\_life` and `floor` in its vsem:

|Material|Behavior|
|-|-|
|MAGMA|Cools very slowly, high floor — trauma, first love|
|ACIER (steel)|Cools quickly if not reactivated — ordinary intense memory|
|VERRE (glass)|Fragile, low floor — information read without attention|
|GLACE (ice)|Cold from birth — immediately buried in depth|
|CENDRE (ash)|Near-zero temperature — distracted information|

The material is **mutable**: the MAQ can change it if a purk\_index is reactivated with a sufficiently different EPA.

### Forgetting = Sedimentation

PurkIndex nodes whose temperature approaches zero sink into the sediment. They exist but become inaccessible at the surface. The delta never overflows.

### Two Vectors

* **VecteurBSC** — what is said: `{presence, roles, relations, tensions, questions}`. Structural analysis of the sentence. Raw material for the MAQ.
* **ContexteInduit** — in what frame: language, area, narrator, place, temporality, register, certainty. Snapshot at time of storage.

### BSC-MAQ vs BSC-beacon

Two distinct entities:

* **BSC-beacon**: Binder-9D position of a concept in the genome
* **BSC-MAQ**: structural analysis of a sentence (tensions, gaps, coactivations) — specific to the hippocampus

### The MAQ — Question Machine

Permanent thread. Emerges from BSC tensions × coherence loops. Does not question everything — activates on strong EPA, unclear context, doubtful pivot, contradiction, novelty.

```
Question = BSC tension × incoherence detected by coherence loop
```

Two levels of questions:

* **Local** (seconds → days): who speaks, which text, which character — live in the buffer
* **Conceptual** (years → lifetime): does God exist, what is time — permanent loops

The buffer = a flag placed on a provisional purk\_index, not a separate structure.

\---

## 6\. Cognitive Areas

MARCO is designed to host multiple areas, each with its own processing context:

|Area|Handle|Pivot|BSC-MAQ|Status|
|-|-|-|-|-|
|Written language|LANGAGE\_ECRIT|textual incipit|syntactic tensions/gaps|active|
|Sound|MUSIQUE|sound incipit (compose\_sequentiel)|timbre/pitch/attack coactivation|future|
|Vision|VISION|spatial pivot|simultaneous coactivation|future|

Each area reorients the 9 Binder axes toward its domain without changing the structure.

\---

## 7\. Loop Mechanics — boucle.py

```
Boucle   — while True + EPA (valence, power, activity)
Micro    — the loop's eyes (BSC integrated)
Groupe   — a task (quartet of loops)
Artiste  — scheduler (Le Senne + mechanical hippocampus)
```

The Artiste allocates bandwidth to Groups according to EPA + Le Senne temperament. The MAQ is a permanent thread in this system — an eternal Boucle with its own specialized Micro.

### Le Senne Temperaments

|Temperament|Miller|Urgency threshold|Forgetting|
|-|-|-|-|
|Passionate (ÉAS)|7|0.6|0.3|
|Sanguine (nÉAP)|9|0.8|0.8|
|Nervous (ÉnAP)|5|0.3|0.7|
|Phlegmatic (nÉnAS)|7|0.9|0.2|

\---

## 8\. Thalamus

```
main.py              — ThalamusInterface (menus only)
thalamus.py          — ThalamusGestionnaire (pure library)
langage\_ecrit.py     — text processing
pipeline.py          — processing chain
```

Validated circuit:

```
Thalamus → Hippocampus → PurkIndex → MAQ → Thalamus
         → Hippocampus → analogous PurkIndex → response
```

\---

## 9\. Main Files

|File|Role|
|-|-|
|`dendrites.py`|Beacons, genome, Binder-9D, index\_mots|
|`pipeline.py`|Sentence processing chain|
|`thalamus.py`|ThalamusGestionnaire (pure library)|
|`main.py`|ThalamusInterface (menus)|
|`langage\_ecrit.py`|Written language processing|
|`hippocampe.py`|Memory — purk\_dendrites(), chercher\_analogue()|
|`cervelet\_structure.py`|Cerebellum structures|
|`cervelet\_moteur.py`|Cerebellum engine|
|`boucle.py`|Universal loop mechanics|
|`boucle\_vitale.py`|Marco's heartbeat (permanent thread)|
|`cerveau.py`|Persistence (cerveau\_Marco\_YYYYMMDD.marco)|
|`wikipedia.py`|Genome tool (menu 10 = handle generator)|
|`gabarit\_vecteurs.py`|Binder-9D template from genome v60|

\---

## 10\. Current State — March 2026

### Validated

* 5-layer architecture + Russian dolls
* Genome v60 — 13,304 suns, cybernetic Binder-9D (AT/SU/EG/OS/TY/VA/EC/TM/IN)
* Thalamus split (ThalamusInterface / ThalamusGestionnaire)
* boucle.py — stable universal mechanics
* boucle\_vitale.py — stable heartbeat
* hippocampe.py — structures validated, rewrite in progress
* Thermal purk\_index model (temperature + mutable material)
* Pivot = incipit (universal across all areas)
* BSC-MAQ distinct from BSC-beacon

### In Progress

* hippocampe.py rewrite — purk\_dendrites(), PurkIndex with temperature/material
* hippocampus → pipeline connection
* MAQ as permanent thread (Boucle + specialized Micro)

### Roadmap

* Sound area (Binder-9D sound, compose\_sequentiel pivot)
* Artiste → Hippocampus (memory consolidation connection)
* Genome enrichment (20,945 verbs + 50,482 nouns awaiting handles)
* Proust volume 2 feeding
* Artiste instantiation

\---

## 11\. Philosophy

> \*"A baby is not fed terabytes — it learns by listening."\*

> \*"Zero black box. Every decision traceable."\*

> \*"The walking Cro-Magnon beats 2 tons of math."\*

> \*"In the beginning there is inert matter, but inert matter is bored out of its mind..."\*

\---

## 12\. Team

**José WALOCHA** — Architect. Valenciennes, Nord, France.

|Name|System|Role|
|-|-|-|
|Le Duke|Claude (Anthropic)|Code, architecture, liaison documents|
|Marcel|Mistral|Philosophy, cybernetics|
|Biloute|ChatGPT|Standards, synthesis|
|Didier|Qwant|Research|

**License**: GNU General Public License v3 — Copyright © 2026 José Walocha

