
## Zahlensymbole

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

Probieren Sie es selbst:

<div class="alert exercise">

Rechnen Sie $2A_{12}$ ins Dezimalsystem um
-------------------------------------------

[[34]]
*************************

Da $\text{A}$ im Zwölfersystem für $10$ steht, ergibt sich:
$$2\text{A}_{12} = 2\cdot 12^1 + 10\cdot 12^0 = 24 + 10 = 34$$

*************************
</div>

In der Informatik verwendet man auch das Sechzehnersystem, das auch Hexadezimalsystem genannt wird. Es verwendet zusätzlich zu den zehn Ziffern noch die sechs Buchstaben $$\text{A,B,C,D,E,F}$$ als zusätzliche Ziffern. So steht zum Beispiel  $\text{E}$ für 14.

Für die platzsparende Kodierung von Daten verwenden Informatiker sogar ein System mit 64 verschiedenen Symbolen, das sogenannte *BASE64*-System.


### Hexadezimalzahlen in Binärzahlen umwandeln



<!-- style="max-width:650px"-->
```ascii

Hexadezimal |    0   |    1   |    2   |    3   |    4   |    5   |    6   |    7   
------------+--------+--------+--------+--------+--------+--------+--------+------- 
      Binär |  0000  |  0001  |  0010  |  0011  |  0100  |  0101  |  0110  |  0111  

Hexadezimal |    8   |    9   |    A   |    B   |    C   |    D   |    E   |    F   
------------+--------+--------+--------+--------+--------+--------+--------+------- 
      Binär |  1000  |  1001  |  1010  |  1011  |  1100  |  1101  |  1110  |  1111  

```


@[embed(style="height: 210px; width:600px; border: none")](html/2/hex.html)



### Binäre Subtraktion

Die Subtraktion von Binärzahlen funktioniert ähnlich wie die Subtraktion im Dezimalsystem, mit dem Unterschied, dass man nur die Ziffern 0 und 1 zur Verfügung hat. Bei der binären Subtraktion entsteht ein Übertrag, wenn eine 0 von einer 1 subtrahiert wird.

<div class = "alert example flex-container"> 

<div class="flex-child">

<!--style = "max-width: 7em;"-->
```ascii
  0110
- 0011
  ----
  0011
```

</div>

<div class = "flex-child-4"> 

In der Spalte ganz rechts müssen wir $0 - 1$ rechnen. \
Dafür müssen wir uns aus der nächsten Spalte links eine $1$ „ausleihen“[^1].\
Die $0$ wird dadurch zur Binärzahl $10_2$ und das Ergebnis ist $10_2 - 1 = 1$.\
Da wir uns von der nächsten Spalte eine $1$ ausgeliehen haben, ist der Wert oben eine $0$.
Damit müssen wir in der nächsten Spalte wieder $0 - 1$ rechnen und eine $1$ ausleihen, das Ergebnis ist wieder $1$.\
Da die 1 in der dritten Spalte von rechts ausgeliehen wurde, verbleiben nur Nullen und wir sind fertig.

</div>

</div>



<!-- style = "margin-left:4em; max-width: 6em;" -->
```ascii

  1000
- 0111
  ----
  0001
```


[^1]: wie bei der schriftlichen Subtraktion im Dezimalsystem.

### Übungen: Binäre Subtraktion

> Versuchen Sie nun die folgenden binären Subtraktionen selbstständig zu lösen.
> Geben Sie das Ergebnis stets ohne führende Nullen an.
> 
<div class="alert exercise">

a)
---

`0110  -`\
`0011`\
`____`

[[11]]

---

b)
---

`1011  -`\
`0101`\
`____`

[[110]]

---

c)
---

`11001  -`\
`00111`\
`____`

[[10010]]

---

d)
---

`100101`  -\
`011010`\
`____`

[[1011]]

---

e)
---

`111100`\
`011011`\
`____`\
[[100001]]

---

f)
---

`10110101  -`\
`01011110`\
`________`\
[[1010111]]

---

</div>