# Szoftver termékfejlesztés

## Absztrakt

A szoftverfejlesztés alapvetően iteratív, rugalmas és gyorsan skálázható folyamat. A fejezet bemutatja az agilis módszertant (Scrum, Kanban), a backlog-kezelés alapelveit, a DoR/DoD szerepét, a szoftverarchitektúra alapfogalmait, a CI/CD és automatizált tesztelési rendszerek működését, az UX-UI tervezés feladatait, valamint az üzemeltetés és monitoring folyamatát.

A Lean Hardware Startup szemlélet itt két módon egészíti ki a tananyagot:

### Hardver-szoftver különbségek

* a szoftver „omelet”, a hardver „spacewalk”: a szoftver gyorsan, fájdalom nélkül javítható; a hardver nem.
* ezért a szoftver iterációk ritmusát tudatosan kell összehangolni a hardver lassúbb ciklusaival.

### Validációs kultúra különbségei
* szoftvernél a Lean Startup teljes mértékben alkalmazható: gyakori kiadások, gyors A/B tesztek, elemzés.
* ez a fejezet kiemeli, hogyan lehet a szoftveres iterációt hozzáilleszteni a csapat egészének tanulási folyamatához.
A hallgatók megtanulják, hogy a szoftverfejlesztési folyamatok rugalmassága a startup működésének egyik legfontosabb versenyelőnye, ugyanakkor szigorú folyamatfegyelmet kíván, hogy a gyorsaság ne menjen a minőség rovására.

### Kötelezően megjelenő fogalmak, kulcsszavak

* Szoftverfejlesztési életciklus
* Agilis fejlesztés, Scrum, Kanban
* Roadmap, Product backlog → Sprint backlog
* DoR - Definition of Ready
* DoD - Definition of Done
* User story, acceptance criteria
* UX → UI → prototyping → usability tests
* Szoftverarchitektúra → monolith, microservices, modularity
* CI/CD: build, test, deploy pipeline
* Verziókezelés: Git, branching strategies (Git-flow, trunk-based)
* Unit test, integration test, E2E test
* Code review, pair programming
* Release management → Canary release, blue-green deployment
* Monitoring, observability → logs, metrics, alerts
* Security basics (OWASP top 10 említésszinten)
* Technical debt, refactoring
* Sprint ritmusok: planning, daily, review, retrospective


## Projektmenedzsment


Az Agile a szoftverfejlesztésben egy rugalmas megközelítés, amely gyors iterációkra, folyamatos visszajelzésre és együttműködésre épül. Számos keretrendszere létezik, például a Scrum, ahol sprintekben dolgoznak, illetve a Kanban, amely folyamatos áramlásra és munkakorlátozásra épít. A cél, hogy a csapat gyorsan és hatékonyan tudjon reagálni a változó igényekre.

### Project management eszközök

A PM eszközök (project management tool-ok) a projektek tervezését, feladatkezelést, kommunikációt és riportolást segítik. Támogatják az Agile, Scrum, Kanban vagy akár vízesés típusú munkafolyamatokat, és hatékonyabbá teszik a csapatmunkát.

**_Trello_**

– Fizetős? Ingyenes alapfunkciókkal, bővített csomagok havi díjért.
– Projekttípus: Kis csapatok, marketing, könnyű Kanban alapú feladatkezelés.
– Jellemző: Kártya-alapú, egyszerű, vizuális.

**_Jira_**

– Fizetős? Ingyenes kis csapatnak (max 10), nagyobb csapatoknak havi díjas.
– Projekttípus: Fejlesztőcsapatok, komplex Agile projektek, enterprise környezet.
– Jellemző: Sprintkezelés, backlog, fejlett riportok.

**_Redmine_**
– Fizetős? Ingyenes, nyílt forráskódú; saját szerveren fut.
– Projekttípus: Olyan csapatoknak, akik testre szabható, önhostolt megoldást akarnak.
– Jellemző: Issue-kezelés, wiki, moduláris bővíthetőség. A mai szemnek ódivatú, de funkcióját jól ellátó felülete van.

**_YouTrack_**
– Fizetős? Ingyenes kis csapatoknak, nagyobbaknak előfizetéses.
– Projekttípus: Fejlesztőcsapatok, akik gyors keresésre és hatékony issue-kezelésre vágynak.
– Jellemző: Keresőalapú workflow, Agile boardok.

**_ClickUp_**
– Fizetős? Ingyenes alapcsomag, fejlettebb funkciókért havi díj.
– Projekttípus: Minden típusú projekt, cégeknek akik „mindent egyben” rendszert akarnak.
– Jellemző: Dokumentumok, dashboardok, automatizációk.

**_Asana_**
– Fizetős? Ingyenes alapcsomag, profi funkciók előfizetéssel.
– Projekttípus: Általános csapatmunka, marketing, operations, kisebb IT-projektek.
– Jellemző: Könnyen tanulható, vizuális tervezés, idővonal, hierarchizálható feladatok.

### Kommunikációs csatornák

**_Google Workspace_**  
– Fizetős? Havidíjas csomagok, vállalati szintű szolgáltatásokkal.  
– Mire való: Olyan cégeknek, ahol fontos a könnyű dokumentummegosztás, valós idejű együttműködés és integrált felhőalapú működés.  
– Jellemző: Gmail, Google Drive, Meet, Chat – minden jól integrálva egy rendszerben.

**_Microsoft 365 (korábban Office 365)_**  
– Fizetős? Előfizetéses rendszer többféle vállalati csomaggal.  
– Mire való: Közép- és nagyvállalatoknak, ahol fontos a fejlett adminisztráció, biztonság és a klasszikus Office alkalmazások integrációja.  
– Jellemző: Outlook, Teams, SharePoint, OneDrive – erős vállalati ökoszisztéma, strukturált kommunikációval.

**_Slack_**  
– Fizetős? Ingyenes alapverzió korlátozásokkal; teljes funkcionalitás előfizetéssel.  
– Mire való: Főleg technológiai csapatoknak, ahol sok integrációra, botra és gyors csatornaalapú kommunikációra van szükség.  
– Jellemző: Csatornák, fejlett keresés, rengeteg integráció, jól skálázódik nagy csapatokra.

**_Discord_**  
– Fizetős? Alapvetően ingyenes, opcionális fizetős funkciókkal (Nitro).  
– Mire való: Rugalmasabb, közvetlenebb kommunikációra, kisebb vagy informálisabb csapatoknak, illetve ahol gyakori a hangalapú együttműködés.  
– Jellemző: Hangcsatornák, egyszerű szobakezelés, gyors chat – kevésbé formális, de nagyon rugalmas eszköz.

### Globális fogalmak

#### Projekt

A projekt egy időben behatárolt, egyedi cél elérésére irányuló, erőforrásokkal és költségkerettel rendelkező tevékenységcsoport. Van kezdete, vége, konkrét eredménye, és egy adott problémára vagy igényre ad megoldást.

#### User (Felhasználó)

Az alkalmazás felhasználója, azaz az a személy, aki az alkalmazást használja.

#### Business (Üzleti oldal)

A termék vízióját és elvárásait megfogalmazó személy(ek), akiknek feladata a koncepciók, követelmények, nagy vonalakban felvázolt tervek és mérföldkövek meghatározása a fejlesztők számára.

#### Issue (Feladat)

Az Issue egy megoldandó feladatot jelöl. Van egy típusa és egy állapota, amely minden boardra jellemző. Nevezik még Ticket-nek, Task-nak is, valamint ha egy Issue egy boardhoz van társítva, azt kártyának is nevezik. 

**_Issue típusok_**

* **Epic**: Egy adott téma/funkció köré szerveződő gyűjtőkártya, amely egy nagyobb egységet alkot.
  * Segít a nagyobb kép megértésében.
  * Tartalmazza a termékoldalról érkező összes elvárást, információt, tervet és azt, hogy mit várunk a funkció befejezésekor.
  * Kifejezi a funkció egységes egészéből származó felhasználói élményt.
  * Az Epic-et az alá gyűjtött Story-k befejezése után tekintjük befejezettnek.
* **Story**: Egy Epic-hez társítható, de önálló jegytípus is.
  * Feature kéréseket ír le, üzleti igényeket vázol fel.
  * A technikai jegynek röviden le kell írnia, hogy mit várunk a story-tól. Ezenkívül egyértelmű és konkrét kritériumokat (Acceptance Criteria) kell meghatározni.
  * Szükség esetén kiegészíthető tervekkel, mellékletekkel, fejlesztői jegyzetekkel stb.
* **Task**: A Story-k alá szervezhető feladatok altípusa.
  * Kisebb alegység, amely önmagában nem feltétlenül nyújt felhasználói élményt.
  * A Story-t az összes benne lévő Task elvégzése után tekintjük befejezettnek.
* **Test**: Kisebb alegység (a Task-kal egyenértékű), amely a tesztelési fázis átláthatóságát hivatott lefedni.
* **Spike**: Olyan típus, amely nem igényel valódi implementációt, de szükséges egy adott fejlesztés összes technikai részletének feltárásához, a nehézségek meghatározásához stb.
  * Minden Spike-hoz meg kell határozni egy kívánt eredményt, amely a Spike célját képviseli (pl. Proof of Concept).
  * A Spike során elengedhetetlen az alapos és rendszeres dokumentáció, amelynek célja a vizsgált tárgyra (pl. Feature kérés) vonatkozó minél több részlet felderítése.
* **Bug**: Hibajelentések típusa.

#### Board

A board egy vizuális tábla, amelyen a feladatok státusza látható oszlopokba rendezve (például: To Do, In Progress, Done). Segít követni a munka előrehaladását és átláthatóvá tenni a csapat feladatait.

Egy jó praktika lehet egy projektben külön board-ot tartani a tervezésnek (Grooming), kivitelezésnek (Implementation) és hibakezelésnek (Troubleshooting).

Példa a board-ok oszlopelrendezésére:

**_Grooming board_**

* **Not Relevant Yet**: Érintetlen jegy, amely a jelenlegi fejlesztési szakaszban még nem releváns.
* **Wait for Grooming**: A jelenlegi fejlesztési szakaszban releváns, megbeszélésre váró jegy.
* **Under Grooming**: Megbeszélés, tisztázás vagy kidolgozás alatt álló jegy.
* **Groomed**: Tisztázott/kidolgozott jegy.

**_Implementation board_**

* **Open**: Nyitott jegy, még nem foglalkoztak vele.
* **In Progress**: A megoldás folyamatban van.
* **Parking**: Elkezdtünk rajta dolgozni, de félretettük, általában egy magasabb prioritású jegy miatt.
* **Blocked**: A jegy megoldása más jegyektől vagy külső tényezőktől való függőségek miatt nem lehetséges.
* **In Review**: Befejezett megoldással rendelkező jegy, amely felülvizsgálatra vár egy Merge Requesten keresztül.
* **In Test**: Befejezett és telepített megoldás, amely tesztelésre vár.
* **Closed**: A jegy megoldódott és lezárult.

**_Troubleshooting board_**

* **Reported**: Jelentett jegy, amellyel még nem foglalkoztak.
* **Incomprehensible**: Nem egyértelmű leírású jegy, amely tisztázást igényel.
* **In Progress**: Jelenleg megoldás alatt álló jegy.
* **Not Reproducible**: A jegyben jelentett hibát nem sikerült reprodukálni, vagy valamilyen más okból már nem reprodukálható.
* **Fixed**: A jegyet javították, de még nem ellenőrizték.
* **Closed**: Javított, ellenőrzött és lezárt jegy.

#### Roadmap

A Roadmap egy magas szintű, vizuális terv, amely bemutatja a termékfejlesztés hosszú távú irányát és a tervezett főbb funkciók, mérföldkövek kiadási ütemezését. Segít összehangolni az üzleti célokat a fejlesztési kapacitással, és kommunikációs eszköz a stakeholderek felé.

#### Product Backlog

A Product Backlog egy priorizált lista, amely tartalmaz minden, a termékkel kapcsolatos követelményt, funkciót, javítást és feladatot. A Product Owner felelős a karbantartásáért. Ez a lista dinamikus, folyamatosan változik az üzleti igények és a piaci visszajelzések alapján.

#### Sprint Backlog

A Sprint Backlog a Product Backlogból kiválasztott elemek halmaza, amelyeket a fejlesztőcsapat a következő sprint során fog megvalósítani. A Sprint Planning során a csapat közösen állítja össze, és a sprint ideje alatt már nem bővíthető, csak a meglévő feladatok elvégzésére fókuszálnak.

#### Definition of Ready (DoR)

A DoR egy ellenőrzőlista, amely meghatározza, hogy egy User Story-nak vagy feladatnak milyen kritériumoknak kell megfelelnie ahhoz, hogy a csapat be tudja venni a sprintbe. Biztosítja, hogy a feladatok jól definiáltak, érthetőek és megvalósíthatóak legyenek, minimalizálva a sprint közbeni kérdéseket.

#### Definition of Done (DoD)

A Definition of Done (DoD) egy fogalom, amelyet az agilis szoftverfejlesztési módszertanokban, különösen a Scrumban használnak. Meghatározza azokat a kritériumokat, amelyeknek egy terméknövekménynek vagy felhasználói történetnek meg kell felelnie ahhoz, hogy teljesnek és kiadásra késznek tekintsék. A DoD segít biztosítani, hogy a fejlesztőcsapat, az érdekelt felek és az ügyfelek közösen értsék, mi minősül befejezett és magas minőségű munkának.

**Példa a DoD-ra:**

1. A kód működik a helyi környezetben
A fejlesztő felelőssége, hogy a kód a saját gépén megfelelően működjön. Ez magában foglalja a szükséges infrastruktúra beállítását is.
2. Az elfogadási kritériumok teljesültek
A fejlesztőnek biztosítania kell, hogy a feladat megfeleljen az aktuális JIRA jegyben rögzített összes elfogadási kritériumnak.
3. A közös rétegszerkezet teljesült
A fejlesztőnek követnie kell a Backend Development Guideline és Frontend Development Guideline dokumentumokban leírtakat.
4. A kapcsolódó OpenAPI definíciók megírva
A fejlesztő felelőssége, hogy az OpenAPI in layers dokumentációnak megfelelően elkészítse a szükséges OpenAPI definíciókat.
5. A kapcsolódó Unit tesztek megírva
A fejlesztőnek a PHP testing/Pest útmutató alapján kell elkészítenie a unit teszteket.
6. A kapcsolódó E2E tesztek megírva
A tesztelő feladata, hogy a funkcióhoz kapcsolódó end-to-end teszteket megírja.
7. A kód felülvizsgálva
A vezető fejlesztőnek a GIT Workflow Guideline alapján felül kell vizsgálnia a kódot.
8. A kapcsolódó unit tesztek átmentek a pipeline-on
A fejlesztő felelőssége, hogy a unit tesztek sikeresen lefussanak a CI/CD pipeline-on.
9. A kapcsolódó E2E tesztek átmentek a pipeline-on
A fejlesztő felelőssége, hogy az end-to-end tesztek sikeresen lefussanak a CI/CD pipeline-on.
10. A kód működik a fejlesztői környezetben (develop branch)
A fejlesztőnek biztosítania kell, hogy a kód működjön az infrastruktúrában.
11. A kapcsolódó manuális tesztek teljesültek
A tesztelő feladata, hogy elvégezze a szükséges manuális teszteket.
12. A dokumentáció frissítve
A fejlesztőnek a Document Maintenance útmutató alapján frissítenie kell a dokumentációt.

#### Acceptance Criteria

Azok a konkrét, tesztelhető feltételek, amelyeknek egy User Story-nak teljesülnie kell ahhoz, hogy "kész"-nek (Done) minősüljön. Egyértelművé teszik a követelményeket, és alapot adnak a teszteléshez.

#### Ceremóniák

A ceremóniák fontosak az együttműködés kialakításához. Az Agile módszertanban a következő típusú meetingeket használjuk:

##### Daily standup
* Cél: Általános státuszjelentés a csapat felé.
* Gyakoriság: Heti kétszer.
* Időtartam: Max. 30 perc.
* Résztvevők: Fejlesztők + Scrum Master.
* Felelős: Scrum Master.
* Menet: Minden csapattagnak 5 perce van elmondani:
  * Min dolgozott múlt héten.
  * Min fog dolgozni ezen a héten.
  * Milyen akadályokkal szembesül.

##### Grooming meeting
* Cél: Epicek és Story-k tisztázása, pontos követelmények meghatározása és leírása a ticketben.
* Gyakoriság: Hetente 1–2 alkalom.
* Időtartam: Max. 1,5 óra.
* Résztvevők: Product Owner, Scrum Master, Fejlesztők.
* Felelős: Product Owner.
* Menet: A ticketek áttekintése, a teendők és üzleti igények megbeszélése. A Grooming board ticketjeinek átnézése.

##### Sprintforduló (Sprint) 
* Cél: A futó sprint lezárása, az új sprint fókuszának meghatározása és elindítása.
* Gyakoriság: Általában 1–2 hetente ismétlődő ciklusok.  
* Időtartam: Max. 1.5 óra.
* Résztvevők: Fejlesztők, Scrum Master, Product Owner.  
* Felelős: Scrum Master a folyamat koordinálásáért, Product Owner a backlog priorizálásáért.  
* Menet: A csapat lezárja a futó sprintet és a fennmaradt jegyeket átviszi a következőbe, valamint kiválasztja a backlogból a további teendőket. A Csapat megtekinti a lezárt sprint Burnout chart-ját, ami képet ad a hatákonyságról.

##### Retrospective meeting
* Cél: A csapat teljesítményének és eszköztárának értékelése és fejlesztése.
* Gyakoriság: Havonta (mérföldkövek után).
* Időtartam: Max. 1,5 óra.
* Résztvevők: Product Owner, Scrum Master + Fejlesztők.
* Felelős: Opcionális.
* Menet: A fejlesztők és az üzleti oldal elmondhatják a múlt hónapban tapasztalt reakcióikat. A cél konstruktívan meghatározni, mi ment jól, milyen külső vagy belső tényezők akadályoztak, és hol lehet javítani. Ha nincs egyértelmű megoldási javaslat, Action Itemet kell rögzíteni, amelynek felelőse a szerepkörtől és a probléma jellegétől függ.

### SDLC (Szoftverfejlesztési életciklus)

A szoftverfejlesztési életciklus (Software Development Life Cycle – SDLC) egy strukturált folyamat, amely a szoftver tervezésétől, fejlesztésétől és tesztelésétől a telepítésen át a karbantartásig terjed. A ciklus fő szakaszai a követelményanalízis, tervezés, implementáció, tesztelés, telepítés (deployment) és karbantartás. A modern, agilis megközelítések ezeket a szakaszokat rövid, iteratív ciklusokban ismétlik, lehetővé téve a rugalmas alkalmazkodást a változó igényekhez.

Ez a dokumentum leírja a SCRUM csapat számára, hogyan tervezhet és valósíthat meg egy új funkciót a szoftvertermékeinkben.

#### Résztvevők

* **Business**
* **SCRUM Team**
* **Product owner**
* **Engineering Team Lead**
* **Product Designer**
* **Developer**
* **Test Automation Expert**
* **DevOps Expert**

> Megjegyzés: Egy induló cég nem biztos, hogy rendelkezik ilyen létszámmal. Egy fő több kalapot is hordhat.

#### Specifikáció

**Üzleti igények**

* **Leírás**: Fel kell fedeznünk a felhasználói igényeket és le kell írnunk egy funkcióigényt (FR), amely üzleti értéket képvisel. Ez a lépés egy üzleti döntés, amely nem tartozik a dokumentum hatálya alá. Az üzleti igény megléte előfeltétel.
* **Felelős Személy**: Elsődleges: Üzlet, Másodlagos: Terméktervező
* **Kapcsolódó dokumentumok**: Feature Creation Process Guideline

**Tervezés**

* **Leírás**: A tervező feladata, hogy együtt érezzen a felhasználói igényekkel, kidolgozza a felhasználói perszónákat, és olyan terveket készítsen, amelyek megoldják a felhasználó problémáit. A tervek ellenőrzése használhatósági tesztekkel. A terméktulajdonos felelős a statisztikai eszközök (Mixpanel, Hotjar) összekapcsolásáért.
* **Felelős Személy**: Elsődleges: Terméktervező, Másodlagos: Terméktulajdonos
* **Felülvizsgáló**: Elsődleges: Üzlet, Másodlagos: Mérnöki csapatvezető
* **Kapcsolódó dokumentumok**: Product Design Development Guideline

**Műszaki specifikáció**

* **Leírás**: A mérnöki csapatvezető kidolgozza az FR műszaki részleteit (egy Epic-ben), és a munka részeit story-kra bontja.
* **Felelős Személy**: Mérnöki csapatvezető
* **Felülvizsgáló**: SCRUM csapat
* **Kapcsolódó dokumentumok**: Issue Specification Guideline

#### Implementáció előkészítése

**Közös tervezési ülés és Grooming**

* **Leírás**: A SCRUM csapatnak át kell néznie a story-kat a Grooming előtt, és segítenie kell azok kiterjesztésében és tisztázásában a jobb megértés és a gördülékenyebb Grooming megbeszélés érdekében.
* **Felelős Személy**: SCRUM csapat
* **Kapcsolódó dokumentumok**: SCRUM Meeting Types | Grooming Meeting

**Prioritizálás**

* **Leírás**: A megbeszélt és időbecsült feladatokat a terméktulajdonosnak kell priorizálnia. Ebben a lépésben a terméktulajdonos dönti el, hogy a következő sprint tartalmazhatja-e a feladatot. A terméktulajdonos tájékoztatja a marketinget és kitölti a termékkiadási egyoldalast.
* **Felelős Személy**: Terméktulajdonos
* **Felülvizsgáló**: Üzlet
* **Kapcsolódó dokumentumok**: Product Release Process

#### Implementáció

**Kódolás**

* **Leírás**: Programozás: A fejlesztő a programozási irányelveinkkel együtt módosításokat hajt végre a szoftverben. Kódellenőrzés: Hozzon létre egy pull requestet, amelyet a mérnöki csapatvezetőnek kell felülvizsgálnia és jóváhagynia.
* **Felelős Személy**: Fejlesztő
* **Felülvizsgáló**: Mérnöki csapatvezető
* **Kapcsolódó dokumentumok**: Backend Development Guideline, Technology Stack

**Tesztelés**

* **Leírás**: Az egységteszteket a fejlesztő hozza létre, a manuális tesztdokumentációt pedig a QA szakértő. Az implementáció vége akkor érhető el, ha megfelel a DoD-nek (Definition of Done).
* **Felelős Személy**: SCRUM csapat, QA szakértő
* **Kapcsolódó dokumentumok**: Definition of Done

**Kiadás**

* **Leírás**: Ha a funkcióigény megfelel a Definition of Done-nak, a DevOps szakértő vagy a SCRUM csapat telepíti azt az éles környezetbe. A kiadás után a QA szakértő ellenőrzi a funkciót az éles környezetben is, és ha problémát talál, szól a fejlesztőknek.
* **Felelős Személy**: SCRUM csapat, DevOps szakértő, QA szakértő, Terméktulajdonos

#### Utókövetés

**Marketing**

* **Leírás**: A terméktulajdonos tájékoztatja a marketing csapatot, hogy a funkció elkészült.
* **Felelős Személy**: Üzlet
**Nyomon követés**
* **Leírás**: Ellenőrizze a Mixpanel és a Hotjar eredményeket, foglalja össze, és hozzon létre egy funkcióigényt (FR). Kezelje a BÉTA teszteket és a funkciózászlókat.
* **Felelős Személy**: Elsődleges: Terméktulajdonos, Másodlagos: Üzlet és Terméktervező


## Fejlesztés

### Alkalmazott technológiák (Technology Stack)

A technology stack azt jelenti, hogy egy szoftverprojektben milyen nyelveket, keretrendszereket, adatbázisokat és egyéb eszközöket használnak a fejlesztéshez. Segít átlátni, hogy a csapat milyen szakértelemmel rendelkezik, milyen költségekkel számolhatunk, és mennyire korszerű vagy népszerű a választott megoldás.

#### Nyelv és keretrendszer

Ide tartozik, hogy milyen programozási nyelvet és hozzá kapcsolódó keretrendszereket használ a projekt. Fontos szempontok:  
* A csapat mennyire ért hozzá, milyen a fejlesztők elérhetősége és ára.  
* A közösségi támogatás és dokumentáció bősége.  
* Helyi vagy globális trendek, divatosság.  

#### Kvalitás a programnyelvek tükrében

Általában a komplexebb, erősebb típusbiztonságot, struktúráltabb architektúrát és fejlettebb eszköztámogatást kínáló nyelvek (pl. Java, C#, Golang, Rust) magasabb kvalitásúak, mert csökkentik a hibalehetőségeket és jobb skálázhatóságot biztosítanak.

Ezzel szemben a könnyebben tanulható, belépő szintű nyelvek (pl. JavaScript, PHP, Python) gyorsan fejleszthetők és széles a közösségük, de nagyobb odafigyelést igényel a kód minőségének fenntartása, különösen komplex projektek esetén.

Érdemes tehát mérlegelni a lehetőségeinket ennek fényében is, hogy megbízható, jól karbantartható és hosszú távon stabil rendszert tudjunk építeni.

#### Platform

Ez azt jelenti, hogy a szoftver mely környezetben fut, és milyen nyelveket érdemes használni hozzá:  
* Mobil: iOS (Swift, Objective-C), Android (Kotlin, Java), cross-platform (Flutter/Dart, React Native/JavaScript)  
* Desktop: Windows (C#, .NET, C++), macOS (Swift, Objective-C), Linux (Python, C++, Java)  
* Web: frontend (JavaScript/TypeScript + React, Angular, Vue.js), backend (Node.js, Python/Django, Java/Spring, PHP/Laravel)  
* Multiplatform: egyszerre több környezetet támogat, pl. web + mobil (React Native, Flutter, Electron)

### Termék architektúra

* Általános best practice, hogy az MVP monolitikus legyen, mert egyszerűbb, gyorsabb fejlesztést és könnyebb karbantartást tesz lehetővé.
* Mikroszolgáltatás-alapú architektúrára érdemes váltani, ha:
  * A kezdetektől fontos a magas terhelhetőség és skálázhatóság.
  * A csapat rendelkezik a szükséges szakértelemmel a komplexebb rendszer kezeléséhez.
  * A projekt hosszú távon komplex, több modulból álló funkcionalitást kíván kiszolgálni.

#### Monolith vs Microservices

**_Monolith_**

Egy olyan szoftverarchitektúra, ahol az alkalmazás összes funkciója egyetlen, egységes kódbázisban fut. Egyszerűbb fejleszteni és telepíteni, de nagyobb méret és komplexitás esetén nehezebb skálázni. Főbb típusai:

* **Egyprocesszes monolit:** A legelterjedtebb forma, ahol minden kód egyetlen processzben fut.
* **Moduláris monolit:** A kód különálló modulokból áll, de a telepítés továbbra is egységes. Ez lehetővé teszi a párhuzamos fejlesztést, de az adatbázis gyakran közös marad, ami nehezíti a későbbi szétválasztást.
* **Elosztott monolit:** Bár több szolgáltatásból áll, a rendszert mégis együtt kell telepíteni a szoros csatolások miatt. Ez a legrosszabb mindkét világból: az elosztott rendszerek komplexitását ötvözi a monolitok rugalmatlanságával. A monolitok előnye az egyszerűbb telepítés, fejlesztői folyamatok és tesztelés. Kisebb csapatoknál vagy a fejlesztés korai szakaszában gyakran ez az legésszerűbb alapértelmezett választás.

**_Microservices_**

Egy olyan szoftverarchitektúra, ahol az alkalmazás összes funkciója egyetlen, egységes kódbázisban fut. Egyszerűbb fejleszteni és telepíteni, de nagyobb méret és komplexitás esetén nehezebb skálázni.

* **Elvek:**
  * **Komponálhatóság:** A funkcionalitás könnyen újrafelhasználható különböző kontextusokban.
  * **Domain-Driven Design (DDD)::** A szolgáltatások határait az üzleti domain (pl. Bounded Context\-ek) mentén érdemes kialakítani a magas kohézió és laza csatolás érdekében.
  * **Információelrejtés:** Minden szolgáltatás elrejti a belső implementációs részleteit, és csak egy jól definiált interfészt (API) tesz közzé.
* **Kihívások (Fájdalompontok):**
  * **Komplexitás:** Az elosztott rendszerek természetéből fakadóan bonyolultabb a fejlesztői élmény, a tesztelés, a monitorozás, a hibakeresés és az adatkonzisztencia biztosítása.
  * **Költségek:** A megnövekedett infrastrukturális és üzemeltetési igények miatt a kezdeti költségek magasabbak lehetnek.
  * **Csatolás:** Különös figyelmet kell fordítani a csatolás típusaira (pl. el kell kerülni a Content Coupling\-ot), hogy a szolgáltatások valóban függetlenek maradjanak.

A mikroszolgáltatások nem minden esetben jelentenek ideális megoldást. Leginkább nagy, gyorsan növekvő rendszereknél, SaaS alkalmazásoknál és olyan szervezeteknél előnyösek, ahol több csapat dolgozik párhuzamosan.

#### SPA vs MPA

**SPA (Single Page Application)**  
Egy SPA egyetlen HTML-oldalt használ, és a felhasználói interakciók során a tartalom dinamikusan frissül JavaScript segítségével, anélkül, hogy az oldal újratöltődne.  
* **Előnyök:**  
  * Gyors, gördülékeny felhasználói élmény.  
  * Modern frontend keretrendszerek támogatása.  
  * Kisebb sávszélesség-használat, mivel nem töltődnek újra teljes oldalak.  
* **Hátrányok:**  
  * Lassabb kezdeti betöltés, mivel az összes JS és app logika betöltődik egyszerre.  
  * SEO optimalizálás nehezebb, bár modern megoldásokkal (SSR, prerender) javítható.  
* **Keretrendszerek / technológiák:** React, Angular, Vue.js, Svelte, Next.js (SSR-rel), Nuxt.js (SSR-rel)

**MPA (Multi Page Application)**  
Az MPA esetén minden oldal külön HTML-oldalként töltődik be a szerverről. A navigáció új oldalbetöltésekkel történik.  
* **Előnyök:**  
  * Egyszerűbb SEO, mivel minden oldal külön URL-en érhető el.  
  * Könnyebb kezdeti betöltés, mivel csak az adott oldal tartalma töltődik.  
  * Klasszikus webfejlesztési modell, stabil és széles körben támogatott.  
* **Hátrányok:**  
  * Lassabb, megszakításokkal teli felhasználói élmény a gyakori újratöltések miatt.  
  * Több szerveroldali logika szükséges a dinamikus tartalom kezeléséhez.  
* **Keretrendszerek / technológiák:** Django, Ruby on Rails, Laravel, Spring MVC, ASP.NET MVC

### Program architektúrák

A szoftverarchitektúra rétegekre bontása, az adattranszfer objektumok (DTO-k) és a dependency injection (függőséginjektálás) használata mind azt a célt szolgálja, hogy az adatáramlás átlátható és követhető legyen.

A modularitás egy szoftverarchitekturális elv, amely a rendszert független, cserélhető és önálló egységekre (modulokra) bontja. Minden modul egy specifikus feladatot lát el, és jól definiált interfészen keresztül kommunikál a többi modullal. A modularitás növeli a kód újrafelhasználhatóságát, megkönnyíti a karbantartást és a párhuzamos fejlesztést, mivel egy-egy modul anélkül módosítható vagy cserélhető, hogy az a teljes rendszert érintené.

#### Rétegek (layers)

A szoftverarchitektúrában a rétegek szétválasztása egy bevett gyakorlat. Különböző modellek léteznek, mint például a klasszikus Model-View-Controller (MVC), vagy a részletesebb, Domain-Driven Design (DDD) által inspirált modellek, mint az Entities \-> Use Cases \-> Interface Adapters \-> Frameworks & Drivers. A rétegekre bontásnak számos előnye van: a modulok könnyen "mockolhatóak" (szimulálhatóak), ami a tesztelést segíti; a kódbázis szervezettebbé válik; a struktúra fix és követhető lesz; a közös kódbázis kialakítását pedig a fix elnevezési konvenciók segítik. Minden réteg egy "fekete doboz", ami elrejti a belső implementációt, és csak a publikus interfészt teszi láthatóvá. Ez a modularitás, a könnyebb tesztelhetőség és a jobb karbantarthatóság alapja. A "Facade" service-ek (homlokzati szolgáltatások) tiszta interfészt biztosítanak több szolgáltatási osztályhoz egyszerre, lehetővé téve a kisebb és fókuszáltabb szolgáltatási osztályok létrehozását, az üzleti logika olvashatóságát, és csökkentve a privát segédfüggvények számát.
A döntések elhalasztása (Decision Postponement)
A rétegzett architektúra támogatja a "decision postponement" elvét, azaz a döntések elhalasztását, amíg elegendő információ áll rendelkezésre a legjobb választáshoz. Ez rugalmasságot biztosít a jövőbeli változásokhoz, jobb döntéseket eredményez a teljesebb információk alapján, költséghatékonyabb, mert elkerüli a felesleges fejlesztési erőfeszítéseket, és skálázhatóbbá teszi az architektúrát, amely a valós igényekkel együtt fejlődhet. Például általános megoldásokat hozhatunk létre, amelyek különböző felhasználási esetekkel működnek, vagy olyan repository osztályokat, amelyek nincsenek adatelérési technológiához kötve.

#### Adattranszfer objektumok (DTOs)

A DTO-k (Data Transfer Objects) összetett adatstruktúrák szállítására, adatvalidációra, valamint a rétegek és szervizosztályok közötti tiszta be- és kimenet biztosítására szolgálnak. Segítenek elkerülni a "code smell"-eket, mint például a túl sok (háromnál több) bemeneti argumentumot vagy a tuple visszatérési értékeket. Implementációjuk nyelvenként változó: PHP-ban osztályok, TypeScriptben interfészek, Pythonban (Pydantic) osztályok, C-ben, Go-ban és Rustban pedig structok formájában valósulnak meg. A DTO-k átjáróként funkcionálnak a rétegek között, csak a szükséges adatokat továbbítják, csökkentve a "zajt" és segítve a fókuszt. Ahogy Robert C. Martin (Uncle Bob) mondja: "Keep the DTOs simple\!" (Tartsd a DTO-kat egyszerűnek\!).

#### Függőségkezelés (Dependency Injection - DI)

A dependency injection (DI) egy olyan tervezési minta, amelynek célja a lazán csatolt komponensek létrehozása. A DI támogatja a "mocking"-ot, központi függőségi fát hoz létre, és könnyű hozzáférést biztosít a függőségekhez. Csökkenti a kódbázist ott, ahol beinjektáljuk a függőséget, és a függő osztálynak nem kell tudnia a függőség implementációjáról. A függőség példányosítása nem a függő osztály hatásköre. Uncle Bob szerint a DI a tiszta kód és a skálázhatóság egyik alapköve.

## Utak a minőséghez

### Minőségbiztosítás

A fejlesztési gyakorlatok és a minőségbiztosítás (Quality Assurance \- QA) olyan folyamatok és eszközök összessége, amelyek célja a szoftver minőségének folyamatos javítása és a hibák megelőzése. Ide tartoznak a kódolási szabványok, az automatizált tesztelés, a kódellenőrzés (code review) és a páros programozás, amelyek együttesen biztosítják, hogy a fejlesztés során a csapat magas minőségű, megbízható és karbantartható kódot állítson elő.

### Technikai adósság és refaktorálás

A technikai adósság (technical debt) a fejlesztés során hozott, tudatos vagy nem tudatos kompromisszumok (pl. egy gyors, de nem optimális megoldás választása) felhalmozódott "költsége". Hosszú távon ez a "kölcsön" kamatozik: nehezíti a karbantartást, lassítja az új funkciók fejlesztését és növeli a hibák kockázatát. A **refaktorálás** az a folyamat, amely során a kód belső szerkezetét javítjuk anélkül, hogy a külső viselkedése megváltozna. A refaktorálás a technikai adósság "törlesztésének" egyik legfontosabb eszköze, amely tisztábbá, érthetőbbé és könnyebben bővíthetővé teszi a kódot.

### Code review
A kódellenőrzés során egy vagy több fejlesztő átnézi egy kollégájuk által írt kódot, mielőtt az beolvasztásra kerülne a közös kódbázisba. A cél a hibák, logikai problémák, a kódolási szabványoktól való eltérések és a potenciális teljesítményproblémák kiszűrése. Ez a gyakorlat nemcsak a kód minőségét javítja, hanem a tudásmegosztást és a csapatszintű felelősségvállalást is elősegíti.

### Pair programming
A páros programozás egy agilis technika, ahol két fejlesztő dolgozik együtt egy munkaállomáson. Az egyikük, a "driver", írja a kódot, míg a másik, a "navigator", folyamatosan figyeli, ellenőrzi a munkát, és stratégiai iránymutatást ad. A szerepeket gyakran cserélik. Ez a módszer javítja a kód minőségét, csökkenti a hibák számát, és felgyorsítja a tudásmegosztást a csapaton belül.

### Félelem a túltervezéstől

Természetesen a szabályokhoz, architektúrákhoz, industry standard-ekhez való ragaszkodásnak vannak (látszólagos) vannak hátrányai is. A rétegek, DTO-k és a DI használata teljesítmény- és komplexitásbeli "overhead"-et (többletterhet) jelenthet, például a "boilerplate" kód (sablonkód) és a módosítási láncok miatt. Azonban, ahogy Uncle Bob mondja: "A kódot másoknak írjuk."

A tiszta, érthető és karbantartható kód hosszú távon mindig megtérül.

## UX/UI tervezés

Az UX (User Experience) és UI (User Interface) tervezés célja, hogy a szoftver ne csak funkcionális, hanem könnyen használható, hatékony és élvezetes is legyen. Az UX a teljes felhasználói élményre fókuszál, beleértve a logikai felépítést és a felhasználói utakat, míg az UI a vizuális megjelenéssel, azaz a gombok, ikonok és a grafikai elemek kinézetével és elrendezésével foglalkozik. A két terület szorosan együttműködik a felhasználóközpontú termék létrehozásában.

### Prototipizálás
A prototípus-készítés során a tervezett funkciók vagy a teljes felület interaktív, de még nem végleges változatát hozzuk létre. A prototípusok lehetnek alacsony részletességű drótvázak (wireframe) vagy nagy részletességű, a végleges termékhez nagyon hasonló vizuális tervek. Céljuk a koncepciók gyors tesztelése, a felhasználói visszajelzések korai gyűjtése és a fejlesztési kockázatok csökkentése, mielőtt a tényleges kódolás megkezdődne.

### Használhatósági tesztek
A használhatósági tesztek során valós felhasználókat kérünk meg, hogy végezzenek el előre meghatározott feladatokat a szoftverrel vagy annak prototípusával. A cél annak megfigyelése, hogy a felhasználók mennyire hatékonyan, eredményesen és elégedetten tudják használni a rendszert. A tesztek során feltárt problémák (pl. nehezen érthető funkciók, logikai buktatók) alapján finomítható a termék a jobb felhasználói élmény érdekében.



## Verziókezelés

### Git workflow útmutató

#### Mono-repository

* Mono-repository mintát alkalmazunk, ami azt jelenti, hogy minden termékünk egyetlen GIT repository-ban van tárolva. Ehhez az NX keretrendszert használjuk.

#### Mappák

* **apps**: Szolgáltatás alkalmazásokat tartalmaz \_service utótaggal és frontend alkalmazásokat \_frontend utótaggal. Ha nincs előtag, a mappa régebbi vagy potenciálisan örökölt projekteket tartalmazhat.
* **libs**: Megosztott könyvtárakat tartalmaz.

### Branching stratégia

#### Branch nevek előtagjai

* feature/: Specifikus feladatokhoz kapcsolódó branchek.
* epic/: Nagyabb fejlesztésekhez nyitott branchek, amelyek egy projektcímkével ellátott epichez kapcsolódnak.
* hotfix/: Hibajavításokhoz használt branchek, a master branchből származtatva.
* release/: Kiadásokhoz használt branchek, a develop branchből származtatva.

#### Branch származtatás

* Az epic branch a develop branchből származik.
* A feature branchek a develop vagy az epic branchből származnak.
* A release branchek a develop branchből származnak.
* A hotfix branchek a master branchből származnak.

#### Rebase

A feature branchekben rebase módszert alkalmazunk.

**1. Checkout feature branch:**
```bash
git checkout <feature branch>
```

**2. Commitok squasholása:**
```bash
git rebase -i HEAD~<saját commitok száma>
```

**3. Squasholt feature branch pusholása:**
```bash
git push --force-with-lease
```

**4. Forrás branch checkout és pull:**
```bash
git checkout <epic branch vagy develop>
<br>git pull
```

**5. Feature branch checkout és rebase:**
```bash
git checkout <feature branch>
git rebase <epic branch vagy develop>
git push --force-with-lease
```

> Ha van egy szülő branched, ami nem a develop (például epic/...), akkor a feature branchedet arra kell rebase-elned! Előtte pedig a szülő branchedet kellene rebase-elned a develop-ra.

### Feature branch életciklusa

#### Branch létrehozása

1. Új funkció esetén a branch az epic branchből jön létre. Ha nincs epic branch, akkor a develop branchből.
2. A branch nevének tartalmaznia kell a feature/ előtagot és a megfelelő issue azonosítót. Példa: feature/SW-80-single-book-upload.

**_8.3.1.1. Wip pr_**

3. Az első push után létre kell hozni egy pull requestet (PR). A címnek tartalmaznia kell a WIP előtagot, hogy megakadályozzuk a merge-elést, amíg a munka folyamatban van.
4. Az issue azonosítót a PR címében is fel kell tüntetni, hogy az automatizálás összekapcsolhassa a PR-t a hozzá tartozó issue-val.

**_8.3.1.2. Review_**

1. Ha a PR készen áll a review-ra, a WIP előtagot el kell távolítani.
2. Legalább egy kollégát és a csapatvezetőt is be kell állítani review-erként.
3. Amikor a review-er változtatásokat kér a PR-on (kommentek hozzáadásával a Gitea-ban): a. a PR szerzőjének el kell végeznie ezeket a változtatásokat és minden egyes kommentet meg kell oldania. b. a PR szerzőjének újra review-t kell kérnie a review-erektől, miután: i. további változtatásokat végzett a PR kezdeti jóváhagyása után. ii. javította a kért változtatásokat.
4. A PR csak akkor merge-elhető, ha: a. a CI/CD pipeline sikeresen lefutott. b. a review-erek jóváhagyták.

**_8.3.1.3. Merge_**

9. A PR merge-elésekor mindig squash merging\-et használj.

### Release branchek

Minden kiadáshoz release brancheket használunk, hogy a develop branch egy adott állapotát tudjuk kiadni, ami csak a szükséges változtatásokat tartalmazza.

#### Névkonvenció

A release/ előtagot az aktuális verzió előzi meg. Példa: release/rc0\_6.3.0

#### Merge stratégia

Amíg egy release branch-csel dolgozunk, "hotfix"-eket lehet alkalmazni rajta, de ezeket a változtatásokat szinkronizálnunk kell a develop\-pal a kiadás után:
* Sikeres kiadás után a master\-t rebase-elnünk kell a release branch-re, majd végül törölnünk kell azt.
* A master branch-et is szinkronizálni akarjuk a develop branch-csel, de ebben az esetben merge\-et kell használnunk rebase helyett, hogy elkerüljük a felesleges commitok alkalmazását és a develop branch sérülését (így a develop\-ból létrehozott folyamatban lévő brancheknek csak egy merge commitot kell rebase-elniük).

## Tesztelés

A tesztelés a szoftverfejlesztés kritikus része, amely biztosítja a kód minőségét, megbízhatóságát és a követelményeknek való megfelelést. A különböző tesztelési szintek együttesen alkotják a tesztpiramist.

### Unit test
Az egységtesztek a szoftver legkisebb, izolált részeit (pl. egy függvényt vagy metódust) ellenőrzik. Céljuk, hogy gyors visszajelzést adjanak a kód helyes működéséről. Mivel nem függenek külső rendszerektől, rendkívül gyorsan futnak, és a CI/CD pipeline alapvető részét képezik.

### Integration test
Az integrációs tesztek több komponenst vagy modult kapcsolnak össze, és azok együttes működését vizsgálják. Ellenőrzik például, hogy a szoftver helyesen kommunikál-e az adatbázissal, egy külső API-val vagy más belső szolgáltatásokkal. Lassabbak, mint az egységtesztek, de a rendszer komplexebb hibáit is képesek feltárni.

### End-to-end (E2E) test
Az E2E tesztek a teljes alkalmazást a felhasználó szemszögéből szimulálják. Egy teljes felhasználói útvonalat (pl. bejelentkezés, termék kosárba helyezése, fizetés) automatizálnak egy valósághű környezetben. Bár ezek a leglassabb és legbonyolultabb tesztek, a legnagyobb magabiztosságot adják a rendszer üzleti folyamatainak helyes működéséről.

## Üzemeltetés

### Hosting

### Pipeline

A CI/CD (Continuous Integration/Continuous Deployment) egy olyan gyakorlat, amely automatizálja a szoftverfejlesztés és \-kiadás folyamatait. A cél a kódváltozások gyors, megbízható és automatizált integrálása, tesztelése és telepítése.

#### Jenkins

A Jenkins egy nyílt forráskódú, széles körben elterjedt automatizálási szerver, amely a CI/CD folyamatok motorja lehet. Plugin-ek ezreivel bővíthető, így rendkívül rugalmasan képes támogatni a buildelési, tesztelési és telepítési folyamatok szinte bármilyen kombinációját. Konfigurálása általában egy Jenkinsfile\-ban, kódszerűen történik.

#### Gitlab CI/CD

A GitLab beépített, szorosan integrált CI/CD megoldása, amely lehetővé teszi a teljes szoftverfejlesztési életciklus kezelését egyetlen platformon. A pipeline-okat YAML formátumú .gitlab-ci.yml fájlban definiálják, ami a repository része. Ez megkönnyíti a verziókövetést és a pipeline-ok kezelését a kóddal együtt.

A Build, Test, Deploy pipeline a CI/CD folyamat gerince. Ez egy automatizált lépéssorozat, amely a kódváltozások repository-ba való feltöltésével indul. A **Build** lépés lefordítja a kódot és összeállítja a futtatható alkalmazást. A **Test** fázisban automatizált tesztek (unit, integration stb.) futnak le a minőségellenőrzés érdekében. Végül a sikeres tesztek után a **Deploy** lépés automatikusan telepíti az alkalmazást a célkörnyezetbe (pl. teszt, éles).

### Release menedzsment

A release menedzsment a szoftverkiadások tervezésének, ütemezésének, koordinálásának és telepítésének folyamata. Célja, hogy az új verziók zökkenőmentesen, minimális kockázattal és a felhasználók lehető legkisebb zavarásával kerüljenek éles környezetbe. Magában foglalja a verziókövetést, a kiadási stratégiák (pl. Canary, Blue-Green) alkalmazását és a kiadások utáni monitorozást.

#### Canary release
A kanári kiadás egy olyan telepítési stratégia, ahol az új szoftververziót először csak a felhasználók egy kis szegmensének teszik elérhetővé (ők a "kanárik"). A rendszer viselkedését és a felhasználói visszajelzéseket figyelve, ha minden rendben van, a kiadást fokozatosan terjesztik ki a teljes felhasználói bázisra. Ez a módszer csökkenti a hibás kiadásokkal járó kockázatot, mivel egy esetleges probléma csak a felhasználók kis részét érinti.

#### Blue-green deployment
A Blue-Green telepítés során két azonos, párhuzamosan futó éles környezetet tartanak fenn: a "Blue" a jelenlegi, stabil verziót futtatja, míg a "Green" a szoftver új verzióját. A telepítés során a bejövő forgalmat egy router segítségével egyszerűen átirányítják a Blue környezetről a Green-re. Ha az új verzióval probléma merül fel, a forgalom azonnal és zökkenőmentesen visszaállítható a Blue környezetre, minimalizálva a leállási időt és a kockázatot.

#### Feature flag
A feature flag (funkciózászló) egy szoftver fejlesztési technika, amely lehetővé teszi, hogy bizonyos funkciókat feltételesen aktiváljunk vagy deaktiváljunk anélkül, hogy új verziót kellene telepíteni. Ez lehetővé teszi a funkciók fokozatos bevezetését, A/B tesztelést és egyszerű rollback-et.

**Előnyei:**
* Funkciókat lehet tesztelni éles környezetben korlátozott felhasználók körén
* Gyors deaktiváció probléma felléptében (nem kell deploy)
* A/B tesztek futtatása könnyedén megvalósítható
* Fejlesztők függetlenül dolgozhatnak, az integráció könnyebb
* Üzleti döntések alapján lehet aktiválni/deaktiválni funkciókat

**Stratégiák:**
* **Release flags** - Új funkciót elrejthet, amíg kész nem áll
* **Experiment flags** - A/B tesztek és felhasználó tesztek
* **Ops flags** - Operatív döntések (terhelés csökkentés, cache kikapcsolás)
* **Permission flags** - Hozzáférés kontrolálása felhasználócsoportoknak
### Monitoring

Az üzemeltetés és monitoring célja a szoftver stabil és megbízható működésének biztosítása az éles környezetben. Magában foglalja a rendszer állapotának folyamatos figyelését, a hibák proaktív észlelését és elhárítását, valamint a teljesítmény optimalizálását.

#### Megfigyelhetőség
A megfigyelhetőség (observability) egy rendszer azon képessége, hogy a külső kimenetei (logok, metrikák, trace-ek) alapján megérthető legyen a belső állapota. Nem csupán a "mi romlott el?" kérdésre ad választ, hanem a "miért?"-re is, segítve a komplex, elosztott rendszerek hibakeresését.

#### Naplófájlok

Az általános naplófájlok a szoftver működésének nyomon követésére és hibakeresésre szolgálnak. Ezek rögzítik az alkalmazás eseményeit, hibáit, figyelmeztetéseit és egyéb diagnosztikai információkat.

A naplófájlok elsődleges céljai:

* **Hibakeresés** - Problémák diagnosztizálása és elemzése
* **Teljesítményfigyelés** - Rendszer teljesítményének monitorozása
* **Üzemeltetési információ** - Alkalmazás működésének követése
* **Fejlesztői támogatás** - Kód viselkedésének megértése
* **Rendszer-terhelés elemzése** - Erőforrás-használat nyomon követése

A naplófájlokban soha ne szerepeljenek érzékeny információk:

* **Jelszavak és API kulcsok** - Titkos hitelesítési adatok
* **Személyes adatok** - Neveik, e-mail címek, telefonszámok
* **Fizetési információk** - Bankkártya számok, tranzakciós adatok
* **Üzleti titkok** - Vásárlói adatok, szerződéses információk
* **Biometrikus adatok** - Ujjlenyomatok, arcfelismerési adatok

**Ajánlás:** Maszkírozz érzékeny adatokat a naplóban (pl. `***` vagy `[REDACTED]`)

A naplófájlok kezelésének legjobb gyakorlatai:

* **Méret alapú rotáció** - Fájl eléri az X MB-ot → új fájl
* **Idő alapú rotáció** - Napi/heti/havi ciklus
* **Tömörítés** - Régi logok ZIP/GZIP formátumba
* **Archiválás** - Hosszú távú tárolás külön helyre
* **Törlési politika** - X hónap után végleges törlés

#### Megvalósítás

* **EFK Stack:** Az EFK (Elasticsearch, Fluentd, Kibana) stack egy népszerű, nyílt forráskódú megoldás a logok központi gyűjtésére, feldolgozására és vizualizálására. A **Fluentd** összegyűjti a logokat különböző forrásokból, az **Elasticsearch** egy kereshető indexet épít belőlük, a **Kibana** pedig egy webes felületet biztosít a logok böngészéséhez, elemzéséhez és dashboardok készítéséhez.
* **Loki:** A Grafana Labs által fejlesztett Loki egy horizontálisan skálázható, költséghatékony log aggregációs rendszer. A Prometheus által inspirált megközelítéssel csak a logok metaadatait (címkéit) indexeli, magát a log szövegét nem. Ezáltal rendkívül hatékony tárolást és gyors keresést tesz lehetővé, különösen a Grafana-val integrálva.

Az **EFK Stack** (Elasticsearch, Fluent, Kibana) egy népszerű megoldás a logok központi gyűjtésére:

* **Elasticsearch** - Elosztott kereső- és analitikai motor
  * Gyors szöveges keresés
  * Valós idejű indexelés
  * Magas rendelkezésre állás

* **Fluent** (Fluentd) - Naplófeldolgozó és -továbbító
  * Több forrásból gyűjt logokat
  * Szűrés és átalakítás
  * Flexibilis routing

* **Kibana** - Vizualizációs és analitikai felület
  * Dashboard készítés
  * Logok böngészése és keresése
  * Valós idejű monitorozás

#### Audit trail

Az audit trail (auditnapló) egy olyan naplózási mechanizmus, amely időrendi sorrendben rögzíti a rendszerben bekövetkező eseményeket és változásokat (munkafolyamatokba rendezve). Célja a felhasználói és rendszertevékenységek nyomon követhető és ellenőrizhető módon történő dokumentálása.

##### Célok és előnyök

A fő célok a következők:
* **Nyomon követhetőség** - Felhasználói és rendszertevékenységek rögzítése
* **Biztonság és megfelelőség** - GDPR, ISO27001, PCI-DSS, NIS2 szabványok betartása
* **Hibaelhárítás és incidenskezelés** - Gyors problémamegoldás

Az előnyök közé tartozik:
* Átláthatóság a rendszer működésében
* Adatintegritás biztosítása
* Megelőzhető csalás és jogosulatlan módosítások
* Váratlan viselkedés azonosítása

##### Jogi követelmények

Több szabvány és irányelv is előírja az auditnaplózást:

* **ISO 27001 (Információbiztonsági Irányítási Rendszer - ISMS)** - Előírja a naplózást és a monitorozást, az auditnaplónak sértetlennek és hozzáférhetőnek kell maradnia.
* **PCI DSS (Payment Card Industry Data Security Standard)** - Részletes felhasználói műveletnaplózás, naplófájlok titkosítása, manipuláció elleni védelem, legalább egyéves megőrzés (három hónapnak hozzáférhetőnek kell lennie).
* **NIS 2 (Hálózati és Információbiztonsági Irányelv 2)** - Biztonsági események naplózása és monitorozása (hatályos: 2024. október 18-tól). Segíti a biztonsági incidensek gyors azonosítását és jogosulatlan hozzáférések megelőzését.

##### Auditnapló vs. hagyományos napló

| Szempont | Auditnapló | Hagyományos napló |
|----------|-----------|------------------|
| **Cél** | Biztonság, megfelelőség, kritikus változások | Hibakeresés, teljesítménymonitorozás |
| **Hatókör** | Felhasználói/rendszer műveletek, érzékeny adatok módosítása | Információs üzenetek, hibák, alkalmazásviselkedés |
| **Megőrzés** | Hosszú ideig, jogi követelmények alapján | Korlátozott ideig, teljesítményi igények alapján |
| **Struktúra** | Magasan strukturált, részletes metaadatokkal | Strukturálatlan vagy félig strukturált (JSON, szöveg) |

##### Az auditnapló tartalma

Az auditnaplónak a következő kérdésekre kell választ adnia: **Ki? Mit? Mikor? Hol?**

Az alapvető entitások a következők:

* **Level** - A napló szintje (pl. INFO, WARN, ERROR)
* **CreatedAt** - A naplóbejegyzés időbélyege
* **TraceId** - A munkafolyamat egyedi azonosítója
* **Workflow Name** - A munkafolyamat neve
* **User** - A felhasználó adatai (ID, Email)
* **Resource** - Az erőforrás adatai (EntityName, EntityID)
* **Operation** - A művelet adatai (Action, Changes - Previous, Current)
* **Metadata** - Metaadatok (UserAgent, GeoLocation)

##### Nyomkövetés (tracing)

**_TraceId_**

A **TraceID** egy egyedi azonosító, amely egy kérés vagy tranzakció teljes életciklusát követi nyomon egy elosztott rendszerben. Lehetővé teszi a kapcsolódó naplók és események összekapcsolását.

* **Formátum**: UUID
* **Generálás**: A munkafolyamat belépési pontján
* **Átvitel**: Fejlécekben (HTTP és AMQP) - `X-Trace-Id`
* **Automatikus továbbítás**: Minden belső kéréssel
* **Kereshetőség**: Teljes mértékben kereshető

**_SpanID_**

A **SpanID** egy egyedi azonosító, amely egy adott műveletet vagy tranzakciós egységet képvisel egy elosztott rendszeren belül.

* Míg a TraceID a teljes kérésfolyamatot követi nyomon
* A SpanID egy adott lépést vagy komponens-végrehajtást azonosít
* Egyetlen nyomvonal több spant is tartalmazhat
* Hierarchikusan vagy szekvenciálisan strukturálhatók

##### Implementáció

**_Technológiák_**

* **Fluent Bit** - Naplófeldolgozó és -továbbító
* **OpenSearch** - Elosztott, RESTful kereső- és analitikai motor
* **Kibana** - Adatvizualizációs műszerfal az OpenSearch-höz

**_Opensearch kulcsfogalmai_**

* **Cluster** - Több OpenSearch csomópontból álló rendszer
* **Node** - Az OpenSearch egy példánya, amely a klaszter része
* **Index** - Logikai egység, amely adatokat tárol (hasonlóan egy relációs adatbázis táblájához)
* **Shard** - Egy index több részre osztása a skálázhatóság érdekében
* **Document** - Egy indexen belül tárolt egyedi adatobjektum (hasonlóan egy relációs adatbázis sorához)

#### Metrikák
A metrikák numerikus adatok, amelyeket a rendszer teljesítményéről, erőforrás-használatáról (CPU, memória) és viselkedéséről gyűjtünk idősoros formában. A metrikák segítenek a trendek elemzésében, a teljesítményproblémák azonosításában és a kapacitástervezésben.
* **Prometheus:** A Prometheus egy nyílt forráskódú, idősoros adatbázis alapú monitoring és riasztási rendszer. Pull-alapú modellt használ, azaz periodikusan lekérdezi a metrikákat a monitorozott szolgáltatásoktól (endpointokról). Erőssége a nagy teljesítmény, a hatékony tárolás és a PromQL nevű, kifejező lekérdezőnyelv, amely komplex analízist és riasztási szabályok definiálását teszi lehetővé.
* **Grafana:** A Grafana egy nyílt forráskódú analitikai és vizualizációs platform, amely lehetővé teszi különböző adatforrások (pl. Prometheus, Loki, Elasticsearch) adatainak lekérdezését, elemzését és gyönyörű, interaktív dashboardokon való megjelenítését. A metrikák és logok vizualizálásának központi eszköze.

#### Riasztások
A riasztások proaktívan értesítik az üzemeltető csapatot, ha a rendszerben előre definiált küszöbértékeket meghaladó vagy abnormális események történnek. A cél a problémák gyors észlelése és a beavatkozás, még mielőtt a felhasználók észlelnék a hibát. A riasztásokat általában a Prometheus (Alertmanager) vagy a Grafana segítségével konfigurálják.

## Dokumentáció

A dokumentáció célja, hogy a csapat munkájához kapcsolódó tudás rendezett, könnyen elérhető és naprakész formában legyen kezelve. A dokumentumok tárolása és frissítése történhet különböző vállalati eszközökben – például Confluence-ben, Google Drive-ban, Figma-ban – A lényeg, hogy minden releváns anyag központilag visszakereshető legyen, és a csapat számára egyértelmű helyen található legyen.

A dokumentáció frissességét általában a rendszerben jelzett utolsó módosítás dátuma határozza meg. Ennek alapján három lejárati kategória különíthető el:

* **Top Priority** – Gyorsan változó, napi működéshez szükséges dokumentumok. Ezek frissítését körülbelül 30 naponta ajánlott ellenőrizni.
* **Normál** – Olyan tartalmak, amelyek idővel elavulhatnak, de nem tartalmaznak kritikus információt. Ezeknél kb. 180 napos felülvizsgálati ciklus az általános.
* **Non-expire** – Múltbeli fejlesztések, történeti anyagok, amelyek nem igényelnek aktualizálást.

Amennyiben a szervezet olyan eszközt használ, mint a Better Content Archiving, a rendszer automatikusan jelölheti a dokumentumok állapotát (például: lejárt, archíválásra jelölt, soha le nem járó). A dokumentumok karbantartása a dokumentum tulajdonosának feladata, de más felhasználók is jelezhetik, ha egy anyag elavult vagy törlésre érett.

A dokumentációhoz különféle sablonok is használhatók (például általános oldal, gyűjtőoldal, fejlesztési dokumentációs sablon), amelyek segítik a konzisztens felépítést: címsorstruktúra, dokumentumcél, tartalomjegyzék, kategóriacímkék, automatikusan generált listák és frissítési információk.

A lényeg: a dokumentáció legyen átlátható, egységes felépítésű, visszakereshető, és olyan rendszerben tárolt, amely támogatja a rendszeres karbantartást és a lejárati logikát.

## Linkek

*   Alertmanager
*   C
*   Elasticsearch
*   Fluentd
*   Git
*   Gitea
*   GitLab
*   Go
*   Grafana
*   Hetzner Development Infrastructure
*   Hotjar
*   JIRA
*   Jenkins
*   Kibana
*   Loki
*   Mixpanel
*   NX
*   OpenAPI
*   OpenSearch
*   Pest
*   PHP
*   Prometheus
*   Pydantic
*   Python
*   Rust
*   TypeScript
*   YouTrack
