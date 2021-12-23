<!-- wp:paragraph -->
<p>V předcházejících článcích jsme rozebírali <a href="https://jiripesik.com/2017/04/02/k-cemu-slouzi-z-test-a-jak-ho-provest-v-excelu/">z-test</a> a <a href="https://jiripesik.com/2017/06/05/t-test-a-jeho-vyuziti/">t-test</a>. Oba testy slouží k otestování hypotézy o střední hodnotě a liší se pouze předpokladem o znalosti rozptylu. Nabízí se ale otázka, k čemu vlastně máme dva testy? <strong>Jakou výhodu vlastně přináší znalost rozptylu? </strong>Na to se nyní podíváme.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>

Pozn: Průběžně aktualizovaný přehled všech článků o statistických testech najdete <a href="https://jiripesik.com/2017/02/19/rozhodovaci-strom-pro-statisticke-testy/">v článku o rozhodovacím stromu pro statistické testy</a>.

</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>U obou dvou testů můžeme testovat hypotézy na stejných hladinách významnosti. Ať už tedy provedeme test pomocí z-testu nebo t-testu, můžeme si předem stanovit, že pravděpodobnost chyby 1. druhu (neoprávněného zamítnutí&nbsp;$latex H_0 $) je například&nbsp;$latex \alpha = 5 % $. Neznalost rozptylu se ale projeví <strong>v pravděpodobnosti chyby 2. druhu</strong>, neboli v <strong>síle testu</strong>. V případě využití t-testu máme větší pravděpodobnost, že nezamítneme neplatnou&nbsp;$latex H_0 $.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Ukažme si to na příkladu oboustranného testu. Předpokládejme stejné hypotézy jako v předchozích článcích, tj.</p>
<!-- /wp:paragraph -->

<!-- wp:list -->
<ul><li>$latex H_0: \mu = 190 \, $,</li><li>$latex H_1: \mu \neq 190 \, $.</li></ul>
<!-- /wp:list -->

<!-- wp:paragraph -->
<p>Vygenerujeme si soubor pomocí generátoru náhodných čísel. Ten nám vygeneruje čísla s požadovanými vlastnostmi. Budeme chtít data se střední hodnotou $latex \mu = 190,35 $ a směrodatnou odchylkou $latex \sigma = 0,5$. Víme tedy, že nulová hypotéza neplatí. Pokud tedy nulovou hypotézu při testu zamítneme, bude náš výsledek správný. V opačném případě se dopouštíme chyby 2. druhu.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":3773} -->
<div class="wp-block-image"><figure class="aligncenter"><img src="http://statistikajednoduse.cz/wp-content/uploads/2017/06/t-test-random-gen.png" alt="t-test-random-gen.PNG" class="wp-image-3773" /></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Na obrázku níže máte vygenerovaná data a výsledky provedených testů.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":4054} -->
<div class="wp-block-image"><figure class="aligncenter"><img src="http://statistikajednoduse.cz/wp-content/uploads/2017/06/t-test-vs-z-test.png" alt="t-test vs z-test" class="wp-image-4054" /></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>p-hodnota z-testu je 0,0196, p-hodnota t-testu je 0,1405. Na hladině významnosti&nbsp;$latex \alpha = 5 % $ bychom tedy nulovou hypotézu zamítli pouze při použití z-testu. V případě použití t-testu bychom se dopustili chyby 2. druhu.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Soubor s výpočty si můžete stáhnout&nbsp;<a title="t-test" href="http://statistikajednoduse.cz/wp-content/uploads/2017/06/t-test1.xlsx">zde</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Na základě jednoho příkladu ale nejde vyvozovat nějaké obecnější závěry. Zkusme tedy komplexnější experiment. Využijeme soubor náhodných čísel, který jsme vytvořili pro <a href="https://jiripesik.com/2017/04/05/jak-vznika-chyba-1-a-2-druhu/">analýzu síly testu z-testu</a>.</p>
<!-- /wp:paragraph -->

<!-- wp:more -->
<!--more-->
<!-- /wp:more -->

<!-- wp:paragraph -->
<p>V souboru jsme měli náhodné výběry se střední hodnotou od $latex \mu =189$ do $latex \mu =191$ a směrodatnou odchylkou $latex \sigma= 0,9$. Velikostí kroku mezi dvěma středními hodnotami byla 0,025. Rozsah náhodného výběru byl 20 a pro každou střední hodnotu jsme generovali 100 náhodných výběrů. Budeme pro každý soubor testovat hypotézu&nbsp;$latex H_0: \mu = 190$ na hladině významnosti&nbsp;$latex \alpha = 5 %$, a to jak pomocí z-testu, tak i pomocí t-testu.</p>
<!-- /wp:paragraph -->

<!-- wp:paragraph -->
<p>Výsledek experimentu je na obrázku níže. Obě křivky zobrazují podíl správných výsledků (tj. zamítnutí&nbsp;$latex H_0: \mu = 190$) v souboru provedených testů. Pro z-test je požita zelená barva, pro t-test červená. Červená křivka se nachází pod zelenou, což značí, že z-test je úspěšnější než t-test.</p>
<!-- /wp:paragraph -->

<!-- wp:image {"align":"center","id":4088} -->
<div class="wp-block-image"><figure class="aligncenter"><img src="http://statistikajednoduse.cz/wp-content/uploads/2017/06/z-test-vs-t-test-test-power1.png" alt="z-test vs t-test test power" class="wp-image-4088" /></figure></div>
<!-- /wp:image -->

<!-- wp:paragraph -->
<p>Soubor s experimenty si můžete stáhnout <a title="z-test vs t-test" href="http://statistikajednoduse.cz/wp-content/uploads/2017/06/z-test-vs-t-test.xlsx">zde</a>.</p>
<!-- /wp:paragraph -->