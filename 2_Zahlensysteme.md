<!--
author:   Tilman Schieber
email:    tilman.schieber@tu-berlin.de
version:  1.0.5
date:     2024
language: de
narrator: Deutsch Female
logo:     img/2/logo.png
icon:     img/TU_Logo_kurz.svg
comment:  Welche Arten gibt es Zahlen darzustellen? Was ist das Binärsystem und welche Bedeutung hat es für die Informatik?
link:     styles/main.css
import:   ./macros.md

-->

# Zahlensysteme

<div class="flex-container">
<div class="flex-child">
![Zahlensymbole](img/2/zahlensymbole.png)

</div>
<div class="flex-child-2">

Es ist wichtig, zwischen einer Zahl und ihrer Darstellung zu unterscheiden.
So können wir die Zahl 142 auch durch das Wort "einhundertzweiundvierzig" beschreiben. 

Alternativ könnten wir eine Strichliste mit 142 Strichen führen oder die römische Zahl ⅭⅩⅬⅠⅠ benutzen.
Eine solche Darstellung nennt man Zahlensystem.

Das heute verbreitetste Zahlensystem ist das Dezimalsystem. Können Sie die Zahl 142 lesen, kennen Sie es bereits.

</div>
</div>


## Das Dezimalsystem

Unser Dezimal- oder Zehnersystem ist ein sogenanntes Positionssystem. Dabei steht jede Ziffer, je nach Position, für einen anderen Wert. 
Die $1$ steht in der Zahl $142$ beispielsweise für $100$, während sie in der Zahl $213$ für $10$ steht.

Die Werte der einzelnen Stellen basieren auf den Potenzen von Zehn: 

$$
1,10,100,1000,10000, \ldots
$$ 

lassen sich als 

$$
10^0,10^1,10^2,10^3,10^4,\ldots
$$
 
schreiben.

Wir sagen dazu auch: das Dezimalsystem hat die Basis $10$.

Um eine Zahl im Dezimalsystem zu lesen, nummerieren wir die Positionen von rechts nach links durch. Wie immer in der Informatik beginnen wir mit dem Zählen bei Null.

Die Wertigkeit einer Ziffer ergibt sich nach der Formel 

$$
\text{Wertigkeit}=\text{Ziffer} \cdot 10^\text{Position}
$$

Der Wert einer Zahl ist die Summe der Wertigkeiten aller ihrer Ziffern.

<div class="flex-container">


<div class="flex-child alert example" style="min-width:500px">

Beispiel
--------

Bei der Zahl 142 steht

* eine $2$ an Position $0$, also $2\cdot10^0$, Wertigkeit $2$
* eine $4$ an Position $1$, also $4\cdot10^1$, Wertigkeit $40$
* eine $1$ an Position $2$, also $1\cdot10^2$, Wertigkeit $100$

So ergibt sich für 142 der Wert

$$
 2 + 40 + 100 = 142 
$$

</div>

<div class="flex-child" style="min-width:300px">

![142 im Dezimalsystem](img/2/dezimalsystem.png)

</div>


</div>

## Positionssysteme 

Im Dezimal- oder Zehnersystem basieren die Wertigkeiten aller Stellen auf den Potenzen der Zahl 10. Man sagt, es ist ein Positionssystem zur Basis 10.

Allgemein berechnet sich die Wertigkeit einer Ziffer in einem Zahlensystem zu einer bestimmten Basis so:

$$
\text{Wertigkeit}=\text{Ziffer} \cdot \text{Basis}^\text{Position}
$$

Der Wert einer Zahl in einem Positionssystem ist die Summe der Wertigkeiten der Ziffern.

Mit diesem Wissen kann man nun auch Zahlen verstehen, die nicht im Dezimalsystem sondern mit einer anderen Basis geschrieben wurden.  

Damit es nicht zu Verwechslungen kommt, schreiben wir die Basis rechts unten neben die Zahl: So ist $120_3$ eine Zahl mit Basis 3 und $231_5$ eine Zahl mit Basis 5.  

Bei Zahlen im Dezimalsystem gibt man die Basis 10 üblicherweise nicht an, $24$ bedeutet also $24_{10}$.  
Um die Zahlen $120_3$ und $231_5$ ins Dezimalsystem umzurechnen, berechnen wir die Summe aller Wertigkeiten der Ziffern:


<div class="flex-container">

<div class="flex-child mx-3" style="min-width:300px">

![Dreiersystem](img/2/dreiersystem.png)

</div>

<div class="flex-child mx-3" style="min-width:300px">

![Fünfersystem](img/2/fuenfersystem.png)

</div>

</div>

---

Versuchen Sie es nun selbst:

<div class="alert exercise">

Welche dieser Zahlen stellen die Dezimalzahl 42 dar?
----------------------------------------------------

- [[X]] $46_{9}$
- [[ ]] $110010_2$
- [[ ]] $1111_3$
- [[X]] $132_5$
- [[X]] $16_{36}$
- [[ ]] $111_6$
*************************

- $46_{9} = 36 + 6 = 42$ ✓
- $110010_2 = 32 +  16 + 2 = 50$ 
- $1111_3 = 27 + 9 + 3 + 1 = 40$ 
- $132_5 = 25 + 15 + 2 = 42$ ✓
- $16_{36} = 36 + 6 = 42$ ✓
- $111_6 = 36 + 6 + 1 = 43$

*************************
</div>

### Spiel: Paare finden

> Unter diesen neun Zahlen in verschiedenen Zahlensystemen finden sich vier Paare. Finden Sie diese, indem Sie auf die Zahlen klicken!

@[embed(style="height: 500px; width:500px; border: none")](html/2/zahlenpaare.html)

## In andere Zahlensysteme umrechnen

Wir haben bereits gelernt, wie wir Zahlen anderer Zahlensysteme in das Zehnersystem umrechnen können. Für den umgekehrten Weg, eine Zahl $n$ aus dem Zehnersystem in ein System mit anderer Basis $b$ umzurechnen, nutzen wir folgenden Algorithmus[^1]:


<div class="alert definition">

Umrechnung der Zahl $n$ in eine Zahl der Basis $b$
---------------------------------------------------

1. Teilen Sie $n$ ganzzahlig durch die Basis $b$. 
2. Das Ergebnis ist der Quotient $q$ und der Rest $r$. Dieser Rest ist die nächste Ziffer des Ergebnisses, geschrieben von rechts nach links. Ist $q=0$ sind Sie fertig.
3. Teilen Sie $q$ ganzzahlig durch $b$ und gehen Sie zu Schritt 2.

</div>

Beispiel
--------

Rechnen wir 143 in eine Zahl mit Basis 8 um, gehen wir folgendermaßen vor:

1. $143 : 8 = 17 \text{, Rest } 7$ 
2. $17 : 8 = 2 \text{, Rest } 1$ 
3. $2 : 8 = 0 \text{, Rest } 2$ 
4. Wir erhalten als Ergebnis der Umwandlung $217_8$



Testen Sie den Algorithmus nun selbst:

@[embed(style="height: 450px; width:450px; border: none")](html/2/zahlensysteme.html)


[^1]: ein Algorithmus ist eine Schritt-für-Schritt-Anleitung zur Lösung eines Problems. Algorithmen sind in der Informatik von zentraler Bedeutung.

## Binärsystem


<div class="flex-container">

<div class="flex-child">
Wie wir bereits wissen, arbeiten Computer digital und kennen meist nur zwei verschiedene Zustände: 

1. keine elektrische Spannung liegt an, oder $0$ 
2. elektrische Spannung liegt an, oder $1$

So haben wir nur zwei Symbole, $0$ und $1$ zur Verfügung, um alle digitalen Daten zu speichern und zu verarbeiten.
Für die Darstellung von Zahlen bietet sich so für Computer das Binärsystem, also das Zahlensystem mit Basis 2, an.

Es kennt nur die Ziffern $0$ und $1$ und kann so alle Zahlen darstellen, die wir im Dezimalsystem kennen.

</div>

<div class="flex-child">


![Leibnitz](https://upload.wikimedia.org/wikipedia/commons/a/ac/Leibniz_binary_system_1703.png "Leibniz, *Explication de l'arithmétique binaire* (1703).  Die erste Publikation über das Rechnen im Binärsystem.")


</div>


</div>

### Binärzahlen lesen

Man interpretiert Binärzahlen genau so wie alle anderen Positionssysteme. 

In diesem Rechner sehen Sie, wie man eine Binärzahl durch Addition der Zweierpotenzen in eine Dezimalzahl umrechnen kann.

*klicken Sie auf die Bits um sie umzuschalten*

<div class="center my-3">

@[embed(style="height: 420px; width:420px; border: none")](html/2/binaerzahlen.html)

</div>

<div class="alert exercise">

Was ist wahr über Binärzahlen?
-------------------------------

- [[X]] Alle Binärzahlen die auf 0 enden sind gerade
- [[ ]] Alle Binärzahlen die auf 10 enden sind durch vier teilbar.
- [[X]] Alle Binärzahlen mit nur einer 1 sind eine Zweierpotenz.
- [[X]] Die größte Binärzahl, die sich mit $n$ Stellen darstellen lässt ist $2^n-1$.
- [[ ]] Alle Binärzahlen mit nur einer 1 sind gerade.

</div>

### Binäre Addition
Man kann man mit binären Zahlen genauso rechnen, wie man es vom Dezimalzahlen gewohnt ist. 
Da es ja aber nur die Ziffern $0$ und $1$ gibt, ergibt schon $1+1=10$ einen Übertrag.

Eine schriftliche Addition mit Binärzahlen kann man so durchführen:

<div class="flex-container">
<div class="flex-child-1 alert exercise">

Übung
-----

Verwenden Sie den Rechner um $0111_2 + 0011_2$ zu addieren. \
Was ist das Ergebnis als Binärzahl?[^1] [[ 1010 ]]\
$0111_2$ ist dezimal: [[ 7 ]]\
$0011_2$ ist dezimal: [[ 3 ]]\
Die Summe der Binärzahlen ist also dezimal: [[ 10 ]]
*************************
Sie sehen, das Ergebnis ist richtig: $7+3=10$.
*************************

</div>
<div class="flex-child">

@[embed(style="height: 320px; width:300px; border: none")](html/2/binaeraddition.html)

</div>

</div>

[^1]: Geben Sie das Ergebnis ohne führende Nullen ein. Das sind Nullen, die vor der ersten Eins stehen und nicht zum Wert der Zahl beitragen.

#### Übungen: Binäre Addition

> Hier können Sie selbst die binäre Addition üben.
> Am besten lösen Sie die Aufgaben schriftlich und überprüfen es dann hier online. Wenn Sie geübter sind, können Sie die Aufgaben auch im Kopf lösen	
> Geben Sie das Ergebnis stets ohne führende Nullen[^1] an.

<div class="alert exercise">

Addieren Sie die folgenden Binärzahlen:
---------------------------------------

a)
---

`00001111`\
`01110101`

<!-- style= "max-width: 16em; "-->
[[10000100]]

---

b)
---

`01110001`\
`01011010`

<!-- style= "max-width: 16em"-->
[[11001011]]


---

c)
---


`10101111`\
`01001001`

<!-- style= "max-width: 16em"-->
[[11111000]]

---

d)
---

`01011000`\
`00010011`

<!-- style= "max-width: 16em"-->
[[1101011]]

---

e)
---

`0100100100110111`\
`1000000100110111`

<!-- style= "max-width: 20em"-->
[[1100101001101110]]


---

f)
---

`0010110101100010`\
`0010111100001011`

<!-- style= "max-width: 20em"-->
[[101110001101101]]

---

[^1]: Führende Nullen sind Nullen, die vor der ersten Eins stehen. Wenn sie also als Ergebnis $0010$ erhalten, schreiben Sie einfach $10$.

</div>



## Oktal- und Hexadezimalsystem


Neben dem Binärsystem sind das Oktal- und insbesondere das Hexadezimalsystem[^1] wichtig für die Informatik. Der Grund dafür ist, dass Binärzahlen sich einfach in Oktal- oder Hexadezimalzahlen umwandeln lassen. So erlauben diese beiden Zahlensysteme Informatikern eine effiziente Darstellung digitaler Daten.

[^1]: Das ist das Zahlensystem, mit der Basis 16.

### Oktalzahlen 

Zunächst können wir am Oktalsystem sehen, wie leicht diese Umwandlung in beide Richtungen geht.
So entspricht jede Ziffer im Oktalsystem genau drei Ziffern im Binärsystem:

<!-- style="max-width:650px"-->
```ascii

Oktal |   0   |   1   |   2   |   3   |   4   |   5   |   6   |   7   
------+-------+-------+-------+-------+-------+-------+-------+------ 
Binär |  000  |  001  |  010  |  011  |  100  |  101  |  110  |  111  
```


<div class="alert example">

Beispiel 1
----------

Die Binärzahl $100001$ besteht aus den zwei Dreierblöcken $100$ und $001$, also $4$ und $1$, 
diese Zahl ist also oktal $41$ (oder dezimal $33$).


Beispiel 2
----------

Bei der Umwandlung einer Binär- in eine Oktalzahl gehen wir von rechts nach links vor und ergänzen, 
falls nötig, links Nullen für den letzten Dreierblock.

Die Binärzahl $11001_2$ entspricht $011\;001_2$ und damit oktal $31_8$


</div>


<div class="alert tip">

Oktal-zu-Binär-Rechner
-----------------------

> Geben Sie eine Oktalzahl ein und sehen Sie, wie sie in eine Binärzahl umgewandelt wird.

@[embed(style="height: 190px; width:400px; border: none")](html/2/octal.html)

</div>

### Zahlensymbole

Für alle Positionssysteme mit einer Basis $b\leq10$ benutzt man die bekannten Ziffern 
$$
0,1,2,3,4,5,6,7,8,9
$$. 

Es gibt aber auch Zahlensysteme mit einer Basis größer als zehn. Dafür genügt dann unser normaler Ziffernvorrat nicht. 
Wir können auf Buchstaben zurückgreifen, sodass wir zum Beispiel in einem Zwölfersystem den Buchstaben $\text{A}$ für $10$ und den Buchstaben $\text{B}$ für $11$ verwenden können. 

$10_{12}$ liest man als $1\cdot 12^1 + 0 \cdot 12^0$ und steht dann für $12$. Wir zählen zur Basis Zwölf also folgendermaßen: 

$$
1,2,3,4,5,6,7,8,9,\text{A},\text{B},10,11,\ldots
$$ 

<div class="alert exercise">

Übung
-----

Was ist der Wert der Zahl $2\text{A}_{12}$? (Basis 12)

- [[ ]] 122
- [[ ]] 26
- [[ ]] 210
- [[X]] 34
***********************
$$ 2 \cdot 12^1 + 10 \cdot 12^0 = 24 + 10 = 34 $$ 
***********************

</div>

In der Informatik verwendet man auch das Sechzehnersystem, das auch Hexadezimalsystem genannt wird. Es verwendet zusätzlich zu den zehn Ziffern noch die sechs Buchstaben $$\text{A,B,C,D,E,F}$$ als zusätzliche Ziffern. So steht zum Beispiel  $\text{E}$ für 14.

Für die platzsparende Kodierung von Daten verwenden Informatiker sogar ein System mit 64 verschiedenen Symbolen, das sogenannte *BASE64*-System.



### Hexadezimalzahlen

Jede Ziffer im Hexadezimalsystem entspricht genau vier Ziffern im Binärsystem. Da wir keine Ziffernsymbole für 10,11,12,13,14 und 15 haben, benutzen wir im Hexadezimalsystem die Buchstaben A,B,C,D,E,F[^1].

Ähnlich wie bei den Oktalzahlen, können wir auch hier die Binärzahlen in Viererblöcke zerlegen und so leicht in Hexadezimalzahlen umwandeln (oder umgekehrt):

<!-- style="max-width:770px"-->
```ascii

Hexadezimal |    0   |    1   |    2   |    3   |    4   |    5   |    6   |    7   
------------+--------+--------+--------+--------+--------+--------+--------+-------- 
Binär       |  0000  |  0001  |  0010  |  0011  |  0100  |  0101  |  0110  |  0111  


Hexadezimal |    8   |    9   |    A   |    B   |    C   |    D   |    E   |    F  
------------+--------+--------+--------+--------+--------+--------+--------+-------- 
Binär       |  1000  |  1001  |  1010  |  1011  |  1100  |  1101  |  1110  |  1111  

```


Beispiel
--------

Die Binärzahl $101011$ besteht aus den zwei Viererblöcken $0010$ und $1011$, also $2$ und $B$, 
diese Zahl ist also hexadezimal $2\text{B}$ (oder dezimal $43$).


<div class="alert tip">

Hexadezimal-zu-Binär-Rechner
----------------------------

> Hier sehen Sie, wie eine Hexadezimalzahl in eine Binärzahl umgewandelt wird.

@[embed(style="height: 190px; width:500px; border: none")](html/2/hex.html)

</div>

<div class="alert exercise">

Übung
------

Wandeln Sie die Binärzahl `0010101000011010` in eine Hexadezimalzahl um:

[[2A1A]]

</div>

[^1]: Manchmal werden auch die Kleinbuchstaben a,b,c,d,e,f verwendet.


## Spiel: Binärmeister 

Wie gut beherrschen Sie bereits die Binärzahlen? Testen Sie sich in diesem Spiel!

*Sobald Sie starten, erscheinen immer mehr gelbe Bits auf der linken Seite. Sie können die Bits mit Klicken umschalten, so dass Sie der Zahl rechts davon entsprechen. Sobald sie eine Zeile gelöst haben, verschwindet sie. Bei 8 ungelösten Zeilen haben sie verloren!*
@[embed(style="height: 800px; width:100%; border: none")](html/2/binaermeister.html)
