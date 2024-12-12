<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  1.0.0
date:     2024
language: de
narrator: Deutsch Female
logo:     img/4/logo.png
icon:     img/TU_Logo_kurz.svg
comment:  Boolesche Logik, Schaltkreise 
link:     styles/main.css
import:   ./macros.md


@style


table {
  --color-border: 160, 160, 160;
  width: auto !important;
}

.lia-table__sort {
  display: none
}

.lia-table-responsive.has-thead-sticky.has-first-col-sticky .lia-table__head th:first-child {
  position: unset;
}

.lia-table-responsive.has-first-col-sticky .lia-table__data:first-child {
  position: unset;
}

@end

-->

# Schaltkreise

<div class="flex-container">
<div class="flex-child">
![Schaltkreise](img/4/logo.png)

</div>
<div class="flex-child-2">

So wie wir aus einzelnen Bits komplexe Daten kodieren können, lässt sich ein kompletter Computer bauen, indem die logischen Operationen `UND`, `ODER` und `NICHT` kombiniert werden. Zunächst lernen wir, mithilfe der Booleschen Algebra logische Berechnungen durchzuführen, und konstruieren anschließend Schaltkreise aus Gattern. Schließlich erfahren wir, wie komplexere Funktionalitäten wie Addition oder Multiplikation realisiert werden können.

</div>
</div>

<!-- class="context"-->
Dieses Kapitel baut auf der @[lialink(Einführung in die Aussagenlogik)](1_Aussagenlogik.md) auf.\
Für einen Gesamtüberblick über den Kurs geht es @[lialink(hier zurück zur Kursübersicht)](0_Inhalt.md).



## Boolesche Logik


<div class="flex-container">
<div class="flex-child-2">

Den Begriff der Algebra kennen Sie sicherlich aus der Mathematik. Er beschreibt einen Satz von Regeln, mit dem man Berechnungen durchführen kann. So erklärt die elementare Algebra, wie wir Zahlen addieren, multiplizieren, substrahieren und dividieren können. Sie verwendet Variablen und erlaubt uns Gleichungen und Ungleichungen aufzustellen. Dabei legt sie fest, welche Regeln man dabei beachten muss.

Die boolesche Algebra hat ihren Namen von George Boole, der sie 1847 in seinem Buch *„The Mathematical Analysis of Logic”* erfand.

Sie ist eine besondere Form der Algebra, die Regeln beschreibt, wie man mit Wahrheitswerten rechnen kann.

So wie in der elementaren Algebra verwendet man in der booleschen Algebra Variablen, nennt diese aber boolesche Variablen. Sie können nur die  Wahrheitswerte *wahr* und *falsch* annehmen.  
Diese zwei Werte *wahr* und *falsch* schreibt man auf englisch *true* und *false* oder verwendet die Ziffern $1$ und $0$.  
Hier wird deutlich, warum die boolesche Algebra so interessant für die Informatik ist: Da man 1 und 0 verwendet, um digitale Daten zu repräsentieren, erlaubt uns diese Algebra Berechnungen auf diesen Daten zu definieren.  
Für diese Berechnungen verwendet man die Operationen oder Verknüpfungen der booleschen Algebra: `UND`, `ODER`, und `NICHT`.

Diese kennen Sie bereits von den Grundlagen der Aussagenlogik im @[lialink(ersten Kurskapitel)](1_Aussagenlogik.md)

</div>

<div class="flex-child">
![George Boole](img/4/boole.jpg "George Boole (1815-1864)")

</div>
</div>

### Boolesche Funktionen

<div class="alert definition">

Definition: Boolesche Funktion
------------------------------

Eine boolesche Funktion ist eine mathematische Funktion, die boolesche Variablen als Eingabe verwendet und Boolesche Werte (1 oder 0) als Ausgabe liefert.  
Jedem möglichen Satz von Eingangsvariablen wird dabei ein eindeutiger Ausgangswert zugewiesen.  

</div>

Notiert man für jede mögliche Kombination von Eingangsvariablen den Ausgangswert, erhält man eine Wahrheitstabelle, die die Funktion charakterisiert.  
Für eine Funktion mit einer Eingabevariablen (*unär*), z.B. $F_1(x)=x$ haben wir nur zwei mögliche Eingangswerte.  
Die Wahrheitstabelle sieht dann so aus:


<!-- data-type="none" -->
| $x$   | $F_1(x)=x$|
| ----- | ----------- |
|   0   |   0   |
|   1   |   1   |


Diese Funktion nennt man auch Identität von $x$. Sie gibt den Eingabewert unverändert zurück.  
Etwas interessanter ist da die schon die Funktion $F_2(x)=\neg x$, die NICHT-Verknüpfung auf $x$:


<!-- data-type="none" -->
| $x$   | $F_2(x)=\neg x$|
| ----- | ----------- |
|   0   |   1   |
|   1   |   0   |


Bei zwei Eingabewerten gibt es 4 mögliche Kombinationen an Eingabewerten.  
Hier die binäre Funktion $F_3$, eine UND-Verknüpfung von $x$ und $y$:


<!-- data-type="none" -->
| $x$   | $y$   | $F_3(x,y) = x \wedge y$|
| ----- | ----- | ----------- |
|   0   |   0   |   0   |
|   0   |   1   |   0   |
|   1   |   0   |   0   |
|   1   |   1   |   1   |


Bei drei Eingabewerten gibt es bereits 8 verschiedene Eingaben.
Hier die Funktion $F_4(x,y,z)$


<!-- data-type="none" -->
| $x$   | $y$   | $z$ | $F_4(x,y,z)$ |
| ----- | ----- | ----- | -----------|
|   0   |   0   |   0   |   0        |
|   0   |   0   |   1   |   0        |
|   0   |   1   |   0   |   0        |
|   0   |   1   |   1   |   1        |
|   1   |   0   |   0   |   0        |
|   1   |   0   |   1   |   1        |
|   1   |   1   |   0   |   1        |
|   1   |   1   |   1   |   1        |


<div class="alert exercise">

Frage
-----

Analysieren Sie die Wahrheitstabelle der Funktion $F_4(x,y,z)$.
Wie lässt sich diese Funktion am besten beschreiben?

- [( )] $F_4$ ist genau dann wahr, wenn mindestens eine Eingangsvariable wahr ist.
- [( )] $F_4$ ist die sogenannte Parity-Funktion, die Ausgabe ist 1 genau dann, wenn die Summe der Eingabebits gerade ist.
- [(X)] $F_4$ ist die sogenannte Mehrheitsfunktion, die Ausgabe ist 1 genau dann, wenn die Mehrheit der Eingabebits 1 ist.

</div>

### Funktionen entdecken

Es gibt nur 16 verschiedene binäre boolesche Funktionen. Jede davon ist eindeutig durch die Abfolge der Ausgabewerte in der Wahrheitstabelle charakterisiert.  
Für $x\wedge y$ ist diese Abfolge z.B. `0001`, für $x\vee y$ ist sie `0111`.  
Welche neuen Funktionen können Sie in der interaktiven Wahrheitstabelle entdecken?

> Klicken Sie auf die Zahlen in der Ergebnisspalte um die Funktion zu verändern, links können Sie dann das Verhalten der Funktion testen
> Einige Funktionen haben spezielle Namen oder sogar besondere Symbole. Versuchen Sie herauszufinden was die Namen oder Symbole bedeuten könnten.


@[embed(style="height: 455px; width:800px; border: none")](html/4/booleschefunktionen.html)



### Boolesche Ausdrücke

Wie Sie gesehen haben, können wir eine boolesche Funktion eindeutig durch ihre Wahrheitstabelle darstellen. Oft ist es jedoch einfacher, einen booleschen Ausdruck zu notieren.

So können wir für die UND-Funktion $x\wedge y$ schreiben.  
Das nennt man einen booleschen Ausdruck.


<div class="alert definition">

Definition: Boolescher Ausdruck
-------------------------------

1. $0$ und $1$ sind boolesche Ausdrücke
2. Jede boolesche Variable (z.B. $x$ oder $a$) ist ein boolescher Ausdruck
3. Sind $t_0$ und $t_1$ boolesche Ausdrücke, so auch:  
    a) $t_0∧t_1$  
    b) $t_0∨t_1$  
    c) $¬t_0$

Wenn der Ausdruck eindeutig ist, können die Klammern weggelassen werden. 
</div>

Eine solche Definition nennt man rekursiv: durch wiederholte Anwendung der Regeln kann man komplexe boolesche Ausdrücke aufbauen.


<div class="alert example">

Beispiel
--------

1. $x$ ist ein boolescher Ausdruck (BA)
2. $¬x$ ist ein BA *(Wende Regel 3c auf 1 an)*
3. $y$  ist ein BA
4. $¬x∨y$ ist ein BA *(Wende Regel 3b auf 2 und 1 an)*

</div>


### Boolesche Algebra

Um mit booleschen Ausdrücken rechnen zu können, müssen wir die Rechengesetze für unsere booleschen Verknüpfungen und Ausdrücke festlegen.  
Die mathematische Struktur, auf der diese Rechenregeln basieren, nennt man boolesche Algebra:

<div class="alert definition">

Definition: Boolesche Algebra
-----------------------------

Eine boolesche Algebra ist eine Menge $B$ mit den zwei binären Verknüpfungen $\wedge$ (die Konjunktion UND) und $\vee$ (die Disjunktion ODER), einer unären Verknüpfung $\neg$ (die Negation NICHT) und zwei speziellen Elementen $0$ und $1$, so dass für alle $x,y,z \in B$ die folgenden Gesetze gelten:

1. Kommutativgesetze

$$
\quad x \vee y = y \vee x
$$

$$
\quad x \wedge y = y \wedge x
$$

2. Assoziativgesetze

$$
\quad (x \vee y) \vee z = x \vee (y \vee z)
$$

$$
\quad (x \wedge y) \wedge z = x \wedge (y \wedge z)
$$

3. Distributivgesetze

$$
\quad x\wedge(y\vee z) =(x\wedge y)\vee(x\wedge z)\\
$$

$$
\quad  x\vee(y\wedge z) = (x\vee y) \wedge (x\vee z)
$$

4. Komplementärgesetze

$$
\quad \neg x\vee x = 1
$$

$$
\quad \neg x\wedge x = 0
$$
 
5. Neutralitätsgesetze

$$
\quad  x\vee 0 = x
$$

$$
\quad  x\wedge 1 = x
$$ 

</div>

Die Kommutativ- und Assoziativgesetze kennen Sie bereits aus der elementaren Algebra. Auch die Neutralitätsgesetze gelten ähnlich für Addition und Multiplikation.
Die boolesche Algebra kennt aber zwei Distributivgesetze anstatt nur einem und außerdem noch die Komplementärgesetze.  

<div class="alert exercise">

Übung
------

Die folgenden Gleichungen sind alle korrekt. Wählen Sie aus, welches Gesetz der Booleschen Algebra zur Anwendung kam.

$$
\neg(x\vee y) \wedge (x\vee y) = 0
$$
[[ Kommutativ | Distributiv | Assoziativ | (Komplementär) | Neutralität ]]
$$
(x\vee z)\wedge \neg (z\vee y)=\neg (z\vee y)\wedge (x\vee z)
$$
[[ (Kommutativ) | Distributiv | Assoziativ | Komplementär | Neutralität ]]
$$
(x\vee y)\vee (z\vee x) = x\vee(y\vee(z\vee x))
$$
[[ Kommutativ | Distributiv | (Assoziativ) | Komplementär | Neutralität ]]
$$
\neg x\wedge(x\vee y) = (\neg x\wedge x)\vee(\neg x\wedge y)
$$
[[ Kommutativ | (Distributiv) | Assoziativ | Komplementär | Neutralität ]]
$$
(x\wedge y)\vee(x\wedge z)\vee 0 = (x\wedge y)\vee(x\wedge z)
$$
[[ Kommutativ | Distributiv | Assoziativ | Komplementär | (Neutralität) ]]

</div>

#### Idempotenzgesetze

Aus der Definition der Booleschen Algebra lassen sich noch weitere Gesetze ableiten, die es einfacher machen, boolesche Ausdrücke umzuformen.\
Die Idempotenzgesetze besagen zum Beispiel, dass ein Wert, der mit sich selbst verknüpft wird, seinen Wert nicht ändert:

<div class="alert definition">

Idempotenzgesetze
-----------------

$$
\quad  x\vee x = x
$$  
und  
$$
\quad  x\wedge x = x
$$ 

</div>

Dieses Gesetz ist nicht notwendigerweise Bestandteil der Definition, da es sich aus den bereits bekannten Gesetzen herleiten lässt:

<div class="alert example">

Beweis des ersten Idempotenzgesetzes $x = x\vee x$
--------------------------------------------------

Das erste Neutralitätsgesetz ist  
$$
x = x\vee 0 
$$  
Wenden wir das Komplementärgesetz rückwärts an, können wir $0$ mit $x \wedge \neg x$ ersetzen  
$$
x = x\vee (x \wedge \neg x)
$$  
Nach dem zweiten Distributivgesetz ist das gleich  
$$
x = (x\vee x) \wedge (x \vee \neg x)
$$  
das entspricht nach dem ersten Komplementärgesetz  
$$
x = (x\vee x) \wedge 1
$$  
und nach dem zweiten Neutralitätsgesetz wissen wir, dass eine Konjunktion mit 1 weggelassen werden kann.  
So erhalten wir  
$$
x = x\vee x \quad \square
$$  

</div>

In diesem Beweis wird gezeigt, wie die Gesetze der booleschen Algebra verwendet werden, um boolesche Ausdrücke zu vereinfachen.  
Beachten Sie, dass die Variablen $x$, $y$ und $z$ in den Gesetzen für beliebig komplexe Ausdrücke stehen können.

So erhalten wir im letzten Schritt des Beweises im Ausdruck $(x\vee x) \wedge 1$  durch die Substitution $x'=(x\vee x)$ direkt das Neutralitätsgesetz $x' \wedge 1 = x'$, so dass wir als Ergebnis $x'$, also $(x\vee x)$ erhalten.

<div class="alert exercise">

Aufgabe
-------

Welcher der folgenden Ausdrücke vereinfacht sich mit dem Idempotenzgesetz zu $ x \lor y $?


- [( )] $ (x \land x) \lor y $  
- [( )] $ x \land (y \lor y) $  
- [(X)] $ (x \lor x) \lor y $
- [( )] $ (x \lor y) \land (x \lor x) $


</div>


#### Extremalgesetze

<div class="alert definition">

Definition
----------

Die Disjunktion mit $1$ ist immer wahr, die Konjunktion mit $0$ ist immer falsch:  
$$
\quad  x\vee 1 = 1
$$  
$$
\quad  x\wedge 0 = 0
$$ 

</div>

Die Extremalgesetze können sehr hilfreich in der praktischen Anwendung sein:

* Wenn mehrere Bedingungen gleichzeitig wahr sein müssen, kann man schon bei der ersten falschen Bedingung die Auswertung abbrechen. 
* Reicht es, wenn nur eine von vielen Bedingungen erfüllt ist, so ist nach der ersten wahren Bedingung bereits bekannt, dass der Gesamtausdruck wahr sein muss. 


<div class="alert example">

Beispiel
--------

$$
(y \wedge \neg z) \vee (\neg x\vee x)
$$
vereinfacht sich nach dem Komplementärgesetz zu

$$
(y \wedge \neg z) \vee 1
$$

und ist damit nach dem Extremalgesetz immer $1$, also eine Tautologie. 

</div>

<div class="alert exercise">

Aufgabe
-------

Betrachten Sie den booleschen Ausdruck
$$
(a \land \lnot (b \lor \lnot b))
$$

zu welchem Ausdruck lässt dieser sich vereinfachen?

- [( )] $ 1 $  
- [(X)] $ 0 $  
- [( )] $ a $
- [( )] $ b $

</div>

#### Doppelnegationsgesetz


<div class="alert definition">

Definition
----------

$$
\quad  \neg (\neg x) = x
$$  

</div>

Die doppelte Negation eines Ausdrucks ist also gleich dem ursprünglichen Ausdruck.  

<div class="alert example">

Beispiel
--------

Das Doppelnegationsgesetz kennen wir auch aus dem Alltag:

*Ich gehe nicht ohne Regenschirm aus dem Haus*,

ist eine doppelte Negation und damit logisch äquivalent zu

*Ich gehe mit Regenschirm aus dem Haus*

</div>

#### De-morgansche Gesetze

<div class="alert definition">

Definition
----------

$$
\quad  \neg (x\wedge y) = \neg x \vee \neg y 
$$  

$$  
\quad \neg(x \vee y) = \neg x \wedge \neg y 
$$ 

</div>

Die De-morganschen Gesetze erlauben es, mit Hilfe der Negation `NICHT` eine Disjunktion als Konjunktion oder eine Konjunktion als Disjunktion zu schreiben. Das führt zu der Erkenntnis, dass jeder boolesche Ausdruck mit nur zwei booleschen Verknüpfungen dargestellt werden kann (eine davon muss die Negation sein).  

Dieses Gesetz lässt sich auch mit einem Alltagsbeispiel veranschaulichen:

<div class="alert example">

Beispiel
--------

Jemand, der keine tierischen Produkte isst, sagt den Satz:\
*Wenn Fleisch oder Eier im Essen sind, esse ich es nicht.*

Anders könnte man auch formulieren:\
*Wenn ich das Essen esse, sind keine Eier und kein Fleisch enthalten.*

Das entspricht dem zweiten De-morganschen Gesetz.

</div>


<div class="alert exercise">

Aufgabe
-------

Wir wollen den Ausdruck   
$$ a \vee b $$  
mit Hilfe der De-morganschen Gesetze ohne die Disjunktion `ODER` schreiben.

Welcher der folgenden Ausdrücke ist äquivalent?

- [(X)] $ \neg(\neg a \wedge \neg b) $
- [( )] $(\neg a \wedge \neg b) $
- [( )] $(a \wedge b) $
- [( )] $\neg (a \wedge b) $
********************
Das zweite De-Morgan'sche Gesetz lautet:

$$
\neg (a \lor b) = \neg a \land \neg b
$$

Wir negieren beide Seiten:
$$ \neg \left( \neg (a \lor b) \right) = \neg (\neg a \land \neg b) $$

Die doppelte Negation auf der linken Seite vereinfacht sich zu:
$$
   a \lor b = \neg (\neg a \land \neg b)
$$

Und so sehen wir direkt, dass $ \neg(\neg a \wedge \neg b) $ die richtige Antwort ist.

********************

</div>

#### Absorptionsgesetze

<div class="alert definition">

Definition
----------

$$
\quad x\wedge (x\vee y) = x 
$$  
$$
\quad x\vee (x\wedge y) = x
$$

</div>

<div class="alert exercise">

Aufgabe
-------

Verwenden Sie die Absorptionsgesetze, um folgenden Ausdruck zu vereinfachen:  
$$
(x\vee \neg z) \wedge ((x\vee \neg z)\vee y)
$$

Was ist das Ergebnis der Vereinfachung?

- [( )] $x$
- [(X)] $(x\vee \neg z)$
- [( )] $(x\vee \neg z) \wedge y$
- [( )] $z$


</div>

