<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  0.0.1
date:     2024
language: de
narrator: Deutsch Female
logo:     img/1/aussagenlogik.png
icon:     img/TU_Logo_kurz.png
comment:  Was bedeutet es einen Computer zu programmieren und 
          wie lernt man es?
link:     styles/main.css
import:   ./macros.md

@style

u {
  color: Navy;
  text-decoration: none;
}

s {
  color: FireBrick;
  text-decoration: none;
}

table {
  --color-border: 160, 160, 160; 
  
  }

@end
-->


# Aussagenlogik


<div class="flex-container">
<div class="flex-child">

![Wittgenstein](https://upload.wikimedia.org/wikipedia/commons/thumb/a/ab/Ludwig_Wittgenstein.jpg/493px-Ludwig_Wittgenstein.jpg "Ludwig Wittgenstein")

</div>

<div class="flex-child-3">

> "Alles was überhaupt gedacht werden kann, kann klar gedacht werden. Alles was sich aussprechen lässt, lässt sich klar aussprechen."
>
> -- Ludwig Wittgenstein[^1]

</div>

</div>

[^1]: Ludwig Wittgenstein, [Tractatus logico-philosophicus](https://de.wikipedia.org/wiki/Tractatus_logico-philosophicus), 4.116

## Was ist die Aussagenlogik?
Die Aussagenlogik ist ein Teilgebiet der Logik, das sich mit der Verknüpfung von Aussagen beschäftigt.
Eine Aussage ist ein Satz, der wahr oder falsch sein kann.

So ist Beispielsweise der Satz "Es regnet." eine Aussage, da er entweder wahr oder falsch ist.[^1]

<div class="alert alert-yellow">

Was ist eine Aussage?
---------------------

- [[X]] Die Sonne scheint.
- [[ ]] Wie heißen Sie?
- [[X]] 1+1=2
- [[ ]] Bitte gehen Sie weiter!
- [[X]] 8 ist eine Primzahl
- [[ ]] Hoffentlich wird es bald Frühling.
- [[ ]] Berlin ist schöner als Hamburg.
****************************************************
Fragen, Aufforderungen, Meinungsäußerungen sind keine Aussagen, da ihnen nicht eindeutig ein Wahrheitswert zugeordnet werden kann.
****************************************************

</div>

Diese einfachen Aussagen können nun verknüpft werden um neue Aussagen zu bilden.

[^1]: Auch wenn der Wahrheitswert unbekannt ist, kann es sich um eine gültige Aussage handeln. So ist $P=NP$ eine Aussage. Bei diesem sogenannten [P-NP-Problem](https://de.wikipedia.org/wiki/P-NP-Problem) handelt es sich um ein ungelöstes Problem der Informatik. Niemand kann also mit Sicherheit sagen, ob $P=NP$ wahr oder falsch ist. Es ist dennoch eine Aussage, da sie entweder wahr oder falsch ist.


## Die NICHT-Verknüpfung

Die einfachste Verknüpfung von Aussagen ist die NICHT-Verknüpfung (oder *Negation*). Es ist eine Verknüpfung auf einer Aussage, die wahr ist, wenn die Aussage falsch ist und umgekehrt.

- ~~"Berlin liegt in Deutschland"~~[^1] ist wahr. 
- **nicht** ~~"Berlin liegt in Deutschland"~~[^2] ist falsch.

- ~"Berlin liegt in England"~ ist falsch. 
- **nicht** ~"Berlin liegt in England"~[^2] ist damit wahr.

[^1]: im Folgenden sind wahre Aussagen blau und falsche Aussagen rot markiert.
[^2]: umgangssprachlich würde man sagen: "Berlin liegt nicht in Deutschland", wir setzen hier die Negation vor die Aussage um die Verknüpfung zu verdeutlichen.


## die UND-Verknüpfung

Die UND-Verknüpfung (oder *Konjunktion*) ist eine Verknüpfung von zwei Aussagen, die nur wahr ist, wenn beide Aussagen wahr sind. Das entspricht auch der umgangssprachlichen Verwendung des Wortes "und".\
So ist die Aussage "~~Berlin liegt in Deutschland~~" wahr. "~~London liegt in England~~" ist ebenfalls wahr.\
Die Verknüpfung ~~Berlin liegt in Deutschland~~ **und** ~~London liegt in England~~ ist auch wahr.

Ist nur eine der Aussagen falsch, so ist auch die Verknüpfung falsch. Die Verknüpfungen

- ~~Berlin liegt in Deutschland~~ **und** ~London liegt in Deutschland~
- ~Berlin liegt in England~ **und** ~~London liegt in England~~
- ~Berlin liegt in England~ **und** ~London liegt in Deutschland~

... sind also alle falsch.

Welche dieser Aussagen sind wahr?
---------------------------------

- [[X]] Berlin liegt in Deutschland **und** (**nicht** London liegt in Deutschland)
- [[ ]] Berlin liegt in Deutschland **und** Berlin liegt in England
- [[X]] Berlin liegt in Deutschland **und** Berlin liegt in Deutschland
- [[ ]] Berlin liegt in Deutschland **und** (**nicht** Paris liegt in Frankreich)

## die ODER-Verknüpfung

Die ODER-Verknüpfung (oder *Disjunktion*) ist eine Verknüpfung von zwei Aussagen, die wahr ist, wenn mindestens eine der Aussagen wahr ist.

- ~~Berlin liegt in Deutschland~~ **oder** ~~London liegt in England~~ ist wahr.
- ~~Berlin liegt in Deutschland~~ **oder** ~London liegt in Deutschland~ ist wahr
- ~Berlin liegt in England~ **oder** ~~London liegt in England~~ ist wahr
- ~Berlin liegt in England~ **oder** ~London liegt in Deutschland~  ist falsch

<div class="alert alert-red">

Vorsicht:
---------
Die ODER-Verknüpfung ist auch wahr, wenn beide Aussagen wahr sind.
Beachten Sie, dass das von der umgangssprachlichen Verwendung des Wortes "oder" abweicht. Im Alltag wird "oder" oft als exklusives Oder verwendet, also als "entweder oder". \
Sagt man Beispielsweise *"Ich möchte ein blaues oder grünes Fahrrad kaufen"* so ist damit gemeint, dass man entweder ein blaues oder ein grünes Fahrrad kaufen möchte, aber nicht beides. 

</div>

Welche dieser Aussagen sind wahr?
---------------------------------

- [[X]] Paris liegt in Deutschland **oder** Berlin liegt in Deutschland
- [[X]] (**nicht** Paris liegt in Deutschland) **oder** Berlin liegt in England
- [[X]] Berlin liegt in Deutschland **oder** Berlin liegt in Deutschland
- [[ ]] (**nicht** Berlin liegt in Deutschland) **oder** **nicht** Paris liegt in Frankreich



## Die WENN-DANN-Verknüpfung

Die WENN-DANN-Verknüpfung (oder *Implikation*) ist eine Verknüpfung von Aussagen, bei der die zweite Aussage wahr sein muss, wenn die erste Aussage wahr ist.

- **Wenn** "Es regnet" **dann** "Die Straße ist nass"

Damit diese Verknüpfung wahr ist, muss die Straße nass sein, wenn es regnet.\
Ist die Straße trocken, obwohl es regnet, so ist die Verknüpfung falsch.\
Ist sie nicht nass, obwohl es regnet, so ist die Verknüpfung ebenfalls falsch.\
Wenn es nicht regnet, so ist die Verknüpfung unabhängig vom Zustand der Straße wahr.\


<div class="alert alert-red">

Vorsicht:
---------
Ein beliebter Fehler ist es anzunehmen, dass aus "Wenn A dann B" auch "Wenn B dann A folgt". Das ist nicht der Fall.\
Wenn die Straße nass ist, muss es nicht geregnet haben. Die Straße kann auch nass sein, weil sie gereinigt wurde.

</div>


<div class="alert alert-yellow">

Übung
-----
Sie wissen diese Aussage ist wahr:\
~~"Wenn Sie jeden Tag Informatik lernen, erreichen Sie in der Klausur volle Punktzahl."~~\
Was ist ebenfalls wahr?

- [[X]] Wenn Sie nicht volle Punktzahl erreichen, haben Sie nicht jeden Tag Informatik gelernt.
- [[ ]] Wenn Sie volle Punktzahl erreichen, haben Sie jeden Tag informatik gelernt.
- [[ ]] Wenn Sie nicht jeden Tag Informatik lernen, erreichen Sie nicht volle Punktzahl in der Klausur.
******************************************
Die erste Aussage ist wahr, da wir wissen dass tägliches Lernen immer zu voller Punktzahl führt. Wurde diese nicht erreicht, so kann es nicht sein, dass täglich gelernt wurde.\
Die zweite Aussage ist falsch, vielleicht sind Sie ja ein Naturtalent und erreichen ohne Lernen volle Punktzahl.\
Die dritte Aussage ist ebenfalls falsch, vielleicht haben Sie ja an einem Tag besonders viel gelernt und erreichen deshalb trotzdem volle Punktzahl.
******************************************

</div>

## Notation
Die Logik befasst sich als Teilgebiet der Mathematik üblicherweise nicht mit umgangssprachlichen Aussagen.
Um Aussagen mathematisch zu formulieren, werden Wahrheitswerte, aussagenlogische Variablen, Junktoren und Klammern verwendet.

- Wahre Aussagen werden mit $1$ bezeichnet, falsche Aussagen mit $0$.
- Aussagenlogische Variablen sind Variablen, die für eine Aussage stehen. Sie werden üblicherweise mit Großbuchstaben bezeichnet.
- Junktoren sind Symbole, die die Verknüpfung von Aussagen beschreiben. Die gängigsten Junktoren sind:

  - $\land$ für die UND-Verknüpfung
  - $\lor$ für die ODER-Verknüpfung
  - $\lnot$ für die NICHT-Verknüpfung
  - $\rightarrow$ für die WENN-DANN-Verknüpfung
- Klammern werden verwendet, um die Reihenfolge der Verknüpfungen festzulegen.

So wird die Aussage "Es regnet" als $R$ bezeichnet und die Aussage "Die Straße ist nass" als $N$.\
Die WENN-DANN-Verknüpfung *"Wenn es regnet, dann ist die Straße nass"* wird also als $$R \rightarrow N$$ dargestellt.

*"Wenn die Straße nicht nass ist, dann hat es nicht geregnet"* ist dann
$$\lnot N \rightarrow \lnot R$$

<div class="alert alert-red">

Vorsicht: Verwirrende Notation
------------------------------
Es gibt zahlreiche Varianten in der Schreibweise der Aussagenlogik.

* Statt $0$ für falsch wird auch $F$ oder $\bot$ verwendet
* Statt $1$ für wahr wird auch $T$,$W$ oder $\top$ verwendet
* Statt $\land$ wird die UND-Verknüpfung auch wie die Multiplikation $A \cdot B$ oder $AB$ geschrieben.
* Statt $\lor$ wird auch $+$ verwendet
* Statt $\lnot$ wird auch $\sim$ verwendet. Auch ein der Variablen nachgestellter Apostroph $A'$ oder ein Überstrich $\overline{A}$ sind gebräuchlich.

So drücken je nach Notation $\neg (\neg A \land B)$ und $\overline{\overline{A}B}$ dasselbe aus.

</div>

### Übungen

<div class="alert alert-yellow">

Übung 1
-------
Die Aussagenlogische Variable $S$ steht für "Die Sonne scheint" und $W$ für "Es ist warm".\
Drücken Sie die folgenden Aussagen in der Aussagenlogik aus:

1. "Die Sonne scheint nicht und es ist nicht warm"
- [(X)] $\lnot S \land \lnot W$
- [( )] $\lnot(S \land W)$
- [( )] $\lnot S \rightarrow \lnot W$

2. "Es ist nicht warm, wenn die Sonne nicht scheint"
- [( )] $\lnot W \rightarrow \lnot S$
- [(X)] $\lnot S \rightarrow \lnot W$
- [( )] $\lnot S \land \lnot W$

3. "Es ist warm, wenn die Sonne scheint und wenn es warm ist, scheint die Sonne"
- [( )] $(S \rightarrow W) \lor (W \rightarrow S)$
- [(X)] $(S \rightarrow W) \land (W \rightarrow S)$
- [( )] $(S \land W) \lor (W \land S)$

</div>

<div class="alert alert-yellow">

Übung 2
-------
Welche der folgenden Aussagen sind wahr?

- [[X]] $(0 \land 1) \lor 1 $
- [[ ]] $0 \land 1$
- [[ ]] $1 \land \lnot 1$
- [[X]] $1 \lor \lnot 1$
- [[ ]] $\lnot 1 \lor \lnot 1$
- [[X]] $\lnot 0 \land \lnot 0$

</div>

<div class="alert alert-yellow">

Übung 3
-------
Wir haben [bereits](#die-oder-verknüpfung) erwähnt, dass die ODER-Verknüpfung auch wahr ist, wenn beide Aussagen wahr sind. Wie kann man ein *"entweder oder"* (auch XOR oder "exklusives Oder"[^1]) aussagenlogisch formulieren?

- [( )] $(A \lor B) \land \lnot 1$
- [(X)] $(\neg A \land B) \lor (A \land \neg B)$
- [( )] $\lnot A \lor \lnot B$
- [( )] $(A \land B) \lor (\lnot A \land \lnot B)$  

[^1]: Für das exklusive Oder wird auch das Symbol $\oplus$ oder $\veebar$ verwendet.

</div>

## Wahrheitstabellen
Um das Verhalten von Verknüpfungen vollständig zu beschreiben, werden Wahrheitstabellen verwendet.\

Für jede mögliche Kombination von Wahrheitswerten der aussagenlogischen Variablen wird der Wahrheitswert der Verknüpfung bestimmt.

Am einfachsten ist das bei der Negation, die nur von einer Aussage abhängt.\
Da eine Aussage entweder wahr ($1$) oder falsch($0$) ist, hat die Wahrheitstabelle für $\neg A$ zwei Zeilen und sieht so aus:

<!-- data-type="none" class="w-30"-->
| $A$  |  $\neg A$ |
|:----:|:---------:|
|   0  | 1         |
|   1  | 0         |

### UND
Die Wahrheitstabelle für die UND-Verknüpfung hat vier Zeilen, da es vier mögliche Kombinationen von Wahrheitswerten für zwei Aussagen gibt. Wie Sie bereits wissen, ist die UND-Verknüpfung nur wahr, wenn beide Aussagen wahr sind:

<!-- data-type="none" class="w-30"-->
| $A$  |  $B$ | $A \land B$ |
|:----:|:----:|:-----------:|
|   0  | 0    | 0           |
|   0  | 1    | 0           |
|   1  | 0    | 0           |
|   1  | 1    | 1           |


### ODER (Übung)


<div class="alert alert-yellow">

Übung
-----

Können Sie die Wahrheitstabelle für die ODER-Verknüpfung $A \lor B$ selbst vervollständigen?

<!-- data-type="none" class="w-30"-->
| $A$  |  $B$ | $A \lor B$ |
|:----:|:----:|:-----------:|
|   0  | 0    | [[0]]       |
|   0  | 1    | [[1]]       |
|   1  | 0    | [[1]]       |
|   1  | 1    | [[1]]       |
***********************************
ODER ist wahr wenn mindestens eine Variable wahr ist. 
***********************************

</div>

### WENN-DANN
Die WENN-DANN-Verknüpfung haben wir ja bereits beschrieben. Wenn die erste Aussage wahr ist, so muss auch die zweite Aussage wahr sein.

<!-- data-type="none" class="w-30"-->
| $A$  |  $B$ | $A \rightarrow B$ |
|:----:|:----:|:-----------------:|
|   0  | 0    | 1                 |
|   0  | 1    | 1                 |
|   1  | 0    | 0                 |
|   1  | 1    | 1                 |


<div class="alert alert-yellow">

Übung
-----
Die WENN-DANN-Verknüpfung lässt sich auch ohne den Junktor $\rightarrow$ formulieren.\
Welcher Ausdruck ist äquivalent zu $A \rightarrow B$?

- [( )] $\lnot A \land B$
- [(X)] $\lnot A \lor B$
- [( )] $A \land \lnot B$
- [( )] $A \lor \lnot B$
******************************

$\lnot A \lor B$ ist richtig. Beweisen kann man das mit einer Wahrheitstabelle.
Wir notieren zunächst die Negation $\lnot A$ und verODERN diese mit B.

<!-- data-type="none" class="w-30"-->
| $A$  |  $B$ | $\neg A$ |$\lnot A \lor B$ |
|:----:|:----:|:--------:|:--------------:|
|   0  | 0    | 1        |   1            |
|   0  | 1    | 1        |   1            |
|   1  | 0    | 0        |   0            |
|   1  | 1    | 0        |   1            |


******************************

</div>

### GENAU-DANN-WENN (Übung)
GENAU-DANN-WENN (auch *Biimplikation* oder *Äquivalenz*) ist wahr, wenn beide Aussagen den gleichen Wahrheitswert haben.\
zum Beispiel: "Wasser ist **genau dann** gefroren **wenn** es unter 0°C ist"
Für diese Verknüpfung wird der Doppelpfeil $\leftrightarrow$ verwendet.

<!-- data-type="none" class="w-30"-->
| $A$  |  $B$ | $A \leftrightarrow B$ |
|:----:|:----:|:-----------------:|
|   0  | 0    | 1                 |
|   0  | 1    | 0                 |
|   1  | 0    | 0                 |
|   1  | 1    | 1                 |

<div class="alert alert-yellow">

Übung
-----

Zwei Wahrheitswerte A und B sind genau dann gleich, wenn $A \rightarrow B$ und $B \rightarrow A$ wahr sind.\
Beweisen Sie das mit dieser Wahrheitstabelle:

<!-- data-type="none" -->
| $A$  |  $B$ | $A \rightarrow B$ | $B \rightarrow A$ |$(A \rightarrow B) \land (B \rightarrow A) $ |
|:----:|:----:|:-----------------:|:-----------------:|:---------------------------------------:|
|   0  | 0    | [[1]]             |   [[1]]           | [[1]]                                   |
|   0  | 1    | [[1]]             |   [[0]]           | [[0]]                                   |
|   1  | 0    | [[0]]             |   [[1]]           | [[0]]                                   |
|   1  | 1    | [[1]]             |   [[1]]           | [[1]]                                   |

</div>

## Vertiefung

<div class="alert alert-yellow">

Aufgabe 1 ✍[^1]
------------

Beweisen Sie mit Wahrheitstabellen, dass $A \land B$ und  $\lnot (\lnot A \lor \lnot B)$ äquivalent sind.

</div>

<div class="alert alert-yellow">

Aufgabe 2 ✍
------------

Beweisen Sie mit Wahrheitstabellen, dass $A \leftrightarrow B$ und  $(A \land B) \lor (\lnot A \land \lnot B)$ äquivalent sind.

</div>

<div class="alert alert-yellow">

Aufgabe 3
---------

Eine Tautologie ist eine Aussage, die unabhängig von den Wahrheitswerten der aussagenlogischen Variablen immer wahr ist.\

Welche der folgenden Aussagen sind Tautologien?

[[X]] $A \lor \neg A$
[[ ]] $A \land 0$
[[ ]] $A \land 1$
[[X]] $(A \land B) \leftrightarrow (B \land A)$
[[ ]] $(A \land \neg B) \leftrightarrow (B \land \neg A)$
[[ ]] $(1 \land 1) \land (1 \lor 0)$
[[ ]] $(0 \land 1) \lor (1 \land 0)$
[[X]] $(A \land \neg A) \leftrightarrow 0$
[[ ]] $(A \rightarrow B) \leftrightarrow (B \rightarrow A)$
[[X]] $(A \rightarrow B) \leftrightarrow (\neg B \rightarrow \neg A)$

</div>


[^1]: Aufgaben mit dem Symbol ✍ sind dafür gedacht, dass Sie Sie auf Papier selbst lösen. Sie werden nicht online überprüft.