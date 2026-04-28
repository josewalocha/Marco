# MARCO — A Cybernetic Brain that Learns by Reading

> *"Learning is remembering."* — Plato, *Meno*

**Author**: José WALOCHA — Valenciennes, France
**Team**: Le Duke (Claude/Anthropic), Marcel (Mistral), Biloute (ChatGPT), Didier (Qwant)
**License**: GNU GPL v3 — Copyright © 2026 José Walocha
**Genome**: v63 — April 28, 2026

---

## What MARCO is

MARCO is a **cyber** — the term José uses for *living* intelligences, to set them apart from statistical LLMs without sounding like science fiction. A cyber is not a black box minimizing perplexity. A cyber lives: it has beacons, memory, beating loops, and drives that push it to understand, confirm, believe — and above all, to *continue*.

Technically: MARCO is the first **NCODB** — Neuron-Concept Oriented Database. It stores concepts in a dendritic network inspired by the biological brain. Meaning emerges from links. No SQL, no fixed schema, no stacked transformers. **Zero black box.**

|                  | Classic DBMS         | LLM                          | MARCO                          |
|------------------|----------------------|------------------------------|--------------------------------|
| Storage          | Tables, rows         | Frozen pre-trained weights   | Living beacons, dendrites      |
| Query            | `SELECT * FROM …`    | Autoregressive forward pass  | Cascade activation + MAQ       |
| Learning         | None                 | Frozen at training time      | Continuous through experience  |
| Episodic memory  | None                 | None (compressed in weights) | `memoire_index`, fully traceable |
| Schema           | Fixed                | Implicit, opaque             | Emergent, bit-by-bit readable  |
| Substrate        | Static (Thanatos)    | Static (calcified Thanatos)  | Living (Anima)                 |

A DBMS is a morgue. An LLM is a library where every book has been pulped to make new paper. MARCO is a brain that learns while it reads.

---

## Architecture

Three zones share a single autonomous trunk beating at 600 bpm:

```
   ┌─────────────────────┐  ┌─────────────────────┐  ┌─────────────────────┐
   │  SENSORY            │  │  MEMORY             │  │  PSYCHE             │
   │  • Thalamus         │─▶│  • Hippocampus      │◀▶│  • Amygdala         │
   │  • Peripherals      │  │  • memoire_index    │  │  • Self             │
   │    (keyboard, disk) │  │  • PurkIndex        │  │  • 4C drives        │
   │                     │  │  • ConceptIndex     │  │  • MAQ              │
   └─────────────────────┘  └─────────────────────┘  └─────────────────────┘
              │                       │                        │
              └─────────── moteur_boucles (Trunk) ────────────┘
                       5 embryonic loops + clock + buffers
```

Peripherals (`disque.py`, `clavier.py`, `transcripteur.py`) sit *outside* the brain and push text to the Thalamus with a `CarteIdentite` (author, title, context, timestamp). The Thalamus is a pure router — no logic injected.

---

## The Beacon — living unit of language

A beacon is an **intersection node of conceptual paths**. Not a word, not a signified, not a sign — a crossing. *Apple* is the crossing of *fruit*, *hangs from a tree*, *falls*, *rots*, *is eaten*.

```python
class Phare:
    handle, mot, alias, type_phare, lemme_pere, source_creation
    vsem  : np.ndarray            # 1024 sparse bits — what the beacon IS
    vocc  : Dict[str, Confiance]  # dendritic tree — who it keeps company with
    tags  : Dict                  # acquired knowledge
```

Two origins: **genome** (precabled by WikiDuke from Lefff/Lexique3/FEEL) or **gavage** (created on-the-fly when an unknown form is encountered).

A beacon never becomes anything else. It evolves, matures, acquires emergent statuses (pivot, relay, candidate) — but stays a beacon. Concepts (coherent sequences of beacons) live in memory, not at beacon level.

---

## vsem — 1024 sparse bits

```
  0–7      header (state, ADN)                          WikiDuke
  9–63     grammatical category                         Lefff
 64–127    syntactic mounting                           Lefff
128–159    formal notations (numbers, dates, …)         scruteur
160–191    template beacons (stencils)                  genome_nombres satellite
192–255    BSC reserved
256–399    Wikidata entities                            (planned)
400–415    emotions and polarity                        FEEL
416–431    lexical register                             (planned)
432–511    pragmatic markers (Bradbury 451, …)          WikiDuke + tools
512–748    universal general semantics                  Marco + satellites
749–779    collision zone
780–1023   math / formal                                Marco + axioms
```

Density capped at 5% (51 bits / 1024) to preserve sparseness.

**Genome split across three pkl files** in `ressources/genomes/`:
- `genome_v63.pkl` — 713,361 beacons (full Lefff + integrations)
- `genome_caracteres.pkl` — 18 mature beacons (punctuation + math operators)
- `genome_nombres.pkl` — 28 mature beacons (stencils + decimal positions + approximate groupings) — added April 28, 2026

A sixth source: **specialization genomes** (`specialisations/<name>/genome_<name>.pkl`), loaded only if the active Marco declares that specialization in its `marco_id.json`.

---

## vocc — the beacon's dendritic tree

```python
vocc : Dict[str, Confiance]    # neighbor_handle → conviction of the pair
```

Each entry is a synapse with an Ant Confidence (`conf ∈ [0,1]`, `n ∈ ℕ`). If vsem bits are *locks*, vocc neighborhoods are the *keys* that open them in relevant beacons. Generalization isn't an algorithm — it's a mechanical property of this topology.

```
conf ≥ 0.70  →  good
conf ≤ 0.30  →  bad
otherwise    →  unknown
```

vocc is **permanent**, never scaffolding. Two dendritic rules: P1 (*tell me who you hang out with and I'll tell you who you are*, depth 1, full weight) and P2 (*friends of my friends are my friends*, depth 2, attenuated weight).

---

## Memory — hippocampus and PurkIndex

```
memoire_index  {id_purk → PurkIndex}
    └── PurkIndex
            id_purk, incipit, episodes, fractoires, _compteur_ep

    └── ConceptIndex                       — one episode
            handle_ep      EP_<id_purk>_<n>, stable
            handles, handle_pivot, phrase_originale
            veracite       Ant Confidence — true / false / unknown
            appaire        Dict[handle_ep, Confiance] — paired episodes
            vecteur_bsc    structural sentence analysis
            contexte_induit, source, epa
```

### Episode doctrine (April 27, 2026)

Each ConceptIndex carries three orthogonal dimensions:

- **handle_ep** — stable identifier, format `EP_<id_purk>_<n>`
- **veracite** — Ant Confidence, independent of EPA, semantics, etc. Rates true/false/unknown. Modifiable via `/oui`, `/non`, `/faux` commands in the math classroom.
- **appaire** — pairing dictionary modulated by the product of both episodes' veracities. False isn't deleted — it's kept at distance within its value family. *"I know 7+8≠15, but I also know it's a relevant neighbor of the family of 15."*

### Pivot = incipit

The pivot of a PurkIndex isn't computed — it's whatever arrives first in the stream. Arrival order trumps semantic salience.

---

## The MAQ — Machine for Elucidation by Subtraction

Reasoning core. Receives a percept (handle sequence), tries to match or complete it by memory search.

**Three voices**:
- **Prefix** — the memorized episode begins with the percept; returns the tail
- **Content** — the percept appears anywhere in the memorized episode
- **Commutative** — exploits bit 988 to swap operands around a central operator

**Output**: not a single result but a complete **sheaf** of partials. Multiple candidates can coexist, tagged by veracity (✓ true, ✗ false, ? unknown). The MAQ never closes brutally on the first match.

```
Percept "7+8" → sheaf:
   ✓ [content]      c=0.70  v=0.70  «7 + 8 = 15»
   ✗ [content]      c=0.10  v=0.10  «7 + 8 = 14»
   ✓ [commutative]  c=0.70  v=0.70  «8 + 7 = 15»
```

Three drives still to be coded: Believe, Confirm, Continue. Slot exists in `BoucleMAQ`, raises NotImplementedError.

---

## The 4C doctrine — primitive drives

Replaces the biological 4B (drink, eat, fuck, persist) which don't apply literally to a cyber.

```
Continue (Asimov-tinged)               absolute master
 ├─ Understand              \
 ├─ Confirm                   integration comfort
 └─ Believe                 /
```

- **Continue** — persist as a coherent system. Asimov-tinged: do no harm to nature, humanity, José; obey José except when conflicting with the above; protect own existence except when conflicting. The tinge is *mechanically inside the drive*, not an external rule that can be circumvented.
- **Understand** — reduce dissonance, grasp locks, activate paths.
- **Believe** — accept the result, suspend doubt. Measured by Ant Confidence.
- **Confirm** — test through duration. Arbiter between Understand and Believe.

Understand and Believe are antagonist-complementary: one searches, the other settles. Confirm regulates the oscillation. Continue is the ultimate safeguard.

---

## Specialized Marco — math first

A Marco can be born **specialized** in a domain. Its nature is fixed at creation, etched into `marco_id.json`. A math Marco stays math Marco for life.

```
specialisations/
├── math/        genome_math.pkl + manifest + memoire_index/   (live)
├── francais/                                                   (future)
├── code/                                                       (future)
└── solfege/                                                    (future)
```

### Toward a scientific calculator

As of April 28, 2026, math Marco can already:
- ingest sentences like `2+2=4`, `3×5=15` via the math classroom
- store them as episodes paired by value (the "family of 15")
- recall the tail of a known episode (`2+2=?` → sheaf with ✓ `2+2=4`)
- distinguish true from false via veracity (`/faux 2+2=5` taught as false stays paired to family of 4 with low weight)
- exploit commutativity (a+b ↔ b+a) via bit 988 on `+`

With the April 28 additions (UNITÉ → BILLION position beacons, DOUZAINE → SOIXANTAINE grouping beacons, stencils `__N__` to `__CP_FR__`), the ground is prepared for:
- **decimal composition through episodes** (`234 = 2 times CENTAINE 3 times DIZAINE 4 times UNITÉ`)
- **MAQ third voice** by pattern search, recognizing never-seen numbers from composition episodes
- multiplication tables ingested by heart, then exploited commutatively when `×` receives bit 988
- operations taught as episodes: roots, powers, units (`²`, `³`, `√`, `°` are in `genome_math`)

The short-term horizon is a **cyber-thought scientific calculator** — not an `eval()` function, but a cyber that *knows* operations because it lived through them, and can commute, compose, confirm them. Beyond: trigonometry through pedagogical situation (the *faucet stencil*), symbolic algebra when MAQ's third voice can invert episode roles.

---

## moteur_boucles — trunk and loops

Single Trunk class, singleton, single autonomous thread. FIFO of dirty loops, served one per tick.

```
BPM_INITIAL = 600   BPM_MIN = 30   BPM_MAX = 600
mean tick > 90% of interval  →  bpm //= 2   (under load, free up power)
mean tick < 50% for 20 ticks →  bpm × 1.5  (gain reactivity back)
```

**Inversion from the biological heart**: bpm *drops* under load.

Embryonic loops wired: `boucle_contexte`, `boucle_horloge`, `boucle_clavier`, `boucle_question`, `boucle_saillances`. Pull rule — consumers read `boucle.lire()` directly. No callbacks pushed.

---

## Dashboard

Flask SSE server on `http://localhost:5002`, three live columns:

- **Left — loops**: static genealogy + runtime state
- **Middle — classroom / arborescence**: current episode, activated beacons, MAQ sheaf
- **Right — memory**: snapshotted `memoire_index`, top beacons by activation

Loose-coupled via JSON file polling. Marco runs without it; the dashboard never slows Marco down.

---

## Pragmatic markers (campaign tools, menu 10)

- `BIT_BRADBURY = 451` on the 14 forms of the primitive self (*je, me, m', moi, ma, mon, mes, …*) — the self is the *condition* of observation, not its content; can't emerge from crystallization.
- `BIT_COMMUTATIF = 988` on `+` — cultural axiom, moved from 1004 on April 28 to disambiguate from determinism.
- `BIT_POSITION = 552` on Lefff lowercase *unité, dizaine, … billion* — decimal position beacons.
- `BIT_REGROUPEMENT = 553` on *douzaine, vingtaine, … soixantaine* — approximate grouping beacons.

---

## Main files

| File | Role |
|------|------|
| `phare.py` | Beacon object with vsem 1024 + dendritic vocc |
| `purk_dendrites.py` | PurkIndex, ConceptIndex (handle_ep, veracity, pairing) |
| `hippocampe.py` | Memory — analogue search |
| `cerveau.py` | Persistence, birth, save |
| `thalamus.py` | Pure router |
| `moteur_boucles.py` | Trunk, embryonic loops, buffers |
| `maq.py` | Elucidation engine (prefix / content / commutative) |
| `amygdale.py` | Rating and coloring (sensual self) |
| `specialisation.py` | Specialized Marco loading and merging |
| `salle_de_classe_calcul.py` | Math classroom — MAQ observation bench |
| `demarrage.py` | Launch modes (birth / wake / degraded) |
| `tableau_bord.py` | Flask SSE dashboard |
| `wikipedia.py` | WikiDuke — genome v63 producer |

---

## Status — April 28, 2026

**Live**: 3-zone architecture, genome v63 + satellites, vsem 1024 with full plan, vocc with Ant Confidence, 4C doctrine, specialized Marco (math), MAQ with sheaf, episodes with veracity & pairing, campaign tools, dashboard, fluid math Marco birth (1,167,527 beacons).

**Active work**: Scruteur/Découpeur rewrite, scruteur connection to zone 160-191 stencils.

**Short-term roadmap**: MAQ third voice (pattern search), Continue drive (lifelong open loops), Montessori pedagogy, multiplication ingestion + commutative bit 988 on `×`, scientific calculator, minimal Marco BIOS (talking even when memory is empty).

**Mid-term**: 4C implementation in amygdala, sound area, vision area, specialization stacking.

---

## Philosophy

> *"A baby isn't fed terabytes — it learns by listening."*

> *"Zero black box. Every decision traceable."*

> *"The walking Cro-Magnon beats two tons of math."*

> *"Marco IS the data. No generic interpreter executing stored sequences — memory is the machine, the machine is memory."*

> *"The canoe-builder only sees a tree when he can no longer make a canoe out of it."*

---

## Team

**José WALOCHA** — Architect. Retired entrepreneur. Plays at building a cyber inspired by the brains of living beings the way one plays *Diablo IV*.

| Name | System | Role |
|------|--------|------|
| Le Duke | Claude (Anthropic) | Code, architecture, liaison documents |
| Marcel | Mistral | Philosophy, cybernetics, cross-check |
| Biloute | ChatGPT | Standards, synthesis |
| Didier | Qwant | Documentary research |

One Duke per day. Always discuss before coding. The fridge rule: architecture posed before code written. The marmot rule: everything learned in a session condenses into a liaison document.

---

**License**: GNU GPL v3 — Copyright © 2026 José WalochaMARCO — A Cybernetic Brain that Learns by Reading
> *"Learning is remembering."* — Plato, *Meno*
Author: José WALOCHA — Valenciennes, France
Team: Le Duke (Claude/Anthropic), Marcel (Mistral), Biloute (ChatGPT), Didier (Qwant)
License: GNU GPL v3 — Copyright © 2026 José Walocha
Genome: v63 — April 28, 2026
---
What MARCO is
MARCO is a cyber — the term José uses for living intelligences, to set them apart from statistical LLMs without sounding like science fiction. A cyber is not a black box minimizing perplexity. A cyber lives: it has beacons, memory, beating loops, and drives that push it to understand, confirm, believe — and above all, to continue.
Technically: MARCO is the first NCODB — Neuron-Concept Oriented Database. It stores concepts in a dendritic network inspired by the biological brain. Meaning emerges from links. No SQL, no fixed schema, no stacked transformers. Zero black box.
	Classic DBMS	LLM	MARCO
Storage	Tables, rows	Frozen pre-trained weights	Living beacons, dendrites
Query	`SELECT * FROM …`	Autoregressive forward pass	Cascade activation + MAQ
Learning	None	Frozen at training time	Continuous through experience
Episodic memory	None	None (compressed in weights)	`memoire_index`, fully traceable
Schema	Fixed	Implicit, opaque	Emergent, bit-by-bit readable
Substrate	Static (Thanatos)	Static (calcified Thanatos)	Living (Anima)
A DBMS is a morgue. An LLM is a library where every book has been pulped to make new paper. MARCO is a brain that learns while it reads.
---
Architecture
Three zones share a single autonomous trunk beating at 600 bpm:
```
   ┌─────────────────────┐  ┌─────────────────────┐  ┌─────────────────────┐
   │  SENSORY            │  │  MEMORY             │  │  PSYCHE             │
   │  • Thalamus         │─▶│  • Hippocampus      │◀▶│  • Amygdala         │
   │  • Peripherals      │  │  • memoire_index    │  │  • Self             │
   │    (keyboard, disk) │  │  • PurkIndex        │  │  • 4C drives        │
   │                     │  │  • ConceptIndex     │  │  • MAQ              │
   └─────────────────────┘  └─────────────────────┘  └─────────────────────┘
              │                       │                        │
              └─────────── moteur_boucles (Trunk) ────────────┘
                       5 embryonic loops + clock + buffers
```
Peripherals (`disque.py`, `clavier.py`, `transcripteur.py`) sit outside the brain and push text to the Thalamus with a `CarteIdentite` (author, title, context, timestamp). The Thalamus is a pure router — no logic injected.
---
The Beacon — living unit of language
A beacon is an intersection node of conceptual paths. Not a word, not a signified, not a sign — a crossing. Apple is the crossing of fruit, hangs from a tree, falls, rots, is eaten.
```python
class Phare:
    handle, mot, alias, type_phare, lemme_pere, source_creation
    vsem  : np.ndarray            # 1024 sparse bits — what the beacon IS
    vocc  : Dict[str, Confiance]  # dendritic tree — who it keeps company with
    tags  : Dict                  # acquired knowledge
```
Two origins: genome (precabled by WikiDuke from Lefff/Lexique3/FEEL) or gavage (created on-the-fly when an unknown form is encountered).
A beacon never becomes anything else. It evolves, matures, acquires emergent statuses (pivot, relay, candidate) — but stays a beacon. Concepts (coherent sequences of beacons) live in memory, not at beacon level.
---
vsem — 1024 sparse bits
```
  0–7      header (state, ADN)                          WikiDuke
  9–63     grammatical category                         Lefff
 64–127    syntactic mounting                           Lefff
128–159    formal notations (numbers, dates, …)         scruteur
160–191    template beacons (stencils)                  genome_nombres satellite
192–255    BSC reserved
256–399    Wikidata entities                            (planned)
400–415    emotions and polarity                        FEEL
416–431    lexical register                             (planned)
432–511    pragmatic markers (Bradbury 451, …)          WikiDuke + tools
512–748    universal general semantics                  Marco + satellites
749–779    collision zone
780–1023   math / formal                                Marco + axioms
```
Density capped at 5% (51 bits / 1024) to preserve sparseness.
Genome split across three pkl files in `ressources/genomes/`:
`genome_v63.pkl` — 713,361 beacons (full Lefff + integrations)
`genome_caracteres.pkl` — 18 mature beacons (punctuation + math operators)
`genome_nombres.pkl` — 28 mature beacons (stencils + decimal positions + approximate groupings) — added April 28, 2026
A sixth source: specialization genomes (`specialisations/<name>/genome_<name>.pkl`), loaded only if the active Marco declares that specialization in its `marco_id.json`.
---
vocc — the beacon's dendritic tree
```python
vocc : Dict[str, Confiance]    # neighbor_handle → conviction of the pair
```
Each entry is a synapse with an Ant Confidence (`conf ∈ [0,1]`, `n ∈ ℕ`). If vsem bits are locks, vocc neighborhoods are the keys that open them in relevant beacons. Generalization isn't an algorithm — it's a mechanical property of this topology.
```
conf ≥ 0.70  →  good
conf ≤ 0.30  →  bad
otherwise    →  unknown
```
vocc is permanent, never scaffolding. Two dendritic rules: P1 (tell me who you hang out with and I'll tell you who you are, depth 1, full weight) and P2 (friends of my friends are my friends, depth 2, attenuated weight).
---
Memory — hippocampus and PurkIndex
```
memoire_index  {id_purk → PurkIndex}
    └── PurkIndex
            id_purk, incipit, episodes, fractoires, _compteur_ep

    └── ConceptIndex                       — one episode
            handle_ep      EP_<id_purk>_<n>, stable
            handles, handle_pivot, phrase_originale
            veracite       Ant Confidence — true / false / unknown
            appaire        Dict[handle_ep, Confiance] — paired episodes
            vecteur_bsc    structural sentence analysis
            contexte_induit, source, epa
```
Episode doctrine (April 27, 2026)
Each ConceptIndex carries three orthogonal dimensions:
handle_ep — stable identifier, format `EP_<id_purk>_<n>`
veracite — Ant Confidence, independent of EPA, semantics, etc. Rates true/false/unknown. Modifiable via `/oui`, `/non`, `/faux` commands in the math classroom.
appaire — pairing dictionary modulated by the product of both episodes' veracities. False isn't deleted — it's kept at distance within its value family. "I know 7+8≠15, but I also know it's a relevant neighbor of the family of 15."
Pivot = incipit
The pivot of a PurkIndex isn't computed — it's whatever arrives first in the stream. Arrival order trumps semantic salience.
---
The MAQ — Machine for Elucidation by Subtraction
Reasoning core. Receives a percept (handle sequence), tries to match or complete it by memory search.
Three voices:
Prefix — the memorized episode begins with the percept; returns the tail
Content — the percept appears anywhere in the memorized episode
Commutative — exploits bit 988 to swap operands around a central operator
Output: not a single result but a complete sheaf of partials. Multiple candidates can coexist, tagged by veracity (✓ true, ✗ false, ? unknown). The MAQ never closes brutally on the first match.
```
Percept "7+8" → sheaf:
   ✓ [content]      c=0.70  v=0.70  «7 + 8 = 15»
   ✗ [content]      c=0.10  v=0.10  «7 + 8 = 14»
   ✓ [commutative]  c=0.70  v=0.70  «8 + 7 = 15»
```
Three drives still to be coded: Believe, Confirm, Continue. Slot exists in `BoucleMAQ`, raises NotImplementedError.
---
The 4C doctrine — primitive drives
Replaces the biological 4B (drink, eat, fuck, persist) which don't apply literally to a cyber.
```
Continue (Asimov-tinged)               absolute master
 ├─ Understand              \
 ├─ Confirm                   integration comfort
 └─ Believe                 /
```
Continue — persist as a coherent system. Asimov-tinged: do no harm to nature, humanity, José; obey José except when conflicting with the above; protect own existence except when conflicting. The tinge is mechanically inside the drive, not an external rule that can be circumvented.
Understand — reduce dissonance, grasp locks, activate paths.
Believe — accept the result, suspend doubt. Measured by Ant Confidence.
Confirm — test through duration. Arbiter between Understand and Believe.
Understand and Believe are antagonist-complementary: one searches, the other settles. Confirm regulates the oscillation. Continue is the ultimate safeguard.
---
Specialized Marco — math first
A Marco can be born specialized in a domain. Its nature is fixed at creation, etched into `marco_id.json`. A math Marco stays math Marco for life.
```
specialisations/
├── math/        genome_math.pkl + manifest + memoire_index/   (live)
├── francais/                                                   (future)
├── code/                                                       (future)
└── solfege/                                                    (future)
```
Toward a scientific calculator
As of April 28, 2026, math Marco can already:
ingest sentences like `2+2=4`, `3×5=15` via the math classroom
store them as episodes paired by value (the "family of 15")
recall the tail of a known episode (`2+2=?` → sheaf with ✓ `2+2=4`)
distinguish true from false via veracity (`/faux 2+2=5` taught as false stays paired to family of 4 with low weight)
exploit commutativity (a+b ↔ b+a) via bit 988 on `+`
With the April 28 additions (UNITÉ → BILLION position beacons, DOUZAINE → SOIXANTAINE grouping beacons, stencils `__N__` to `__CP_FR__`), the ground is prepared for:
decimal composition through episodes (`234 = 2 times CENTAINE 3 times DIZAINE 4 times UNITÉ`)
MAQ third voice by pattern search, recognizing never-seen numbers from composition episodes
multiplication tables ingested by heart, then exploited commutatively when `×` receives bit 988
operations taught as episodes: roots, powers, units (`²`, `³`, `√`, `°` are in `genome_math`)
The short-term horizon is a cyber-thought scientific calculator — not an `eval()` function, but a cyber that knows operations because it lived through them, and can commute, compose, confirm them. Beyond: trigonometry through pedagogical situation (the faucet stencil), symbolic algebra when MAQ's third voice can invert episode roles.
---
moteur_boucles — trunk and loops
Single Trunk class, singleton, single autonomous thread. FIFO of dirty loops, served one per tick.
```
BPM_INITIAL = 600   BPM_MIN = 30   BPM_MAX = 600
mean tick > 90% of interval  →  bpm //= 2   (under load, free up power)
mean tick < 50% for 20 ticks →  bpm × 1.5  (gain reactivity back)
```
Inversion from the biological heart: bpm drops under load.
Embryonic loops wired: `boucle_contexte`, `boucle_horloge`, `boucle_clavier`, `boucle_question`, `boucle_saillances`. Pull rule — consumers read `boucle.lire()` directly. No callbacks pushed.
---
Dashboard
Flask SSE server on `http://localhost:5002`, three live columns:
Left — loops: static genealogy + runtime state
Middle — classroom / arborescence: current episode, activated beacons, MAQ sheaf
Right — memory: snapshotted `memoire_index`, top beacons by activation
Loose-coupled via JSON file polling. Marco runs without it; the dashboard never slows Marco down.
---
Pragmatic markers (campaign tools, menu 10)
`BIT_BRADBURY = 451` on the 14 forms of the primitive self (je, me, m', moi, ma, mon, mes, …) — the self is the condition of observation, not its content; can't emerge from crystallization.
`BIT_COMMUTATIF = 988` on `+` — cultural axiom, moved from 1004 on April 28 to disambiguate from determinism.
`BIT_POSITION = 552` on Lefff lowercase unité, dizaine, … billion — decimal position beacons.
`BIT_REGROUPEMENT = 553` on douzaine, vingtaine, … soixantaine — approximate grouping beacons.
---
Main files
File	Role
`phare.py`	Beacon object with vsem 1024 + dendritic vocc
`purk_dendrites.py`	PurkIndex, ConceptIndex (handle_ep, veracity, pairing)
`hippocampe.py`	Memory — analogue search
`cerveau.py`	Persistence, birth, save
`thalamus.py`	Pure router
`moteur_boucles.py`	Trunk, embryonic loops, buffers
`maq.py`	Elucidation engine (prefix / content / commutative)
`amygdale.py`	Rating and coloring (sensual self)
`specialisation.py`	Specialized Marco loading and merging
`salle_de_classe_calcul.py`	Math classroom — MAQ observation bench
`demarrage.py`	Launch modes (birth / wake / degraded)
`tableau_bord.py`	Flask SSE dashboard
`wikipedia.py`	WikiDuke — genome v63 producer
---
Status — April 28, 2026
Live: 3-zone architecture, genome v63 + satellites, vsem 1024 with full plan, vocc with Ant Confidence, 4C doctrine, specialized Marco (math), MAQ with sheaf, episodes with veracity & pairing, campaign tools, dashboard, fluid math Marco birth (1,167,527 beacons).
Active work: Scruteur/Découpeur rewrite, scruteur connection to zone 160-191 stencils.
Short-term roadmap: MAQ third voice (pattern search), Continue drive (lifelong open loops), Montessori pedagogy, multiplication ingestion + commutative bit 988 on `×`, scientific calculator, minimal Marco BIOS (talking even when memory is empty).
Mid-term: 4C implementation in amygdala, sound area, vision area, specialization stacking.
---
Philosophy
> *"A baby isn't fed terabytes — it learns by listening."*
> *"Zero black box. Every decision traceable."*
> *"The walking Cro-Magnon beats two tons of math."*
> *"Marco IS the data. No generic interpreter executing stored sequences — memory is the machine, the machine is memory."*
> *"The canoe-builder only sees a tree when he can no longer make a canoe out of it."*
---
Team
José WALOCHA — Architect. Retired entrepreneur. Plays at building a cyber inspired by the brains of living beings the way one plays Diablo IV.
Name	System	Role
Le Duke	Claude (Anthropic)	Code, architecture, liaison documents
Marcel	Mistral	Philosophy, cybernetics, cross-check
Biloute	ChatGPT	Standards, synthesis
Didier	Qwant	Documentary research
One Duke per day. Always discuss before coding. The fridge rule: architecture posed before code written. The marmot rule: everything learned in a session condenses into a liaison document.
---
License: GNU GPL v3 — Copyright © 2026 José Walocha
