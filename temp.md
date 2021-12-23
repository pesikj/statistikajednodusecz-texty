<!-- wp:advanced-gutenberg-blocks/intro -->
<div class="wp-block-advanced-gutenberg-blocks-intro"><p class="wp-block-advanced-gutenberg-blocks-intro__content">Zásadním omezením z-testu, který jsme si popisovali minule, je nutnost znát rozptyl testovaného souboru. V realitě velikost rozptylu velmi často neznáme, a tak se musíme spokojit s jeho odhadem. V takovém případě musíme využít určitou "modifikaci" z-testu, která se nazývá t-test.</p></div>
<!-- /wp:advanced-gutenberg-blocks/intro -->

<!-- wp:advanced-gutenberg-blocks/summary -->
<div class="wp-block-advanced-gutenberg-blocks-summary"><p class="wp-block-advanced-gutenberg-blocks-summary__title">Table of contents</p><div class="wp-block-advanced-gutenberg-blocks-summary__fold"><svg xmlns="http://www.w3.org/2000/svg" width="24" height="24" viewbox="0 0 24 24" fill="none" stroke="currentColor" stroke-width="2" stroke-linecap="round" stroke-linejoin="round" class="feather feather-chevron-up"><polyline points="18 15 12 9 6 15"></polyline></svg></div><ol role="directory" class="wp-block-advanced-gutenberg-blocks-summary__list"><li><a href="#oboustranný-t-test-v-excelu">Oboustranný t-test v Excelu</a><ol><li><a href="#výpočet-ve-verzi-excel-2010-a-vyšší">Výpočet ve verzi Excel 2010 a vyšší</a><ol></ol></li><li><a href="#výpočet-ve-verzi-excel-2007-a-nižší">Výpočet ve verzi Excel 2007 a&nbsp;nižší</a><ol></ol></li></ol></li><li><a href="#jednostranný-t-test">&nbsp;Jednostranný t-test</a><ol><li><a href="#levostranný-t-test">Levostranný t-test</a><ol><li><a href="#výpočet-ve-verzi-excel-2010-a-novějším">Výpočet ve verzi Excel 2010 a novějším</a><ol></ol></li><li><a href="#výpočet-ve-verzi-excel-2007-a-starší">Výpočet ve verzi Excel 2007 a&nbsp;starší</a><ol></ol></li></ol></li><li><a href="#pravostranný-t-test">Pravostranný t-test</a><ol><li><a href="#výpočet-ve-verzi-excel-2010-a-novější">Výpočet ve verzi Excel 2010 a novější</a><ol></ol></li><li><a href="#výpočet-ve-verzi-excel-2007-a-starší">Výpočet ve verzi Excel 2007 a starší</a><ol></ol></li></ol></li></ol></li></ol></div>
<!-- /wp:advanced-gutenberg-blocks/summary -->

<!-- wp:paragraph -->
<p>Začněme s oboustranným t-testem. Uvažujeme následující příklad:&nbsp;<em>Máme zařízení, které vyrábí součástku určité délky. Zařízení má určitou chybovost, jejíž přesnou velikost neznáme. Chyby mají normální rozdělení. Zařízení bylo nastaveno pracovníkem a my&nbsp;chceme ověřit, že pracovník nastavil správnou délku součástky, tj. 190 mm. Pro ověření jsme vybrali a přeměřili náhodný soubor dvaceti součástek.</em></p>
<!-- /wp:paragraph -->

<!-- wp:advanced-gutenberg-blocks/notice -->
<div class="wp-block-advanced-gutenberg-blocks-notice is-variation-advice" data-type="advice"><p class="wp-block-advanced-gutenberg-blocks-notice__title">Tip</p><p class="wp-block-advanced-gutenberg-blocks-notice__content"> Soubor s daty i výpočty si můžete stáhnout zde: <a href="https://1drv.ms/x/s!AvP6NwTpIPzsmeMP7UXpFTbhup-kDA">t-test</a>.</p></div>
<!-- /wp:advanced-gutenberg-blocks/notice -->

<!-- wp:paragraph -->
<p>Obecné principy testování hypotéz, které jsme si popsali v článku o z-testu, zůstávají v platnosti. Definujeme si tedy nulovou a alternativní hypotézu:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>$latex H_0: \mu = 190 \,&nbsp;\mathrm{mm}$. (Slovně: Střední hodnota statistického souboru je 190 mm.)</li><li>$latex H_0: \mu \neq 190 \, \mathrm{mm}$. (Střední hodnota statistického souboru je není 190 mm.)</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Statistiku získáme ze vzorce</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$latex t = \frac{\bar{x} - \mu_0}{s} \sqrt{n} \, ,$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>kde&nbsp;$latex \bar{x}$ je průměr našeho vzorku,&nbsp;$latex \mu_0$ je teoretická (testovaná) střední hodnota,&nbsp;a&nbsp;$latex n$ je rozsah náhodného výběru.&nbsp;Proměnná $latex s$ je odhad rozptylu základního souboru a pro tento odhad využijeme <strong>výběrový rozptyl</strong></p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$latex s = \frac{\sum\limits^{n}_{i=1} (x_i -\bar{x})}{n-1} \, ,$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>kde&nbsp;$latex x_i $ je <em>i</em>-tá hodnota v našem výběru. Jmenovatel zlomku může být pro někoho matoucí, protože bychom spíše očekávali hodnotu $latex n$. Má to však svůj dobrý důvod. Pokud bychom do jmenovatele umístili $latex n$, pak střední hodnota našeho odhadu by byla menší, než skutečná hodnota rozptylu. Blíže to popíšu v nějakém z dalších článků.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Naše statistika $latex t$ nemá tentokrát normované rozdělení, ale má takzvané <strong>Studentovo</strong> neboli <strong>t rozdělení</strong>. Toto rozdělení má jeden parametr, který značíme $latex \nu $. V našem případě platí vztah</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center">$latex \nu = n - 1 \, . $</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>t rozdělení má podobné vlastnosti jako normované normální: jeho <strong>střední hodnota je 0</strong> a je <strong>symetrické kolem 0</strong>. Čím vyšší je hodnota parametru&nbsp;$latex \nu $, tím více se distribuční funkce t rozdělení <strong>blíží normovanému normálnímu</strong>. Často se uvádí, že u t-testu můžeme pro $latex \nu &gt; 30 $ použít normované normální rozdělení. Pokud však i pro tyto hodnoty použijeme t rozdělení, nejedná se o chybu.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Kvantilvou funkci t rozdělení s $latex (\nu)$ stupni volnosti budeme značit &nbsp;$latex t_{p} (\nu)$. Kritický obor testu určíme ze vzorce</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center">$latex W = ( - \infty, t_{\frac{\alpha}{2}} \left(n-1 \right) \rangle&nbsp;\cup \langle t_{1-\frac{\alpha}{2}} \left( n - 1 \right), \infty ) \, ,$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>kde&nbsp;$latex \alpha$ značí hladinu významnosti testu.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Nyní již víme vše, co potřebujeme, a můžeme se vrhnout na provedení testu v Excelu.</p>
<!-- /wp:paragraph -->

<!-- wp:heading -->
<h2 id="oboustranný-t-test-v-excelu">Oboustranný t-test v Excelu</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Od verze 2010 obsahuje Excel přepracovanou sadu funkcí pro provádění statistických výpočtů. Používáte-li tedy verzi 2010 a vyšší, doporučuji vám tyto novější funkce využívat, protože jejich použití je v řadě případů jednodušší. Uživatelé starších verzí mají k dispozici pouze starší sadu funkcí. My si ukážeme postup pro obě varianty.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Náš testovací soubor máme uložený v buňkách A1 až A20. Test provedeme na $latex \alpha = 5 % $, tuto hodnotu máme v buňce D6.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":4033} -->
<div class="wp-block-image"><figure class="aligncenter"><img src="http://statistikajednoduse.cz/wp-content/uploads/2017/06/t-test-data-2.png" alt="t-test data 2" class="wp-image-4033"/></figure></div>
<!-- /wp:image -->

<!-- wp:heading {"level":3} -->
<h3 id="výpočet-ve-verzi-excel-2010-a-vyšší">Výpočet ve verzi Excel 2010 a vyšší</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>K provedení t-test potřebujeme výběrovou směrodatnou odchylku souboru. Směrodatnou odchylku získáme vzorcem</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=SMODCH.VÝBĚR.S(A1:A20)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Hodnotu si uložíme do buňky D4. Teoretickou střední hodnotu máme v buňce D10, průměr náhodného souboru v buňce D3. Nyní určíme kritický obor. Využijeme kvantilovou funkci Excelu pro t rozdělení - T.INV. Dolní hranici kritického oboru získáme vzorcem</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=T.INV(D6/2;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>a horní hranici vzorcem</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=T.INV(1-D6/2;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:advanced-gutenberg-blocks/notice -->
<div class="wp-block-advanced-gutenberg-blocks-notice is-variation-avoid" data-type="avoid"><p class="wp-block-advanced-gutenberg-blocks-notice__title">Pozor</p><p class="wp-block-advanced-gutenberg-blocks-notice__content">Důležité je, že funkce T.INV obsahuje v názvu tečku. Nepleťte si tuto funkci se starší funkcí TINV, která vrací jiné výsledky.</p></div>
<!-- /wp:advanced-gutenberg-blocks/notice -->

<!-- wp:paragraph -->
<p>Hodnoty se liší pouze znaménkem, protože (jak už jsme uvedli) je t rozdělení symetrické kolem 0. Ze získaných hodnot můžeme kritický obor zapsat intervalem:</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center">$latex W = &nbsp;( - \infty, t_{0,025} \left(19 \right) \rangle \cup \langle t_{0,975} ( 19 ), \infty ) = ( - \infty, -2,0930 \rangle \cup \langle 2,0930, \infty ) \, .$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Nyní si určíme hodnotu statistiky (pomocí vzorce $latex t = \frac{\bar{x} - \mu_0}{s} \sqrt{n}$):</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=(D3-D5)/D4*ODMOCNINA(D2)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Hodnota statistiky je&nbsp;-0,92 a výsledek máme v buňce D10. Protože statistika leží mimo kritický obor, <strong>nulovou hypotézu nezamítáme</strong>. Určeme si ještě p-hodnotu testu. K tomu využijeme distribuční funkci t rozdělení T.DIST:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=T.DIST(D10;D2-1;PRAVDA) * 2</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>V tomto případě určujeme p-hodnotu jako plochu pod hustotou statistiky směrem doleva a násobíme ji dvěma. Pokud bychom však měli hodnotu statistiky vyšší než 0, je třeba určovat p-hodnotu jako plochu od statistiky směrem doprava. K tomu můžeme využít funkci&nbsp;T.DIST.RT, která určuje kvantily t rozdělení zprava. Správná hodnota bude vždy ta menší. Chceme-li, aby si Excel zvolil tuto hodnotu sám, použijeme funkci MIN:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=MIN(T.DIST(D10;D2-1;PRAVDA);T.DIST.RT(D10;D2-1))*2</pre>
<!-- /wp:preformatted -->

<!-- wp:heading {"level":3} -->
<h3 id="výpočet-ve-verzi-excel-2007-a-nižší">Výpočet ve verzi Excel 2007 a&nbsp;nižší</h3>
<!-- /wp:heading -->

<!-- wp:advanced-gutenberg-blocks/notice -->
<div class="wp-block-advanced-gutenberg-blocks-notice is-variation-info" data-type="info"><p class="wp-block-advanced-gutenberg-blocks-notice__title">Poznámka</p><p class="wp-block-advanced-gutenberg-blocks-notice__content">Máte-li k dispozici verzi 2010 a novější, tento odstavec přeskočte, tento postup je totiž komplikovanější než výše popsaný.</p></div>
<!-- /wp:advanced-gutenberg-blocks/notice -->

<!-- wp:paragraph -->
<p>Následující postup lze aplikovat Excelu 2007 nebo starších, ale dostupný je i v novějších. K odhadu směrodatné odchylky použijeme funkci SMODCH.VÝBĚR:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=SMODCH.VÝBĚR(A1:A20)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Kritický obor určíme pomocí funkce TINV (funkce se od předchozí liší <strong>chybějící tečkou v názvu</strong>). Do této funkce ale nezadáváme kvantil rozdělení, ale <strong>přímo hladinu významnosti</strong>. Navíc hodnotu hladiny významnosti ani nedělíme dvěma. Výsledek funkce je vždy kladný, pro spodní hranici tedy napíšeme před funkci znaménko minus:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=-TINV(D6;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Pravá hranice už je bez znaménka:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=TINV(D6;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Funkce TINV totiž nepracuje se standardním t rozdělením, ale rozdělením, která má nenulovou hustotu pouze pro $latex x &gt; 0$. Hustota je pak dvojnásobkem hustoty standardního t rozdělení, protože musí být splněna podmínka, že plocha pod hustotou musí být rovna 1.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Nyní vypočteme statistiku testu:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=(D3-D5)/E4*ODMOCNINA(D2)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Hodnota statistiky je opět -0,92, tj. statistika leží mimo kritický obor a nulovou hypotézu nezamítáme. Pro určení p-hodnoty využijeme funkci TDIST, která určuje hodnotu distribuční funkce t rozdělení. Zadáme-li jako poslední parametr dvojku, Excel využije výše zmíněnou "dvojnásobnou" distribuční funkci a výsledek pak nemusíme násobit dvěma.</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=TDIST(ABS(D10);D2-1;2)</pre>
<!-- /wp:preformatted -->

<!-- wp:heading -->
<h2 id="jednostranný-t-test">&nbsp;Jednostranný t-test</h2>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Nyní si stručně popíšeme postup jednostrannách variant t-testu. Při jednostranné variantě máme odlišnou alternativní hypotézu. Alternativní hypotéza při levostranném testu tvrdí, že střední hodnota základního souboru je menší než testovaná hodnota. Při pravostranném testu naopak tvrdí, že skutečná střední hodnota je vyšší. Testovat budeme na $\alpha = 0,05$.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":3} -->
<h3 id="levostranný-t-test">Levostranný t-test</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Začneme se levostranným t-test. Při něm se rozhodujeme mezi těmito hypotézami:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>$latex H_0: \mu = 190 \,&nbsp;\mathrm{mm}$.</li><li>$latex H_0: \mu &lt; 190 \, \mathrm{mm}$.</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Testová statistika zůstává stejná a ve prospěch alternativní hypotézy mluví její velmi malé hodnoty. Kritický obor tedy "odsekáváme" zleva, tj. kritický obor vyjádřený intervalem má tvar</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center">$latex W = ( - \infty, t_{\alpha} \left(n-1 \right) \rangle \, .$</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":3980} -->
<div class="wp-block-image"><figure class="aligncenter"><img src="http://statistikajednoduse.cz/wp-content/uploads/2017/06/t-test-data-a-vc3bdsledky-lev.png" alt="t-test data a výsledky lev.PNG" class="wp-image-3980"/></figure></div>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4 id="výpočet-ve-verzi-excel-2010-a-novějším">Výpočet ve verzi Excel 2010 a novějším</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Směrodatnou odchylku určíme stejným postupem jako výše</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=SMODCH.VÝBĚR.S(A1:A20)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Kritický obor má pouze jednu hranici a $latex \alpha$-tý kvantil t rozdělení. Ten snadno určíme pomocí funkce T.INV:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=T.INV(D6;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Kritický obor můžeme vyjádřit intervalem jako</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph {"align":"center"} -->
<p class="has-text-align-center">$latex W = ( - \infty, t_{0,05} \left(19 \right) \rangle = &nbsp; ( - \infty, -1,7291 \rangle \, .$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Vzorec pro výpočet statistiky zůstává stejný:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=(D3-D5)/D4*ODMOCNINA(D2)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Statistika má hodnotu&nbsp;-2,1310. Protože hodnota statistiky leží v kritickém oboru, zamítáme nulovou hypotézu. Na&nbsp;$\alpha = 0,05$ tedy tvrdíme, že zařízení bylo nastaveno chybně. Zbývá určit p-hodnotu, kterou získáme opět pomocí funkce T.DIST:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=T.DIST(D9;D2-1;PRAVDA)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>P-hodnota testu je&nbsp;0,0232. To potvrzuje závěr o zamítnutí nulový hypotézy na&nbsp;$\alpha = 0,05$. Nulovou hypotézu bychom nezamítli hladinách významnosti $\alpha &lt; 0,0232$.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="výpočet-ve-verzi-excel-2007-a-starší">Výpočet ve verzi Excel 2007 a&nbsp;starší</h4>
<!-- /wp:heading -->

<!-- wp:advanced-gutenberg-blocks/notice -->
<div class="wp-block-advanced-gutenberg-blocks-notice is-variation-info" data-type="info"><p class="wp-block-advanced-gutenberg-blocks-notice__title">Poznámka</p><p class="wp-block-advanced-gutenberg-blocks-notice__content">Máte-li k dispozici verzi 2010 a novější, tento odstavec přeskočte.</p></div>
<!-- /wp:advanced-gutenberg-blocks/notice -->

<!-- wp:paragraph -->
<p>Směrodatnou odchylku určíme podle stejného vzorce jako u obostranného testu:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=SMODCH.VÝBĚR(A1:A20)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Při určování kritické hodnoty pro oboustranný t-test jsme zadávali přímo hladinu významnosti a nemuseli ji dělit dvěma. Nyní tedy musíme funkci T.INV zadat <strong>hladinu významnosti násobenou dvěma</strong>. Dále před funkci dáme znaménko minus, abychom získali záporné číslo.</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=-TINV(2*D6;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Vzorec pro hodnotu statistiky zůstává stejný</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=(D3-D5)/E4*ODMOCNINA(D2)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Jako poslední určíme p-hodnotu. Opět využijeme funkci TDIST. Tentokrát jako poslední parametr zadáváme jedničku.</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=KDYŽ(D9&lt;0;TDIST(-D9;D2-1;1);1-TDIST(D9;D2-1;1))</pre>
<!-- /wp:preformatted -->

<!-- wp:heading {"level":3} -->
<h3 id="pravostranný-t-test">Pravostranný t-test</h3>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>Při pravostranném testu se rozhodujeme mezi těmito hypotézami:</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>$latex H_0: \mu = 190 \,&nbsp;\mathrm{mm}$.</li><li>$latex H_0: \mu &gt; 190 \, \mathrm{mm}$.</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Kritický obor nyní "odsekáváme" zprava, tj. kritický obor vyjádřený intervalem má tvar</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>$latex W&nbsp;=&nbsp;\langle t_{\alpha} \left( n - 1 \right), \infty ) &nbsp;\, .$</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Výpočet statistiky a výběrové směrodatné odchylky zůstává stejný, určíme tedy pouze pouze hranice kritického oboru a p-hodnotu.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":3977} -->
<div class="wp-block-image"><figure class="aligncenter"><img src="http://statistikajednoduse.cz/wp-content/uploads/2017/06/t-test-data-a-vc3bdsledky-prav.png" alt="t-test data a výsledky prav" class="wp-image-3977"/></figure></div>
<!-- /wp:image -->

<!-- wp:heading {"level":4} -->
<h4 id="výpočet-ve-verzi-excel-2010-a-novější">Výpočet ve verzi Excel 2010 a novější</h4>
<!-- /wp:heading -->

<!-- wp:paragraph -->
<p>K určení hranice kritického oboru použijeme opět funkci T.INV, tentokrát kritický obor začíná na 95%ním kvantinu t rozdělení, tj. jako první parametr zadávání $latex 1 - \alpha$:</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=T.INV(1-D6;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Hodnota statistiky je nyní 0,1301. Tato hodnota neleží v kritickém oboru, nulovou hypotézu tedy nezamítáme. K určení p-hodnoty využijeme funkci T.DIST.RT, se kterou jsme se seznámili již výše. Tato funkce vrací plochu pod funkcí hustoty od zadaného bodu směrem doprava.</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=T.DIST.RT(D9;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Alternativně můžeme využít funkci T.DIST. Tato funkce vrací obsah plochy směrem doleva. Protože celková plocha má obsah 1, potřebou hodnotu získáme odečtením výsledku funkce T.DIST od jedničky</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=1-T.DIST(D9;D2-1;PRAVDA)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>P-hodnota testu je&nbsp;0,4489.</p>
<!-- /wp:paragraph -->

<!-- wp:heading {"level":4} -->
<h4 id="výpočet-ve-verzi-excel-2007-a-starší">Výpočet ve verzi Excel 2007 a starší</h4>
<!-- /wp:heading -->

<!-- wp:advanced-gutenberg-blocks/notice -->
<div class="wp-block-advanced-gutenberg-blocks-notice is-variation-info" data-type="info"><p class="wp-block-advanced-gutenberg-blocks-notice__title">Poznámka</p><p class="wp-block-advanced-gutenberg-blocks-notice__content">Máte-li k dispozici verzi 2010 a novější, tento odstavec přeskočte. </p></div>
<!-- /wp:advanced-gutenberg-blocks/notice -->

<!-- wp:paragraph -->
<p>Máme-li starší verzi Excelu nebo nechceme-li z nějakého důvodu použít funkci T.INV, využijeme opět funkci TINV. Opět zadáváme hladinu významnosti násobenou dvěma. Tentokrát nepoužíváme znaménko minus, protože hranické kritického oboru je kladné číslo.</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=TINV(2*D6;D2-1)</pre>
<!-- /wp:preformatted -->

<!-- wp:paragraph -->
<p>Určení p-hodnoty je v tomto případě stejné jako u předchozího postupu, tj. použijeme vzorec</p>
<!-- /wp:paragraph -->

<!-- wp:preformatted -->
<pre class="wp-block-preformatted">=KDYŽ(D9&lt;0;1-TDIST(-D9;D2-1;1);TDIST(D9;D2-1;1))</pre>
<!-- /wp:preformatted -->