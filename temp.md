<!-- wp:paragraph -->
<p>V minulých článcích jsme se zabývali testy o střední hodnotě. Střední hodnota je nejznámějším ukazatelem polohy. Ukazatele polohy charakterizují určitou úroveň hodnot v souboru. Dále se ale můžeme zajímat o to, <strong>nakolik jsou hodnoty souboru vzájemně diverzifikované</strong>. Například průměrný počet bodů z testu ve škole popisuje průměrnou úroveň znalostí studentů, rozptyl známek nám pak říká, jak velké jsou rozdíly mezi studenty. Pokud je rozptyl velký, znamená to, že jednotliví studenti se vzájemně velmi liší svými vědomostmi. U sériově vyráběných součástek výrobce často požaduje minimální rozptyl, tj. jednotlivé výroby by se měly co nejméně lišit svými rozměry, hmotností atd.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Uvažujeme následující příklad:&nbsp;<em>Máme zařízení, pomocí kterého vyrábíme součástky průměrné délky 190 mm. Výrobce garantuje, že maximální rozptyl délky součástky je 0,09 mm a víme, že odchylky od nastavené délky mají normální rozdělení. Ověřte na hladině významnosti $latex \alpha = 0{,}05$, zda rozptyl délky překračuje hranici zadanou výrobcem.</em></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Dle zadání bychom měli provést jednostranný (pravostranný) test.&nbsp;Reálné příklady oboustranného testu by se hledaly poměrně složitě. Většinou požadujeme větší nebo naopak menší variabilitu, než je daná hranice.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Formulujme nejprve hypotézy testu:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>$latex H_0: \sigma^2 = 0{,}09 \, \mathrm{mm} \, .$ (Slovně: Rozptyl délky je 0,09 mm.)</li><li>$latex H_1: \sigma^2 &gt; 0{,}09 \, \mathrm{mm} \, .$ (Slovně: Rozptyl délky je větší než 0,09 mm.)</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Statistiku testu&nbsp;$latex&nbsp;T $ vypočteme ze vztahu</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$latex T = \frac{(n - 1) s^2}{\sigma_0^2} \, ,$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>kde $latex n$ je rozsah výběru, $latex \sigma_0^2$ je teoretický (testovaný, hypotetický) rozptyl a $latex s$ je <a href="https://statistikajednoduse.cz/k-cemu-slouzi-rozptyl-a-jak-ho-odhadujeme/">výběrový rozptyl</a>. Statistika je tedy poměrem teoretického a výběrového rozptylu, kterou násobíme rozsahem výběru. Jestliže je tedy například výběrový rozptyl výrazně větší než teoretický, má statistika relativně vysokou hodnotu. Naopak relativně nízké hodnoty svědčí o výrazně menším výběrovém rozptylu ve srovnání s teoretickým.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Statistika&nbsp;$latex T$ má&nbsp;$latex \chi^2$ rozdělení. Toto rozdělení má jeden parametr, který nazýváme počet stupňů volnosti. Stupeň volnosti se rovná počtu pozorování sníženému o jedničku. Kritický obor tedy určíme pomocí kvantilů&nbsp;$latex \chi^2$ jako</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$latex W = \langle \chi^2_{1 - \alpha} \left( n - 1 \right), \infty ) \, .$</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>Provedení testu v Excelu</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Pro provedení testu si vygenerujeme náhodný soubor o velikosti&nbsp;$latex n = 20$. Soubor si vygenerujeme takový, že směrodatná odchylka&nbsp;$latex \sigma^2 = 0{,}3$ (rozptyl $latex \sigma^2 = 0{,}09$), tj. ve skutečnosti bude platit nulová hypotéza.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":4890} -->
<div class="wp-block-image"><figure class="aligncenter"><img src="http://statistikajednoduse.cz/wp-content/uploads/2017/12/test-rozptyl-data1.png" alt="test-rozptyl data" class="wp-image-4890"/></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Na následujícím obrázku si můžete prohlédnout data i výsledky výpočtů. Vidíme, že výsledek testu správný, tj. hypotézu $latex H_0$ jsme nezamítli.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":4891} -->
<div class="wp-block-image"><figure class="aligncenter"><img src="http://statistikajednoduse.cz/wp-content/uploads/2017/12/test-rozptyl-data-a-vysledky.png" alt="test-rozptyl data a vysledky" class="wp-image-4891"/></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Opět zde narážíme na rozdíly mezi staršími a novějšími verzemi Excelu. Provedeme si výpočet v obou verzích. Opět platí, že postup pro starší verzi je možné provést i v novější verzi.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Výpočet ve verzi Excel 2010 a vyšší</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Nejprve určíme <strong>výběrový rozptyl</strong>. K tomu využijeme funkci VAR.S:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=VAR.S(A1:A20)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Pro určení <strong>kritického oboru</strong> máme dvě možnosti. Můžeme využít standardní kvantilovou funkci pro&nbsp;$latex \chi^2$ rozdělení CHISQ.INV. Protože ale část rozdělení odpovídající hladině významnosti "odsekáváme" zprava, jako kvantil zadáváme&nbsp;$latex 1 - \alpha$. Jako druhý parametr zadáváme počet stupňů volnosti. Vzorec pro výpočet je tedy</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=CHISQ.INV(1-D5;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Alternativně je možné využít funkci&nbsp;CHISQ.INV.RT. Jedná se o <strong>pravostrannou kvantilovou funkci</strong> $latex \chi^2$ rozdělení, tj. již samotná funkce určuje z námi zadaného kvantilu jednotkový doplněk a tento kvantil standardního rozdělení pak vrací.&nbsp; Hranici kritického oboru tedy určíme vzorcem</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=CHISQ.INV.RT(D5;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Chceme-li zapsat hodnotu kritického oboru $latex W$ intervalem, pak napíšeme:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$latex W = \langle 30{,}1435, \infty ) \, .$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Hodnotu statistiky vypočteme jednoduše vzorcem</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=(D2-1)*E3/D4</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Hodnota statistiky je&nbsp;$latex T = 16{,}9049$, neleží tedy v kritickém oboru a tím pádem na dané hladině významnosti nulovou hypotézu nezamítáme.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>K určení p-hodnoty máme opět k dispozici dvojici funkcí -&nbsp;CHISQ.DIST a&nbsp;CHISQ.DIST.RT. První je standardní distribuční funkcí&nbsp;$latex \chi^2$ rozdělení, druhá funkce je pravostrannou distribuční funkcí&nbsp;$latex \chi^2$ rozdělení. Tato funkce vrací plochu pod hustotou rozdělení napravo od zadané hodnoty. Jinak řečeno, vrací rozdíl mezi jedničkou a hodnotou distribuční funkce pro zadanou hodnotu.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Při využití funkce&nbsp;CHISQ.DIST musíme sami dopočítat doplněk hodnoty do jedničky, protože počítáme pravostranný test a p-hodnota se určuje jako plocha pod hustotou od hodnoty statistiky směrem napravo. Jako poslední parametr zadáváme PRAVDA, protože chceme hodnotu distribuční funkce, při zadání NEPRAVDA bychom získali hodnotu hustoty pravděpodobnosti. Správný vzorec tedy je:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=1-CHISQ.DIST(D8;D2-1;PRAVDA)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>V případě pravostranné distribuční funkce žádnou úpravu již neprovádíme:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=CHISQ.DIST.RT(D8;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:heading -->
<h2>Výpočet ve starších verzích</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Výběrový rozptyl určíme pomocí funkce VAR:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=VAR(A1:A20)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Ve starších verzích Excelu máme k dispozici funkci&nbsp;CHIINV. Dle názvu bychom předpokládali, že jde o kvantilovou funkci. Ve skutečnosti ale jde o <strong>pravostrannou kvantilovou funkci</strong>, která je jednotkovým doplňkem ke standardní kvantilové funkci. V případě pravostranného testu tento fakt zjednoduší používaný vzorec, obecně je chování této funkce velmi neintuitivní a v novějších verzích ji doporučuji nepoužívat.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Správný vzorec pro určení hranice kritického oboru je:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=CHIINV(D5;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Hodnotu statistiky určíme jednoduše:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=(D2-1)*D3/D4</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>K určení p-hodnoty využijeme funkci CHIDIST. Opět se jedná o pravostrannou distribuční funkci, výsledek tedy neodečítáme od jedničky:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=CHIDIST(F8;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:heading {"level":1} -->
<h1>Levostranný test na rozptyl</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Krátce si ještě vysvětlíme, jak bychom provedli levostranný test, tentokrát již bez slovního zadání. Důvodem je, abychom si ukázali chování funkcí pro&nbsp;$latex \chi^2$ při levostranném testu. V případě levostranného testu budeme mít následující hypotézy:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>$latex H_0: \sigma^2 = 0{,}64 .$ (Slovně: Rozptyl je 0,64.)</li><li>$latex H_1: \sigma^2 &lt; 0{,}64 .$ (Slovně: Rozptyl je menší než 0,64.)</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Vygenerujeme si náhodný soubor dat, tentokrát se směrodatnou odchylkou&nbsp;$latex \sigma = 0{,}5$ a tím pádem rozptylem&nbsp;$latex \sigma^2 = 0{,}25$, platí tedy alternativní hypotéza&nbsp;$latex H_1$.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":4895} -->
<div class="wp-block-image"><figure class="aligncenter"><img src="http://statistikajednoduse.cz/wp-content/uploads/2017/12/test-rozptyl-data-2.png" alt="test-rozptyl data 2" class="wp-image-4895"/></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Vzorce pro výpočty výběrových rozptylů a statistiky se neliší od předchozích.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Výpočet ve verzi Excel 2010 a vyšší</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Pro určení hranice kritického oboru u levostranného testu je výhodnější standardní kvantilová funkce&nbsp;CHISQ.INV:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=CHISQ.INV(D5;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Při využití pravostranné kvantilové funkce musíme provést úpravu analogickou té, kterou jsme prováděli u standardní kvantilové funkce u pravostranného testu:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=CHISQ.INV.RT(1-D5;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Protože rozdělení&nbsp;$latex \chi^2$ nabývá pouze kladných hodnot, kritický obor zapsaný intervalem je:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$latex W = \langle 0,&nbsp;10{,}1170 \rangle \, .$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Hodnota statistiky $latex T = 9{,}0587$ leží v kritickém oboru, proto na dané hladině významnosti zamítáme nulovou hypotézu.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Vzorec pro výpočet p-hodnoty testu je u standardní distribuční funkce opět jednoduchý:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=CHISQ.DIST(D8;D2-1;TRUE)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>U pravostranné distribuční funkce je opět třeba odečíst výslednou hodnotu od jedničky.</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=1-CHISQ.DIST.RT(D8;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Správně vidíme, že p-hodnota&nbsp;$latex 0{,}0275$ je nižší než hladina významnosti, což potvrzuje náš předchozí závěr o zamítnutí nulové hypotézy.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2>Výpočet ve starších verzích</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Starší verze Excelu nabízejí pouze pravostranné varianty funkcí. V případě určení hranice kritického oboru musíme jako hodnotu kvantilu zadat&nbsp;$latex 1 - \alpha$:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=CHIINV(1-D5;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Při určování p-hodnoty je pak třeba odečíst výslednou hodnotu od jedničky, abychom získali plochu pod hustotou pravděpodobnosti mezi nulou a hodnotou statistiky:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=1-CHIDIST(F8;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:heading -->
<h2>Výsledek testu</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Oba postupy vedou ke stejnému výsledku, jak je vidět na obrázku níže. Sloupec F pracuje s funkcemi ze starší verze Excelu, sloupce D a E s funkcemi z novější verze.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":4896} -->
<div class="wp-block-image"><figure class="aligncenter"><img src="http://statistikajednoduse.cz/wp-content/uploads/2017/12/test-rozptyl-data-a-vysledky-2.png" alt="test-rozptyl data a vysledky 2" class="wp-image-4896"/></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Soubor se všemi výpočty si můžete stáhnout zde:&nbsp;<a title="test-rozptyl" href="http://statistikajednoduse.cz/wp-content/uploads/2017/12/test-rozptyl.xlsx">test-rozptyl</a></p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":1} -->
<h1>Rozdělení testové statistiky</h1>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Nyní si velmi zjednodušeně vysvětlíme, proč má statistika $latex T$ právě&nbsp;$latex \chi^2$ rozdělení. Toto rozdělení má jednu důležitou vlastnost. Uvažujme, že máme&nbsp;$latex n$ náhodných veličin, které jsou vzájemně nezávislé a které mají normované normální rozdělení. Tyto veličiny si označíme $latex U_1, U_2,&nbsp; \dots U_n$. Jestliže pak máme veličinu, která je součtem druhých mocnin těchto veličin, tj. veličinu&nbsp;$latex \chi^2 = \sum\limits_{i=1}^n U_i^2$, pak má tato veličina&nbsp;$latex \chi^2$ rozdělení a počet stupňů volnosti odpovídá počtu náhodných veličin.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Rozepišme si nyní vzorec pro statistiku testu $latex T$:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$latex T = \frac{ \left( n - 1 \right) \sum\limits_{i=1}^n \left( x_i - \bar{x} \right)^2 }{ \left(n - 1 \right) \sigma_0^2 } = \frac{ \sum\limits_{i=1}^n \left( x_i - \bar{x} \right)^2 }{ \sigma_0^2 } = \left(\frac{x_1 - \bar{x}}{ \sigma_0} \right)^2 +&nbsp;\left(\frac{x_2 - \bar{x}}{ \sigma_0 } \right)^2 + \dots + \left( \frac{x_n - \bar{x}}{ \sigma_0 } \right)^2\, .$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Uvažujme nyní libovolný $latex i$-tý výraz&nbsp;$latex \frac{x_i - \bar{x}}{ \sigma_0 }$. Náhodná veličina $latex x_i$ má normální rozdělení, což je dáno předpokladem testu. Průměr náhodného výběru&nbsp;$latex \bar{x}$ je nestranným odhadem střední hodnoty rozdělení. Platí-li nulová hypotéza&nbsp;$latex H_0$, pak má náhodná veličina $latex x_i$ rozptyl&nbsp;$latex \sigma_0^2$ a tedy směrodatnou odchylku $latex \sigma_0$.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Obecně platí, že máme-li náhodnou veličinu s normálním rozdělením $latex X$, můžeme ji snadno převést na veličinu s normovaným normálním rozdělením&nbsp;$latex U$ tím, že od ní odečteme její střední hodnotu $latex \mu$ a výsledek vydělíme směrodatnou odchylkou $latex \sigma$, tj. provedeme operaci</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$latex U = \frac{X-\mu}{\sigma} \, .$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Platí-li tedy nulová hypotéza&nbsp;$latex H_0$, pak je statistika&nbsp;$latex T$ součtem druhých mocnin veličin s normovaným normálním rozdělením a tím pádem vyhovuje základní vlastnosti&nbsp;$latex \chi^2$ rozdělení. Je rovněž zřejmé, proč u tohoto testu formulujeme předpoklad normality.</p>
<!-- /wp:paragraph -->