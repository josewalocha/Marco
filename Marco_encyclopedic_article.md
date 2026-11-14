# Marco (artificial intelligence)

> *Article written to the standards of an encyclopedia: neutral point of view, sourced facts. It is hosted in the project's repository, because Marco does not yet meet Wikipedia's notability criteria, which require independent secondary sources. The author's own presentation: [README.md](README.md).*
>
> *Version française : [Marco_article_encyclopedique.md](Marco_article_encyclopedique.md).*

| **Marco** | |
|---|---|
| Author | José Walocha |
| Development started | before 2026 |
| Latest version | program of 14 November 2026 |
| Status | in development |
| Written in | Python (standard library); BSC language for the rules |
| Type | Symbolic artificial intelligence, deduction system |
| Language processed | French |
| Licence | GNU Affero GPL v3 |
| Public repository | [github.com/josewalocha/Marco](https://github.com/josewalocha/Marco) (documentation) |
| Website | [machine-a-deduire.com](https://machine-a-deduire.com) |

**Marco** is a symbolic artificial intelligence program under development, designed by José Walocha, a retired business owner from Valenciennes (Nord, France). Its author describes it as a "bionic processor with nodal memory" and as a "deduction machine" (*machine à déduire*)[^lisez]. The program contains no neural network and no statistically learned parameters. It stores explicit, dated and sourced relations between nodes called *phares* (beacon-nodes). It answers questions by crossing these relations and states, for each answer, where it comes from. When nothing supports an answer, it says that it does not know.

The program processes French. It is written under the author's direction by assistants based on large language models[^lisez]. The project's stated goal is a dedicated microprocessor that would run Marco[^lisez].

As of November 2026, the project has not been the subject of any scientific publication or independent coverage. The available evaluations are published by the development team itself.

---

## Contents

1. [History](#history)
2. [Architecture](#architecture)
3. [Development method](#development-method)
4. [Evaluations](#evaluations)
5. [Comparisons and influences](#comparisons-and-influences)
6. [Goals](#goals)
7. [Reception](#reception)
8. [See also](#see-also)
9. [References](#references)

---

## History

### Early architectures (before 2026 – August 2026)

The first versions, prior to 2026, are built on "concept neurons" and an embryonic *phare* carrying a semantic vector of 256, then 512, then 1,024 bits[^hist]. A first architecture, built from January to March 2026, combines capsules, loops and an event bus. It is abandoned on 9 April 2026 in favour of an engine reduced to three parts: a passive loop, a trunk that alone runs by itself, and buffers[^hist].

On 18 April 2026, the term *phare* takes on its current meaning: a node where conceptual paths cross[^hist]. On 8 July 2026, weighting mechanisms are abandoned: nearest neighbours by cosine similarity, continuous scores, "attention". They are replaced by *intersection*: what two sets of *phares* have in common is enough to make the deduction[^hist].

On 12 July 2026 the demonstration console is born, inspired by the IBM 5250 terminals of the AS/400[^hist]. On 27 August 2026, Marco gives its first arithmetic answer together with its provenance ("Twelve times zero is zero"), then its first sentence in the first person[^hist].

### The nodal structure (September – October 2026)

From 15 to 19 September 2026, the program changes structure. All memory is reduced to a single *thread table* (*table de fils*), a text file of four-field relations: origin, destination, rank, instant. The earlier serialized structures are abandoned and an SQLite database is ruled out[^hist]. The rules themselves become *phares* in the table. Putting them into equations (*mise en équation*, MEQ) forms the BSC language[^hist].

On 2 October 2026, the program acquires a wake–sleep cycle. During "revision", a question left open only once in a closed context is forgotten by means of a dated thread; nothing is erased[^hist]. From 22 to 25 October 2026, the project fixes the processor's reduced instruction set, which the kernel schedules. The expression "bionic processor" dates from 25 October[^lisez].

### Reading and evaluations (October – November 2026)

At the end of October 2026, a "Great Genome" gathers knowledge held to be innate: the animals that threaten, the effects on living things, the loop "as long as there is life, it lives"[^lisez]. In November 2026, the project tests Marco against reference corpora: a first test on unseen sentences (1 November), the Universal Dependencies benchmark (measured on 4 November), FraCaS (7 November)[^lisez]. On 6 November, the senses of verbs are taken from the dictionary *Les Verbes français* by Jean Dubois and Françoise Dubois-Charlier[^lvf]: 616 senses for 401 verbs[^lisez].

### Logic as rules (November 2026)

From 10 to 14 November 2026, work focuses on the FraCaS benchmark. The deduction logic, until then written in Python in a single module (`electrique.py`), moves into "stages" (*étages*) of rules written in the genome[^conv]. The stages successively handle quantifiers and sets ("all", "some", "most", "at most"), comparison, which the author sums up as "to see is to compare" (placing two things on the same line), adjectives (qualifying or comparing within a reference), and then comparatives ("faster than", "as fast as")[^etages][^voir][^adj]. On 13 and 14 November come the universe of each problem, which the author calls its "door" (*porte*: the entry point that holds the context), and ellipses, sentences that do not repeat their verb ("Guillaume too.", "Guillaume did it.", "And Guillaume by train.")[^porte][^ellipses]. On 12 November, the author decides that the logic module may only be modified on his express order, and only to remove code from it[^conv]. On 13 and 14 November, two organs leave it in this way and are replaced by rules: Proteus inversion (what the "it" of "Guillaume did it" designates) and the quantity of a fact ("all", "no")[^conv][^ellipses]. Between 7 and 14 November, the FraCaS score rises from 106 to 200 problems solved out of 335[^fracasdoc].

---

## Architecture

### Nodal memory

Marco's memory is held in a thread table. Each thread links two *phares*; it carries a rank and the instant (*tic*) at which it was written[^lisez]. Everything the program knows is a *phare*: words, their senses, rules, contexts. Context is not a separate object: it is the instant of the thread[^hist]. The genome is read at instant zero, at the "birth" of the brain; lived experience is then written thread by thread. Nothing is erased: forgetting is itself a dated thread[^lisez].

### Genome

As of 14 November 2026, the genome comprises 322 text files and about 13.8 million rows[^etat]. It is built by programs from open lexical resources: Lefff, Lexique, GLAWI, the French Wiktionary, the Littré dictionary (XMLittré), Verbiste, *Les Verbes français*, and data from INSEE and Wikidata[^lisez]. The rule files are tables readable in a spreadsheet.

### The BSC language

BSC is the language in which the program's rules are written: rules put into equations (MEQ), "hexalines" and "cases", stored in the genome as rows[^lisez]. In the author's words, "the neuron is coded with the neuron": rules are *phares* described by other *phares*[^lisez].

Since November 2026, part of the deduction rules has been written as *cases*: small machines that read the sentence word by word and write what they draw from it into memory. Cases are grouped into stages. As of 14 November 2026, the reference program has ten stages and 538 cases: "see" (placing and comparing), "set" (quantifiers), "presentation" (constructions such as "there is … who"), "instruction" (the manner of answering), "quality" (the position of the adjective), "units" ("many"), "compare" (placing two things ahead, behind or side by side), "count" (comparing numbers, column addition), "door" (the universe opened by a problem's title, and the lines it keeps) and "action taken up again" (ellipses, 123 cases)[^etages][^porte][^ellipses]. A stage that settles a question answers with a short sentence giving its reason, for example "no, the adjective undoes the noun" (*non, l'adjectif défait le nom*)[^adj].

### Processor and kernel

The `processeur.py` module executes a small instruction set on triples. The `noyau.py` module acts as the operating system: it schedules moments, stages and organs[^lisez]. The Python code that still decides meaning, which the author calls the "casting burrs" (*barbes de fonderie*), is to be moved progressively into genome rows: this is *de-pythonization*[^lisez]. On 13 November the author gives its compass: "Processor: neurons, synapses, the chemistry of neurotransmitters. Electrique.py: the current that carries the signal."[^conv] As of 14 November 2026, the program has 29 modules and 34,370 lines of Python, of which 8,574 belong to the logic module (8,952 the morning before). The function-by-function analysis of that module still counts about 4,500 lines there that decide, to be moved into rules organ by organ, and about 2,800 lines of transport, which stay[^etat][^conv].

### Reading and dialogue

A single "ear" reads both a book and the line typed at the keyboard[^lisez]. Reading attaches each verb to its subject and complements, and resolves pronouns (*il*, *elle*) by the last mentioned referent, by default, or by the program's "culture"[^lisez]. The sense of a word is chosen among its possible "dimensions", according to the other words in the context[^lisez]. Parallel processes called *daimons* look for missing answers; a "hippocampus" compares the present with the past; a "control room" (*régie*) decides what is said[^lisez].

Example dialogue published by the project (translated from French)[^lisez]:

```
🧑 Paul heard the sound of the waves.
🤖 Paul heard the sound of the waves, I note it.
🧑 Paul heard the sea?
🤖 Yes, Paul heard the sea.
🧑 Paul smelled the smell of the sea?
🤖 I have Paul and smell and sea in my memory, but nothing tells me whether Paul smelled the smell of the sea.
```

Example from the FraCaS benchmark, run of 12 November 2026 (translated from French)[^fracasdoc]:

```
🧑 Jean is a former student.
🤖 Jean is a former student, I note it.
🧑 Jean is a student?
🤖 no, the adjective undoes the noun
```

Two ellipses from the same benchmark, run of 14 November 2026 (problems 142 and 147), as the benchmark records them (translated from French)[^fracasdoc]:

```
Premise   : Jean talked to Marie.
Premise   : Guillaume too.
Question  : Guillaume talked to Marie?
Marco     : yes, like Jean

Premise   : Jean talked to Marie on Monday.
Premise   : Guillaume did not do it.
Question  : Guillaume talked to Marie on Monday?
Marco     : no, unlike Jean
```

---

## Development method

The project is led by a single designer, José Walocha. The code, the genome and the benchmarks are written by instances of Claude (Anthropic), often two at a time in separate conversations: one for the code, the other for the doctrines[^lisez][^methode]. ChatGPT and Qwant are used for proofreading, summarising and documentary research; Mistral was used until 11 November 2026[^lisez]. Every architectural decision is recorded in a dated "doctrine"; none enters it without a sentence from the designer[^lisez]. The project's history keeps abandoned doctrines, to avoid reinventing them[^hist]. Measurements are made on fresh brains, born for the benchmark, with a fixed random seed[^lisez].

---

## Evaluations

The following results are published by the development team. They have not been independently reproduced: the program's source code is not published in the public repository.

| Benchmark | Measure | Marco's result | Point of comparison |
|---|---|---|---|
| Universal Dependencies (GSD and Sequoia) | subject, object or predicative complement of verbs | 23,689 / 32,077 (73.9%) — 4 November 2026 | — |
| FraCaS, French version | answer yes / no / unknown | 200 / 335 (59.7%) — 14 November 2026 | always "yes": 204 / 335 (60.9%) |
| Internal word-sense gold standard | sense chosen for each word | 315 / 474 (66%) | — |

### Universal Dependencies

Universal Dependencies is an international project of corpora annotated with syntactic dependencies[^ud]. Marco's benchmark covers 19,441 sentences from the French corpora GSD[^gsd] and Sequoia[^sequoia]. On 4 November 2026, Marco correctly attaches 23,689 verb subjects, objects and predicative complements out of 32,077, i.e. 73.9%[^lisez]. This measure covers only certain relations. It is not directly comparable with the attachment scores (UAS, LAS) usually published for syntactic parsers. A first test on 1 November, on 50 sentences, had found 45 subjects out of 62[^lisez].

### FraCaS

FraCaS is a suite of 346 natural-language inference problems, published in 1996[^fracas] and translated into French in 2020[^fracasfr]. Each problem gives one or more premises and a question, to be answered yes, no or "unknown". Of the 335 problems kept for scoring, Marco solves 200 (59.7%) on 14 November 2026, against 183 (54.6%) on 13 November, 166 (49.6%) on 12 November and 106 (31.6%) on 7 November[^fracasdoc][^lisez]. Answering "yes" to every problem would solve 204 (60.9%); always answering "unknown", 98 (29.3%). Marco's score therefore remains four problems below that of a systematic "yes".

On 14 November, Marco answers "yes" 144 times, 116 of them correctly; "no" 18 times, 17 of them correctly; "unknown", or an answer that is neither yes nor no, 173 times, 67 of them correctly. Its main weakness is still failing to find an expected "yes": it does not give it in 88 of the 204 problems whose answer is "yes" (95 the day before)[^fracasdoc].

| Section | Solved |
|---|---|
| Adjectives | 22 / 22 |
| Generalized quantifiers | 59 / 74 |
| Verbs | 6 / 8 |
| Attitudes | 8 / 13 |
| Plurals | 14 / 33 |
| Comparatives | 29 / 31 |
| Ellipsis | 33 / 55 |
| Temporal reference | 21 / 71 |
| Anaphora | 8 / 28 |

The adjectives section rises from 4 to 22 problems solved out of 22 in the course of 12 November. The rule adopted by the author: an adjective stated without a reference qualifies; stated with a reference ("a small animal"), it compares within that reference[^adj]. Quantifiers have been read since 11 November. Five problems solved by an earlier version were lost on 12 November, when the Python code that handled them was removed; they are to be rewritten as rules[^conv].

On 13 November, reading comparatives ("faster than", "as fast as") raises that section from 12 to 29 problems solved out of 31[^fracasdoc]. Two of the comparatives still missed are due to a reading choice: the team reads "as fast as" as an equality, whereas FraCaS takes it to mean "at least as fast"[^voir]. The author regards the score as secondary: "the main thing is to have a MAD [deduction machine] that makes logical deductions"[^fracasdoc].

On 13 and 14 November, the ellipsis section rises from 17 to 33 problems solved out of 55. An ellipsis does not repeat its verb: "Jean talked to Marie. Guillaume too." For the author, the second character holds the handle of the first one's action: nothing is copied or restated[^ellipses]. The rules read three signals, "too" without a verb, "do it" and the line without a verb, then rebuild the sentence piece by piece: in "Jean went to Paris by car and Guillaume by train", "by train" takes the place of "by car", and "to Paris" is kept[^ellipses]. These rules only read the universe of the current problem, held by its "door"[^porte]. The same day, problem 105 ("Exactly one accountant attended the meeting. None of the accountants attended the meeting?": no) is won by reading zero as rules. The temporal reference (21 of 71) and anaphora (8 of 28) sections remain the least solved. For the author, the benchmark is no longer anecdotal: Marco is "on the road to the inference of MADs" (14 November 2026).

### Internal word-sense gold standard

The gold standard covers ten texts from the program's reading book, from *Frère Jacques* to *Le Dormeur du val*, by way of La Fontaine, Perrault and *La Chèvre de M. Seguin*. It gives the expected sense of 474 words. Marco chooses the right sense in 66% of cases (315 out of 474); 75% on *La Chèvre de M. Seguin*, 73% on *Le Dormeur du val*[^lisez]. The gold standard was annotated by an assistant (Claude Opus 5.5) without seeing Marco's choices; it has yet to be validated by the author. This measure is internal to the project and cannot be compared with a public benchmark.

---

## Comparisons and influences

### Cyc

The project's documentation compares Marco with Cyc[^lisez]. That program, launched in 1984 by Douglas Lenat, also relies on explicit knowledge and rules rather than statistical learning[^cyc]. Initial estimates for Cyc ranged from 1,000 to 3,000 person-years. In 2017, Cyc had about 24 million rules and assertions, largely entered by hand, for some 2,000 person-years of work[^cyc].

Marco's genome, by contrast, is built by programs from open dictionaries, and the project is run by a single person with automated assistants[^lisez]. The documentation states that Marco "does not claim to equal" Cyc[^lisez].

### Hofstadter

The author traces his project back to a question he has been asking himself for forty years: how can a neuron carry a concept such as *verb*? He cites as his starting point Douglas Hofstadter's *Gödel, Escher, Bach*[^geb], published in French in 1985[^lisez]. He takes three ideas from it: the symbol is an active subsystem; the ant colony thinks although no ant thinks; the "strange loop" makes reading into the reader[^lisez].

---

## Goals

The project states that it aims at a microprocessor that runs Marco, with its thread memory[^lisez]. According to the author, de-pythonization leads there: once all decisions of meaning are written as genome rows, only a processor with a reduced instruction set will remain, transposable into silicon[^lisez]. The other announced projects are understanding the sense of 100% of the words read, moving all deduction logic into genome rules, and reading and summarising a novel, Balzac's *Eugénie Grandet*[^lisez][^conv].

---

## Reception

As of November 2026, Marco has not been the subject of any publication in a scientific journal or conference, nor of any press articles. Its results have not been evaluated by third parties.

---

## See also

- [Cyc](https://en.wikipedia.org/wiki/Cyc)
- [Expert system](https://en.wikipedia.org/wiki/Expert_system)
- [Symbolic artificial intelligence](https://en.wikipedia.org/wiki/Symbolic_artificial_intelligence)
- [Universal Dependencies](https://universaldependencies.org/)
- [FraCaS in French](https://gitlab.inria.fr/semagramme-public-projects/resources/french-fracas)
- [Douglas Hofstadter](https://en.wikipedia.org/wiki/Douglas_Hofstadter)

---

## References

[^lisez]: José Walocha, *MARCO — Bionic processor with nodal memory* ([README.md](README.md)), josewalocha/Marco repository, as of 8 November 2026. French original: [LisezMoi.md](LisezMoi.md).

[^hist]: José Walocha, *MARCO — Development history to date* ([Development_history.md](Development_history.md)), josewalocha/Marco repository, from the beginnings to 14 October 2026. French original: [Historique_du_developpement.md](Historique_du_developpement.md).

[^fracasdoc]: José Walocha, *BANC — FraCaS*, project doctrine (BANC_FraCaS.html), as of 14 November 2026; benchmark runs of 12 November 2026 (fracas_2026-11-12_python_sorti.txt), 13 November 2026 (fracas_2026-11-13_comparatifs.txt) and 14 November 2026 (fracas_simple_2026-11-14_11h17.txt), the latter run by the author. Internal documentation, not published in the public repository. In French.

[^adj]: José Walocha, *ADJECTIF — qualifier ou comparer*, project doctrine (ADJECTIF_qualifier_ou_comparer.html), 13 November 2026. Internal documentation, not published in the public repository. In French.

[^voir]: José Walocha, *FLUX — voir, c'est comparer*, project doctrine (FLUX_voir_c_est_comparer.html), as of 13 November 2026. Internal documentation, not published in the public repository. In French.

[^etages]: José Walocha, *LANGAGES — le joueur unique*, project doctrine (LANGAGES_le_joueur_unique.html), as of 14 November 2026. Internal documentation, not published in the public repository. In French.

[^porte]: José Walocha, *CONTEXTE — l'univers et sa porte*, project doctrine (CONTEXTE_l_univers_et_sa_porte.html), as of 14 November 2026. Internal documentation, not published in the public repository. In French.

[^ellipses]: José Walocha, *CONTEXTE — tenir et croiser*, project doctrine (CONTEXTE_tenir_et_croiser.html), strata of 14 November 2026: the action taken up again, quantity as rules. Internal documentation, not published in the public repository. In French.

[^conv]: José Walocha, *LANGAGES — histoire des conversions*, project doctrine (LANGAGES_7_histoire_des_conversions.html), § 14 and 15, 13 and 14 November 2026. Internal documentation, not published in the public repository. In French.

[^methode]: José Walocha, *Méthode de travail*, project doctrine (00Methode_de_travail.html), as of 13 November 2026. Internal documentation, not published in the public repository. In French.

[^etat]: Marco program, state as of 14 November 2026 (the author's demonstration version, unpublished): counts of Python modules, lines of code and genome files.

[^lvf]: Jean Dubois and Françoise Dubois-Charlier, *Les Verbes français*, Paris, Larousse, 1997.

[^ud]: Universal Dependencies, [universaldependencies.org](https://universaldependencies.org/).

[^gsd]: Bruno Guillaume, Marie-Catherine de Marneffe and Guy Perrier, "Conversion et améliorations de corpus du français annotés en Universal Dependencies", *Traitement Automatique des Langues*, vol. 60, no. 2, 2019, pp. 71–95.

[^sequoia]: Marie Candito and Djamé Seddah, "Le corpus Sequoia : annotation syntaxique et exploitation pour l'adaptation d'analyseur par pont lexical", *Actes de la conférence JEP-TALN-RECITAL 2012*, vol. 2: TALN, Grenoble, ATALA/AFCP, 2012, pp. 321–334.

[^fracas]: Robin Cooper, Dick Crouch, Jan van Eijck, Chris Fox, Josef van Genabith, Jan Jaspars, Hans Kamp, David Milward, Manfred Pinkal, Massimo Poesio and Steve Pulman, *Using the Framework*, FraCaS, deliverable D16, January 1996.

[^fracasfr]: Maxime Amblard, Clément Beysson, Philippe de Groote, Bruno Guillaume and Sylvain Pogodalla, "A French Version of the FraCaS Test Suite", *Proceedings of the Twelfth Language Resources and Evaluation Conference (LREC 2020)*, Marseille, ELRA, 2020, pp. 5887–5895. Resource licensed under CC BY-NC-SA 4.0.

[^cyc]: "Cyc", *Wikipedia*, [en.wikipedia.org/wiki/Cyc](https://en.wikipedia.org/wiki/Cyc).

[^geb]: Douglas Hofstadter, *Gödel, Escher, Bach: An Eternal Golden Braid*, New York, Basic Books, 1979; French translation *Gödel, Escher, Bach : les Brins d'une Guirlande Éternelle*, Paris, InterÉditions, 1985.
