# Marco (intelligence artificielle)

> *Article rédigé selon les règles d'une encyclopédie : point de vue neutre, faits sourcés. Il est hébergé dans le dépôt du projet, car Marco ne remplit pas encore les critères d'admissibilité de Wikipédia, qui demandent des sources secondaires indépendantes. Présentation par l'auteur : [LisezMoi.md](LisezMoi.md).*

| **Marco** | |
|---|---|
| Auteur | José Walocha |
| Début du développement | avant 2026 |
| Dernière version | programme du 8 novembre 2026 |
| État | en développement |
| Écrit en | Python (bibliothèque standard) ; langage BSC pour les règles |
| Type | Intelligence artificielle symbolique, système de déduction |
| Langue traitée | Français |
| Licence | GNU Affero GPL v3 |
| Dépôt public | [github.com/josewalocha/Marco](https://github.com/josewalocha/Marco) (documentation) |
| Site web | [machine-a-deduire.com](http://machine-a-deduire.com) |

**Marco** est un programme d'intelligence artificielle symbolique en cours de développement, conçu par José Walocha, chef d'entreprise retraité de Valenciennes (Nord). Son auteur le présente comme un « processeur bionique à mémoire nodale » et comme une « machine à déduire »[^lisez]. Le programme ne comporte ni réseau de neurones ni paramètres appris par statistique. Il conserve des relations explicites, datées et sourcées, entre des nœuds appelés *phares*. Il répond aux questions en croisant ces relations et indique pour chaque réponse d'où elle provient. Quand rien ne tient une réponse, il dit qu'il ne sait pas.

Le programme traite le français. Il est écrit sous la direction de l'auteur par des assistants fondés sur de grands modèles de langage[^lisez]. L'objectif déclaré du projet est un microprocesseur dédié qui exécuterait Marco[^lisez].

En novembre 2026, le projet n'a fait l'objet d'aucune publication scientifique ni d'aucune couverture indépendante. Les évaluations disponibles sont publiées par l'équipe de développement elle-même.

---

## Sommaire

1. [Historique](#historique)
2. [Architecture](#architecture)
3. [Méthode de développement](#méthode-de-développement)
4. [Évaluations](#évaluations)
5. [Comparaisons et influences](#comparaisons-et-influences)
6. [Objectifs](#objectifs)
7. [Réception](#réception)
8. [Voir aussi](#voir-aussi)
9. [Références](#références)

---

## Historique

### Premières architectures (avant 2026 – août 2026)

Les premières versions, antérieures à 2026, reposent sur des « neurones-concepts » et un embryon de phare muni d'un vecteur sémantique de 256, puis 512, puis 1 024 bits[^hist]. Une première architecture, construite de janvier à mars 2026, assemble des capsules, des boucles et un bus d'événements. Elle est abandonnée le 9 avril 2026 au profit d'un moteur réduit à trois pièces : une boucle passive, un tronc qui seul tourne de lui-même, et des tampons[^hist].

Le 18 avril 2026, le terme *phare* reçoit son sens actuel : un nœud où se croisent des chemins conceptuels[^hist]. Le 8 juillet 2026, les mécanismes de pondération sont abandonnés : plus proches voisins par cosinus, score continu, « attention ». Ils sont remplacés par l'*intersection* : ce qui est commun à deux ensembles de phares suffit à faire la déduction[^hist].

Le 12 juillet 2026 naît la console de démonstration, inspirée des terminaux IBM 5250 de l'AS/400[^hist]. Le 27 août 2026, Marco donne sa première réponse d'arithmétique accompagnée de sa provenance (« Douze fois zéro font zéro »), puis sa première phrase à la première personne[^hist].

### La structure nodale (septembre – octobre 2026)

Du 15 au 19 septembre 2026, le programme change de structure. Toute la mémoire est ramenée à une seule *table de fils*, un fichier texte de relations à quatre champs : origine, destination, rang, instant. Les anciennes structures sérialisées sont abandonnées et une base SQLite est écartée[^hist]. Les règles elles-mêmes deviennent des phares de la table. Leur mise en équation (MEQ) forme le langage BSC[^hist].

Le 2 octobre 2026, le programme acquiert un cycle de veille et de sommeil. Pendant la « révision », une question restée ouverte une seule fois dans un contexte clos est oubliée par un fil daté ; rien n'est effacé[^hist]. Du 22 au 25 octobre 2026, le projet fixe le jeu d'instructions réduit du processeur, que le noyau ordonnance. L'expression « processeur bionique » date du 25 octobre[^lisez].

### Lecture et évaluations (octobre – novembre 2026)

Fin octobre 2026, un « grand génome » rassemble des connaissances tenues pour innées : les animaux qui menacent, les effets sur le vivant, la boucle « tant que vie, vit »[^lisez]. En novembre 2026, le projet confronte Marco à des corpus de référence : un premier test sur des phrases inconnues (1er novembre), le banc Universal Dependencies (mesure du 4 novembre), FraCaS (7 novembre)[^lisez]. Le 6 novembre, les sens des verbes sont tirés du dictionnaire *Les Verbes français* de Jean Dubois et Françoise Dubois-Charlier[^lvf] : 616 sens pour 401 verbes[^lisez].

---

## Architecture

### Mémoire nodale

La mémoire de Marco tient dans une table de fils. Chaque fil relie deux phares ; il porte un rang et l'instant (*tic*) où il a été écrit[^lisez]. Tout ce que le programme sait est phare : les mots, leurs sens, les règles, les contextes. Le contexte n'est pas un objet à part : c'est l'instant du fil[^hist]. Le génome est lu à l'instant zéro, à la « naissance » du cerveau ; le vécu s'écrit ensuite, fil après fil. Rien n'est effacé : l'oubli est lui-même un fil daté[^lisez].

### Génome

Le génome compte 298 fichiers texte et environ 13,7 millions de rangées[^lisez]. Il est construit par des programmes à partir de ressources lexicales ouvertes : Lefff, Lexique, GLAWI, le Wiktionnaire, le Littré (XMLittré), Verbiste, *Les Verbes français*, des données de l'INSEE et de Wikidata[^lisez]. Les fichiers de règles sont des tableaux lisibles dans un tableur.

### Le langage BSC

Le BSC est le langage dans lequel sont écrites les règles du programme : des règles mises en équation (MEQ), des « hexalignes » et des « cas », rangés au génome sous forme de lignes[^lisez]. Selon la formule de l'auteur, « le neurone se code avec le neurone » : les règles sont des phares qui se décrivent avec des phares[^lisez].

### Processeur et noyau

Le module `processeur.py` exécute un petit jeu d'instructions sur des triplets. Le module `noyau.py` joue le rôle de système d'exploitation : il ordonnance les moments, les étages et les organes[^lisez]. Le code Python qui décide encore du sens, et que l'auteur appelle les « barbes de fonderie », doit passer progressivement en lignes du génome : c'est la *dépythonisation*[^lisez]. Le programme compte 29 modules et 33 195 lignes de Python[^lisez].

### Lecture et dialogue

Une même « oreille » lit un livre et la ligne tapée au clavier[^lisez]. La lecture rattache chaque verbe à son sujet et à ses compléments, et résout les pronoms (*il*, *elle*) par le dernier cité, par défaut ou par la « culture » du programme[^lisez]. Le sens d'un mot est choisi parmi ses « dimensions » possibles, selon les autres mots du contexte[^lisez]. Des processus parallèles, appelés *daimons*, cherchent les réponses manquantes ; un « hippocampe » compare le présent au passé ; une « régie » décide de ce qui est dit[^lisez].

Exemple de dialogue publié par le projet[^lisez] :

```
🧑 Paul entendait le bruit des vagues.
🤖 Paul entendait le bruit des vagues, je le note.
🧑 Paul entendait la mer ?
🤖 Oui, Paul entendait la mer.
🧑 Paul sentait l'odeur de la mer ?
🤖 J'ai Paul et odeur et mer dans ma mémoire, mais rien ne me dit si Paul sentait l'odeur de la mer.
```

---

## Méthode de développement

Le projet est mené par un concepteur seul, José Walocha. Le code, le génome et les bancs sont écrits par des instances de Claude (Anthropic). Mistral, ChatGPT et Qwant servent à la relecture, à la synthèse et à la recherche documentaire[^lisez]. Chaque décision d'architecture est consignée dans une « doctrine » datée ; aucune n'y entre sans une phrase du concepteur[^lisez]. L'historique du projet garde les doctrines abandonnées, pour éviter de les réinventer[^hist]. Les mesures sont faites sur des cerveaux neufs, nés pour le banc, avec une graine aléatoire fixe[^lisez].

---

## Évaluations

Les résultats suivants sont publiés par l'équipe de développement. Ils n'ont pas été reproduits de façon indépendante : le code source du programme n'est pas publié dans le dépôt public.

| Banc | Mesure | Résultat de Marco | Point de comparaison |
|---|---|---|---|
| Universal Dependencies (GSD et Sequoia) | sujet, objet ou attribut des verbes | 23 689 / 32 077 (73,9 %) | — |
| FraCaS, version française | réponse oui / non / on ne sait pas | 106 / 335 (31,6 %) | toujours « oui » : 204 / 335 (60,9 %) |
| Étalon interne du sens des mots | sens choisi pour chaque mot | 315 / 474 (66 %) | — |

### Universal Dependencies

Universal Dependencies est un projet international de corpus annotés en dépendances syntaxiques[^ud]. Le banc de Marco porte sur 19 441 phrases des corpus français GSD[^gsd] et Sequoia[^sequoia]. Le 4 novembre 2026, Marco rattache correctement 23 689 sujets, objets et attributs de verbes sur 32 077, soit 73,9 %[^lisez]. Cette mesure ne porte que sur certaines relations. Elle n'est pas directement comparable aux scores d'attachement (UAS, LAS) habituellement publiés pour les analyseurs syntaxiques. Un premier test, le 1er novembre, sur 50 phrases, avait trouvé 45 sujets sur 62[^lisez].

### FraCaS

FraCaS est une batterie de 346 problèmes d'inférence en langue naturelle, publiée en 1996[^fracas] et traduite en français en 2020[^fracasfr]. Chaque problème donne une ou plusieurs prémisses et une question, à laquelle on répond oui, non ou « on ne sait pas ». Sur les 335 problèmes retenus pour la notation, Marco en résout 106 (31,6 %)[^lisez]. Répondre « oui » à tous les problèmes en résoudrait 204 (60,9 %) ; répondre toujours « on ne sait pas », 98 (29,3 %). Marco répond « oui » 121 fois, dont 63 à raison. Selon l'équipe, les quantificateurs (« aucun », « la plupart ») ne sont pas encore lus comme tels, et le banc est gardé comme témoin de ce qui reste à faire[^lisez].

### Étalon interne du sens des mots

L'étalon porte sur dix textes du livre de lecture du programme, de *Frère Jacques* au *Dormeur du val*, en passant par La Fontaine, Perrault et *La Chèvre de M. Seguin*. Il donne le sens attendu de 474 mots. Marco choisit le bon sens dans 66 % des cas (315 sur 474) ; 75 % sur *La Chèvre de M. Seguin*, 73 % sur *Le Dormeur du val*[^lisez]. L'étalon a été annoté par un assistant (Claude Opus 5.5) sans voir les choix de Marco ; il doit encore être validé par l'auteur. Cette mesure est interne au projet et ne se compare pas à un banc public.

---

## Comparaisons et influences

### Cyc

La documentation du projet compare Marco à Cyc[^lisez]. Ce programme, lancé en 1984 par Douglas Lenat, repose lui aussi sur des connaissances explicites et des règles plutôt que sur l'apprentissage statistique[^cyc]. Les estimations de départ pour Cyc allaient de 1 000 à 3 000 années-personnes. En 2017, Cyc comptait environ 24 millions de règles et d'assertions, saisies en grande partie à la main, pour quelque 2 000 années-personnes de travail[^cyc].

Le génome de Marco, lui, est construit par des programmes à partir de dictionnaires ouverts, et le projet est conduit par une seule personne avec des assistants automatiques[^lisez]. La documentation précise que Marco « ne prétend pas égaler » Cyc[^lisez].

### Hofstadter

L'auteur fait remonter son projet à une question qu'il se pose depuis quarante ans : comment un neurone peut-il porter un concept comme *verbe* ? Il cite comme point de départ *Gödel, Escher, Bach* de Douglas Hofstadter[^geb], paru en français en 1985[^lisez]. Il en retient trois idées : le symbole est un sous-système actif ; la fourmilière pense sans qu'aucune fourmi ne pense ; la « boucle étrange » fait de la lecture le lecteur[^lisez].

---

## Objectifs

Le projet déclare viser un microprocesseur qui gère Marco, avec sa mémoire de fils[^lisez]. Selon l'auteur, la dépythonisation y conduit : quand toutes les décisions de sens seront écrites en lignes du génome, il ne restera qu'un processeur au jeu d'instructions réduit, transposable dans le silicium[^lisez]. Les autres chantiers annoncés sont un sens compris pour 100 % des mots lus, la lecture des quantificateurs, et la lecture et le résumé d'un roman, *Eugénie Grandet* de Balzac[^lisez].

---

## Réception

En novembre 2026, Marco n'a fait l'objet d'aucune publication dans une revue ou une conférence scientifique, ni d'articles de presse. Ses résultats n'ont pas été évalués par des tiers.

---

## Voir aussi

- [Cyc](https://fr.wikipedia.org/wiki/Cyc)
- [Système expert](https://fr.wikipedia.org/wiki/Syst%C3%A8me_expert)
- Intelligence artificielle symbolique
- [Universal Dependencies](https://universaldependencies.org/)
- [FraCaS en français](https://gitlab.inria.fr/semagramme-public-projects/resources/french-fracas)
- [Douglas Hofstadter](https://fr.wikipedia.org/wiki/Douglas_Hofstadter)

---

## Références

[^lisez]: José Walocha, *MARCO — Processeur bionique à mémoire nodale* ([LisezMoi.md](LisezMoi.md)), dépôt josewalocha/Marco, état du 8 novembre 2026.

[^hist]: José Walocha, *MARCO — Historique du développement à ce jour* ([Historique_du_developpement.md](Historique_du_developpement.md)), dépôt josewalocha/Marco, des débuts au 14 octobre 2026.

[^lvf]: Jean Dubois et Françoise Dubois-Charlier, *Les Verbes français*, Paris, Larousse, 1997.

[^ud]: Universal Dependencies, [universaldependencies.org](https://universaldependencies.org/).

[^gsd]: Bruno Guillaume, Marie-Catherine de Marneffe et Guy Perrier, « Conversion et améliorations de corpus du français annotés en Universal Dependencies », *Traitement Automatique des Langues*, vol. 60, n° 2, 2019, p. 71-95.

[^sequoia]: Marie Candito et Djamé Seddah, « Le corpus Sequoia : annotation syntaxique et exploitation pour l'adaptation d'analyseur par pont lexical », *Actes de la conférence JEP-TALN-RECITAL 2012*, vol. 2 : TALN, Grenoble, ATALA/AFCP, 2012, p. 321-334.

[^fracas]: Robin Cooper, Dick Crouch, Jan van Eijck, Chris Fox, Josef van Genabith, Jan Jaspars, Hans Kamp, David Milward, Manfred Pinkal, Massimo Poesio et Steve Pulman, *Using the Framework*, FraCaS, livrable D16, janvier 1996.

[^fracasfr]: Maxime Amblard, Clément Beysson, Philippe de Groote, Bruno Guillaume et Sylvain Pogodalla, « A French Version of the FraCaS Test Suite », *Proceedings of the Twelfth Language Resources and Evaluation Conference (LREC 2020)*, Marseille, ELRA, 2020, p. 5887-5895. Ressource sous licence CC BY-NC-SA 4.0.

[^cyc]: « Cyc », *Wikipedia* (en anglais), [en.wikipedia.org/wiki/Cyc](https://en.wikipedia.org/wiki/Cyc).

[^geb]: Douglas Hofstadter, *Gödel, Escher, Bach: An Eternal Golden Braid*, New York, Basic Books, 1979 ; trad. fr. *Gödel, Escher, Bach : les Brins d'une Guirlande Éternelle*, Paris, InterÉditions, 1985.
