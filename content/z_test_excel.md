Ukažme si nyní, jak provést výpočet v Excelu. Na ukázkovém listu máme data v buňkách A1 až A20\. Do buňky D2 si umístíme počet pozorování. Můžeme tam přímo zadat hodnotu 20, případně použít funkci POČET. Průměr pozorování zjistíme vzorcem

<pre class="wp-block-preformatted">=PRŮMĚR(A1:A20)</pre>

a uložíme ho v buňce D3\. Směrodatnou odchylku zapíšeme do D4, teoretickou střední hodnotu do D5 a hladinu významnosti do D6\. Hranice kritického oboru, které jsme si určili výše, uložíme do D8 a D9.

Nyní můžeme určit hodnotu statistiky pomocí vzorce:

<pre class="wp-block-preformatted">=(PRŮMĚR(A1:A20)-D5)/D4*ODMOCNINA(D2)</pre>

Protože ještě budeme zadávat vzorec pro p-hodnotu, uložte hodnotu statistiky do buňky D10.

![z-test data a výsledky](media/z-test-excel/z-test-data-a-vc3bdsledky.png)

Hodnota statistiky [latex] Z = -1,2125 [/latex]. Tato hodnota je mimo kritický obor, proto nulovou hypotézu nezamítáme.

## Určení p-hodnoty

V současné době se při testování hypotéz často využívá **p-hodnota**. p-hodnota je **mezní hladina významnosti, pro kterou ještě nulovou hypotézu nezamítáme**. Jinak řečeno, platí, že pokud je p-hodnota větší nebo rovna než hladina významnosti, nulovou hypotézu nezamítáme.

Podívejme-se na následující obrázek. Na něm vidíme p-hodnotu jako modrou šrafovanou plochu, což je plocha od hodnoty statistiky směrem vlevo. V případě našeho oboustranného testu musíme uvažovat i stejně velkou plochu napravo.

![](media/z-test-excel/p-hodnota.png)

p-hodnotu určíme pomocí distribuční funkce normálního rozdělení. Hodnotu statistiky máme v buňce D10\. Pro hodnoty distribuční funkce v Excelu použijeme funkci NORM.DIST, přičemž jako čtvrtý parametr zadáváme hodnotu PRAVDA. Pokud bychom zadali hodnota NEPRAVDA, získáme hodnotu funkce hustoty. Hodnotu distribuční funkce potřebujeme pro hodnotu statistiky. Protože uvažujeme i stejně velkou plochu v pravé části, násobíme výsledek funkce dvěma:

<pre class="wp-block-preformatted">=NORM.DIST(D10;0;1;PRAVDA)*2</pre>

## Použití funkce Z.TEST

Microsoft Excel obsahuje funkci Z.TEST pro provedení z-testu, která vrací p-hodnotu testované hypotézy. Bohužel je standardně tato funkce napsána pro provedení jednostranného testu pro nulovou hypotézu, že střední hodnota souboru větší než zadaná střední hodnota. Pro náš případ tedy musíme vzorec trochu upravit.

Proveďme následující úvahu.

*   Pokud je průměr náhodného výběru větší než teoretická střední hodnota, vrací nám funkce Z.TEST p-hodnotu menší než 0,5\. Takovou p-hodnotu můžeme použít. Protože však provádíme oboustranný test, pro náš výsledek násobíme ještě tuto hodnotu dvěma.
*   Pokud je průměr náhodného výběr menší než teoretická střední hodnota, vrací nám funkce Z.TEST p-hodnotu větší než 0,5\. V takovém případě odečteme tuto p-hodnotu od jedničky a výsledek násobíme dvěma.

Pro výpočet můžeme použít funkci MIN, která nám vrátí menší hodnotu z obou variant. Výsledek násobíme dvěma. Výsledný vzorec vypadá takto:

<pre class="wp-block-preformatted">=2*MIN(Z.TEST(A1:A20;D5;D4);1-Z.TEST(A1:A20;D5;D4))</pre>

Pro snazší pochopení se podívejte na obrázky níže. Na prvním jsou zeleně a modře obě varianty výsledků získaných z funkce Z.TEST. Z nich vybíráme tu menší, tj. modrou plochu. To provádí funkce MIN. Modrou plochu pak násobíme dvěma a získáme výslednou p-hodnotu.
