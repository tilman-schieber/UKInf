

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