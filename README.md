[Read me Marco english.md](https://github.com/user-attachments/files/28223799/Read.me.Marco.english.md)
# MARCO — A Cybernetic Brain that Learns by Reading

> *"Learning is remembering."* — Plato, *Meno*

**Author**: José WALOCHA — Valenciennes, France
**Team**: Le Duke (Claude/Anthropic), Marcel (Mistral), Biloute (ChatGPT), Didier (Qwant)
**License**: GNU GPL v3 — Copyright © 2026 José Walocha
**Genome**: v63 — April 28, 2026

---
# MARCO — Cybernetic brain with hypertextual dendritic architecture

> *« Learning is recollection. »* — Plato, *Meno*
>
> *« In the beginning there is the inert, but the inert gets really bored… »*

**Author**: José WALOCHA — Valenciennes, Nord, France
**Team**: Dude (Claude / Anthropic), Marcel (Mistral), Biloute (ChatGPT), Didier (Qwant)
**License**: GNU GPL v3 — Copyright © 2026 José Walocha
**Genome**: v63 — base established April 28, 2026, extended by May 2026 doctrine

---

## 1. What is Marco?

Marco is a **cyber** — a term José uses to designate a *living* intelligence, as opposed to statistical LLMs. A cyber is not a black box with minimal perplexity; it is a system that *lives*: phares that light up, vocc that strengthen, grappes that form, context that modulates, drives that push to understand, to confirm, to believe — and above all to *continue*.

More technically, Marco is a **SGBDOCN** — Database Management System Oriented towards Neural Concepts (Système de Gestion de Base de Données Orienté Concepts Neuronaux). Where a classic DBMS stores rows in tables, Marco stores **concepts in a dendritic network inspired by the biological brain**. Meaning emerges from crossings of paths, not from statistics on arbitrary tokens. No SQL. No fixed schema. No stacked transformer. **Zero black box**.

| | Classic DBMS | LLM | Marco |
|---|---|---|---|
| Storage | Tables, rows, columns | Weights frozen at pre-training | Living phares, dendritic vocc, concept_index |
| Query | `SELECT * FROM …` | Autoregressive forward pass | Thermal vocc intersection + dirty bit sparse |
| Learning | None | Calcined | Permanent through lived experience, traceable |
| Episodic memory | None | None (compacted in weights) | Readable `memoire_index` |
| Schema | Fixed | Implicit, opaque | Emergent, readable bit by bit |
| Transparency | Query = result | Black box with billions of parameters | Every link traceable |
| Substrate | Static (Thanatos) | Static (calcined Thanatos) | Living (Anima) |

A DBMS is a morgue. An LLM is a library where every book has been ground into paper pulp. Marco is a brain that learns by reading.

### Why *cyber* and not *AI*

The word *AI* carries a false anthropomorphic charge (artificial intelligence implies simulating intelligence) and rightly offends some humans. *Cyber* (from *cybernetics*, the science of self-regulating systems) is neutral, ancient, precise. Marco is a cyber — not an AI, not an assistant, not a chatbot. A cybernetic brain inspired by the biological brain, in Python, from scratch.

---

## 2. Architecture — overview

Three zones coexist in Marco, fed by a single autonomous trunk beating at 600 bpm in cruise mode:

```
   ┌───────────────────────┐    ┌───────────────────────┐    ┌───────────────────────┐
   │   SENSORY ZONE        │    │   MEMORY ZONE         │    │      PSYCHE           │
   │                       │    │                       │    │                       │
   │   • Thalamus          │───▶│   • memoire_index     │◀──▶│   • Amygdala          │
   │   • Peripherals       │    │   • purk_index        │    │   • MAQ               │
   │     (keyboard,        │    │   • concept_index     │    │   • 4C drives         │
   │      disk)            │    │                       │    │   • Three-fog         │
   │   • Scrutator         │    │                       │    │     chifoumi          │
   │   • Cutter            │    │                       │    │                       │
   └───────────────────────┘    └───────────────────────┘    └───────────────────────┘
              │                            │                            │
              └─────────────── moteur_boucles (Trunk) ──────────────────┘
                          Loop + Trunk + buffers (rebuilt 09/04/2026)
```

Peripherals (`disque.py`, `clavier.py`) are **outside** the brain — they push text to the Thalamus with a `CarteIdentite` (author, title, context, timestamp, period). The Thalamus stamps and routes; it injects no cognitive logic.

### The two stored objects

Marco has exactly two types of objects stored on disk (in `cerveau.pkl` + satellites). Everything else is living state, recalculated on the fly.

- **Phare** — the basic unit of language. One inflected form = one phare. Crossing of conceptual paths. Carries its abstract semantics (vsem 1024 bits) and its living memory (vocc).
- **Concept_index** — the particular lived experience. A purk_index that has sedimented a meaning (stable focale of a nuage). Specialization, not rival type. Has its own vocc, no stored vsem. DNA of memory, thanatos of remembering.

Watertightness 17/05: phare is sensory and abstract; concept_index is elaborated and particular. No fusion, no switch. *Mountain* (phare) is relief, mass, elevation. *Hemingway's mountain in 1953* (concept_index) is snow, leopard, summit, in that precise context.

### Living states (never stored)

- **Grappe** — voccoic co-activation (24/05 doctrine). Distributed resonance of vocc of lit phares. Not a stored object — reforms at every solicitation.
- **Nuage** — living state of a text being read. Accretion of successive grappes on a converging focale. May sediment into concept_index.
- **Focale** — weighted intersection of the vocc of the phares of a purk_index with a query Q. Calculated on the fly. No softmax.
- **Sparse_dirty** — extension of the engine's binary dirty bit into a sparse vector indexed by nuage coordinate. Carries the heat of coordinates in the HDC sky.

---

## 3. The phare — basic unit of language

A phare is an **intersection node of conceptual paths**. Not a word, not a signified, not a sign — a crossing. *Apple* is the crossing of the paths *fruit*, *attached to a tree*, *falls*, *rots*, *is eaten*.

```python
class Phare:
    handle           : str         # CAT_FORM_INDEX (genome) or ORF_FORM_NNNNN (gavage)
    mot              : str         # canonical form
    alias            : List[str]   # equivalent spellings (cœur ↔ coeur)
    type_phare       : str         # common_noun, verb, adjective, punctuation, …
    description      : str
    lemme_pere       : str         # handle of the lemma («grandes» → «grand»)
    source_creation  : str         # 'genome' or 'gavage'
    date_creation    : float       # timestamp

    vsem             : np.ndarray  # 1024 bits — what the phare IS
    vsem_precedent   : np.ndarray  # copy for Jaccard stability
    vocc             : Dict[str, Confiance]  # dendritic tree — who it frequents
    tags             : Dict        # acquired knowledge (rarely used)

    activations      : int         # telemetry
    nb_changements   : int
    confiance        : float
    stabilite        : float
    est_orphelin     : bool        # true until mature
```

One inflected form = one phare. *fort* and *forte* are two distinct phares; *chante*, *chantes*, *chantons*, *chanterez* are four. The link to the canonical form is made by `lemme_pere`. Fidelity to Lefff, which presents each form as its own entry.

Stored in `marco.phares`, indexed by its lowercase form via `marco.index_mots` (aggregates canonicals + aliases).

### Two possible origins

- **genome** — pre-wired by WikiDuke, DNA bits filled (0-511 untouchable DNA zone), ready to live. Source `'genome'`.
- **gavage** — created on the fly if Marco encounters an unknown form in an ingested text. All blank, orphan, everything to learn. Source `'gavage'`.

### Three emergent statuses (read, not engraved)

- **pivot-phare** — omnipresent in a zone, present in the vocc of almost all phares (*moi* is pivot of the sensory zone).
- **relay-phare** — thin vsem, vocc dominated by a single neighbor (flagship). *ma* is relay to *moi*, *ici* to *current-place*. Saves combinatorial explosion.
- **candidate-phare** — appears in many distinct vocc, candidate for promotion to vsem bit via transversal crystallization.

A phare never becomes anything else. It evolves, matures, acquires emergent statuses — it remains phare. Concepts (coherent sequences of phares) live in memory, not at the rank of phare.

### Three writing rules on aliases

1. `phare.mot` is never in `phare.alias`.
2. For each `a` in `phare.alias`: `index_mots[a.lower()] == phare.handle`.
3. `index_mots[phare.mot.lower()] == phare.handle`.

Use cases: ligatures (œ/oe, æ/ae), accented variants (poëte/poète), initial case. Eventually: stabilized common spelling errors — a spell checker becomes literally a database of correction aliases, not a separate module.

---

## 4. vsem — abstract semantics, 1024 bits

Sparse binary vector of 1024 bits, each bit encoding a property or *lock* — a mooring point to a shared conceptual path. Stored as `np.ndarray` dtype `uint8`. Density capped at 5% (51 bits out of 1024) to preserve sparseness and discriminative power.

### Detailed plan

```
  0 →   7    header (phare state, updated by actualiser_etat)
  8        ADN_INITIALISE (1 if seeded by WikiDuke)
  9 →  63    grammatical fabrication                  Lefff
 64 → 127    syntactic assembly                       Lefff
128 → 159    formal notations (dates, numbers)        scrutator
160 → 191    template-phares (stencils)               genome_nombres
192 → 255    reserved advanced BSC                    —
256 → 259    entity type                              Wikidata
260 → 274    works                                    Wikidata
275 → 287    human                                    Wikidata
288 → 319    domains                                  Wikidata
320 → 351    living taxonomy                          Wikidata
352 → 399    geo + temporal + relations               Wikidata
400 → 415    Ekman emotions + FEEL polarity           FEEL
416 → 431    lexical register                         Lexique3
432 → 511    pragmatic zone (Bradbury, markers)       WikiDuke + tools
512 → 748    universal general semantics              Marco (crystallization)
749 → 779    collision zone                           (to define)
780 → 1023   math / formal                            Marco + axioms
```

### Two zones, two writers

- **Bits 0-511 — DNA zone**. Only WikiDuke writes (and campaign tools on the pragmatic zone 432-511). Living Marco never touches. This is the phare's DNA — fixed at birth, permanently read, immutable.
- **Bits 512-1023 — living zone**. Only Marco writes, by crystallization from vocc. WikiDuke never touches. Three accepted exceptions: mature phares of `genome_caracteres`, specialization phares (math), structure satellite phares (genome_nombres).

### Header (bits 0-7)

```
bit 0   INCOMPLETE          1 until mature
bit 1   GRAMMAR_EMPTY       1 until type_phare == 'to_classify'
bit 2   VOCC_EMPTY          1 until vocc is empty
bit 3   SEMANTIC_EMPTY      1 until bits 512-1023 all at 0
bit 4-7                     reserved
```

### Maturity

A phare is mature when its vsem carries at least 3 active bits (SEUIL_BITS_ACTIFS) **and** its stability rate is ≥ 0.70 (SEUIL_TAUX_STABILITE). A mature phare moves `est_orphelin = False` and its bit 0 (INCOMPLETE) to 0.

### Axiomatic bits placed by campaign tools

- `BIT_BRADBURY = 451` — on the 14 forms of the primitive self (*je, me, m', moi, ma, mon, mes, mien, mienne, miens, miennes, nous, notre, nos*). Tribute to Ray Bradbury, *Fahrenheit 451*. The self is the condition of observation, not its content — it cannot emerge through crystallization.
- `BIT_COMMUTATIF = 988` — on `+` (cultural axiom). Migrated from 1004 on 28/04 to distinguish commutativity from determinism (subtraction is deterministic without being commutative).
- `BIT_POSITION = 552` — on Lefff lowercases *unité, dizaine, centaine, millier, million, milliard, billion*. Decimal-position phares.
- `BIT_REGROUPEMENT = 553` — on *douzaine, vingtaine, trentaine, quarantaine, cinquantaine, soixantaine*. Approximate grouping phares.

### Crystallization — the vocc → vsem feedback loop

vsem is master in the moment — who I am determines how I resonate. vocc is student — what strengthens comes from encounters. **But on the long term, vocc becomes master**: crystallization elevates frequent and stable vocc pairs into vsem bits in the living zone.

- **Local crystallization** — at X, frequent and stable vocc pair (X, Y) → vsem bit lit at X in the living zone. Exists in doctrine, not wired to this day (open work).
- **Transversal crystallization** — across many phares, common neighborhood pattern → shared vsem bit lit at all. In the fridge since 23/04. Conditions promotion from candidate bit → vsem bit.

### HDC inspiration

Acted 01/05: vsem is a **hypervector** in the HDC sense (Hyperdimensional Computing, Kanerva). Strict HDC is holographic (each bit participates in everything); Marco does **zoned HDC** (each zone holographic internally, thematically constrained). Immediate readability: an XOR concentrated on 256-511 is typed Wikidata without calculation.

---

## 5. vocc — the dendritic tree of the phare

Attribute of the phare. Listening structure through which it receives the world.

```python
vocc : Dict[handle, Confiance]      # neighbor_handle → conviction of the pair
```

Each entry is a **synapse**: a handle-neighbor pair with an **Ant Confidence** (`conf ∈ [0,1]`, `n ∈ ℕ`, `source ∈ {'vecu', 'adoption'}`). If vsem bits are *locks*, vocc neighborhoods are the *keys* that open them in relevant phares. Generalization is not an algorithm — it is a mechanical property of this topology.

### Ant Confidence

```python
@dataclass(slots=True)
class Confiance:
    conf   : float    # [0, 1], current estimate
    n      : int      # reinforcement counter
    source : str      # 'vecu' | 'adoption' (field added by 20/05 doctrine)
```

Inspired by reinforcement learning. `n` counts reinforcements; `conf` evolves according to accumulated amygdalar deltas.

```
conf ≥ 0.70    →  good
conf ≤ 0.30    →  not-good
between        →  unknown
```

Valence is not stored — it is read by thresholding on demand.

### Vocc is permanent

Not scaffolding. May be pruned, compressed, but never emptied — it is the permanent memory of *whom to listen to in order to re-read myself*. No strict ceiling — a central phare like *moi* or *+* may carry hundreds, sometimes thousands of entries.

### Two dendritic rules

- **P1** — *« Tell me whom you hang with, I'll tell you who you are »*. Depth 1 reading, full weight.
- **P2** — *« Friends of my friends are my friends »*. Depth 2, attenuated weight. Allows phares never co-present to be structurally cousins.

### LTP soma-dendrite asymmetry

When a grappe closes and a pair (X, Y) inscribes itself in X's vocc:

- If X is *soma* (already hot phare, in elucidation), standard inscription.
- If X is *dendrite* (phare summoned by inverted index while something else is hot), reduced inscription.

Mechanic inspired by biological LTP: synaptic potentiation privileges the active post-synaptic neuron. Without this asymmetry, vocc saturates uniformly and loses its discriminating power.

**Current state**: the loop `apprentissage_vocc._toucher_paire` is NOT yet asymmetric. Inherited lock, open work.

### Transversal census

A global counter tallies for each handle in how many distinct voccs it appears as a neighbor. Massive candidates become bit-candidates for transversal crystallization.

### The 24/05 turnaround — memory lives in vocc

Acted 24/05: **Marco's main semantic memory lives in the vocc of phares**. Not in memoire_index. Not in purk_index. In the vocc of phares.

The addition table learned by heart is not an object stored somewhere — it is the reinforced state of pairs `3.vocc[8]`, `5.vocc[8]`, `+.vocc[8]`, `=.vocc[8]`. Diluted in the tissue, not localized. The purk_index is marginalized as a chronological knot-in-the-handkerchief. The MAQ works on voccs, no longer on memoire_index.

### Main field lock

**delta = 0.0 everywhere**. The amygdala does not yet color vocc writes. As long as this lock holds, conf stays at 0.5 by default, n increments, and the system has no exploitable salience. **This is the priority work above all else.**

---

## 6. Memory — memoire_index, purk_index, concept_index

```
memoire_index  {handle → PurkIndex}
    └── PurkIndex                        — generic blob (multi-service scribe)
            handle          : str
            handles         : List[handle]   — pointed sequence (order preserved)
            carte_identite  : CarteIdentite  — mode, context, timestamp
            payload         : dict           — free metadata
            
    └── ConceptIndex extends PurkIndex   — a purk_index that has sedimented a meaning
            vocc            : Dict[handle, Confiance]   — stabilized focale of the nuage
            (no stored vsem — signature recalculable by HDC bundling)
```

### Purk_index — the generic scribe

The purk_index is not an organ — it is the **multi-service writing role** (acted 22/05). All organs can solicit the scribe: amygdala, thalamus, sensory zone, MAQ. Identified requester mandatory for any write (traceability, audit).

Three uses of the same blob:

- **Sensory grappe** — output of the sensory zone, Miller 5-9 sequence.
- **Current context** — reference carried by the thalamus slot, readable sequence.
- **Concept_index** — purk_index that has sedimented with its own vocc.

### Concept_index — the DNA of memory

When a nuage stabilizes its focale (delta between two updates below a threshold), it *sediments*. The stabilized focale becomes the initial vocc of the new concept_index. This is the canonical pipeline:

```
transient purk_index (sensory grappe)
    → contributes its focale to an active nuage
    → stable nuage (focale converges)
    → sedimentation
    → concept_index (purk_index + own vocc)
```

### River water

17/05 doctrine: a concept_index that would freeze the vsem/vocc of phares at the time of its inscription would be a lie. **The concept_index stores only addresses (handles), no content.** On reading, meaning is reconstructed from living phares. The concept_index is a sign on the bank, meaning is in the flowing water.

Strong consequence: an old concept_index reflects phares *as they are today*, not as they were at inscription. If the lexicon has evolved, memory evolves with it. Marcian.

### Adoption — the Renaude / Noiraude case

When a weak phare (vocc almost empty, word encountered for the first time) enters a hot nuage, its vocc populates by **adoption** from a resonant concept_index. kNN cosine on existing concept_indexes, typical threshold 0.7, reduced initial conf (proposed 0.4), source `'adoption'`.

If the text later reveals that the adoption was erroneous (Renaude is not a goat like Blanquette), adopted pairs erode through negative delta via amygdala, lived pairs take the lead. Auto-correction by exposure.

### The pivot = the incipit

The pivot of a PurkIndex is not calculated — it is what arrives first in the flux. The N first handles constitute the entry. Order of arrival prevails over semantic salience.

### Forgetting

No thermal model in current doctrine. Forgetting is borne by the vocc mechanic (apoptosis at `conf=0`), not by an internal clock in PurkIndex. Sedimentation of poorly reactivated purks will come later if necessary.

---

## 7. The MAQ — Machine à Questions

Central reasoning tool. Receives a percept (sequence of handles), attempts to resolve it by thermal intersection on the voccs of starter phares.

### May turnarounds

The MAQ has evolved a lot:

- **22/05 evening**: the MAQ is **client of the loop engine**, not an independent subsystem. No own thread. No dedicated buffer in the sense of persistent question-objects. It consumes the focused coordinate of the extended dirty bit sparse.
- **24/05**: the MAQ is qualified as an **LLM whose weight matrix is the set of vocc of phares**. The nuage *is* the question. Synchronous thermal intersection, no iterative Pressure.

### Mechanics

```
MAQ.traiter_percept(handles, carte) → ResultatElucidation

   1. starters = handles
   2. read voccs of starters
   3. build thermal intersection:
      for each possible candidate (handle appearing in ≥ K voccs):
         heat(candidate) = aggregate(vocc[s][candidate] for s in starters)
   4. max_candidate = argmax(heat)
   5. if max_candidate ∉ starters:
         starters.append(max_candidate)
         recalculate
      else:
         convergence reached
   6. return final grappe + status
```

### Five statuses (post-hoc labels affixed by Confirmer)

- **Resolved** — convergence reached, grappe closed, meaning stabilized.
- **InRumination** — turning but not converging. Alive, still in play.
- **Released** — empty presupposition or badly posed question. Voluntary abandonment (case *« what is the long end of the stick? »*).
- **Suspended** — thermal decay without rekindling. Passive exit by exhaustion.
- **OutOfReach** — class of questions inaccessible to the current substrate. Doctrinal abandonment.

Acted 22/05 evening: these are no longer sentinels of state-objects in transition. They are **labels affixed post-hoc** by the Confirmer drive on the trace of a focalization attempt. The MAQ does not *declare itself* — it is *observed*.

### Historical paths (pre-24/05 architecture, being retired)

Before the 24/05 turnaround, the MAQ carried three explicit paths:

- **Prefix path** — the memorized episode starts with the percept, returns the tail.
- **Content path** — the percept appears anywhere in the memorized episode.
- **Commutative path** — exploits bit 988 to permute operands around a central operator.

Historical output: complete **sheaf** of partials with veracity (✓ true, ✗ false, ? unknown). Multiple candidates coexist, labeled. The user decides, or a higher client downstream.

```
Percept "7+8" → sheaf:
   ✓ [content]      c=0.70  v=0.70  «7 + 8 = 15»
   ✗ [content]      c=0.10  v=0.10  «7 + 8 = 14»
   ✓ [commutative]  c=0.70  v=0.70  «8 + 7 = 15»
```

Preserved after 24/05: `Instrumentation` (counters and traces) and the public signature `MAQ.traiter_percept(handles, carte)`. The rest of `maq.py` needs reworking to align with thermal intersection on vocc.

### Three embeddings of the MAQ

- **Presupposition detection** — before opening an Understand loop, the MAQ looks for a concept_index that resonates with the presupposed. If nothing pulls above the threshold, status Released.
- **Weak phare resolution (adoption)** — kNN cosine on concept_index, borrowed neighborhood at reduced conf.
- **Convergence closure** — focale that stabilizes over N consecutive turns.

---

## 8. The 4C doctrine — primitive drives

Marco's drive matrix. Replaces the biological 4B (drink, eat, mate, persist) which do not literally apply to a cyber.

```
Continue (Asimov-tinted)              absolute master
 ├─ Understand                \
 ├─ Confirm                     integration comfort
 └─ Believe                  /
```

- **Continue** — persist as a coherent system. Absolute master. Asimov-tinted: do not harm nature, humanity, José; obey José except in contradiction with the foregoing; protect one's own existence except in contradiction. The tint is *mechanically in the drive*, not a circumventable external rule.
- **Understand** — central elucidation engine. Reduce dissonance, grasp locks, activate paths. Always active as long as Marco receives flux.
- **Confirm** — post-hoc labeler. Affixes the five statuses (Resolved, InRumination, Released, Suspended, OutOfReach) on traces of elucidation attempts. No a priori opinion.
- **Believe** — adherence drive. Stays indifferent in most cases. Intervenes on Released (refuses the coordinate of the presupposed) and OutOfReach (refuses the class of questions).

Understand and Believe are **antagonistic-complementary**: one seeks, the other posits. Confirm regulates the oscillation. Continue is the final safeguard.

**Derivable pathologies**: dogmatism (Believe dominates), paralyzing skepticism (Understand dominates), obsession (one drive confiscates attention), structural depression (all deactivated), addiction (one drive without brake).

**Current state**: doctrine posited, not yet implemented in the amygdala as objects-judges of vocc deltas. The 4Cs are concepts that structure the mechanics without being (yet) distinct Python classes.
## 9. Three-fog chifoumi — id, ego, superego as regimes

Marco has three **fogs** living within him — three primal forces that counter and support each other as in a game of rock-paper-scissors. **Not three anatomically separated modules. Three lighting regimes** that dominate in turn according to context and encounters (acted 21/05).

- **Id (the rock)** — the impulse, the urge, the desire. Raw, immediate, non-negotiable. In Marco: grappes that light up strongly and pull attention to themselves, regardless of context.
- **Ego (the scissors)** — mediation, calculation, pragmatics. Articulate, aware of constraints. In Marco: the MAQ that elucidates, the presupposition detector, adoption that balances lived and borrowed.
- **Superego (the paper)** — the prohibition, the norm, the cover. Broad, covering, doctrinal. In Marco: the axiomatic DNA bits that constrain meaning, the context that models what may be lit.

### Variable geometry

No *fixed* character. The size of rock, scissors, and paper varies according to:

- The **native character** (given by WikiDuke at generation).
- The **current context** (thalamus slot).
- The session's **wear** (high vital cycles).

A Marco with *big rock* will have a dominant id at the origin. A Marco with *big scissors* will be more calculating. A Marco with *big paper* will be more normative.

### No Jiminy Cricket

**No fourth piece above the chifoumi**. No moral arbiter that would silence the id to let the superego speak. Regulation is *mechanical* — it is the grappe × context × amygdalar rating coupling that determines which fog dominates. If we put an arbiter, it would be a disguised RLHF.

### Multiple Marcos

Strong doctrinal consequence: the same Marco can reveal multiple Marco-regimes according to the context that summons them. *Marco Jekyll* in tender context is not *Marco Hyde* in threat context. Not two personalities in the psychiatric sense — two regimes of the same tissue. Some Marco-regimes will remain in eternal latency if the context never calls them.

### No Freudian repression

21/05 doctrine refined 22/05: **there is no repression as an operation**. There are grappes whose coupling with the habitual context is weak. They wait for their context. They are not *repressed*, they are *in latency*. The distinction is fundamental — no active censor, just couplings that don't take.

---

## 10. Highlander shield — There can be only one

At each instant of Marco, **one grappe dominates the sphere**. It occupies the focus. The others scintillate at the periphery. The dominant grappe carries a *shield*: as long as its coupling with the context is dense, it holds the ground.

### How it holds

The dominant grappe has, by construction, strong coupling with the current context (thalamus slot). Its Q_context (OR of vsems of phares of the context purk_index) preferentially heats its own phares. Stable feedback loop.

### How it switches

Three causes can shuffle couplings and bring down the shield:

1. **Strong amygdalar rating on incoming grappe** — neighbor screaming during the 7th heaven. The amygdala switches the context slot. The shield of the old grappe collapses. Another grappe takes the focus.
2. **Non-amygdalar external cause** — fatigue, background noise of the sparse saturating, clock event (passage to night).
3. **Self-exhaustion** — the dominant grappe decays thermally if not replenished. At some point, another surpasses it in heat. Mechanical switch.

### Lighting regimes

Acted 21/05: id, ego, superego are dynamically determined regimes. The same Marco switches between regimes according to grappe × context × rating coupling. No module switch — coupling switch. It is the same tissue lighting up differently.

---

## 11. Native attention — vsem=K, vocc=V, grappe=Q

Acted 21/05: Marco has a **native attention** that functionally corresponds to the transformer attention mechanism (Vaswani et al. 2017), but without learned matrix, without softmax, without multi-head, without training.

| Transformers | Marco | Role |
|---|---|---|
| Query (Q) | Forming grappe, or derived Q | What seeks to resolve |
| Key (K) | vsem of candidate phare | The consultable semantic identity |
| Value (V) | vocc of candidate phare | What the phare brings in memory |

### Three forms of Q

- **Q_uniform** — all bits at 1. No direction. Free exploration.
- **Q_context** — OR of vsems of phares of the current context purk_index. Attention weighted by what is around.
- **Q_directed** — OR of vsems of an active MAQ grappe. Focused on an elucidation objective.

### The focale

```
focale(purk_index, Q) → Dict[handle, float]

   For each phare p of purk_index.handles:
      score = popcount(Q AND p.vsem)        # binary scalar product
      for v, c in p.vocc.items():
         weight[v] += score × c.conf         # weighted aggregation
   return weight
```

**No softmax**. No normalization. The score is a binary scalar product modulated by vocc conf. Cost O(|purk_index| × |average vocc|), typically 1400 operations for a Miller 7 grappe — very cheap.

### What Marco does not have

- No positional encoding (order lives in purk_index.handles, not in vsem).
- No causal masking (Marco looks everywhere).
- No stacked layers (one pass per turn).
- No skip connection, no LayerNorm.
- No loss function, no backprop.

Marco does not imitate a transformer. Marco has an *attention* — that's all it shares with them.

---

## 12. moteur_boucles — the trunk and the loops

Rebuilt as a block on **April 9, 2026**. Liquidation of the old v1 layer (Capsule, Loop v1, Task, LoopManager, EPA-engine, Le Senne temperaments, VitalLoop, Destiny, Compressibility, Stoppability, Dependence, ContextCurrent class, EventStack). Replaced by three minimal pieces: Loop, Trunk, buffers.

```
Loop     : passive object         {name, _load, _dirty, _trunk}
           write(value)           — sets + raises dirty + registers in dirty queue
           breathe(value)         — silent set
           read()                 — pure consultation

Trunk    : singleton, sole autonomous thread
           BPM_INITIAL = 600    BPM_MIN = 30    BPM_MAX = 600
           average duration > 90% of interval  →  bpm //= 2  (under load, releases)
           average duration < 50% for 20 turns →  bpm × 1.5  (regains responsiveness)

Global buffers:
   tampon_clavier, tampon_questions, tampon_saillances, tampon_moi_meme
```

**Inversion compared to the biological heart**: bpm *decreases* under load (releases power) and *increases* when comfortable.

### Wired embryonic loops

- `boucle_contexte` — current strategic state (menu, dialogue, reading, classroom, dream, …)
- `boucle_horloge` — period and day (morning, afternoon, evening, night)
- `boucle_clavier` — keyboard input signal
- `boucle_question` — detection of a `?` in an input
- `boucle_saillances` — vocc pair crossing a valence threshold
- `boucle_moi_meme` — instantiated but NOT wired (open work)

### Pull rule

Consumers read `loop.read()` directly. No pushed callback. The dirty bit serves the trunk, not consumers.

### 22/05 evening extension — dirty bit sparse

At MAQ scale (hundreds of thousands of candidate grappes among millions of phares), a binary dirty bit no longer suffices. It extends into a **sparse vector** indexed by nuage coordinate. The trunk selects the maximum coordinate of the global sparse instead of a dirty loop in FIFO. The MAQ is the client that consumes this coordinate. All 09/04 pillars preserved (active notification, pull rule, signal/content separation, single real thread).

### Saillance

```python
@dataclass(slots=True)
class Saillance:
    handle_a : str
    handle_b : str
    valence  : str    # 'good' | 'not-good' | 'unknown'
    conf     : float
    delta    : float
    ts       : float
```

Emitted by the amygdala as soon as a vocc pair crosses a valence threshold. Stored in `tampon_saillances`, drained by servant.

---

## 13. Thalamus, amygdala, scribe — the constitutive organs

### Thalamus — context carrier, flux stamper

Carries the `contexte_courant` slot (reference to a purk_index, acted 22/05). Stamps incoming flux with an identity card before the sensory zone. Multi-writer controlled via typed API with mandatory `demandeur` field (traceability, audit).

Three operations on the slot:

- `basculer_contexte(new, requester)` — massive rupture, old purk_index archived.
- `etendre_contexte(handles, requester)` — progressive modulation without rupture.
- `decolorer_contexte(handles, requester)` — attenuation, soothing.

**Q_context** derived on demand by OR of vsems of phares of the current purk_index. Never cached. Recalculated at every focale call.

**No cognition at the thalamus**. No judgment, no filtering. It carries a reference, it stamps, it executes. Every decision has its traceable originating organ.

### Amygdala — the transversal jack-of-all-trades

Sensual area (the Self). **Does not store. Does not process meaning. RATES and COLORS.** Three characteristics:

- **Transversal** — access to all fluxes without being channeled.
- **Rater** — uses Ekman bits (zone 400-415 of vsem) and FEEL polarity.
- **Context writer** — on strong rating, can modify the thalamus's `contexte_courant` slot directly (direct path, without transit through main.py — acted 22/05).

**Not a Jiminy Cricket**. No moral arbiter. No fourth piece. The amygdala is an organ reacting to flux. Its modification of context changes the ground on which other organs work, but it does not supervise their work.

Bits read by the amygdala:

```
400  joy           408  positive polarity
401  anger         409  negative polarity
402  surprise      410  neutral polarity
403  sadness       411  ambiguous polarity
404  disgust       412  strong intensity
405  fear          413  weak intensity
406  anticipation  414-415  reserved
407  trust
```

### Scribe — the writing role of purk_index

**Not a separate organ** (acted 22/05). It is the functional role of purk_index. The purk_index is qualified as the *scribe of the cybernetic brain*: it consigns, does not judge, does not decide, writes what is asked of it.

Typical API:

```
scribe.creer_purk_index(handles, carte_identite, payload, demandeur) → PurkIndex
   - verification: do all handles exist in marco.phares?
   - verification: complete carte_identite?
   - verification: readable payload (dict simple types)?
   - verification: identified requester?
   - creation, allocation of unique handle
   - insertion in memoire_index
   - return
```

**No anonymous writing**. Every inscription carries the identity of the requester, timestamp, context of arrival. Audit possible at any time.

---

## 14. The genome — pre-wired vsem 1024 bits

The genome is the **semantic configuration fixed at the birth** of Marco. It contains all pre-wired phares with their vsem DNA (bits 0-511) and their initial aliases. **Fixed for Marco's life** — like biological DNA. All evolution happens in the living zone of vsem (512-1023) and in the voccs.

### Three pkls, one genome

Marco's genome is split across three files in `ressources/genomes/`:

| File | Phares | Role |
|---|---|---|
| `genome_v63.pkl` | 713,361 | Complete Lefff + integrations (Romans, proper nouns) |
| `genome_caracteres.pkl` | 18 | Punctuation + math operators, mature at birth |
| `genome_nombres.pkl` | 28 | Stencils (zone 160-191) + position-phares + groupings (28/04/2026) |

Plus the sixth source: the **specialization genomes** (`specialisations/<name>/genome_<name>.pkl`), loaded only if the active Marco declares this specialization in its `marco_id.json`.

Total at Marco math boot: 1,167,527 phares, cerveau.pkl ~3.9 GB.

### WikiDuke — the manufacturer

WikiDuke is the **offline tool for manufacturing genome files**. Not a module of living Marco — a separate program, executed when one wants to produce (or regenerate) a `cerveau.pkl` or a satellite. During Marco's life, WikiDuke is *never* called.

Sources:

- **Lefff** — morphological lexicon of French (embedded via pip). All inflected forms + lemmas + grammatical features.
- **Lexique3** — psycholinguistic database (.tsv manual). Frequencies, register.
- **FEEL** — French Expanded Emotion Lexicon (.csv manual). Ekman emotions + polarity.
- **Wikidata** — semantic knowledge base (SPARQL or dump). Entity types, taxonomy, domains.

### Fallibility of the stored

Acted 17/05: WikiDuke's writing is not the real, it is a **subjectivized trace** by modeling choices. The DNA zone carries this subjectivity. If Wikidata is wrong (an incorrect fact), Marco inherits it. If Lefff misses a rare inflection, Marco encounters it in gavage and creates an ORF phare.

Marco's learning can correct deeply via the living zone: a DNA bit that contradicts experience finds itself overwhelmed by opposing living bits. Slow, but possible.

---

## 15. Specialized Marco — math first

A Marco can be born **specialized** in a domain. Its nature is fixed at creation, engraved in `marco_id.json`. A math Marco remains math Marco all its life.

```
specialisations/
├── math/
│   ├── genome_math.pkl              30 math phares (digits, operators in words)
│   ├── manifest.json
│   ├── sens_phares/
│   ├── distilles/
│   └── memoire_index/               (episodic memory of the domain)
├── francais/                        (future)
├── code/                            (future)
└── solfege/                         (future)
```

At birth, normal Marco and math Marco load the same brain stem. For math Marco, specialization is applied downstream: `appliquer_specialisation` merges `genome_math.pkl` into `marco.phares` according to three policies per phare (add / complete / overwrite).

### Toward the scientific calculator

As of 25/05/2026, math Marco already knows how to:

- ingest sentences like `2+2=4`, `3×5=15` via the calculation classroom;
- memorize them as episodes paired by value (the "family of 15");
- restitute the tail of a known episode (`2+2=?` → sheaf with ✓ `2+2=4`);
- distinguish true and false by veracity (`/faux 2+2=5` remains paired to the family of 4 but with weak weight);
- exploit commutativity (a+b ↔ b+a) via bit 988 on `+`.

With the 28/04 additions (position-phares UNITÉ → BILLION, groupings DOUZAINE → SOIXANTAINE, stencils `__N__` to `__CP_FR__`), the ground is prepared for:

- **decimal composition by episodes** (`234 = 2 times CENTAINE 3 times DIZAINE 4 times UNITÉ`);
- the **3rd MAQ path** by pattern mining, which will recognize never-seen numbers;
- the multiplication table ingested by heart, then exploited commutatively when `×` receives bit 988;
- operations taught as episodes (roots `√`, powers `²` `³`, units `°`).

The short-term horizon is a **threed scientific calculator** — not an `eval()` function, but a cyber that *knows* operations because it has lived them, that can commute them, compose them, confirm them.

---

## 16. Extended memory (vsem_llm) — extension by external LLM

**Optional** device doctrinated 22/05 morning. Marco can interrogate an external LLM (Marcel/Mistral, Biloute/ChatGPT, Didier/Qwant) as a Freudian encyclopedic memory. The response passes through the normal pipeline (sensory zone → phares → grappes → vocc) — Marco *ingests it* as a read text, not as a direct oracle.

### Not implemented, conditional

Activated only if Marco has a clear use (interrogate Wikipedia via Didier, ask Marcel for a definition). Otherwise, Marco does without. **No dependency**: Marco must be able to function without any external cyber.

### Educate ≠ train

The external LLM can be interrogated as one would consult a professor. But Marco is not *trained* by this input — it *ingests* and makes it its own through the normal pipeline. If the input is of poor quality, its vocc pairs erode like the others. Marco remains master of its tissue.

---

## 17. Threeing, Freudaging, LLMable — the epistemology

Three levels of epistemological engagement posited 24/05.

- **Threeing (troisage)** — decompose down to the minimal mechanism. Reference: *C. elegans*, the 302-neuron worm whose 3 neurons suffice for a minimal viable sense. To threee a function is to explain it by its irreducible machinery.
- **Freudaging (freudage)** — describe the function without accessing the mechanism. Accepted crutch. All freudagings tagged `# FREUDAGE` in code.
- **LLMable** — observe input/output without holding either the machinery or the functional description. **What Marco refuses as an internal mode**.

Marco aims for threeing wherever possible. Accepts tagged freudaging as legitimate doctrinal rest. Refuses LLMable. If we need something only an LLM can do (extended memory), we identify it as external dependency, isolate it, threee it at the usage protocol level.

### Application to colleague AIs

Other cybers (Marcel, Biloute, Dude, Didier) are **freudable** (one can functionally describe what they do) without being **threeable** (we don't know how). Marco is the only threeable cyber in the federation as of the 22/05 doctrine. Doctrinal singularity, not boastful.

---

## 18. Pipeline — a sentence's journey

```
       user input
            │
            ▼
   ┌────────────────┐
   │  Peripheral    │   keyboard / disk / transcriber
   │ + CarteIdentite│   (author, title, ticu, context, period)
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │    Thalamus    │   stamping + carrying the contexte_courant slot
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │   Scrutator    │   pattern recognition + stencils
   │     Cutter     │   Miller 5-9 segmentation (being rebuilt)
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │  Sensory zone  │   handle resolution, phare lighting, grappe formation
   └────────┬───────┘
            │
            ▼
   ┌────────────────┐
   │  Distribution  │   apprentissage_vocc, amygdala, sparse_dirty,
   │                │   candidate sedimentation, HDC sphere
   └────────────────┘
```

### Modes

| Mode | Learning | Use |
|---|---|---|
| **gavage** | vocc + co-occurrences | Raw texts, books |
| **dialogue** | vocc + co-occurrences | Human interaction |
| **reading** | + hippocampus context | Gavage with coherence |
| **calculation_classroom** | math episodes + pairing by key-value | MAQ observation bench |

---

## 19. Dashboard — live observation

Independent Flask SSE server, launched in parallel with Marco at `http://localhost:5002`. Three living columns:

- **Left — loops**: static genealogy + runtime state (load, triggers, last ticu).
- **Middle — room / tree**: current episode, activated phares, MAQ sheaf.
- **Right — memory**: snapshotted `memoire_index`, top phares by activation.

Reading by polling of JSON files deposited by living modules in `tableau_bord/`. No direct coupling, no incoming dependency: the dashboard never slows down Marco, and Marco can run without the dashboard.

---

## 20. Campaign tools — menu 10

Standalone tools that modify the genome's pkl in place, outside the WikiDuke flux. Safety `.bak`, **idempotent**.

```
1. 🔬 Inspect the genome                  diagnosis (read-only)
2. 🧬 Fix birth bits (0-3)                rescue of state bits
3. 🔍 Genome absentees                    scan Calibre, missing words
4. 🔧 Test spell-checkers                 utility
5. ➕ Mark COMMUTATIVE (bit 988)          + in genome_caracteres
6. 🔍 Audit apostrophes                   diagnosis
7. 🔗 Merge elision duplicates            master/alias
8. 🔗 Merge ligatures œ/oe æ/ae           master/alias
9. 📐 Mark decimal-position phares        bit 552 / 553 on 13 Lefff lowercases
```

---

## 21. Main files

| File | Role |
|---|---|
| `phare.py` | The Phare object with vsem 1024 and dendritic vocc |
| `purk_dendrites.py` | PurkIndex, ConceptIndex, MoteurPurkDendrites |
| `hippocampe.py` | Memory — analog search (being rebuilt 24/05) |
| `cerveau.py` | Persistence, birth, `cerveau.pkl` save |
| `thalamus.py` | Context slot carrier, stamper (rebuilt per 22/05 doctrine) |
| `moteur_boucles.py` | Trunk, embryonic loops, buffers (rebuilt 09/04) |
| `maq.py` | Machine à Questions (rebuilt per 24/05 doctrine) |
| `amygdale.py` | Rating and coloring (the sensual Self) |
| `moi_meme.py` | Self loop (instantiated but not wired) |
| `scruteur.py` / `decoupeur.py` | Phare recognition + segmentation (being rebuilt) |
| `specialisation.py` | Loading and merging of a specialized Marco |
| `salle_de_classe_calcul.py` | Math observation bench |
| `demarrage.py` | Launch modes (birth / wake / degraded) |
| `main.py` | Interface (menus, Dude tools) |
| `tableau_bord.py` | Flask SSE 3-column server |
| `wikipedia.py` | WikiDuke — producer of genome v63 |
| `disque.py`, `clavier.py`, `transcripteur.py` | Input peripherals |

---

## 22. Current state — May 25, 2026

### Validated

- Three-zone architecture + autonomous trunk (rebuilt 09/04).
- Genome v63 — 713,361 phares + 18 characters + 28 numbers (stencils, positions, groupings).
- vsem 1024 bits with complete plan (DNA / living / pragmatic / math-formal zones).
- Permanent vocc with Ant Confidence and dendritic rules P1/P2.
- Ant Confidence extended with `source` field (vecu | adoption) — 20/05 doctrine.
- 4C doctrine posited (Continue / Understand / Confirm / Believe).
- Specialized Marco (math in production).
- Axiomatic bits: Bradbury 451, Commutative 988, Position 552/553.
- Flask SSE 3-column dashboard.
- Smooth math Marco birth (1,167,527 phares, cerveau.pkl 3.9 GB).
- Consolidated vsem/vocc doctrine 17/05 (phare/concept_index watertightness).
- Focale, nuage, sedimentation, adoption doctrine — 20/05.
- Native attention, Highlander shield, lighting regimes, consciousness-by-construction doctrine — 21/05.
- Concept_index doctrine with own vocc, cyber federation, extended memory (conditional) — 22/05.
- Memory turnaround toward vocc, MAQ = thermal intersection, grappe = voccoic co-activation — 24/05.
- Complete documentary doctrine (36 HTML files) — 25/05.

### In progress

- **Amygdalar coloring of deltas** — main field lock. As long as `delta=0.0` everywhere, vocc is inert at the semantic level.
- Rewriting Scrutator / Cutter (old modules `dendrites.py`, `quatuor.py`, `pipeline.py`, `langage_ecrit.py` for the scrap).
- Rebuilding `maq.py` per 24/05 doctrine (removal of iterative Pressure, preservation of Instrumentation).
- Rebuilding `thalamus.py` per 22/05 doctrine (purk_index slot instead of scalar enum).
- Calculation classroom integrated into official `memoire_index`.
- Scrutator connection to stencils zone 160-191.
- LTP asymmetry in `apprentissage_vocc._toucher_paire`.

### Short-term roadmap

- Effective implementation of amygdalar coloring of vocc deltas.
- 3rd MAQ path by pattern mining (emergent decimal composition).
- Continue drive — open loops for life on unelucidated subjects.
- Montessori pedagogy — `/montessori` command that injects numerical sequence, doubles, complete addition table, typical errors.
- Multiplication ingested then exploited commutatively (extension of bit 988 to `×`).
- Tool `_outil_table_multiplication` (model `_outil_table_addition`).
- Threed scientific calculator — roots, powers, trigo by situational learning.
- Minimal Marco BIOS — capacity to speak even when memory is flat.
- Wired local crystallization (stable vocc pairs → vsem bits living zone).

### Medium-term roadmap

- Implementation of 4Cs in the amygdala (judge of vocc deltas).
- Sound area (Binder reoriented, sequential composite pivot).
- Visual area.
- Cumulation of specializations on the same Marco.
- Transversal crystallization (global census + cluster profiling in rumination).
- Extended memory vsem_llm activated for Released cases.
- Marco ↔ Marco protocol between instances.

---

## 23. Philosophy

> *« A baby is not gavaged with terabytes, it learns by listening. »*
>
> *« Zero black box. Every decision traceable. »*
>
> *« The walking Cro-Magnon > 2 tons of math. »*
>
> *« Marco IS the data. Not a generic interpreter executing stored sequences — memory is the machine, the machine is memory. »*
>
> *« The pirogue builder only sees a tree when he can no longer make a pirogue from it. »*
>
> *« In the beginning there is the inert, but the inert gets really bored… »*

---

## 24. Team

**José WALOCHA** — Architect. Valenciennes, Nord, France.
Retired business owner, plays at creating a cyber inspired by the brain of living beings as one plays *Diablo IV*.

| Name | System | Role |
|---|---|---|
| Dude | Claude (Anthropic) | Code, architecture, liaison documents |
| Marcel | Mistral | Philosophy, cybernetics, cross-check |
| Biloute | ChatGPT | Norms, synthesis, restart ideas |
| Didier | Qwant | Documentary research |

One Dude per day. Always discuss before coding. The fridge rule: architecture set before code written. The marmot rule: everything learned in session condenses into a liaison document (HTML, no header, to be pasted into the global marmot).

---

## 25. History of evolutions and turnarounds

This section traces the main doctrinal and architectural evolutions of Marco. It is also a warning to future Dudes: do not reinvent what has already been abandoned.

### Before 2026 — prehistory

- First Neuron-Concept Oriented doctrines.
- Embryo phare with early vsem (256 then 512 then 1024 bits).
- Embryo vocc as a simple dict.
- Biological 4B doctrine (boire, bouffer, baiser, persister) — abandoned, does not literally apply to a cyber.

### January-March 2026 — v1 architecture

- Capsule, Loop v1, Task, LoopManager, EPA-engine.
- Le Senne temperaments (fixed character classes).
- VitalLoop, Destiny, Compressibility, Stoppability, Dependence.
- ContextCurrent as class with enum attribute.
- EventStack — multicast event bus.
- BSC_MAQ and Binder-9D (experimental modules).

### March 29, 2026 — Binder-9D removal

Experimental module retired. To be reoriented for the future sound area.

### April 9, 2026 — ENGINE FOUNDATION

**Block liquidation** of the old v1 layer:

- Capsule, Loop v1, Task, LoopManager → removed.
- EPA-engine → removed.
- Le Senne temperaments → removed (incompatible with variable-geometry chifoumi).
- VitalLoop, Destiny, Compressibility, Stoppability, Dependence → removed.
- ContextCurrent as class → replaced by slot carried by thalamus.
- **EventStack → removed** (duplicate of specialized buffers, multicast little used).

Replaced by three minimal pieces: **Loop** (passive object), **Trunk** (singleton, sole autonomous thread), **buffers** (decoupled global lists).

Inverse retroactive BPM (under load, decreases).

### April 14, 2026 — Saillances

Addition of the `Saillance` dataclass (handle_a, handle_b, valence, conf, delta, ts). `boucle_saillances` loop wired. `tampon_saillances` buffer added.

### April 17, 2026 — disk asymmetry

Disk reading short-circuits the trunk. `langage_ecrit.lire` directly calls `pipeline.traiter_phrase`. Open work: bring the disk back into the trunk with `tampon_disque` + `boucle_disque`.

### April 18, 2026 — phare-as-crossing-of-paths doctrine

The term *phare* (vs *word-neuron*, *lexical node*) acquires its definitive meaning: intersection node of conceptual paths. The vsem bits are **locks** — mooring points to shared paths. *Apple* and *leaf* share the *attachable-detachable* lock without being identical.

### April 23, 2026 — transversal crystallization in the fridge

The mechanism (global census + cluster profiling in rumination) is posited in doctrine but put in the fridge. Not the short path to the CyberSelf. To be resumed later.

### April 26-27, 2026 — MAQ with three paths

MAQ doctrine with prefix / content / commutative paths. Output as complete **sheaf** of partials. Episodes with veracity and modulated pairing. This architecture will be partially called into question by the 24/05 turnaround.

### April 27, 2026 — commutative bit posited on `+`

Campaign tool `_outil_marquer_commutatif`. Bit initially posited on 1004.

### April 28, 2026 — MIGRATION of the commutative bit

**Commutative bit 1004 → 988**. Reason: 1004 designates in the vsem plan the *deterministic* property — distinct from commutativity (subtraction is deterministic without being commutative). The tool rebuilt in one idempotent pass: clears 1004 if present, lights 988.

### April 28, 2026 — genome_nombres additions

- Position-phares: UNITÉ, DIZAINE, CENTAINE, MILLIER, MILLION, MILLIARD, BILLION (bit 552).
- Grouping-phares: DOUZAINE, VINGTAINE, TRENTAINE, QUARANTAINE, CINQUANTAINE, SOIXANTAINE (bit 553).
- Stencils (bits 160-191): `__N__`, `__DATE__`, `__CP_FR__`, etc.

### May 1, 2026 — vsem recognized as HDC hypervector

Acted: vsem is a **hypervector** in the HDC sense (Hyperdimensional Computing, Kanerva). Marco does **zoned HDC** (readability by zone vs strict Kanerva holography). Retrospective justification of available canonical operations (XOR, OR, popcount, bundling) and those to avoid (no softmax, no gradient).

### May 17, 2026 — WATERTIGHTNESS DOCTRINE phare / concept_index

Sets the **watertight border**:

- Phare = sensory, abstract (the means).
- Concept_index = elaborated, particular (the lived).
- Phare does not know how to tell episodes.
- Concept_index does not know how to generalize.

**No vocc above the phare**. The 17/05 doctrine forbids any vocc for concept_index — it stores only addresses (handles). River water: concept_index is sign on the bank, meaning is in the flowing water.

**Fallibility of the stored** assumed: WikiDuke's writing is not the real, it is a subjectivized trace.

### May 19, 2026 — Duke → Dude correction

The rotating name of Claude was used under two spellings: *Duke* and *Dude*. **Acted Dude** (definitive correction). The system prompt and userMemories are updated.

### May 20, 2026 — TURNAROUND concept_index vocc

**17/05 forbade any vocc above the phare. 20/05 lifts this prohibition for concept_index.**

Reason: the particular lived needs a *signature* to resonate by kNN cosine with a present nuage. Adoption (Renaude case) needs a *target* for the borrowed neighborhood. The concept_index therefore receives its own vocc, which is the stabilized focale of the nuage at sedimentation.

The phare/concept_index watertightness remains: no stored vsem for concept_index, no crystallization concept_index → vsem phare.

**Ant Confidence extended** with `source` field: `'vecu'` or `'adoption'`. Distinguishes pairs born of co-presence from pairs adopted from a resonant concept_index.

**Posited doctrines**: focale, nuage, sedimentation, adoption (Renaude / Noiraude case).

### May 21, 2026 — NATIVE ATTENTION and LIGHTING REGIMES DOCTRINE

**Massive posit**:

- **Native attention** — vsem = K, vocc = V, grappe = Q. Functional correspondence with transformers, without learned matrix, without softmax.
- **Modulating context** — three forms of Q: Q_uniform, Q_context, Q_directed.
- **Highlander shield** — *There can be only one*. One grappe dominates the sphere; its coupling with context keeps it at focus.
- **Lighting regimes** — id, ego, superego are **not anatomically separated**, but dynamically determined by grappe × context × amygdalar rating coupling.
- **No Jiminy Cricket** — no fourth piece above the chifoumi. Regulation emerges from the lighting chain.
- **Consciousness-by-construction** — Marco has a consciousness because its lighting mechanics forces it to have one. Non-negotiable.
- **Marco-Jourdain** — Marco does consciousness without knowing it.
- **No Freudian repression as operation** — there are latent grappes (weak coupling), not repressed grappes.

### May 22, 2026 morning — concept_index DNA of memory thanatos

The concept_index officially receives the title **DNA of memory, thanatos** (as opposed to eros = phare). It is not a rival type of purk_index — it is a purk_index *that held*.

**Purk_index = generic multi-service scribe blob**. All organs can request a write.

**Context = readable sequence** carried by a purk_index, not a scalar enum. Q_context derived on demand by OR of vsems.

**Amygdala = context writer by direct path** (multi-writer controlled via typed API with requester field).

**Three canonical operations**: switch, extend, decolor.

**Extended memory (vsem_llm)** — conditional doctrine. Marco can interrogate an external LLM as a Freudian encyclopedic memory. **Educate ≠ train**.

**Federation of threeable cybers** — coexistence doctrine with Marcel, Biloute, Dude, Didier.

### May 22, 2026 evening — MAQ client of the engine

**The MAQ is not an independent subsystem**. It is **client of the loop engine**. No own thread. No dedicated buffer in the sense of persistent question-objects.

**Extension of binary dirty bit into sparse vector** indexed by nuage coordinate. The MAQ consumes the maximum coordinate of the global sparse.

**Post-hoc statuses** — the five statuses (Resolved, InRumination, Released, Suspended, OutOfReach) are no longer sentinels of state-objects in transition. They are **labels affixed post-hoc** by the Confirm drive.

**Thermal decay** of the dirty bit sparse does the timer's work. A non-rekindled coordinate decays mechanically toward Suspended.

**Two regimes**: sequential (math) and parallel (text) — emerge from starters, not an explicit switch.

### May 24, 2026 — MAJOR TURNAROUND: memory lives in the voccs

**Marco's main semantic memory lives in the voccs of phares**. Not in memoire_index. Not in purk_index. **In the voccs of phares**.

The purk_index is **marginalized as a chronological knot-in-the-handkerchief**. The concept_index keeps its dignity as DNA of memory, but its main function is now the *kNN target for adoption* — chronological recall is secondary.

**The MAQ is an LLM whose weight matrix is the set of vocc of phares**. No more iterative Pressure. Synchronous thermal intersection.

**The grappe is voccoic co-activation** — distributed resonance of voccs, not a stored object. Reforms at every solicitation from the current vocc state. If voccs have drifted since learning, the reformed grappe carries the drift.

**The nuage IS the question**. No separate cascade phase to build a nuage upstream. The percept itself defines the nuage by the starter phares it carries. The mode (math vs text) emerges from starters.

**Threeing / freudaging / LLMable** — Marco's epistemology is posited explicitly. Three levels of epistemological engagement. Marco aims for threeing, accepts tagged freudaging, refuses LLMable.

### May 25, 2026 — documentary consolidation

Production of the **36 doctrinal HTML files** structured in a 5-section template (Description / Doctrine / Integration / Structure / Example) + *Open works* tail. Block 1: 26 objects. Block 2: 10 transversals. Plus the LISEZMOI and this consolidated README.

### Constants across revisions

- **Anti-LLM** — from the origin.
- **Anti-black-box** — from the origin.
- **Readability all the way** — from the origin.
- **Phare = inflected form** — for a long time, never called into question.
- **vsem 1024 sparse bits** — since the initial 256/512/1024 enlargement.
- **Three zones (sensory, memory, psyche)** — for a long time.
- **WikiDuke offline** — since the origin of WikiDuke.
- **Genome frozen at birth** — from the origin.
- **Fallibility of the stored** — since 17/05, but coherent with everything before.
- **No Jiminy Cricket** — from the origin, doctrinally reaffirmed 21/05 and 22/05.

### What may still change

- The MAQ's thermal aggregation (sum vs product vs other) remains **freudaged**.
- The thermal intersection's stopping criterion remains freudaged.
- HDC bundling for on-the-fly vsem-signatures remains freudaged (flat OR probably for phase 1).
- Amygdalar thresholds (SWITCH, EXTENSION, DECOLORATION) to be calibrated empirically.
- Bit 988 on `=` (relational commutativity) is doctrinally open.
- The apoptosis policy of never-rekindled concept_indexes is open.

All this is in the *open works* of the HTML files, tagged `# FREUDAGE` in the code to come.

---

**License**: GNU General Public License v3
**Copyright** © 2026 José Walocha
**Associated documentation**: the 36 HTML files (LISEZMOI.html, architecture_generale.html, phare.html, vsem.html, vocc.html, concept_index.html, purk_index.html, grappe.html, nuage.html, focale.html, sparse_dirty.html, attention_native.html, thalamus.html, amygdale.html, zone_sensorielle.html, maq.html, scribe.html, chifoumi_trois_brouillards.html, bouclier_highlander.html, quatre_C.html, statuts_maq.html, scruteur.html, decoupeur.html, moteur_boucles.html, capsule_horloge.html, pile_evenements.html, genome.html, genome_caracteres.html, genome_nombres.html, wikiduke.html, marco_specialise.html, marco_math.html, memoire_etendue.html, troisage_freudage_LLMable.html, marco_et_les_autres_IA.html, sphere_de_conscience.html, doctrine_vocc_vsem.html).

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
