
Welchův test používáme pro soubory, jejichž pozorování **nejsou spárována a nemůžeme u nich předpokládat shodný rozptyl**. V některých učebnicích statistiky je doporučeno začít s ověřením hypotézy o shodě rozptylů pomocí Fischerova testu a dle výsledku poté zvolit variantu t-testu. Tento postup však není korektní.

Levostranný Welchův t-test
--------------------------

Abychom si ještě jednou ukázali odlišnost Welchova testu, vyjdeme ze zadání z předchozích dvou článku: *Máme data o průměrném počtu vyrobených výrobků pracovníky **ve dvou různých závodech**, přičemž v jednom ze závodů jsou testovány nové výrobní procesy. Vedení společnosti potřebuje ověřit, zda nové výrobní postupy zvýšily produktivitu práce. Ověřte na [latex] \alpha = 5 % [/latex] hypotézu, že v závodě s novými výrobními postupy vyrobí pracovníci v průměru více výrobků, než v závodě s původními postupy, přičemž předpokládáme, že **rozptyly** průměrného počtu výrobků **se mohou lišit**. Vedení v minulosti statisticky ověřilo, že před změnou procesů byli pracovníci v obou závodech v průměru stejně výkonní.*

Data jsou v tabulce níže

| Závod 1 | 199.98214 | 200.02066 | 200.02763 | 199.95948 | 199.99668 | 200.01018 | 199.99315 | 199.97664 | 200.01485 | 199.96795 | 199.92523 | 200.02216 | 200.03065 | 200.01761 | 200.01264 | 200.08308 | 199.99550 | 200.00041 | 199.99517 | 200.02942 |
| Závod 2 | 200.04822 | 200.08817 | 200.04806 | 200.01402 | 200.03498 | 199.92516 | 200.09787 | 200.10234 | 199.95363 | 200.01334 | 199.97706 | 200.01043 | 199.96209 | 199.91984 | 200.08773 | 200.04719 | 199.98357 |  |  |  |


Opět zavedeme značení: [latex] X\_1 [/latex] obsahuje pozorování ze závodu se starými postupy a soubor [latex] X\_2 [/latex] pozorování ze závodu s upravenými postupy. Příslušné střední hodnoty pak označíme [latex] \mu\_{X\_1} [/latex] a [latex] \mu\_{X\_2} [/latex]. Nyní můžeme formulovat nulovou a alternativní hypotézu:


* [latex] H\_0: \mu\_{X\_1} = \mu\_{X\_2} [/latex] (Střední hodnota obou souborů je stejná.)
* [latex] H\_1: \mu\_{X\_1} < \mu\_{X\_2} [/latex] (Střední hodnota prvního souboru je nižší.)


Statistiku testu vypočteme dle vzorce


[latex] T = \frac{\bar{X\_1} - \bar{X\_2}}{\sqrt{\frac{s\_1^2}{n\_1} + \frac{s\_2^2}{n\_2}}} \, , [/latex]


kde [latex] \bar{X\_1} [/latex] a [latex] \bar{X\_2} [/latex] značí průměry, [latex] s\_1^2 [/latex] a [latex] s\_2^2 [/latex] výběrové rozptyly a [latex] n\_1 [/latex] a [latex] n\_2 [/latex] počty pozorování. Statistika má opět Studentovo (t) rozdělení. Poměrně složitý je tentokrát určení počtů stupňů volnosti, proto se ručnímu výpočtu vyhneme a provedeme výpočet pouze pomocí Analýzy dat a funkce T.TEST.



![](https://statistikajednoduse.cz/wp-content/uploads/2019/12/Levostranný-Welchův-test-Excel-1-1024x398.png)

### Výpočet pomocí doplňku Analýza dat


V Analýze dat tentokrát volíme možnost **Dvouvýběrový t-test s nerovností rozptylů**.



![](https://statistikajednoduse.cz/wp-content/uploads/2019/12/Výběr-testu.png)
Do polí 1. soubor a 2. soubor vybereme oblasti s daty. Vybereme-li oblasti včetně záhlaví, zaškrtneme pole Popisky. Dále označíme Výstupní oblast a stiskneme tlačítko OK.



![](https://statistikajednoduse.cz/wp-content/uploads/2019/12/Levostranný-Welchův-test-AD-výsledky.png)
Na obrázku níže vidíme výsledky.



![](https://statistikajednoduse.cz/wp-content/uploads/2019/12/Levostranný-Welchův-test-AD-výsledky-2-1.png)
 Protože provádíme levostranný test, zajímají nás označené řádky. Hodnota statistiky je tedy [latex] T = -0{,}9650 [/latex]. Kritický obor se nachází vlevo, proto vezmeme hranici z řádku t krit (1) a přidáme k ní tlačítko minus. Kritický obor tedy leží v intervalu [latex] W = \left( - \infty, -1{,}7109 \right\rangle [/latex]. P-hodnota testu je [latex] 0{,}1721 [/latex]. P-hodnota skutečně odpovídá naší variantě testu. Protože p-hodnota je vyšší než hladina významnosti, nezamítáme [latex] H\_0 [/latex].


Poznámka

 Statistika testu je totiž záporná a tím pádem musí být p-hodnota menší než [latex] 0{,}05[/latex]. 


### Výpočet pomocí funkce T.TEST


Funkce T.TEST (ve starších verzích TTEST) vrací p-hodnotu testu. Prvními dvěma parametry jsou soubory s daty. Třetím parametrem je varianta testu (oboustranný nebo jednostranný), zadáváme tedy 1. Posledním parametrem volíme, zda se jedná o párový t-test (1), Studentův t-test (2) nebo Welchův test (3).



```
=T.TEST(A2:A21,B2:B18,1,3)
```

Pro naše data vrací funkce hodnotu [latex] 0{,}1721 [/latex], na základě toho bychom tedy nezamítli [latex] H\_0 [/latex].


#### Obecná funkce pro levostranný test


Funkce T.TEST funguje na podobném principu jako výpočet p-hodnoty u Analýzy dat, tj. vrací menší z možných dvou p-hodnot. Teoreticky by se mohlo stát, že by hodnota statistiky byla vyšší než 0 a tím pádem by p-hodnota testu byla vyšší 0,5. Funkce T.TEST však vrací vždy p-hodnotu menší než 0,5, tj. vracela by p-hodnotu pro pravostranný test. Rozhodnutí můžeme opět provést na základě hodnoty statistiky a pomocí funkce KDYŽ:



```
=KDYŽ(E8<0,T.TEST(A2:A21,B2:B18,1,3),1-T.TEST(A2:A21,B2:B18,1,3))
```

Samotný vzorec pro výpočet statistiky je 



```
=(E3-F3)/ODMOCNINA(E4/E2+F4/F2)
```

Pravostranný Welchův test
-------------------------


Uvažujme nyní, že máme obdobné zadání, máme však data o průměrné době potřebné na výrobu jednoho výrobku. Pokud by technologické postupy v novém závodě byly efektivnější, průměrná doba výroby by měla být nižší. Data jsou v tabulce níže.




| Závod 1 | 44.69267 | 45.69315 | 44.42006 | 44.49233 | 44.76451 | 45.71278 | 45.26229 | 44.96354 | 45.32207 | 43.99095 | 45.64706 | 45.13311 | 44.88322 | 45.76855 | 43.95434 | 45.43278 | 45.29947 | 44.9996 | 45.76979 | 45.38547 | 45.88574 | 44.68477 | 44.88063 | 45.06176 | 45.37277 |  |  |
| Závod 2 | 44.22226 | 44.78572 | 44.39838 | 45.08415 | 44.80706 | 44.03529 | 44.19068 | 45.15528 | 43.99419 | 44.79819 | 43.9513 | 44.92697 | 44.97488 | 45.43995 | 44.49937 | 44.81813 | 45.614 | 44.51578 | 43.90898 | 44.15076 | 43.78361 | 44.33133 | 44.362 | 44.22765 | 44.01149 | 45.01004 | 44.2919 |


Modifikujeme alternativní hypotézu a získáme dvojici hypotéz:


* [latex] H\_0: \mu\_{X\_1} = \mu\_{X\_2} [/latex]
* [latex] H\_1: \mu\_{X\_1} > \mu\_{X\_2} [/latex]


Hladina významnosti je stále [latex] \alpha = 5 % [/latex].



![](https://statistikajednoduse.cz/wp-content/uploads/2019/12/Pravostranný-Welchův-test-Excel-1024x488.png)
### Výpočet pomocí doplňku Analýza dat


Postup výpočtu je naprosto stejný jako u levostranného testu. Pro aktuální data máme výstup na obrázku níže.



![](https://statistikajednoduse.cz/wp-content/uploads/2019/12/Pravostranný-Welchův-test-AD-výsledky-2.png)
Hodnota statistiky je nyní [latex] T = 3{,}9928 [/latex]. Kritický obor se nachází vpravo, proto hranici najdeme v řádku t krit (1) a tentokrát ji nijak neupravujeme. Kritický obor tedy leží v intervalu [latex] W = \left\rangle 1{,}6766 , \infty \right) [/latex]. Vidíme, že statistika lež v kritickém oboru. p-hodnota testu je [latex] 0{,}0001 [/latex], zamítáme tedy [latex] H\_0 [/latex]. Na [latex] \alpha = 5 % [/latex] jsme prokázali, že výroba ve druhém závodě je rychlejší.


### Výpočet pomocí funkce T.TEST


Zápis funkce je opět stejný, tj.:



```
=T.TEST(A2:A26,B2:B28,1,3)
```

Funkce vrací p-hodnotu testu, což je [latex] 0{,}0001[/latex]. Nulovou hypotézu bychom opět zamítli.


Pokud bychom opět chtěli obecný vzorec, který si poradí i s p-hodnotami vyššími než 0,5, upravíme jej o podmínku na základě hodnoty statistiky:



```
=KDYŽ(E8>0,T.TEST(A2:A26,B2:B28,1,3),1-T.TEST(A2:A26,B2:B28,1,3))
```

Oboustranný Welchův test
------------------------


V případě oboustranného testu řešíme pouze to, zda je mezi středními hodnotami rozdíl. Vraťme se k našemu příkladu s počty vyrobených výrobků ve dvou různých závodech. Nyní tedy rozhodneme "pouze" o tom, zda se průměrné počty mezi závody liší.


Naše hypotézy jsou nyní:


* [latex] H\_0: \mu\_{X\_1} = \mu\_{X\_2} [/latex] (Střední hodnota obou souborů je stejná.)
* [latex] H\_1: \mu\_{X\_1} \neq \mu\_{X\_2} [/latex] (Střední hodnota prvního souboru je nižší.)


Data z obou závodů jsou v tabulce níže.




| Závod 1 | 190.53082 | 190.70691 | 190.68514 | 189.32068 | 189.93107 | 189.65363 | 189.62920 | 190.15749 | 189.88063 | 190.15778 | 189.86708 | 190.81115 | 190.35090 | 189.60921 | 190.38187 | 190.85053 | 189.79748 | 189.90501 | ######## | ######## |  |  |  |  |  |
| Závod 2 | 190.51846 | 191.86783 | 191.71020 | 189.71007 | 189.79866 | 190.82983 | 191.09171 | 190.59191 | 190.10827 | 190.59553 | 190.91844 | 190.10630 | 190.16401 | 190.00247 | 190.19419 | 190.20659 | 190.03263 | 190.37341 | ######## | ######## | ######## | ######## | ######## | ######## | ######## |


Test opět provedeme na hladině významnosti [latex] \alpha = 5 % [/latex].



![](https://statistikajednoduse.cz/wp-content/uploads/2019/12/Oboustranný-Welchův-test-Excel-1024x469.png)
### Výpočet pomocí doplňku Analýza dat


Test spustíme pomocí stejného postupu jako v ostatních variantách. Hodnota statistiky testu je [latex] T = -2{,}0854 [/latex]. p-hodnotu a hranici kritického oboru nyní najdeme v posledních dvou řádcích. p-hodnota testu je [latex] 0{,}0430 [/latex]. Kritický obor je v případě oboustranného testu rozdělen na dvě části. Analýza dat nám vrací dolní hranici pravé části, horní hranici levé získáme, když před danou hranici napíšeme 0. Kritický obor je tedy [latex] W = \left( -\infty, - 2{,}0167 \right\rangle \cup \left\langle 2{,}0167, \infty \right) [/latex].



![](https://statistikajednoduse.cz/wp-content/uploads/2019/12/Oboustranný-Welchův-test-AD-výsledky.png)
Statistika tedy leží v kritickém oboru a p-hodnota je nižší než hladina významnosti, na [latex] \alpha = 5 % [/latex] tedy zamítáme [latex] H\_0 [/latex]. Tentokrát jsme však pouze prokázali, že mezi výkonností závodů existuje rozdíl, nelze však tvrdit, že v druhém závodě je výkonnost vyšší.


### Výpočet pomocí funkce T.TEST


V případě oboustranného testu zadáváme na třetí pozici číslo 2, díky čemuž nám funkce T.TEST vrátí p-hodnotu oboustranného testu. V našem případě to je tedy hodnota [latex] 0{,}0430 [/latex].



```
=T.TEST(A2:A21,B2:B26,2,3)
```

V případě oboustranného testu je vrácená hodnota vždy správná a funkci již nemusíme nijak upravovat.


