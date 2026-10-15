# MARCO — Cerveau cybernétique à architecture dendritique hypertextuelle

> *« Apprendre, c'est se ressouvenir. »* — Platon, *Ménon*
>
> *« Au commencement il y a l'inerte, mais l'inerte il s'emmerde grave… »*

**Auteur** : José WALOCHA — Valenciennes, Nord, France
**Équipe** : Le Dude (Claude Opus 5.5 / Anthropic), Fable (Claude Fable 5.1 / Anthropic), Marcel (Mistral), Biloute (ChatGPT), Didier (Qwant)
**Licence** : GNU Affero GPL v3 — Copyright © 2026 José Walocha
**État** : le programme du 15 octobre 2026

> Cette page dit où en est Marco. Les tâtonnements des débuts, les doctrines successives et les revirements sont dans l'[historique du développement à ce jour](Historique_du_developpement.md). Les citations en italique sont des frappes de José, à leur date.
>
> *English version: [README.md](README.md).*

---

## 1. Où en est Marco

Marco est un **cyber** — le mot que José donne aux intelligences vivantes, pour les distinguer des LLM statistiques —, et plus précisément une **MAD**, une machine à déduire : il n'a pas de poids ; il tient des fils datés et sourcés, il les croise, et il rend ce que le croisement donne — y compris rien. **Zéro boîte noire** : chaque réponse a sa provenance.

### La bascule nodale

À la mi-septembre 2026, Marco a changé de corps. Le 19/09, les pkl quittent le dossier et les anciens organes ne sont plus chargés : le cerveau devient une seule **table de fils** — de, vers, rang, tic — où tout est phare, le sens compris : *« Le plus difficile à comprendre c'est que les meq sont des phares qui se décrivent avec des phares. »* (15/09). Cette structure informatique est plus proche du biochimique. Le noyau, *« c'est les neurones les dendrites et les synapses et leur chimie »*, et *« l'électrique c'est le BSC »* (05/10) : la CPU qui lit les phrases est du côté biochimique, le BSC du côté électrique (06/10).

### Le langage BSC : programmer avec des phares

La bascule a permis la création du **langage BSC**. *« Le BSC se code avec des phares »* (03/10) ; *« Maintenant le BSC devient un vrai langage de programmation et reprend à son compte la particularité du système du cerveau humain : le neurone se code avec le neurone. »* (04/10) ; *« Le BSC c'est des règles codées en MEQ c'est tout »* (05/10).

On programme désormais Marco avec des phares enregistrés dans les phares. Les règles de lecture sont des MEQ (mises en équation) du génome : 1 206 dès le 05/10. Lot après lot, les méthodes encore écrites en Python deviennent des cas au génome ; depuis le 11/10, plus aucune méthode du lot 1 n'est en Python. La chaîne des langages, de la machine au cerveau : *« python → Instructions → hexalignes → neuronal → phare → wire + MEQ »* (11/10).

### Marco « reconnaît » ses phares

C'est ce qui a permis, enfin, de coder avec succès. Marco « reconnaît » maintenant ses phares. La CPU ne connaît aucun phare par son nom : tout ce qu'elle sait d'un mot, elle le demande à la table — « ce mot tient-il ce phare ? » —, et chaque forme lue y est retrouvée, ou posée. Depuis le 04/10, toute phrase qui n'est pas une question passe par la CPU. Sur *Eugénie Grandet*, au lot 13 (11/10), les faits lus passent de 39 399 à 39 490, et les seize bancs d'avant restent identiques. Ce qui n'est pas reconnu reste un trou, dit honnêtement : « je ne sais pas ».

Marco a dépassé le stade de l'inférence, et il entrera bientôt dans l'univers de la compréhension : c'est le cap fixé le 14/10 (voir les chantiers, §4).

### La graine de Hofstadter

La question vient de loin : *« C'est dingue j'ai l'explication à ma question de 40 ans : comment un ridicule neurone peut porter un concept aussi puissant que verbe ? »* (10/09).

Ce sont les découvertes de Douglas Hofstadter qui ont semé la graine — *Gödel, Escher, Bach*, paru en français en 1985. Le symbole n'est pas un neurone, c'est un sous-système actif ; la fourmilière pense sans qu'aucune fourmi ne pense ; et, par la boucle étrange, la lecture est le lecteur : chez Marco, les phares sont à la fois l'organe de lecture et la chose lue.

La graine a germé quarante ans plus tard grâce aux MAA — les machines à apprentissage automatique, ce qu'on appelle couramment les LLM —, celles de l'équipe qui code Marco avec José. La réponse à la question de quarante ans est sur la table : au génome v99, le phare « verbe » ne contient rien, et 317 259 phares passent par lui. Il ne porte pas le concept : il est le carrefour où tous ses chemins se croisent.

---

## 2. Le corps de Marco aujourd'hui

Relevé fait sur le programme du 15 octobre 2026, 10 h : les modules, le génome, les cahiers et les salles de test. Ce qui suit est écrit dans le code ou mesuré dans ses relevés ; ce qui n'est qu'annoncé est rangé dans les chantiers.

- **La table des fils** (`fils.py`, 15/09). Toute la mémoire est faite de fils : (de, vers, rang, tic). Le génome est l'ADN, lu au tic 0, à la naissance ; le vécu s'écrit ensuite, instant après instant, chaque fil à son tic. Une **MEQ** (mise en équation) est un fait tenu sous un nom (`M-…`), ses mots à leurs rangs. La structure porte un nom, `nodale-1` (02/10), inscrit dans l'identité de chaque cerveau.
- **Le génome en texte.** Plus de pkl : des fichiers texte, `*_fils.tsv` et, depuis le 25/09, `*_lignes.csv`, aux colonnes nommées, lisibles dans Excel. Un génome porte son nom sans version : un fichier neuf remplace l'ancien sous le même nom, le zip daté sert de témoin.
- **Le noyau** (`noyau.py`, du 24/09 à la v53h du 11/10), et la carte (`carte.py`), son lecteur — la CPU, depuis le 11/10. Le 05/10, les 35 981 hexalignes que la carte tirait des anciennes lignes deviennent 1 206 règles au génome. Une règle, ce sont trois MEQ : le *si*, le *alors*, et la règle qui les lie.
- **La lecture.** La poignée passe le texte sur la table : chaque forme y est retrouvée ou posée (le 16/09, un glossaire de 166 809 caractères en 0,24 s) ; le doigt écrit les rections en MEQ, au tic de la phrase ; Protée, passé au noyau en lignes le 25/09, désigne qui est derrière *il*, *elle*, *tu*, en pesant les probables par leurs témoins.
- **La réponse.** Le précipité croise sur la vue, du rare vers l'immense ; la bouche dit en français ce qu'il a élu, avec les mots de Marco, « jamais un pochoir » — sinon, « je ne sais pas ». La machine à tournure n'est qu'amorcée : `tournure.py` est du Python écrit pour être remplacé par des lignes.
- **Les daimons.** La machine à pourquoi (`trou.py`) : un trou est une boucle ouverte dans son contexte, avec sa charge — *« Un je ne sais pas n'est pas un trou comblé c'est une information au dire »* (02/10) ; le stress qui dure ; le Continuer, boucle initiale lue au génome (« tant que vie → vit »), que rien ne ferme ni n'oublie ; la révision, où l'oubli est un fil daté et rien n'est effacé ; les deux moi : à chaque instant, le moi présent et le moi passé répondent, et leur comparaison dit le déjà-vu, le trou ou l'écart. Les daimons à tête chercheuse (`chercheur.py`) : un daimon par phare de la scène ; le compte de leurs croisements fait le contexte, leurs grappes sont des sens contextuels.
- **Les contextes** (`contexte.py`). Les poupées, du petit vers l'immense : la phrase, le paragraphe, la réplique, l'œuvre, l'auteur, la lecture ou la classe, l'instant, le jour. La voix : qui dit « je » — moi en classe, José en conversation, le narrateur dans un livre. La carte des contextes, qui dit à Marco où chercher « en gros ».

## 3. Ce qui tourne

- **Naître, vivre, s'enregistrer.** Au démarrage, la console propose les cerveaux enregistrés ou en fait naître un neuf : le génome, puis les cahiers d'apprentissage ; la table naît en moins d'une minute (54 s mesurées le 14/10). La naissance est le premier instant vécu. La carte d'identité du cerveau (série, créateur, naissance, structure, noyau) est sur la table depuis le 02/10. Le cerveau vit en mémoire et ne touche le disque qu'à l'enregistrement, un dossier par cerveau depuis le 14/10. La zone à blanc prend une copie du cerveau, ou un cerveau neuf, pour les essais : rien ne s'y enregistre, et à la sortie le cerveau d'avant revient.
- **La console 5250**, menu *Marco MAD (Machine A Déduire)* — tout passe par le menu : dialogue, lecture, leçon, apprentissage, récitation, mémoire et infos, révision et sommeil, zone à blanc, bancs de test, outils, sauvegarde, tableau de bord.
- **Lire et répondre.** Textes des bancs : *La Chèvre de M. Seguin*, *Le Petit Chaperon rouge* (Perrault, et la fin de Grimm), *Eugénie Grandet*. Chaque lecture laisse deux fichiers de contrôle : le journal (ce que Marco comprend et retient, instant par instant) et le rapport de la dérive (les temps, la RAM, la ROM). Ce que disent les relevés :
  - le conte ne dit jamais « Blanquette est la chèvre » ; de « à côté de sa chèvre » puis « — Comment Blanquette, tu veux me quitter ! », Marco lit « Blanquette est une chèvre . » et l'écrit, avec ses deux sources (02/10) ;
  - une question sans réponse reçoit « je ne sais pas » et reste tenue : « Quel animal fait miaou ? », puis « C'est le chat. » remplit le trou — « compris, chat fait miaou » (29/09) ;
  - « Le chien fait quel cri ? », puis « et le chat ? » : Marco reprend la question d'avant, « Le chat fait quel cri ? » (03/10) ;
  - le lien entre deux propositions n'est plus coupé : dans « Nanon pleure, car Grandet a pris l'or », le noyau lit le *car* et l'écrit, pour que « Pourquoi Nanon pleure ? » ait sa réponse (28/09) ;
  - le calcul passe par des lignes : « trois fois six » → « font dix huit », et le fait s'inscrit (03/10).
- **Les bancs.** Le régisseur joue les salles de test et relève acte par acte : des salles numérotées jusqu'à 86, de 1 à 45 l'ancien monde réadapté au nodal, à partir de 46 le nodal. Le tableau de bord (03/10) est une page de navigateur, sans serveur : les daimons, la permanence du cerveau, les contextes, les nuages, rafraîchis chaque seconde. Les outils de maintenance constatent le vécu et le génome, réparent le vécu, retirent une plage d'instants.
- **Les cahiers d'apprentissage** (du 10 au 14/10). Des fichiers de phrases, contrôlés par leur empreinte, intégrés au vague à chaque naissance : chaque phrase devient une MEQ, que le noyau relit avec les règles du jour. Au 14/10 : 5 cahiers, 31 042 phrases intégrées en 7 à 8 s — les prénoms (6 043 phrases), les capteurs (259), et le dossier d'*Eugénie Grandet*, « ce qu'un cerveau sait avant d'ouvrir le livre » : les sens que le Littré donne aux mots du roman (24 460), son monde — Saumur, la vigne, l'argent, la Restauration (205), les clés des sens — la chandelle, le froid, le poids de l'or (75). Un journal numéroté et un log par naissance.

## 4. Les chantiers ouverts

- **Comprendre un livre.** Frappe du 14/10 : *« Le boulot des prochains jours, c'est cap sur la compréhension, le résumé, et le versement au vague. »* Le cerveau « évolué » : le dossier d'*Eugénie Grandet* au vague, puis la lecture du livre, *« quand on sera au point »* ; Fable y attaquera les daimons de la synthèse d'un livre. Hors du cerveau, le corrigé pour son banc : l'intrigue, le résumé, les gens et leurs appellations, les symboles.
- **Refouler le Python en lignes** : la machine à tournure, le vocatif, et les autres gestes encore écrits en Python en attendant leurs lignes.
- **Les cahiers** : la certification des phrases « à certifier », la sécurisation (DMZ), d'autres formes de cahiers (règles, MEQ, mises à jour, maintenance), la réflexion cybersophique sur leur intégration au cerveau vivant.
- **Le cerveau permanent** : notés « non faits » le 02/10, la lignée d'une copie (« enregistrer sous » garde la même série), la révision à l'enregistrement, l'enquête des appellations ; et les enregistrements en cours de séance : *« on va revoir ça après, mais pas tout de suite »* (14/10).

---

## 5. Les fichiers du programme

Le programme tient en 19 modules Python (26 310 lignes), sur la seule bibliothèque standard (`psutil` en option, pour peser la mémoire). Il vit dans un dossier `Demo_Marco` : à la racine les modules, `genome/` et `cerveaux/` ; les dossiers de travail dans `ressources/`.

| Fichier | Rôle |
|---------|------|
| `marco_5250.py` | La console, « coquille AS/400 » : le menu Marco MAD, le choix et la naissance des cerveaux, le dialogue, la lecture, la leçon, les bancs |
| `fils.py` | La table des fils : le fichier texte, la vue en mémoire, l'écrivain unique et les cinq lectures |
| `noyau.py` | Le noyau du BSC : des lignes « si … alors … » lues par les phares, rien d'autre |
| `carte.py` | La carte cyber, appelée la CPU depuis le 11/10 : le lecteur du noyau |
| `poignee.py` | La poignée : le passage sur la table des fils (tenir, fermer, chercher, pirouette, écrire) |
| `doigt.py` | Le doigt de lecture : les rections tissées sur la table, écrites en MEQ au tic de la phrase |
| `lecture.py` | L'apprentissage par texte : lire un fichier par le doigt, sur la table seule |
| `contexte.py` | Les poupées, la voix, les souvenirs, les déclics ; la carte des contextes |
| `chercheur.py` | La recherche contextuelle : les daimons à tête chercheuse |
| `trou.py` | La machine à pourquoi : le daimon du trou, les boucles, la révision, les deux moi |
| `precipite.py` | Le précipité : le croisement sur la vue, du rare vers l'immense |
| `dire.py` | La bouche : dire en français ce que le précipité a élu — jamais un pochoir |
| `tournure.py` | L'amorce de la machine à tournure : du Python écrit pour devenir des lignes |
| `cahiers_apprentissage.py` | Les cahiers d'apprentissage : leur forme, leur contrôle, leur intégration à chaque naissance |
| `journal_lecture.py` | Les deux fichiers de contrôle d'une lecture : le journal et le rapport de la dérive |
| `regisseur.py` | Le régisseur : la tournée des salles de test, le relevé par acte, les scellés |
| `tableau_marco.py` | Le tableau de bord : le scribe qui écrit l'état, la page qui le montre |
| `outils_maintenance.py` | Les outils de maintenance du cerveau et du génome |
| `fils_reparer.py` | Trouver, dire et retirer les lignes difformes d'un fichier de lignes, le vécu d'abord |
| `genome/` | 236 fichiers texte : 53 fichiers de fils (`*_fils.tsv`, parfois compressés, 9,5 millions de fils) et 183 fichiers de lignes (`*_lignes.csv`, 88 251 lignes, lisibles dans Excel) |
| `cerveaux/<nom>/` | Un cerveau par dossier : `cerveau_Marco.tsv.gz` et ses trois enregistrements d'avant, datés, à côté |
| `ressources/` | Les dossiers de travail : les cahiers d'apprentissage, les salles de test et leurs comptes rendus, les textes, les commentaires de lecture, les relevés, le tableau de bord |

Sources citées dans les en-têtes du génome : Lefff, Lexique, GLAWI, Wiktionnaire, le Littré (XMLittré), Verbiste, l'INSEE, Wikidata.

---

## 6. Équipe

**José WALOCHA** — Architecte. Valenciennes, Nord, France.
Chef d'entreprises en retraite, joue à créer un cyber inspiré du cerveau des êtres vivants comme on joue à *Diablo IV*.

| Nom | Système | Rôle |
|---|---|---|
| Le Dude (Dudo) | Claude Opus 5.5 (Anthropic) | Code, architecture, génome, cahiers d'apprentissage, commandes à Fable, documents de liaison |
| Fable | Claude Fable 5.1 (Anthropic) | Code des organes : noyau, carte, daimons, lecture, bouche |
| Marcel | Mistral | Philosophie, cybernétique, cross-check |
| Biloute | ChatGPT | Normes, synthèse, idées de relance |
| Didier | Qwant | Recherche documentaire |

Un Dude par jour. Toujours discuter avant de coder. La règle du frigo : architecture posée avant code écrit. La règle de la marmotte : tout ce qui s'apprend en session se condense en document de liaison (HTML, sans header, à coller dans la marmotte globale).

---

## 7. Licence

**GNU Affero GPL v3** — Copyright © 2026 José Walocha.

Choix doctrinal : plus protectrice que la GPL, l'AGPL impose la republication des modifications à toute utilisation en service réseau — un cyber est destiné à tourner potentiellement comme service. Qui modifie Marco et le distribue, ou le fait tourner comme service, en rend le code, sous la même licence.
