html_content = """<!DOCTYPE html>
<html lang="cs">
<head>
<meta charset="UTF-8">
<title>Teorie grafů - Základní pojmy</title>
<style>
    @page {
        size: A4;
        margin: 18mm 15mm;
        background-color: #fcfcfd;
        @bottom-right {
            content: "Strana " counter(page) " z " counter(pages);
            font-family: 'Liberation Sans', sans-serif;
            font-size: 9pt;
            color: #718096;
        }
    }

    *, *::before, *::after {
        box-sizing: border-box;
    }

    body {
        font-family: 'Liberation Serif', 'Times New Roman', serif;
        font-size: 10.5pt;
        line-height: 1.5;
        color: #2d3748;
        margin: 0;
        padding: 0;
    }

    /* Title Header / Banner */
    .header-banner {
        background-color: #1a365d;
        color: #ffffff;
        padding: 24px 20px;
        border-radius: 6px;
        margin-bottom: 25px;
    }

    .header-banner h1 {
        font-family: 'Liberation Sans', sans-serif;
        font-size: 22pt;
        font-weight: 700;
        margin: 0 0 6px 0;
        color: #ffffff;
        letter-spacing: -0.5px;
    }

    .header-banner .subtitle {
        font-family: 'Liberation Sans', sans-serif;
        font-size: 13pt;
        color: #e2e8f0;
        margin: 0 0 16px 0;
        font-weight: 400;
    }

    .meta-grid {
        display: table;
        width: 100%;
        border-top: 1px solid rgba(255, 255, 255, 0.25);
        padding-top: 12px;
        margin-top: 12px;
        font-family: 'Liberation Sans', sans-serif;
        font-size: 9.5pt;
        color: #cbd5e0;
    }

    .meta-col {
        display: table-cell;
        width: 33.33%;
    }

    .meta-col strong {
        color: #ffffff;
    }

    /* Headings */
    h2 {
        font-family: 'Liberation Sans', sans-serif;
        font-size: 14pt;
        color: #1a365d;
        border-left: 4px solid #dd6b20;
        padding-left: 10px;
        margin-top: 24px;
        margin-bottom: 12px;
        page-break-after: avoid;
    }

    h3 {
        font-family: 'Liberation Sans', sans-serif;
        font-size: 11.5pt;
        color: #2c5282;
        margin-top: 16px;
        margin-bottom: 8px;
        page-break-after: avoid;
    }

    /* Definition, Theorem, and Corollary Boxes */
    .env-box {
        background-color: #ffffff;
        border: 1px solid #e2e8f0;
        border-radius: 5px;
        padding: 12px 16px;
        margin: 12px 0;
        page-break-inside: avoid;
    }

    .env-box.definition {
        border-left: 4px solid #3182ce;
        background-color: #f7fafc;
    }

    .env-box.theorem {
        border-left: 4px solid #dd6b20;
        background-color: #fffaf0;
    }

    .env-box.corollary {
        border-left: 4px solid #38a169;
        background-color: #f0fff4;
    }

    .env-title {
        font-family: 'Liberation Sans', sans-serif;
        font-weight: bold;
        font-size: 10.5pt;
        margin-bottom: 6px;
    }

    .definition .env-title { color: #2b6cb0; }
    .theorem .env-title { color: #c05621; }
    .corollary .env-title { color: #2f855a; }

    /* Math styling */
    .math {
        font-family: 'Liberation Serif', 'Times New Roman', serif;
        font-style: italic;
    }

    .math-block {
        text-align: center;
        margin: 10px 0;
        font-size: 11pt;
    }

    /* Lists & Items */
    ul {
        margin: 6px 0 12px 20px;
        padding: 0;
    }

    li {
        margin-bottom: 6px;
    }

    .note-box {
        background-color: #edf2f7;
        border-left: 3px solid #718096;
        padding: 10px 14px;
        font-style: italic;
        margin: 12px 0;
        page-break-inside: avoid;
    }
</style>
</head>
<body>

<div class="header-banner">
    <h1>Teorie grafů</h1>
    <div class="subtitle">Základní pojmy</div>
    <div class="meta-grid">
        <div class="meta-col"><strong>Autor:</strong> Petr Liška</div>
        <div class="meta-col"><strong>Instituce:</strong> Univerzita Hradec Králové</div>
        <div class="meta-col" style="text-align: right;"><strong>Datum:</strong> 21.09.2026</div>
    </div>
</div>

<h2>1. Co je to graf?</h2>

<div class="env-box definition">
    <div class="env-title">Definice 1.1 (Graf)</div>
    <strong>Graf</strong> <span class="math">G</span> je uspořádaná dvojice <span class="math">(V, E)</span>, kde <span class="math">V</span> je nějaká neprázdná množina a <span class="math">E</span> je množina dvouprvkových podmnožin množiny <span class="math">V</span>. Prvky množiny <span class="math">V</span> se jmenují <strong>vrcholy</strong> grafu <span class="math">G</span> a prvky množiny <span class="math">E</span> <strong>hrany</strong> grafu <span class="math">G</span>.
</div>

<div class="env-box definition">
    <div class="env-title">Definice 1.2 (Rovnost a izomorfismus grafů)</div>
    Dva grafy <span class="math">G<sub>1</sub> = (V<sub>1</sub>, E<sub>1</sub>)</span> a <span class="math">G<sub>2</sub> = (V<sub>2</sub>, E<sub>2</sub>)</span> považujeme za <strong>stejné</strong> (neboli <span class="math">G<sub>1</sub> = G<sub>2</sub></span>), jestliže
    <div class="math-block">
        <span class="math">V<sub>1</sub> = V<sub>2</sub> &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; a &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; E<sub>1</sub> = E<sub>2</sub></span>
    </div>
    Jestliže existuje bijektivní zobrazení <span class="math">f : V<sub>1</sub> &rarr; V<sub>2</sub></span> tak, že platí
    <div class="math-block">
        <span class="math">{x, y} &isin; E<sub>1</sub> &nbsp;&nbsp; &hArr; &nbsp;&nbsp; {f(x), f(y)} &isin; E<sub>2</sub></span>
    </div>
    pak grafy <span class="math">G<sub>1</sub></span> a <span class="math">G<sub>2</sub></span> nazveme <strong>izomorfní</strong> (<span class="math">G<sub>1</sub> &cong; G<sub>2</sub></span>) a zobrazení <span class="math">f</span> <strong>izomorfismus grafů</strong> <span class="math">G<sub>1</sub></span> a <span class="math">G<sub>2</sub></span>.
</div>

<h2>2. Významné grafy</h2>

<div class="env-box definition">
    <div class="env-title">Definice 2.1 (Třídy významných grafů)</div>
    <ul>
        <li><strong>Úplný graf</strong> <span class="math">K<sub>n</sub></span> (kde <span class="math">n &ge; 1</span>):
            <div class="math-block"><span class="math">V = {1, 2, &hellip;, n}, &nbsp;&nbsp;&nbsp;&nbsp; E = &binom;(V, 2)</span></div>
        </li>
        <li><strong>Kružnice</strong> <span class="math">C<sub>n</sub></span> (kde <span class="math">n &ge; 3</span>):
            <div class="math-block"><span class="math">V = {1, 2, &hellip;, n}, &nbsp;&nbsp;&nbsp;&nbsp; E = {{i&minus;1, i}; i = 1, &hellip;, n&minus;1} &cup; {{1, n}}</span></div>
        </li>
        <li><strong>Cesta</strong> <span class="math">P<sub>n</sub></span> (kde <span class="math">n &ge; 0</span>):
            <div class="math-block"><span class="math">V = {0, 1, &hellip;, n}, &nbsp;&nbsp;&nbsp;&nbsp; E = {{i&minus;1, i}; i = 1, &hellip;, n}</span></div>
        </li>
        <li><strong>Úplný bipartitní graf</strong> <span class="math">K<sub>n,m</sub></span> (kde <span class="math">n, m &ge; 1</span>):
            <div class="math-block"><span class="math">V = {u<sub>1</sub>, &hellip;, u<sub>n</sub>} &cup; {v<sub>1</sub>, &hellip;, v<sub>m</sub>}</span></div>
            <div class="math-block"><span class="math">E = {{u<sub>i</sub>, v<sub>j</sub>}; i = 1, 2, &hellip;, n, &nbsp; j = 1, 2, &hellip;, m}</span></div>
        </li>
    </ul>
</div>

<h2>3. Souvislost grafů</h2>

<div class="env-box definition">
    <div class="env-title">Definice 3.1 (Podgraf)</div>
    Řekneme, že graf <span class="math">H</span> je <strong>podgrafem grafu</strong> <span class="math">G</span>, jestliže 
    <div class="math-block"><span class="math">V(H) &sube; V(G) &nbsp;&nbsp;&nbsp;&nbsp; a &nbsp;&nbsp;&nbsp;&nbsp; E(H) &sube; E(G)</span></div>
</div>

<p>Podgraf grafu <span class="math">G</span> izomorfní nějaké cestě <span class="math">P<sub>t</sub></span> se nazývá <strong>cesta v grafu</strong> <span class="math">G</span>, podgraf grafu <span class="math">G</span> izomorfní nějaké kružnici <span class="math">C<sub>t</sub></span> se nazývá <strong>kružnice v grafu</strong> <span class="math">G</span>.</p>

<div class="env-box definition">
    <div class="env-title">Definice 3.2 (Souvislý graf)</div>
    Řekneme, že graf je <strong>souvislý</strong>, jestliže pro každé dva jeho vrcholy <span class="math">x</span> a <span class="math">y</span> v něm existuje cesta z <span class="math">x</span> do <span class="math">y</span>.
</div>

<h2>4. Sled, tah a cesta</h2>

<div class="env-box definition">
    <div class="env-title">Definice 4.1 (Sled)</div>
    Nechť <span class="math">G = (V, E)</span> je graf. Posloupnost
    <div class="math-block"><span class="math">v<sub>0</sub>, v<sub>0</sub>v<sub>1</sub>, v<sub>1</sub>, v<sub>1</sub>v<sub>2</sub>, &hellip;, v<sub>n&minus;1</sub>, v<sub>n&minus;1</sub>v<sub>n</sub>, v<sub>n</sub></span></div>
    se nazývá <strong>sled</strong> v grafu <span class="math">G</span>, číslo <span class="math">n</span> nazýváme <strong>délkou</strong> tohoto sledu.
</div>

<div class="env-box definition">
    <div class="env-title">Definice 4.2 (Tah a cesta)</div>
    Sled, v němž se neopakuje žádná hrana, se nazývá <strong>tah</strong> v daném grafu. Je-li počáteční uzel tahu roven koncovému, nazývá se tah <strong>uzavřený</strong>. V opačném případě se tento tah nazývá <strong>otevřený</strong>.<br><br>
    Sled, v němž se neopakuje žádný uzel, se nazývá <strong>cesta</strong>.
</div>

<div class="note-box">
    <strong>Poznámka:</strong> Existuje-li mezi uzly <span class="math">x</span> a <span class="math">y</span> sled, pak existuje i cesta. Navíc každá cesta je tahem.
</div>

<h2>5. Stupeň vrcholu jako základní charakterizace</h2>

<div class="env-box definition">
    <div class="env-title">Definice 5.1 (Stupeň vrcholu)</div>
    Nechť <span class="math">G = (V, E)</span> je graf a <span class="math">v &isin; V</span>. Řekneme, že vrchol <span class="math">v</span> je <strong>konečného stupně</strong>, jestliže jej obsahuje konečný počet hran. V opačném případě je vrchol <span class="math">v</span> <strong>nekonečného stupně</strong>.<br><br>
    Symbolem <span class="math">deg<sub>G</sub>(v)</span> označujeme počet hran grafu <span class="math">G</span> obsahujících vrchol <span class="math">v</span>. Toto číslo nazýváme <strong>stupeň</strong> vrcholu <span class="math">v</span> v grafu <span class="math">G</span>.<br><br>
    Je-li <span class="math">deg<sub>G</sub>(v) = 0</span>, nazývá se vrchol <strong>izolovaný</strong>.
</div>

<div class="env-box theorem">
    <div class="env-title">Věta 5.1 (Princip podání rukou / Eulerova věta)</div>
    Pro každý konečný graf <span class="math">G = (V, E)</span> platí:
    <div class="math-block">
        <span class="math">&sum;<sub>v &isin; V</sub> deg<sub>G</sub>(v) = 2 &middot; |E|</span>
    </div>
</div>

<div class="env-box corollary">
    <div class="env-title">Důsledek 5.1</div>
    Počet vrcholů lichého stupně je sudé číslo pro každý konečný graf.
</div>

<h2>6. Průměrný stupeň grafu</h2>

<div class="env-box definition">
    <div class="env-title">Definice 6.1 (Průměrný stupeň)</div>
    Nechť <span class="math">G = (V, E)</span> je konečný graf, <span class="math">|V| = N</span> a <span class="math">k &isin; &mathbb;N<sub>0</sub></span> libovolně. Pak klademe
    <div class="math-block">
        <span class="math">N<sub>k</sub> = |{v &isin; V; deg<sub>G</sub>(v) = k}|, &nbsp;&nbsp;&nbsp;&nbsp;&nbsp; p<sub>k</sub> = N<sub>k</sub> / N</span>
    </div>
    Číslo
    <div class="math-block">
        <span class="math">&lang;deg<sub>G</sub>(v)&rang; = (1 / N) &sum;<sub>v &isin; V</sub> deg<sub>G</sub>(v)</span>
    </div>
    nazýváme <strong>průměrný stupeň</strong> grafu <span class="math">G</span>.
</div>

<div class="env-box theorem">
    <div class="env-title">Vztahy pro výpočet průměrného stupně:</div>
    <div class="math-block" style="font-size: 11.5pt;">
        <span class="math">&lang;deg<sub>G</sub>(v)&rang; = (1 / N) &sum;<sub>v &isin; V</sub> deg<sub>G</sub>(v) = (1 / N) &sum;<sub>k=0</sub><sup>&infin;</sup> k &middot; N<sub>k</sub> = &sum;<sub>k=0</sub><sup>&infin;</sup> k &middot; p<sub>k</sub> = (2 &middot; |E|) / N</span>
    </div>
</div>

</body>
</html>
