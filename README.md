# Taxicab numbers, upper bounds and their decomposition

**[English] Introduction**\
Refers to https://oeis.org/A011541 sequence.\
See also http://www.christianboyer.com/taxicab/ and http://www.christianboyer.com/taxicab/TaxicabUpperBounds.pdf 
(or archive at https://cs.uwaterloo.ca/journals/JIS/VOL11/Boyer/boyer-new.pdf)

Taxicab(n) - or Ta(n) or T(n) or T(n, 1) or Taxicab(**3**, n, n) - is the smallest number expressible as a sum of two positive **cubes** in n different ways.\
For n > 6, as described in Boyer's paper, there is an <ins>upper bound</ins> list, as Bta(n) described in OEIS sequence.

> Ta(n) <= BTa(n) = r * s, with r < s\
 r = x + y, with x < y\
 s = x² - xy + y²\
 delta = 12s - 3r²\
 x = (3r - sqrt(delta)) / 6\
 y = (3r + sqrt(delta)) / 6\
 sqrt(delta) = 3 * (y - x)

Note that s can also be written: s = (y - x)² + x * y\
then for each {x,y}, Ta(n) = sum * ( (diff)² + product ).

Let x(n, i) and y(n, i) denote the i th x and y for BTa(n) or Ta(n).

If x or y is odd (but not both):
> w = (y + x + 1) / 2 = (r + 1) / 2\
v = (y - x - 1) / 2 = y - w = (sqrt(delta) - 1) / 6\
Ta(n) <= BTa(n) = (w - v - 1)³ + (v + w)³

else (if x and y are both even or are both odd)
> w = (x + y) / 2 = r / 2\
v = (y - x) / 2 = y - w = sqrt(delta) / 6\
Ta(n) <= BTa(n) = (w - v)³ + (v + w)³

**[English] Decomposition of Ta(n) or BTa(n)**

* [source code](https://github.com/JL2014/taxicab/blob/main/taxicab.cpp) contains all x,y values with r,s and delta components for checking matches
* [text output of the program execution](https://github.com/JL2014/taxicab/blob/main/taxicab.txt) shows if values are correct
* [taxicab_x](https://github.com/JL2014/taxicab/blob/main/taxicab_x.md) contains x values
* [taxicab_y](https://github.com/JL2014/taxicab/blob/main/taxicab_y.md) contains y values
* [taxicab_r](https://github.com/JL2014/taxicab/blob/main/taxicab_r.txt) contains r values
* [taxicab_s](https://github.com/JL2014/taxicab/blob/main/taxicab_s.txt) contains s values

**[French]**\
Détails sur [wikipedia](https://fr.wikipedia.org/wiki/Nombre_taxicab).\
Le plus petit nombre Ta(n) qui est la somme de 2 cubes entiers positifs x<sub>(n, i)</sub> et y<sub>(n, i)</sub> de n façons, soit Ta(n) = x<sub>(n, i)</sub>^3 + y<sub>(n, i)</sub>^3 (pour i allant de 1 à n).\
Pour n > 6, BTa(n) indique la limite supérieure de Ta(n).\
On pourra également utiliser la notation T(n, k) pour la k-ième plus petite solution non-primitive (avec k > 1) pouvant s'écrire de n manières comme une somme de deux cubes d'entiers positifs.

**[French] Remarques**
- La valeur de x<sub>(n+1, 1)</sub> est supérieure (ou égale pour n=1) à celle de y<sub>(n, 1)</sub>
- Si on multiplie les {x<sub>(5, i)</sub>, y<sub>(5, i)</sub>} par **79** ou **139** ou un multiple de 79 ou un multiple de 139, on obtient un multiple de T(6)
- Certains x<sub>(n, i)</sub> ont une différence multiple de **11**: {1,12}, {414,436}, {331954,365757}, {27093208,28906206}
  - de même pour: {255,167}, {13322,2421}, {231518,38787}, {26590452,582162}
- Sauf pour T(1), il y a plusieurs x<sub>(n, i)</sub> multiples de **3** mais on peut constater un couple de x<sub>(n, i)</sub> (espacés de 2 termes) multiples de **3** (et donc leur différence aussi): {9,12}, {228,423}, {10200,18072}, {221424,336588}, {1766742096,2685635652}

**[English] Relationships**

- BTa(23) <= 505624992450102221744244678441689845434887715317085055675501100061664233777550644179891369792998312033624027623507268993575520089167244066787797454194149200985506392000000000

  - z = 97 * 491 = 47627
  - BTa(23) = z^3 * BTa(22)

- BTa(22) <= 4680247859298792255465896583920257161776853980641720488623945439873944558056759119053262369879441902130153472288312996410513410535472957059046536164424000000000

  - z = 11 * 31 * 103 = 35123
  - BTa(22) = z^3 * BTa(21)

- BTa(21) <= 108017480260055891349349434078007118409816211596074421874782013152781209964290521967447172971431469705047741717793222992124981940703226072000000000

  - z = 127 * 197 = 25019
  - BTa(21) = z^3 * BTa(20)
  - {x<sub>(21, i)</sub>, y<sub>(21, i)</sub>} = z * {x<sub>(20, i)</sub>, y<sub>(20, i)</sub>} (except for i=7)

- BTa(20) <= 6897380753715950027554119762858815120976857451913869723850868496922922856256366585322070924221550029921862628606999892276808000000000

  - z = 5^2 * 457 * 521 = 5952425
  - BTa(20) = z^3 * BTa(18)
  - {x<sub>(20, i)</sub>, y<sub>(20, i)</sub>} = z * {x<sub>(18, i)</sub>, y<sub>(18, i)</sub>} (except for i=14)

- BTa(19) <= 89155799373431424956779039683208074195259067508030416952016859893056008200986665364956362114476625742414288155368000000000

  - 

- BTa(18) <= 32704115261272222010108668321371490956498583891096244871994833214348230808345220932546725287574509356813791744000

  - z = 37 * 181 = 6697
  - BTa(18) = z^3 * BTa(17)
  - {x<sub>(18, i)</sub>, y<sub>(18, i)</sub>} = z * {x<sub>(17, i)</sub>, y<sub>(17, i)</sub>} (except for i=1)

- BTa(17) <= 108883358434560363503260016942467566965657808716401027019007732065428469239764403684536752685040128000

  - z = 4261
  - BTa(17) = z^3 * BTa(16)
  - {x<sub>(17, i)</sub>, y<sub>(17, i)</sub>} = z * {x<sub>(16, i)</sub>, y<sub>(16, i)</sub>} (except for i=3)

- BTa(16) <= 1407430328457240141244921568479580896498768360005757901394557724136294559835243494681088000

  - z = 2 * 607 = 1214
  - BTa(16) = z^3 * BTa(15)
  - {x<sub>(16, i)</sub>, y<sub>(16, i)</sub>} = z * {x<sub>(15, i)</sub>, y<sub>(15, i)</sub>} (except for i=12)

- BTa(15) <= 786630615595626829796137755567437844038832146564530660386728812791938555036352000

  - z = 503
  - BTa(15) = z^3 * BTa(14)
  - {x<sub>(15, i)</sub>, y<sub>(15, i)</sub>} = z * {x<sub>(14, i)</sub>, y<sub>(14, i)</sub>} (except for i=4)

- BTa(14) <= 6181115942163278484307116174514304039670628856329988877227399275142976000

  - z = 397
  - BTa(14) = z^3 * BTa(13)
  - {x<sub>(14, i)</sub>, y<sub>(14, i)</sub>} = z * {x<sub>(13, i)</sub>, y<sub>(13, i)</sub>} (except for i=6)

- BTa(13) <= 98785992977316717572070208794037178343163969803121800608526912000

  - z = 3 * 61 = 183
  - BTa(13) = z^3 * BTa(12)
  - {x<sub>(13, i)</sub>, y<sub>(13, i)</sub>} = z * {x<sub>(12, i)</sub>, y<sub>(12, i)</sub>} (except for i=4)

- BTa(12) <= 16119148654034302034428760115512552827992287460693283776000

  - z = 3 * 19 = 57
  - BTa(12) = z^3 * BTa(11)
  - {x<sub>(12, i)</sub>, y<sub>(12, i)</sub>} = z * {x<sub>(11, i)</sub>, y<sub>(11, i)</sub>} (except for i=2)
  - {x<sub>(12,12)</sub>, y<sub>(12,12)</sub>} ​​do not contain 7
  - {x<sub>(12, 5)</sub>, y<sub>(12, 5)</sub>} ​​do not contain 13
  - {x<sub>(12, 4)</sub>, y<sub>(12, 4)</sub>} ​​do not contain 17

- BTa(11) <= 87039729655193781808322993393446581825405320183232000

  - {x<sub>(11,11)</sub>, y<sub>(11,11)</sub>} ​​do not contain 7
  - {x<sub>(11, 4)</sub>, y<sub>(11, 4)</sub>} ​​do not contain 13
  - {x<sub>(11, 3)</sub>, y<sub>(11, 3)</sub>} ​​do not contain 17

- BTa(10) <= 7335345315241855602572782233444632535674275447104

  - z = 13 * 29 = 377
  - BTa(10) = z^3 * BTa(9)
  - {x<sub>(10, i)</sub>, y<sub>(10, i)</sub>} = z * {x<sub>(9, i)</sub>, y<sub>(9, i)</sub>} (except for i=2)
  - {x<sub>2</sub>, y<sub>2</sub>} ​​do not contain 13 * 29
  - {x<sub>3</sub>, y<sub>3</sub>} ​​do not contain 139
  - {x<sub>5</sub>, y<sub>5</sub>} ​​do not contain 101

- BTa(9) <= 136897813798023990395783317207361432493888

  - z = 139
  - BTa(9) = z^3 * BTa(8)
  - {x<sub>(9, i)</sub>, y<sub>(9, i)</sub>} = z * {x<sub>(8, i)</sub>, y<sub>(8, i)</sub>} (except for i=2)

- BTa(8) <= 50974398750539071400590819921724352

  - z = 127
  - BTa(8) = z^3 * BTa(7)
  - {x<sub>(8, i)</sub>, y<sub>(8, i)</sub>} = z * {x<sub>(7, i)</sub>, y<sub>(7, i)</sub>} (except for i=8)

- BTa(7) <= 24885189317885898975235988544

  - z = 101
  - BTa(7) = z^3 * BTa(6)
  - {x<sub>(7, i)</sub>, y<sub>(7, i)</sub>} = z * {x<sub>(6, i)</sub>, y<sub>(6, i)</sub>} (except for i=3)

- Ta(6) = 24153319581254312065344

  - z = 79
  - BTa(6) = z^3 * BTa(5)
  - {x<sub>(6, i)</sub>, y<sub>(6, i)</sub>} = z * {x<sub>(5, i)</sub>, y<sub>(5, i)</sub>} (except for i=1)

- Ta(5) = 48988659276962496

- Ta(4) = 6963472309248

- Ta(3) = 87539319

  -  Ta(3) = (302 - 134 -1)³ + (302 + 134)³ = (326 - 97 - 1)³ + (326 + 97)³ = (335 - 79 - 1)³ + (335 + 79)³

- Ta(2) = 1729

- Ta(1) = 2

**Others**

~~T(19) <= 20400824749409517528805616329601248054238975120047899653306832282155305931553802798551427446267572330642814901020208524571911529017539708401834884288000~~ = **2^9** × **3^12** × 5^3 × **7^4** × **11^3** × **13^4** × 17^3 × **19** × **29^3** × **41^3** × **43** × **73** × **79^3** × **97** × **101^3** × **127^3** × **139^3** × **157** × 271^3 × **349^3** × **601^3** × **727^3** × **733^3** × **2311^3** × **2971^3** × **4327^3** × **7549^3**\
~~T(18) <= 1669102760262770599073633207770749663711833995754118800009115774272350540676865796358235477762975575548685960795354954969975483624898697728~~ = **2^9** × 3^12 × **7^4** × **11^3** × **13^4** × **19** × **29^3** × **41^3** × **43** × **73** × **79^3** × **97** × **101^3** × **127^3** × **139^3** × **157** × **349^3** × 601^3 × **727^3** × **733^3** × **2311^3** × **2971^3** × **4327^3** × **7549^3**\
~~T(17) <= 390632494425592857308683115941747067399542361030496398592266116103976300384768055853952870509972688279894938439376270144482816~~ = **2^9** × **3^3** × **7^4** × **11^3** × **13^4** × **19** × **29^3** × 41^3 × **43** × **73** × **79^3** × **97** × **101^3** × **127^3** × **139^3** × **157** × 349^3 × **727^3** × **733^3** × **2311^3** × **2971^3** × **4327^3** × **7549^3**\
~~T(16) <= 133333879575067044255496407342541909372921060713622256889696224426242257299346008208169434186136206003482924680704~~ = **2^9** × **3^3** × **7^4** × **11^3** × **13^4** × **19** × **29^3** × **43** × **73** × **79^3** × **97** × **101^3** × **127^3** × **139^3** × **157** × **727^3** × **733^3** × **2311^3** × **2971^3** × **4327^3** × **7549^3**\
~~T(15) <= 254361007450418467683691805874871224061387429621450309607817376336263717732850126485501423293412997632~~ = **2^9** × **3^3** × **7^4** × **13^4** × **19** × **29^3** × **43** × **73** × **79^3** × **97** × **101^3** × **127^3** × **139^3** × **157** × **727^3** × **2311^3** × **2971^3** × **4327^3**\
~~T(14) <= 591265120715306076227178149379165201865336472346517495072293984450950965960475614042157568~~ = **2^9** × **3^3** × **7^4** × **13^4** × **19** × **29^3** × **43** × **73** × **79^3** × **97** × **101^3** × **127^3** × **139^3** × **157** × **727^3** × 2311^3 × **2971^3** × **4327^3**\
~~T(13) <= 5988146776742829080553965820313279739849705084894534523771076163371248442670016~~ = 2^6 × 3^3 × **7^4** × 13^4 × 19 × 29^3 × **43** × **73** × **79^3** × 97 × 101^3 × 127^3 × **139^3** × **157** × 727^3 × 2971^3 × 4327^3

T(7, ?) = 64866613980488624314617087936\
x<sub>1</sub> = 80920518 = <ins>2 * 3 * 7 * 83 * 139 * 167</ins>\
x<sub>2</sub> = 317835644 = 2^2 * 7 * 79 * 143687\
x<sub>3</sub> = 425920047 = 3 * 7 * 79 * 139 * 1847\
x<sub>4</sub> = 1184180059 = 79 * 139 * 107839\
x<sub>5</sub> = 2254311452 = 2^2 * 17 * 79 * 139 * 3019\
x<sub>6</sub> = 2431456944 = 2^4 * 3 * 7 * 79 * 139 * 659\
x<sub>7</sub> = 2542299158 = 2 * 7 * 23 * 79 * 139 * 719\
y<sub>7</sub> = 3645186874 = 2 * 7 * 79 * 131 * 139 * 181\
y<sub>6</sub> = 3696072828 = 2^2 * 3 * 7 * 79 * 139 * 4007\
y<sub>5</sub> = 3765955912 = 2^3 * 79 * 139 * 163 * 263\
y<sub>4</sub> = 3983390693 = 79 * 139 * 362753\
y<sub>3</sub> = 4016377617 = 3 * 7 * 79 * 139 * 17417\
y<sub>2</sub> = 4017310528 = 2^6 * 7 * 11 * 17 * 79 * 607\
y<sub>1</sub> = 4017962634 = <ins>2 * 3 * 7 * 139 * 311 * 2213</ins>

T(4, ?) = 1801049058342701083 = 7 * 31 * 37 * 43 * 163 * 193 * 9151 * 18121\
x<sub>1</sub> = 92227\
x<sub>2</sub> = 136635 = 3 * 5 * 9109\
x<sub>3</sub> = 341995 = 5 * 68399\
x<sub>4</sub> = 600259 = 11 * 197 * 277\
y<sub>4</sub> = 1165884 = 2^2 * 3 * 97157\
y<sub>3</sub> = 1207602 = 2 * 3^3 * 11 * 19 * 107\
y<sub>2</sub> = 1216102 = 2 * 23 * 26437\
y<sub>1</sub> = 1216500 = 2^2 * 3 * 5^3 * 811

T(3, ?) = 15170835645 = 3^2 * 5 * 7 * 31 * 37 * 199 * 211\
x<sub>1</sub> = 517 = 11 * 47\
x<sub>2</sub> = 709\
x<sub>3</sub> = 1733\
y<sub>3</sub> = 2152 = 2^3 * 269\
y<sub>2</sub> = 2456 = 2^3 * 307\
y<sub>1</sub> = 2468 = 2^2 * 617

T(3, 4) = 175959000 = 35^3 ∗ T(2, 2)\
x<sub>1</sub> = 70 = 2 * 5 * 7\
x<sub>2</sub> = 198 = 2 * 3^2 * 11\
x<sub>3</sub> = 315 = 3^2 * 5 * 7\
y<sub>3</sub> = 525 = 3 * 5^2 * 7\
y<sub>2</sub> = 552 = 2^3 * 3 * 23\
y<sub>1</sub> = 560 = 2^4 * 5 * 7

T(2, 2) = 4104 = (12 − 3)³ + (12 + 3)³ = 2³ * (1³ + 8³)\
x<sub>1</sub> = 2\
x<sub>2</sub> = 9 = 3^2\
y<sub>2</sub> = 15 = 3 * 5\
y<sub>1</sub> = 16 = 2^4
