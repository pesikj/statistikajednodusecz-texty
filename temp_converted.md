

Levostranný test na rozptyl
===========================





Výpočet ve starších verzích
---------------------------


Starší verze Excelu nabízejí pouze pravostranné varianty funkcí. V případě určení hranice kritického oboru musíme jako hodnotu kvantilu zadat $ 1 - \alpha$:



```
=CHIINV(1-D5;D2-1)
```

Při určování p-hodnoty je pak třeba odečíst výslednou hodnotu od jedničky, abychom získali plochu pod hustotou pravděpodobnosti mezi nulou a hodnotou statistiky:



```
=1-CHIDIST(F8;D2-1)
```

Výsledek testu
--------------


Oba postupy vedou ke stejnému výsledku, jak je vidět na obrázku níže. Sloupec F pracuje s funkcemi ze starší verze Excelu, sloupce D a E s funkcemi z novější verze.



![test-rozptyl data a vysledky 2](http://statistikajednoduse.cz/wp-content/uploads/2017/12/test-rozptyl-data-a-vysledky-2.png)
Soubor se všemi výpočty si můžete stáhnout zde: [test-rozptyl](http://statistikajednoduse.cz/wp-content/uploads/2017/12/test-rozptyl.xlsx "test-rozptyl")


Rozdělení testové statistiky
============================


Nyní si velmi zjednodušeně vysvětlíme, proč má statistika $ T$ právě $ \chi^2$ rozdělení. Toto rozdělení má jednu důležitou vlastnost. Uvažujme, že máme $ n$ náhodných veličin, které jsou vzájemně nezávislé a které mají normované normální rozdělení. Tyto veličiny si označíme $ U\_1, U\_2,  \dots U\_n$. Jestliže pak máme veličinu, která je součtem druhých mocnin těchto veličin, tj. veličinu $ \chi^2 = \sum\limits\_{i=1}^n U\_i^2$, pak má tato veličina $ \chi^2$ rozdělení a počet stupňů volnosti odpovídá počtu náhodných veličin.


Rozepišme si nyní vzorec pro statistiku testu $ T$:


$ T = \frac{ \left( n - 1 \right) \sum\limits\_{i=1}^n \left( x\_i - \bar{x} \right)^2 }{ \left(n - 1 \right) \sigma\_0^2 } = \frac{ \sum\limits\_{i=1}^n \left( x\_i - \bar{x} \right)^2 }{ \sigma\_0^2 } = \left(\frac{x\_1 - \bar{x}}{ \sigma\_0} \right)^2 + \left(\frac{x\_2 - \bar{x}}{ \sigma\_0 } \right)^2 + \dots + \left( \frac{x\_n - \bar{x}}{ \sigma\_0 } \right)^2\, .$


Uvažujme nyní libovolný $ i$-tý výraz $ \frac{x\_i - \bar{x}}{ \sigma\_0 }$. Náhodná veličina $ x\_i$ má normální rozdělení, což je dáno předpokladem testu. Průměr náhodného výběru $ \bar{x}$ je nestranným odhadem střední hodnoty rozdělení. Platí-li nulová hypotéza $ H\_0$, pak má náhodná veličina $ x\_i$ rozptyl $ \sigma\_0^2$ a tedy směrodatnou odchylku $ \sigma\_0$.


Obecně platí, že máme-li náhodnou veličinu s normálním rozdělením $ X$, můžeme ji snadno převést na veličinu s normovaným normálním rozdělením $ U$ tím, že od ní odečteme její střední hodnotu $ \mu$ a výsledek vydělíme směrodatnou odchylkou $ \sigma$, tj. provedeme operaci


$ U = \frac{X-\mu}{\sigma} \, .$


Platí-li tedy nulová hypotéza $ H\_0$, pak je statistika $ T$ součtem druhých mocnin veličin s normovaným normálním rozdělením a tím pádem vyhovuje základní vlastnosti $ \chi^2$ rozdělení. Je rovněž zřejmé, proč u tohoto testu formulujeme předpoklad normality.


