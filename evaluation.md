
Köszönjük, hogy beadtak az önálló megoldásodat. Igazán szuper volt átnézni, reméljük, hogy az alábbiak segíteni fognak a további szakmai fejlődésedben, valamint inspirációként tudnak szolgálni számodra.

A review-t felosztottam pár fejezetre, hogy könnyebben át tudd tekinteni, valamint szerintem ezek a legfontosabb területek, ami a megoldást illeti. A HTML és CSS kódok ellenőrzéséhez [validátort](https://validator.w3.org) használtam első lépésben, ezt követően magam is megnéztem őket.

# Dizájn
Első lépésben megnéztem a honlapodat design és felhasználói élmény (UX) szempontjából. Mivel ez egy meglehetősen szubjektív kategória, ezért kérlek úgy olvasd, hogy ez az én véleményem, benyomásom az oldaladról.

A repozitoridat leklónoztam, majd megnyitottam Chrome böngészőben a GitHub Pages oldalon keresztül megosztott verzióját.

Azt tapasztaltam, hogy egy ügyes oldalt raktál össze. Az oldal hangulata, színe jól illeszkedik a választott témához. A felhasználó számára könnyen azonosíthatóak az egyed funkciónalitások mint a navigávió, a törzsszöveg vagy az akcióra felhívó gomb.

Jól választottál betűtípust: a headerben egy a feliratokhoz jobban illeszkedő, figyelemkeltő fontot választottál, addig a content esetén egy könnyen olvasható mellett tetted le a voksod.

Az oldalt megnéztem desktop, tablet és mobil nézetben is. Desktop méretben jó megoldás a menüt oldalt elhelyezni, így a törzsszöveg nem vett fel kényelmetnül nagy szélességet. Az emberi szem jellemzően nem kedveli a 850-900 pixelnél szélesebb szövegeket monitoron. A szöveg kényelmesen és jól olvasható, a képek szépen illeszkednek a szövegfolyamba. Az oldal alján a "Tovább a cikkekre" akcióra felhívó gomb felirata sajnos nem fér ki, ami zavaró.

Tablet méretben ugyanazt az elrendezést láttam, mint desktopon, ami fektetve kényelmes megjelenést biztosított, viszont már álló helyzetben az oldal elkezdett szorossá válni. Ez alatt azt értem, hogy álló tablet méretben már az oldalsó menü nem biztos, hogy a legjobb választás. Itt azt tapasztaltam, hogy az oldalmenü feliratai nem férnek el kényelmesen a gombokon, ami ismét ront a felhasználói élményen.

Mobil nézetben már ismét minden szépen megtalálja a helyét. Az oldalmenüt egy teljes szélességet kitöltő hamburger menü váltja fel, ami remek választás ezen a méreten. A szöveg és a képek térbeli viszonya is szépen igazodik a keskenyebb kijelzőhöz, megtartva a szemnek kényelmes oldaltávokat.

Jól bántál az üres terekkel is, az oldalad nem túlzsúfolt.

Ami engem kicsit zavart, de értettem az okát, hogy minden link, gomb az oldalon kívülre mutatott. Ez nem feltétlenül hiba, bár érdemes a felhasználóknak egyértelművé tenni, hogy milyen akcióval navigál az adott oldalon belül, és mi az, ami kimutat az oldalról. Ami engem zavart, hogy az oldalon belüli navigációt sejtető menüsor is végül elvitt az oldaladről. Az szerintem rendben van, hogy csak egy oldalt készítettél el egy összetettebb honlapból, hiszen a feladat nem várta el egy teljes honlap leprogramozását. Ilyenkor a konvenció, hogy a honlapon belül navigáció nem csinál semmit sem. Rá lehet kattintani a menü egyes elemeire, de azzal csak újratöltjük az oldalt.


# HTML
A HTML kódodat első lépésben megmutattam a validátornak, ami nem talált benne szintaktikai hibát. Ez már önmagában is dícséretes teljesítmény. Ezt követően magam is átnéztem a kódodat.

A megoldásod alapján azt mondhatom, hogy ismered és használni is tudod a legfontosabb HTML elemeket. Képes vagy egy honlap tartalmát elemeire bontani, azokat adekvát módot HTML elemekké transzformálni, majd ezekből egy logikus és letisztult HTML architektúrát felépíteni.

Ami viszint feltűnt, hogy a HTML 10. sorában beimportálsz egy `style.css` fájlt, ami nem létezik a repozitoriban. Erre a Chrome böngésző dob is egy errort, amit a inspektor konzoljában te is meg tudsz nézni.

Az is feltűnt, hogy a kódod indentálása kesze-kusza. Ez alatt azt értem, hogy nincs mindig összefüggés aközött, hogy mit kezdesz beljebb azzal, hogy az mibe van beágyazva. Pl. a `<head>` elembe beágyazott legtöbb elem pontosan ott kezdődik, ahol a `<head>` elem is, kivéve egy-két link elemet, amely két egységgel is beljebb került.
Ez pont egy olyan hiba, amit nagyon könnyű javítani, ha VS Code szerkesztőben dolgozol. Windowsos gépen `Shift + Alt + F`, Macen a `Shift + Option + F` billentyűparanccsal automatikusan javítja az architektúrának megfelelően.

Örültem annak, hogy több helyen is használtál szemantikus HTML elemeket, mint a `<header>`, `<nav>`, `<main>`, `<article>` vagy `<footer>`. Amit javasolni tudok, hogy amikor azt látod, hogy szinte ugyanazokat az elemeket rakod egymás alá, akkor az egy jó jel arra, hogy használj felsorolást. Pl.:
```html
  <nav class="menu">
    <a class="btn btn__study" href="https://kert.tv/category/zold-otthon/">Növénykés okosságok</a>
    <a class="btn btn__buy" href="https://plantebudapest.com/shop/novenyek/"> Vigyél haza növényt!</a>
    <a class="btn btn__workshop" href="https://plantebudapest.com/shop/workshop/">Workshop</a>
    <a class="btn btn__shop" href="https://plantebudapest.com/viszonteladok/">Üzleteink</a>
    <a class="btn btn__contact" href="https://plantebudapest.com/kapcsolat/">Kapcsolat</a>
  </nav>
```
Itt a `<nav>` elembe csupa `<a>` elemeket raktál, ha jobban megnézed, akkor ez lényegében egy felsorolás. Ilyenkor érdemes akként is kezelni:
```html
  <nav class="menu">
    <ul>
        <ol><a class="btn btn__study" href="https://kert.tv/category/zold-otthon/">Növénykés okosságok</a></ol>
        <ol><a class="btn btn__buy" href="https://plantebudapest.com/shop/novenyek/"> Vigyél haza növényt!</a></ol>
        <ol><a class="btn btn__workshop" href="https://plantebudapest.com/shop/workshop/">Workshop</a></ol>
        <ol><a class="btn btn__shop" href="https://plantebudapest.com/viszonteladok/">Üzleteink</a></ol>
        <ol><a class="btn btn__contact" href="https://plantebudapest.com/kapcsolat/">Kapcsolat</a></ol>
    </ul>
  </nav>
```
Ez megint növeli a kódod szemantikusságát, illetve formázáskor is van előnye, hiszen az `<ol>` elemeket praktikus konténerelemként használhatod. Hasonlóképpen járhatsz el a `<footer>` esetén is.

# CSS
Hasonlóan a HTML-hez, a CSS kódjaidat is első lépésben megmutattam a validátornak, és örömmel tapasztaltam, hogy egyik fájlban sem talált hibát. Sikersen építettél fel egy jól skálázható CSS architektúrát, amelyeben elkülönítetted az egyes layereket (base, layout, components).

Ismered és használni is tudod a legfontosabb CSS szabályokat, a grid, flexbox technológiákat, helyesen használod a CSS függvényeket. A saját elképzelésedet képes vagy CSS szabályokká transzformálni. Az architektúrádhoz két javaslatot tennék csak:
1. A képeket érdemes egy `/assets` mappába betenni. Egy kisebb projekt esetében talán nem feltűnő, miért problémás ezeket "kint hagyni" a projektmappában, de egy nagyobb projekt esetén (300+ kép), már szerintem te is el tudod képzelni, micsoda káoszt okozna ez. Ezért jobb, ha már kicsitben (is) külön mappákban tárolod.
2. Sokkal elegánsabb a CSS architektúrád, ha a HTML-be tényleg csak egyetlen CSS fájlt importálsz be, mondjuk egy `style.css`-t. Az összes többi CSS fájlt pedig ebbe. Ennek a fájlnak nem is kell mást tartalmaznia, mint a többi fájl importját. Ennek előnye, hogy lehet akár 50+ CSS fájlod is (egy valós projektben ez nem ritka), akkor sem dagasztja a HTML fájl `<head>`-jét. Illetbe bármikor hozzá tudsz adni egy új fájlt, nem kell a HTML-t módosítanod hozzá, csak beimportálni a `style.css`-be.

Feltűnt, hogy a `layout.css`-ben ezt írod:
```css
  grid-template-areas:
                         "header header header"
                         "menu main empty"
                         "footer footer footer";
```
Először azt hittem, hogy létezik egy `empty` kulcsszó, amit én nem ismerek. Aztán rövid internetes kutatodást követően azt találtam, hogy nincs ilyen, tehát itt a böngésző arra számítana, hogy létezik egy olyan HTML elem, amit majd `emtpy` alias-szal definiálsz. Ennek hiányában valójában ez történik a böngészőben:
```css
  grid-template-areas:
                         "header header header"
                         "menu main main"
                         "footer footer footer";
```
Ha szeretnél egy grid-cellát üresen hagyni, tehát ne legyen ott egyetlen HTML elem sem, akkor erre való a `.`. Tehát helyesen az, amit te szerettél volna:
```css
  grid-template-areas:
                         "header header header"
                         "menu main ."
                         "footer footer footer";
```

Azt is örömmel láttam, hogy igyekeztél a _BEM_ nevezéktant követni az osztályok elnevezése során. Nem tudom, hogy ennek-e a következménye, de vannak olyan osztálynevek, amelyek igazából teljesen feleslegesek, mert nem tartozik hozzájuk szelektor. Ilyen a `<nav>` elembe ágyazott linkekre rakott `btn__*` osztályok. Ezek igazából hibának minősülnek. Az osztályok sosem öncélúak, hanem azt a cél szolgálják, hogy minél takarékosabb CSS kódot írhassunk a segítségükkel. Ha egy osztályhoz nem tartozik CSS szabály, akkor az törölhető, felesleges.

Olykor a kódod nem tesz eleget a _DRY_ alapelvnek, azaz helyenként ismétled önmagad. Erre példát a `components.css`-ből mutatnék:
```css
.btn {
 text-decoration: none;
 color:           inherit;
 display:         block;
 text-align:      start;
}


.btn {
  display:          inline-block;
  background-color: #163e2f;
  color:            #e1faf0;
  font-family:      'Kumbh Sans', sans-serif;
  font-weight:      400;
  font-size:        .85rem;
  letter-spacing:   .06rem;
  text-transform:   uppercase;
  border-radius:    .3rem;
  border:           none;
}
```

Ez a két szelektor egymás alatt van, pontosan ugyanazokra az elemekre vonatkozik, akár össze is lehetne vonni őket. Mindkét szelektor esetén használod a `color` property-t, egyszer egy konkrét, egyszer pedig `inherit` értékkel. A böngészőben valójában csak a második fog érvényesülni.

Szeretném azt is megmutatni, hogy a media query-kbe csak olyan szabályokat kell megfogalmaznod, amiben az egyes nézetek eltérnek egymástól. Ha ezzel a szemmel nézed az alábbi kódrészletet, akkor te is láthatod, hogy volna itt mit egyszerűsíteni:
```css
.container {
  display:               grid;
  grid-template-areas:
                         "header header header"
                         "menu main empty"
                         "footer footer footer";
  grid-template-columns: .9fr 2.85fr .15fr;
  grid-template-rows:    auto 1fr auto;
  grid-gap:              1rem 0;
  height:                180vh;
}

@media (max-width: 768px) {
  .container {
    grid-template-areas: 
                           "header"
                           "menu"
                           "main"
                           "footer";
    grid-template-columns: 100%;
    display:               grid;
    margin-left:           auto;
    margin-right:          auto;
    }

  }
```
Igazából az, amit te szerettél volna, megoldható ennyivel is:
```css
@media (max-width: 768px) {
  .container {
    grid-template-areas: 
                           "header header header"
                           "menu menu menu"
                           "main main main"
                           "footer footer footer";
  }
```
Minden más voltaképpen változatlan. Illetve ezen a ponton szeretném még azt kiemelni, ha csak nem valamiért nagyon muszáj, sose adj meg magasságot. A legtöbb HTML elem default viselkedése az, hogy felveszi a contenthez szükséges magasságot. Nem pontosan értem, hogy miért érezted szükségét a teljes oldalnak `180vh` magasságot adni. Egyrészt kicsi szélesség mellett ez nem lesz elég, másrészt nagy szélesség mellett sok lesz.

Egy utolsó témát szeretném még felvetni: pontosan hány méretre érdemes, kell optimalizálni egy oldalt? Nicsenek erre igazán abszolút válaszok, részben attól is függ, hogy milyen oldalt készítesz és kinek. De az ökölszabály, hogy azért legalább három mérethez érdemes igazítani egy oldalt: asztali gép, tablet és mobil. A _mobile first_ szemlélet azt javasolja, hogy a default nézet a mobil legyen, és egy-egy media query-ben mondd meg, hogy mitől lesz több vagy más a tablet és a desktop méret. Te most a desktopot vetted defaultként, ami egyáltalán nem hiba, majd ezen felül csak mobilra optimalizáltál.

# Pontszámok
_[szerzett / maximális pontok]_

__Általános dizájn__: 8 / 10 levontam 1-1 pontot a cikk alján kilógó szövegért, illetve a tablet méretben csúnya menüért.

__Szintaktikai helyesség__: 7 / 10 levontam 2 pontot az `empty` grid area-ért, illetve 1 pontot a bent maradt `style.css` importért.

__Architektúra__: 18 / 22 levontam 1-1 pontot a felesleges osztályokért, azért, mert a képeket nem rendezted mappákba, 2 pontot pedig a kódismétlésekért,

__Elvárt technológiák__: 8 / 8 maximális pontszámot adtam, a kódodban megjelent a grid, a flexbox, a transition és a függvények is.

Összesen __41 pontot__ szereztél a maximális 50 pontból, ami egy __82%-os teljesítményt__ jelent. Gratulálok!

# Összegzés, javaslatok
Összességében azt tudom mondani, hogy egy szép, elegáns oldalt álmodtál meg, és szemmel láthatóan rendelkezel azzal a tudással, hogy ezt meg is valósítsd. Nem ijedsz meg egy komplexebb CSS architektúrától sem, sőt, olyan haladó szintű technológiákat is készség szinten ismersz mint a grid vagy a CSS függvények. A végeredmény is azt mutatja, hogy egy erős szinten ismered és használni is tudod azokat a technológiákat, amelyek szükségesek egy profi oldal összeállításához. A hiányzó 18%-ot pedig további gyakorlással simán hozzá tudod tenni. Ezek jellemzően olyan 
Gratulálok az eredményhez, csak bátorítani tudlak, hogy folytasd a kódolást!
