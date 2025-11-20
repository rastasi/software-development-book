# 1. Szoftverfejlesztés

# 2. Absztrakt

A szoftverfejlesztés alapvetően iteratív, rugalmas és gyorsan skálázható folyamat. A fejezet bemutatja az agilis módszertant (Scrum, Kanban), a backlog-kezelés alapelveit, a DoR/DoD szerepét, a szoftverarchitektúra alapfogalmait, a CI/CD és automatizált tesztelési rendszerek működését, az UX-UI tervezés feladatait, valamint az üzemeltetés és monitoring folyamatát.

A Lean Hardware Startup szemlélet itt két módon egészíti ki a tananyagot:

## 2.1. Hardver-szoftver különbségek

* a szoftver „omelet”, a hardver „spacewalk”: a szoftver gyorsan, fájdalom nélkül javítható; a hardver nem.
* ezért a szoftver iterációk ritmusát tudatosan kell összehangolni a hardver lassúbb ciklusaival.

## 2.2. Validációs kultúra különbségei
* szoftvernél a Lean Startup teljes mértékben alkalmazható: gyakori kiadások, gyors A/B tesztek, elemzés.
* ez a fejezet kiemeli, hogyan lehet a szoftveres iterációt hozzáilleszteni a csapat egészének tanulási folyamatához.
A hallgatók megtanulják, hogy a szoftverfejlesztési folyamatok rugalmassága a startup működésének egyik legfontosabb versenyelőnye, ugyanakkor szigorú folyamatfegyelmet kíván, hogy a gyorsaság ne menjen a minőség rovására.

## 2.3. Kötelezően megjelenő fogalmak, kulcsszavak

* Szoftverfejlesztési életciklus
* Agilis fejlesztés, Scrum, Kanban
* Roadmap, Product backlog → Sprint backlog
* DoR \- Definition of Ready
* DoD \- Definition of Done
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

# 3. A szoftverfejlesztés életciklusa

A szoftverfejlesztési életciklus (Software Development Life Cycle \- SDLC) egy strukturált folyamat, amely a szoftver tervezésétől, fejlesztésétől és tesztelésétől a telepítésen át a karbantartásig terjed. A ciklus fő szakaszai a követelményanalízis, tervezés, implementáció, tesztelés, telepítés (deployment) és karbantartás. A modern, agilis megközelítések ezeket a szakaszokat rövid, iteratív ciklusokban ismétlik, lehetővé téve a rugalmas alkalmazkodást a változó igényekhez.

# 4. Agilis fejlesztési módszertanok

Az agilis szoftverfejlesztés egy iteratív megközelítés, amely a rugalmasságot, az ügyfél-együttműködést és a folyamatos fejlődést helyezi előtérbe. Két népszerű keretrendszer a Scrum és a Kanban, amelyek segítenek a csapatoknak hatékonyabban szállítani értéket.

## 4.1. Scrum

A Scrum egy olyan keretrendszer, amelyben a csapatok rövid, időkeretes iterációkban, úgynevezett sprintekben dolgoznak. A cél a folyamatos visszajelzés és a gyors alkalmazkodás. A Scrum csapatok meghatározott szerepkörökből állnak, amelyek segítik a munkafolyamat hatékonyságát.

### 4.1.1. Szerepkörök

* **Product Owner (Terméktulajdonos)**: Felelős a termék értékének maximalizálásáért. Meghatározza a fejlesztési irányt, priorizálja a feladatokat (a termék backlogban), és egyértelműen kommunikálja a termék vízióját. Feladatai:
  * A termékfejlesztés irányának meghatározása.
  * A fejlesztések priorizálása.
  * Mérföldkövek meghatározása.
  * A termék víziójának egyértelmű kommunikálása.
  * Részvétel a jegyek tisztázásában.
* **Scrum Master**: A Scrum folyamat facilitátora. Segíti a csapatot a Scrum elvek és gyakorlatok betartásában, elhárítja az akadályokat, és biztosítja a zökkenőmentes kommunikációt a csapat és a külső érdekelt felek között. Feladatai:
  * A kommunikáció elősegítése a technikai és nem technikai érdekelt felek között.
  * Az előre meghatározott agilis ceremóniák levezetése.
  * Akciópontok létrehozása a felmerülő problémákra vagy kérdésekre, és azok tisztázása az érintett felekkel.
  * Megbeszélések szervezése.
* **Developer (Fejlesztő)**: A fejlesztőcsapat tagjai, akik a sprint során a kiválasztott feladatokat megvalósítják. Ők felelősek a működő terméknövekmény leszállításáért a sprint végén. Feladatai:
  * Az ügyféligények technikai megvalósítása.
  * Funkciók, új kód implementálása, értékteremtés.
  * Hibák és bugok javítása.
  * Részvétel a technikai jegyek létrehozásában és naprakészen tartásában.
* **Client (Ügyfél/Stakeholder)**: Bár nem hivatalos Scrum szerepkör, az ügyfél vagy érdekelt fél az, aki a követelményeket megfogalmazza, és visszajelzést ad a termékről, szorosan együttműködve a Product Ownerrel. Feladatai:
  * Fejlesztések javaslata a termékhez.
  * A javaslatok rögzítése a projektmenedzsment eszközben.
  * A termék tesztelése és szükség esetén hibajelentések készítése.

### 4.1.2. Sprint ceremóniák

A ceremóniák elengedhetetlenek az együttműködési rendszerek kialakításához. A Scrum módszertanban a következő típusú megbeszéléseket használjuk:

#### 4.1.2.1. Planning
A Sprint Planning a sprint elején tartott megbeszélés, ahol a Product Owner bemutatja a legfontosabb backlog elemeket, a csapat pedig közösen kiválasztja és megbecsüli azokat a feladatokat, amelyeket a következő sprintben el tud végezni. Az eredmény a Sprint Backlog és a sprint célja.

#### 4.1.2.2. Daily Standup
* **Cél**: Általános állapotjelentés a csapat többi tagjának.
* **Gyakoriság**: Hetente kétszer.
* **Időtartam**: Maximum 30 perc.
* **Résztvevők**: Fejlesztők \+ Scrum Master.
* **Levezető**: Scrum Master.
* **Folyamat**: Minden csapattagnak 5 perce van, hogy megossza:
  * Min dolgozott a múlt héten.
  * Min fog dolgozni ezen a héten.
  * Milyen akadályokba ütközik.

#### 4.1.2.3. Grooming meeting

* **Cél**: Az Epicek és Story-k tisztázása, a pontos követelmények megfogalmazása és leírása a jegyben.
* **Gyakoriság**: Hetente 1-2 alkalommal.
* **Időtartam**: Maximum 1,5 óra.
* **Résztvevők**: Product Owner \+ Scrum Master \+ opcionálisan Fejlesztők.
* **Levezető**: Product Owner.
* **Folyamat**: Végigmegyünk a jegyeken, megbeszéljük, mit kell megvalósítani és mik az üzleti követelmények. Áttekintjük a Grooming boardon lévő jegyeket.

#### 4.1.2.4. Review (Sprint)
A Sprint Review a sprint végén tartott informális megbeszélés, ahol a fejlesztőcsapat bemutatja az elkészült terméknövekményt a stakeholdereknek. A cél a visszajelzések gyűjtése és a Product Backlog esetleges frissítése a tapasztalatok alapján.

#### 4.1.2.5. Retrospective
* **Cél**: A csapat teljesítményének és eszköztárának értékelése és javítása.
* **Gyakoriság**: Havonta (minden mérföldkő befejezése után).
* **Időtartam**: Maximum 1,5 óra.
* **Résztvevők**: Product Owner, Scrum Master \+ Fejlesztők.
* **Levezető**: Opcionális.
* **Folyamat**: A megbeszélés során mind a fejlesztőknek, mind az üzleti oldalnak lehetősége van hangot adni az elmúlt hónapban tapasztalt ingerekre adott reakcióiknak. A cél az, hogy konstruktívan azonosítsuk, mit csinált jól a csapat, milyen külső vagy belső, rajtunk kívül álló tényezők hátráltatták a haladást, vagy mely területeken lehet javítani. Ha egy probléma megoldására nincs egyértelmű javaslat, Akciópontot kell rögzíteni. Az Akciópont elvégzésének felelőssége a szerepkörtől és a probléma természetétől függően változik.

## 4.2. Kanban

A Kanban egy vizuális menedzsment módszer, amely a munkafolyamat optimalizálására és a folyamatos szállításra összpontosít. A cél a munka vizualizálása, a folyamatban lévő munka (WIP) korlátozása és a flow maximalizálása.

A csapat jelenlegi képességeihez igazodva a klasszikus Kanban módszertant használjuk, kiegészítve a mérföldkövek célként való kitűzésével. Az Implementációs táblán folyamatosan oldjuk meg azokat a jegyeket, amelyek a groomingon való átesés után az Open oszlopba kerültek. Egy mérföldkő befejezését egy Retrospektív megbeszélés követi.

### 4.2.1. Korlátozások (WIP Limits)

A Kanban egyik legfontosabb eleme a folyamatban lévő munka (Work in Progress \- WIP) korlátozása, ami segít elkerülni a túlterhelést és javítja a munka áramlását.

* **Under Grooming állapot**: maximum 2 jegy személyenként
* **In Progress állapot**: maximum 2 jegy személyenként
* **Mérföldkövek elérésének időkerete**: \~4 hét
* **Grooming megbeszélések**: heti 1-2 alkalommal


A dokumentum célja a termékfejlesztéssel kapcsolatos munkafolyamatok rögzítése, az eljárások lépésről-lépésre történő leírása. Jelenleg a projektmenedzsmentet támogató eszköz a YouTrack. A kialakított entitások a YouTrack adottságait használják ki, de az elvek és a munkafolyamatok általánosak és szoftverfüggetlenek.

## 4.3. Globális fogalmak

### 4.3.1. Projekt

A projekt a legfőbb alapegység számunkra. Minden projekt több issuet és boardot foglal magába. Minden projekthez egyedi mezőket rendelhetünk a feladatokhoz. Minden szoftverhez külön projektet hozunk létre, valamint egy globális projektet a több szoftverterméken átívelő funkciókhoz és problémákhoz.

### 4.3.2. Projektek

* **Product Development**: Ebben a projektben zajlik a termék fejlesztése, és ebben a dokumentumban a erre a projektre vonatkozó definíciókat és folyamatleírásokat értjük.
* **Management**: Ebben a projektben kezeljük a céginformációkat és a menedzsmenttől érkező folyamatokat információs céllal.

### 4.3.3. User (Felhasználó)

Az alkalmazás felhasználója, azaz az a személy, aki az alkalmazást használja.

### 4.3.4. Business (Üzleti oldal)

A termék vízióját és elvárásait megfogalmazó személy(ek), akiknek feladata a koncepciók, követelmények, nagy vonalakban felvázolt tervek és mérföldkövek meghatározása a fejlesztők számára.

### 4.3.5. Issue (Feladat)

Az Issue egy megoldandó feladatot jelöl. Van egy típusa és egy állapota, amely minden boardra jellemző. Ha egy Issue egy boardhoz van társítva, azt kártyának is nevezik.

#### 4.3.5.1. Issue típusok

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

### 4.3.6. Feature implementáció állapotai

Az Issue állapotai az implementációs boardon:
* **Open**: Nyitott jegy, még nem foglalkoztak vele.
* **In Progress**: A megoldás folyamatban van.
* **Parking**: Elkezdtünk rajta dolgozni, de félretettük, általában egy magasabb prioritású jegy miatt.
* **Blocked**: A jegy megoldása más jegyektől vagy külső tényezőktől való függőségek miatt nem lehetséges.
* **In Review**: Befejezett megoldással rendelkező jegy, amely felülvizsgálatra vár egy Merge Requesten keresztül.
* **In Test**: Befejezett és telepített megoldás, amely tesztelésre vár.
* **Closed**: A jegy megoldódott és lezárult.

### 4.3.7. Feature előkészítés állapotai

* **Not Relevant Yet**: Érintetlen jegy, amely a jelenlegi fejlesztési szakaszban még nem releváns.
* **Wait for Grooming**: A jelenlegi fejlesztési szakaszban releváns, megbeszélésre váró jegy.
* **Under Grooming**: Megbeszélés, tisztázás vagy kidolgozás alatt álló jegy.
* **Groomed**: Tisztázott/kidolgozott jegy.

### 4.3.8. Hibák állapotai

* **Reported**: Jelentett jegy, amellyel még nem foglalkoztak.
* **Incomprehensible**: Nem egyértelmű leírású jegy, amely tisztázást igényel.
* **In Progress**: Jelenleg megoldás alatt álló jegy.
* **Not Reproducible**: A jegyben jelentett hibát nem sikerült reprodukálni, vagy valamilyen más okból már nem reprodukálható.
* **Fixed**: A jegyet javították, de még nem ellenőrizték.
* **Closed**: Javított, ellenőrzött és lezárt jegy.

### 4.3.9. Roadmap

A Roadmap egy magas szintű, vizuális terv, amely bemutatja a termékfejlesztés hosszú távú irányát és a tervezett főbb funkciók, mérföldkövek kiadási ütemezését. Segít összehangolni az üzleti célokat a fejlesztési kapacitással, és kommunikációs eszköz a stakeholderek felé.

### 4.3.10. Backlogok

Minden olyan Issue, amely nem szerepel a boardon, a Backlogba kerül. A board felületén van lehetőség a backlog megnyitására és a jegyek áthelyezésére a boardra. A backlog minden boardhoz egyedi lekérdezések alapján működik, és ez a lekérdezés az igényeknek megfelelően módosítható.

### 4.3.11. Product Backlog

A Product Backlog egy priorizált lista, amely tartalmaz minden, a termékkel kapcsolatos követelményt, funkciót, javítást és feladatot. A Product Owner felelős a karbantartásáért. Ez a lista dinamikus, folyamatosan változik az üzleti igények és a piaci visszajelzések alapján.

### 4.3.12. Sprint Backlog

A Sprint Backlog a Product Backlogból kiválasztott elemek halmaza, amelyeket a fejlesztőcsapat a következő sprint során fog megvalósítani. A Sprint Planning során a csapat közösen állítja össze, és a sprint ideje alatt már nem bővíthető, csak a meglévő feladatok elvégzésére fókuszálnak.

### 4.3.13. Definition of Ready (DoR)

A DoR egy ellenőrzőlista, amely meghatározza, hogy egy User Story-nak vagy feladatnak milyen kritériumoknak kell megfelelnie ahhoz, hogy a csapat be tudja venni a sprintbe. Biztosítja, hogy a feladatok jól definiáltak, érthetőek és megvalósíthatóak legyenek, minimalizálva a sprint közbeni kérdéseket.

### 4.3.14. Definition of Done (DoD)

A Definition of Done (DoD) egy fogalom, amelyet az agilis szoftverfejlesztési módszertanokban, különösen a Scrumban használnak. Meghatározza azokat a kritériumokat, amelyeknek egy terméknövekménynek vagy felhasználói történetnek meg kell felelnie ahhoz, hogy teljesnek és kiadásra késznek tekintsék. A DoD segít biztosítani, hogy a fejlesztőcsapat, az érdekelt felek és az ügyfelek közösen értsék, mi minősül befejezett és magas minőségű munkának.

* A kód működik a helyi környezetben - A fejlesztő felelőssége, hogy a kód a saját gépén megfelelően működjön. Ez magában foglalja a szükséges infrastruktúra beállítását is.
* Az elfogadási kritériumok teljesültek - A fejlesztőnek biztosítania kell, hogy a feladat megfeleljen az aktuális JIRA jegyben rögzített összes elfogadási kritériumnak.
* A közös rétegszerkezet teljesült - A fejlesztőnek követnie kell a Backend Development Guideline és Frontend Development Guideline dokumentumokban leírtakat.
* A kapcsolódó OpenAPI definíciók megírva - A fejlesztő felelőssége, hogy az OpenAPI in layers dokumentációnak megfelelően elkészítse a szükséges OpenAPI definíciókat.
* A kapcsolódó Unit tesztek megírva - A fejlesztőnek a PHP testing/Pest útmutató alapján kell elkészítenie a unit teszteket.
* A kapcsolódó E2E tesztek megírva - A tesztelő feladata, hogy a funkcióhoz kapcsolódó end-to-end teszteket megírja.
* A kód felülvizsgálva - A vezető fejlesztőnek a GIT Workflow Guideline alapján felül kell vizsgálnia a kódot.
* A kapcsolódó unit tesztek átmentek a pipeline-on - A fejlesztő felelőssége, hogy a unit tesztek sikeresen lefussanak a CI/CD pipeline-on.
* A kapcsolódó E2E tesztek átmentek a pipeline-on - A fejlesztő felelőssége, hogy az end-to-end tesztek sikeresen lefussanak a CI/CD pipeline-on.
* A kód működik a fejlesztői környezetben (develop branch) - A fejlesztőnek biztosítania kell, hogy a kód a Hetzner Development Infrastructure\-nek megfelelően működjön a develop branchen.
* A kapcsolódó manuális tesztek teljesültek - A tesztelő feladata, hogy elvégezze a szükséges manuális teszteket.
* A dokumentáció frissítve - A fejlesztőnek a Document Maintenance útmutató alapján frissítenie kell a dokumentációt.

## 4.4. User Story

Egy rövid, egyszerű leírás egy funkcióról a felhasználó szemszögéből. A tipikus formátuma: "Mint egy \<felhasználó típus\>, szeretnék \<célt elérni\>, hogy \<értéket kapjak\>." A User Story segít a csapatnak a felhasználói igényekre fókuszálni.

## 4.5. Acceptance Criteria

Azok a konkrét, tesztelhető feltételek, amelyeknek egy User Story-nak teljesülnie kell ahhoz, hogy "kész"-nek (Done) minősüljön. Egyértelművé teszik a követelményeket, és alapot adnak a teszteléshez.

# 5. Feature Fejlesztési Életciklus

Ez a dokumentum leírja a SCRUM csapat számára, hogyan tervezhet és valósíthat meg egy új funkciót a szoftvertermékeinkben.

## 5.1. Résztvevők

* **Business**
* **SCRUM Team**
* **Product owner**
* **Engineering Team Lead**
* **Product Designer**
* **Developer**
* **Test Automation Expert**
* **DevOps Expert**

## 5.2. Életciklus

### 5.3.1. Specifikáció

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

## 5.3.2. Implementáció előkészítése

**Közös tervezési ülés és Grooming**

* **Leírás**: A SCRUM csapatnak át kell néznie a story-kat a Grooming előtt, és segítenie kell azok kiterjesztésében és tisztázásában a jobb megértés és a gördülékenyebb Grooming megbeszélés érdekében.
* **Felelős Személy**: SCRUM csapat
* **Kapcsolódó dokumentumok**: SCRUM Meeting Types | Grooming Meeting

**Prioritizálás**

* **Leírás**: A megbeszélt és időbecsült feladatokat a terméktulajdonosnak kell priorizálnia. Ebben a lépésben a terméktulajdonos dönti el, hogy a következő sprint tartalmazhatja-e a feladatot. A terméktulajdonos tájékoztatja a marketinget és kitölti a termékkiadási egyoldalast.
* **Felelős Személy**: Terméktulajdonos
* **Felülvizsgáló**: Üzlet
* **Kapcsolódó dokumentumok**: Product Release Process

### 5.3.3. Implementáció

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

### 5.3.4 Kiadás után

**Marketing**

* **Leírás**: A terméktulajdonos tájékoztatja a marketing csapatot, hogy a funkció elkészült.
* **Felelős Személy**: Üzlet
**Nyomon követés**
* **Leírás**: Ellenőrizze a Mixpanel és a Hotjar eredményeket, foglalja össze, és hozzon létre egy funkcióigényt (FR). Kezelje a BÉTA teszteket és a funkciózászlókat.
* **Felelős Személy**: Elsődleges: Terméktulajdonos, Másodlagos: Üzlet és Terméktervező

# 6. UX/UI tervezés

Az UX (User Experience) és UI (User Interface) tervezés célja, hogy a szoftver ne csak funkcionális, hanem könnyen használható, hatékony és élvezetes is legyen. Az UX a teljes felhasználói élményre fókuszál, beleértve a logikai felépítést és a felhasználói utakat, míg az UI a vizuális megjelenéssel, azaz a gombok, ikonok és a grafikai elemek kinézetével és elrendezésével foglalkozik. A két terület szorosan együttműködik a felhasználóközpontú termék létrehozásában.

## 6.1. Prototyping
A prototípus-készítés során a tervezett funkciók vagy a teljes felület interaktív, de még nem végleges változatát hozzuk létre. A prototípusok lehetnek alacsony részletességű drótvázak (wireframe) vagy nagy részletességű, a végleges termékhez nagyon hasonló vizuális tervek. Céljuk a koncepciók gyors tesztelése, a felhasználói visszajelzések korai gyűjtése és a fejlesztési kockázatok csökkentése, mielőtt a tényleges kódolás megkezdődne.

## 6.2. Usability Tests
A használhatósági tesztek során valós felhasználókat kérünk meg, hogy végezzenek el előre meghatározott feladatokat a szoftverrel vagy annak prototípusával. A cél annak megfigyelése, hogy a felhasználók mennyire hatékonyan, eredményesen és elégedetten tudják használni a rendszert. A tesztek során feltárt problémák (pl. nehezen érthető funkciók, logikai buktatók) alapján finomítható a termék a jobb felhasználói élmény érdekében.

# 7. A szoftverarchitektúra alapjai

A szoftverarchitektúra rétegekre bontása, az adattranszfer objektumok (DTO-k) és a dependency injection (függőséginjektálás) használata mind azt a célt szolgálja, hogy az adatáramlás átlátható és követhető legyen.

## 7.1. Rétegek (Layers)

A szoftverarchitektúrában a rétegek szétválasztása egy bevett gyakorlat. Különböző modellek léteznek, mint például a klasszikus Model-View-Controller (MVC), vagy a részletesebb, Domain-Driven Design (DDD) által inspirált modellek, mint az Entities \-> Use Cases \-> Interface Adapters \-> Frameworks & Drivers. A rétegekre bontásnak számos előnye van: a modulok könnyen "mockolhatóak" (szimulálhatóak), ami a tesztelést segíti; a kódbázis szervezettebbé válik; a struktúra fix és követhető lesz; a közös kódbázis kialakítását pedig a fix elnevezési konvenciók segítik. Minden réteg egy "fekete doboz", ami elrejti a belső implementációt, és csak a publikus interfészt teszi láthatóvá. Ez a modularitás, a könnyebb tesztelhetőség és a jobb karbantarthatóság alapja. A "Facade" service-ek (homlokzati szolgáltatások) tiszta interfészt biztosítanak több szolgáltatási osztályhoz egyszerre, lehetővé téve a kisebb és fókuszáltabb szolgáltatási osztályok létrehozását, az üzleti logika olvashatóságát, és csökkentve a privát segédfüggvények számát.
A döntések elhalasztása (Decision Postponement)
A rétegzett architektúra támogatja a "decision postponement" elvét, azaz a döntések elhalasztását, amíg elegendő információ áll rendelkezésre a legjobb választáshoz. Ez rugalmasságot biztosít a jövőbeli változásokhoz, jobb döntéseket eredményez a teljesebb információk alapján, költséghatékonyabb, mert elkerüli a felesleges fejlesztési erőfeszítéseket, és skálázhatóbbá teszi az architektúrát, amely a valós igényekkel együtt fejlődhet. Például általános megoldásokat hozhatunk létre, amelyek különböző felhasználási esetekkel működnek, vagy olyan repository osztályokat, amelyek nincsenek adatelérési technológiához kötve.

## 7.2. Adattranszfer Objektumok (DTOs)

A DTO-k (Data Transfer Objects) összetett adatstruktúrák szállítására, adatvalidációra, valamint a rétegek és szervizosztályok közötti tiszta be- és kimenet biztosítására szolgálnak. Segítenek elkerülni a "code smell"-eket, mint például a túl sok (háromnál több) bemeneti argumentumot vagy a tuple visszatérési értékeket. Implementációjuk nyelvenként változó: PHP-ban osztályok, TypeScriptben interfészek, Pythonban (Pydantic) osztályok, C-ben, Go-ban és Rustban pedig structok formájában valósulnak meg. A DTO-k átjáróként funkcionálnak a rétegek között, csak a szükséges adatokat továbbítják, csökkentve a "zajt" és segítve a fókuszt. Ahogy Robert C. Martin (Uncle Bob) mondja: "Keep the DTOs simple\!" (Tartsd a DTO-kat egyszerűnek\!).

## 7.3. Függőséginjektálás (Dependency Injection - DI)

A dependency injection (DI) egy olyan tervezési minta, amelynek célja a lazán csatolt komponensek létrehozása. A DI támogatja a "mocking"-ot, központi függőségi fát hoz létre, és könnyű hozzáférést biztosít a függőségekhez. Csökkenti a kódbázist ott, ahol beinjektáljuk a függőséget, és a függő osztálynak nem kell tudnia a függőség implementációjáról. A függőség példányosítása nem a függő osztály hatásköre. Uncle Bob szerint a DI a tiszta kód és a skálázhatóság egyik alapköve.

## 7.4. Félelmek és frusztrációk

Természetesen ezeknek a mintáknak vannak hátrányai is. A rétegek, DTO-k és a DI használata teljesítmény- és komplexitásbeli "overhead"-et (többletterhet) jelenthet, például a "boilerplate" kód (sablonkód) és a módosítási láncok miatt. Azonban, ahogy Uncle Bob mondja: "A kódot másoknak írjuk." Egy másik híres mondás szerint pedig: "A memória olcsóbb, mint a programozó órabére." A tiszta, érthető és karbantartható kód hosszú távon mindig megtérül.

## 7.5. Monolith

A monolit architektúra egyetlen telepítési egységként definiálható, ahol a rendszer minden funkcióját együtt kell telepíteni. Főbb típusai:
* **Egyprocesszes monolit:** A legelterjedtebb forma, ahol minden kód egyetlen processzben fut.
* **Moduláris monolit:** A kód különálló modulokból áll, de a telepítés továbbra is egységes. Ez lehetővé teszi a párhuzamos fejlesztést, de az adatbázis gyakran közös marad, ami nehezíti a későbbi szétválasztást.
* **Elosztott monolit:** Bár több szolgáltatásból áll, a rendszert mégis együtt kell telepíteni a szoros csatolások miatt. Ez a legrosszabb mindkét világból: az elosztott rendszerek komplexitását ötvözi a monolitok rugalmatlanságával.
A monolitok előnye az egyszerűbb telepítés, fejlesztői folyamatok és tesztelés. Kisebb csapatoknál vagy a fejlesztés korai szakaszában gyakran ez a legésszerűbb alapértelmezett választás.

## 7.6. Microservices

A mikroszolgáltatási architektúra a rendszert függetlenül telepíthető, kis, üzleti képességek köré szervezett szolgáltatások gyűjteményeként építi fel. A cél a rugalmasság, skálázhatóság és a gyorsabb, független fejlesztési ciklusok lehetővé tétele.
* **Elvek:**
  * **Komponálhatóság:** A funkcionalitás könnyen újrafelhasználható különböző kontextusokban.
  * **Domain-Driven Design (DDD):** A szolgáltatások határait az üzleti domain (pl. Bounded Context\-ek) mentén érdemes kialakítani a magas kohézió és laza csatolás érdekében.
  * **Információelrejtés:** Minden szolgáltatás elrejti a belső implementációs részleteit, és csak egy jól definiált interfészt (API) tesz közzé.
* **Kihívások (Fájdalompontok):**
  * **Komplexitás:** Az elosztott rendszerek természetéből fakadóan bonyolultabb a fejlesztői élmény, a tesztelés, a monitorozás, a hibakeresés és az adatkonzisztencia biztosítása.
  * **Költségek:** A megnövekedett infrastrukturális és üzemeltetési igények miatt a kezdeti költségek magasabbak lehetnek.
  * **Csatolás:** Különös figyelmet kell fordítani a csatolás típusaira (pl. el kell kerülni a Content Coupling\-ot), hogy a szolgáltatások valóban függetlenek maradjanak.

A mikroszolgáltatások nem minden esetben jelentenek ideális megoldást. Leginkább nagy, gyorsan növekvő rendszereknél, SaaS alkalmazásoknál és olyan szervezeteknél előnyösek, ahol több csapat dolgozik párhuzamosan.

## 7.7. Modularitás

A modularitás egy szoftverarchitekturális elv, amely a rendszert független, cserélhető és önálló egységekre (modulokra) bontja. Minden modul egy specifikus feladatot lát el, és jól definiált interfészen keresztül kommunikál a többi modullal. A modularitás növeli a kód újrafelhasználhatóságát, megkönnyíti a karbantartást és a párhuzamos fejlesztést, mivel egy-egy modul anélkül módosítható vagy cserélhető, hogy az a teljes rendszert érintené.

# 8. CI/CD és automatizáció

A CI/CD (Continuous Integration/Continuous Deployment) egy olyan gyakorlat, amely automatizálja a szoftverfejlesztés és \-kiadás folyamatait. A cél a kódváltozások gyors, megbízható és automatizált integrálása, tesztelése és telepítése.

## 8.1. Jenkins

A Jenkins egy nyílt forráskódú, széles körben elterjedt automatizálási szerver, amely a CI/CD folyamatok motorja lehet. Plugin-ek ezreivel bővíthető, így rendkívül rugalmasan képes támogatni a buildelési, tesztelési és telepítési folyamatok szinte bármilyen kombinációját. Konfigurálása általában egy Jenkinsfile\-ban, kódszerűen történik.

## 8.2. GitLab CI/CD

A GitLab beépített, szorosan integrált CI/CD megoldása, amely lehetővé teszi a teljes szoftverfejlesztési életciklus kezelését egyetlen platformon. A pipeline-okat YAML formátumú .gitlab-ci.yml fájlban definiálják, ami a repository része. Ez megkönnyíti a verziókövetést és a pipeline-ok kezelését a kóddal együtt.

## 8.3. Build, Test, Deploy Pipeline

A Build, Test, Deploy pipeline a CI/CD folyamat gerince. Ez egy automatizált lépéssorozat, amely a kódváltozások repository-ba való feltöltésével indul. A **Build** lépés lefordítja a kódot és összeállítja a futtatható alkalmazást. A **Test** fázisban automatizált tesztek (unit, integration stb.) futnak le a minőségellenőrzés érdekében. Végül a sikeres tesztek után a **Deploy** lépés automatikusan telepíti az alkalmazást a célkörnyezetbe (pl. teszt, éles).

# 9. Verziókezelés

## 9.1. GIT Workflow Útmutató

### 9.1.1. Mono-repository

* Mono-repository mintát alkalmazunk, ami azt jelenti, hogy minden termékünk egyetlen GIT repository-ban van tárolva. Ehhez az NX keretrendszert használjuk.

### 9.1.2. Mappák

* **apps**: Szolgáltatás alkalmazásokat tartalmaz \_service utótaggal és frontend alkalmazásokat \_frontend utótaggal. Ha nincs előtag, a mappa régebbi vagy potenciálisan örökölt projekteket tartalmazhat.
* **libs**: Megosztott könyvtárakat tartalmaz.
* **e2e**: End-to-end tesztcsomagokat tartalmaz.
* **infrastructure**: Infrastruktúra konfigurációs fájlokat tartalmaz.
* **database**: Adatbázis migrációs eszközöket (Liquibase) tartalmaz.

## 9.2. Branching Stratégia

### 9.2.1. Branch nevek előtagjai:

* feature/: Specifikus feladatokhoz kapcsolódó branchek.
* epic/: Nagyobb fejlesztésekhez nyitott branchek, amelyek egy projektcímkével ellátott epichez kapcsolódnak.
* hotfix/: Hibajavításokhoz használt branchek, a master branchből származtatva.
* release/: Kiadásokhoz használt branchek, a develop branchből származtatva.

### 9.2.2. Branch származtatás

* Az epic branch a develop branchből származik.
* A feature branchek a develop vagy az epic branchből származnak.
* A release branchek a develop branchből származnak.
* A hotfix branchek a master branchből származnak.

### 9.2.3. Rebase

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
git pull
```

**5. Feature branch checkout és rebase:**
```bash
git checkout <feature branch>
git rebase <epic branch vagy develop>
git push --force-with-lease
```

> Ha van egy szülő branched, ami nem a develop (például epic/...), akkor a feature branchedet arra kell rebase-elned! Előtte pedig a szülő branchedet kellene rebase-elned a develop-ra.

## 9.3. Feature Branch Életciklusa

### 9.3.1. Branch létrehozása

1. Új funkció esetén a branch az epic branchből jön létre. Ha nincs epic branch, akkor a develop branchből.
2. A branch nevének tartalmaznia kell a feature/ előtagot és a megfelelő issue azonosítót. Példa: feature/SW-80-single-book-upload.

#### 9.3.1.1. WIP PR

3. Az első push után létre kell hozni egy pull requestet (PR). A címnek tartalmaznia kell a WIP előtagot, hogy megakadályozzuk a merge-elést, amíg a munka folyamatban van.
4. Az issue azonosítót a PR címében is fel kell tüntetni, hogy az automatizálás összekapcsolhassa a PR-t a hozzá tartozó issue-val.

#### 9.3.1.2. Review

1. Ha a PR készen áll a review-ra, a WIP előtagot el kell távolítani.
2. Legalább egy kollégát és a csapatvezetőt is be kell állítani review-erként.
3. Amikor a review-er változtatásokat kér a PR-on (kommentek hozzáadásával a Gitea-ban): a. a PR szerzőjének el kell végeznie ezeket a változtatásokat és minden egyes kommentet meg kell oldania. b. a PR szerzőjének újra review-t kell kérnie a review-erektől, miután: i. további változtatásokat végzett a PR kezdeti jóváhagyása után. ii. javította a kért változtatásokat.
4. A PR csak akkor merge-elhető, ha: a. a CI/CD pipeline sikeresen lefutott. b. a review-erek jóváhagyták.

#### 9.3.1.3. Merge

9. A PR merge-elésekor mindig squash merging\-et használj.

## 9.4. Release branchek

Minden kiadáshoz release brancheket használunk, hogy a develop branch egy adott állapotát tudjuk kiadni, ami csak a szükséges változtatásokat tartalmazza.

### 9.4.1. Névkonvenció

A release/ előtagot az aktuális verzió előzi meg. Példa: release/rc0\_6.3.0

### 9.4.2. Merge stratégia

Amíg egy release branch-csel dolgozunk, "hotfix"-eket lehet alkalmazni rajta, de ezeket a változtatásokat szinkronizálnunk kell a develop\-pal a kiadás után:
* Sikeres kiadás után a master\-t rebase-elnünk kell a release branch-re, majd végül törölnünk kell azt.
* A master branch-et is szinkronizálni akarjuk a develop branch-csel, de ebben az esetben merge\-et kell használnunk rebase helyett, hogy elkerüljük a felesleges commitok alkalmazását és a develop branch sérülését (így a develop\-ból létrehozott folyamatban lévő brancheknek csak egy merge commitot kell rebase-elniük).

# 10. Tesztelés a szoftverfejlesztésben

A tesztelés a szoftverfejlesztés kritikus része, amely biztosítja a kód minőségét, megbízhatóságát és a követelményeknek való megfelelést. A különböző tesztelési szintek együttesen alkotják a tesztpiramist.

## 10.1. Unit Test
Az egységtesztek a szoftver legkisebb, izolált részeit (pl. egy függvényt vagy metódust) ellenőrzik. Céljuk, hogy gyors visszajelzést adjanak a kód helyes működéséről. Mivel nem függenek külső rendszerektől, rendkívül gyorsan futnak, és a CI/CD pipeline alapvető részét képezik.

## 10.2. Integration Test
Az integrációs tesztek több komponenst vagy modult kapcsolnak össze, és azok együttes működését vizsgálják. Ellenőrzik például, hogy a szoftver helyesen kommunikál-e az adatbázissal, egy külső API-val vagy más belső szolgáltatásokkal. Lassabbak, mint az egységtesztek, de a rendszer komplexebb hibáit is képesek feltárni.

## 10.3. End-to-End (E2E) Test
Az E2E tesztek a teljes alkalmazást a felhasználó szemszögéből szimulálják. Egy teljes felhasználói útvonalat (pl. bejelentkezés, termék kosárba helyezése, fizetés) automatizálnak egy valósághű környezetben. Bár ezek a leglassabb és legbonyolultabb tesztek, a legnagyobb magabiztosságot adják a rendszer üzleti folyamatainak helyes működéséről.

# 11. Fejlesztési gyakorlatok és minőségbiztosítás

A fejlesztési gyakorlatok és a minőségbiztosítás (Quality Assurance \- QA) olyan folyamatok és eszközök összessége, amelyek célja a szoftver minőségének folyamatos javítása és a hibák megelőzése. Ide tartoznak a kódolási szabványok, az automatizált tesztelés, a kódellenőrzés (code review) és a páros programozás, amelyek együttesen biztosítják, hogy a fejlesztés során a csapat magas minőségű, megbízható és karbantartható kódot állítson elő.

## 11.1. Code Review
A kódellenőrzés során egy vagy több fejlesztő átnézi egy kollégájuk által írt kódot, mielőtt az beolvasztásra kerülne a közös kódbázisba. A cél a hibák, logikai problémák, a kódolási szabványoktól való eltérések és a potenciális teljesítményproblémák kiszűrése. Ez a gyakorlat nemcsak a kód minőségét javítja, hanem a tudásmegosztást és a csapatszintű felelősségvállalást is elősegíti.

## 11.2. Pair Programming
A páros programozás egy agilis technika, ahol két fejlesztő dolgozik együtt egy munkaállomáson. Az egyikük, a "driver", írja a kódot, míg a másik, a "navigator", folyamatosan figyeli, ellenőrzi a munkát, és stratégiai iránymutatást ad. A szerepeket gyakran cserélik. Ez a módszer javítja a kód minőségét, csökkenti a hibák számát, és felgyorsítja a tudásmegosztást a csapaton belül.

# 12. Release menedzsment

A release menedzsment a szoftverkiadások tervezésének, ütemezésének, koordinálásának és telepítésének folyamata. Célja, hogy az új verziók zökkenőmentesen, minimális kockázattal és a felhasználók lehető legkisebb zavarásával kerüljenek éles környezetbe. Magában foglalja a verziókövetést, a kiadási stratégiák (pl. Canary, Blue-Green) alkalmazását és a kiadások utáni monitorozást.

## 12.1. Canary Release
A kanári kiadás egy olyan telepítési stratégia, ahol az új szoftververziót először csak a felhasználók egy kis szegmensének teszik elérhetővé (ők a "kanárik"). A rendszer viselkedését és a felhasználói visszajelzéseket figyelve, ha minden rendben van, a kiadást fokozatosan terjesztik ki a teljes felhasználói bázisra. Ez a módszer csökkenti a hibás kiadásokkal járó kockázatot, mivel egy esetleges probléma csak a felhasználók kis részét érinti.

## 12.2. Blue-Green Deployment
A Blue-Green telepítés során két azonos, párhuzamosan futó éles környezetet tartanak fenn: a "Blue" a jelenlegi, stabil verziót futtatja, míg a "Green" a szoftver új verzióját. A telepítés során a bejövő forgalmat egy router segítségével egyszerűen átirányítják a Blue környezetről a Green-re. Ha az új verzióval probléma merül fel, a forgalom azonnal és zökkenőmentesen visszaállítható a Blue környezetre, minimalizálva a leállási időt és a kockázatot.

# 13. Üzemeltetés és monitoring

Az üzemeltetés és monitoring célja a szoftver stabil és megbízható működésének biztosítása az éles környezetben. Magában foglalja a rendszer állapotának folyamatos figyelését, a hibák proaktív észlelését és elhárítását, valamint a teljesítmény optimalizálását.

## 13.1. Observability
A megfigyelhetőség (observability) egy rendszer azon képessége, hogy a külső kimenetei (logok, metrikák, trace-ek) alapján megérthető legyen a belső állapota. Nem csupán a "mi romlott el?" kérdésre ad választ, hanem a "miért?"-re is, segítve a komplex, elosztott rendszerek hibakeresését.

## 13.2. Naplófájlok

Az általános naplófájlok a szoftver működésének nyomon követésére és hibakeresésre szolgálnak. Ezek rögzítik az alkalmazás eseményeit, hibáit, figyelmeztetéseit és egyéb diagnosztikai információkat.

### 13.2.1. Célja

A naplófájlok elsődleges céljai:

* **Hibakeresés** - Problémák diagnosztizálása és elemzése
* **Teljesítményfigyelés** - Rendszer teljesítményének monitorozása
* **Üzemeltetési információ** - Alkalmazás működésének követése
* **Fejlesztői támogatás** - Kód viselkedésének megértése
* **Rendszer-terhelés elemzése** - Erőforrás-használat nyomon követése

### 13.2.2. Érzékeny adatok szűrése

A naplófájlokban soha ne szerepeljenek érzékeny információk:

* **Jelszavak és API kulcsok** - Titkos hitelesítési adatok
* **Személyes adatok** - Neveik, e-mail címek, telefonszámok
* **Fizetési információk** - Bankkártya számok, tranzakciós adatok
* **Üzleti titkok** - Vásárlói adatok, szerződéses információk
* **Biometrikus adatok** - Ujjlenyomatok, arcfelismerési adatok

**Ajánlás:** Maszkírozz érzékeny adatokat a naplóban (pl. `***` vagy `[REDACTED]`)

### 13.2.3. Rotáció

A naplófájlok kezelésének legjobb gyakorlatai:

* **Méret alapú rotáció** - Fájl eléri az X MB-ot → új fájl
* **Idő alapú rotáció** - Napi/heti/havi ciklus
* **Tömörítés** - Régi logok ZIP/GZIP formátumba
* **Archiválás** - Hosszú távú tárolás külön helyre
* **Törlési politika** - X hónap után végleges törlés

### 13.2.4. EFK Stack

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

## 13.3. Audit trail

Az audit trail (auditnapló) egy olyan naplózási mechanizmus, amely időrendi sorrendben rögzíti a rendszerben bekövetkező eseményeket és változásokat (munkafolyamatokba rendezve). Célja a felhasználói és rendszertevékenységek nyomon követhető és ellenőrizhető módon történő dokumentálása.

### 13.3.1. Célok és előnyök

A fő célok a következők:
* **Nyomon követhetőség** - Felhasználói és rendszertevékenységek rögzítése
* **Biztonság és megfelelőség** - GDPR, ISO27001, PCI-DSS, NIS2 szabványok betartása
* **Hibaelhárítás és incidenskezelés** - Gyors problémamegoldás

Az előnyök közé tartozik:
* Átláthatóság a rendszer működésében
* Adatintegritás biztosítása
* Megelőzhető csalás és jogosulatlan módosítások
* Váratlan viselkedés azonosítása

### 13.3.2. Jogi követelmények

Több szabvány és irányelv is előírja az auditnaplózást:

* **ISO 27001 (Információbiztonsági Irányítási Rendszer - ISMS)** - Előírja a naplózást és a monitorozást, az auditnaplónak sértetlennek és hozzáférhetőnek kell maradnia.
* **PCI DSS (Payment Card Industry Data Security Standard)** - Részletes felhasználói műveletnaplózás, naplófájlok titkosítása, manipuláció elleni védelem, legalább egyéves megőrzés (három hónapnak hozzáférhetőnek kell lennie).
* **NIS 2 (Hálózati és Információbiztonsági Irányelv 2)** - Biztonsági események naplózása és monitorozása (hatályos: 2024. október 18-tól). Segíti a biztonsági incidensek gyors azonosítását és jogosulatlan hozzáférések megelőzését.

### 13.3.3. Auditnapló vs. hagyományos napló

| Szempont | Auditnapló | Hagyományos napló |
|----------|-----------|------------------|
| **Cél** | Biztonság, megfelelőség, kritikus változások | Hibakeresés, teljesítménymonitorozás |
| **Hatókör** | Felhasználói/rendszer műveletek, érzékeny adatok módosítása | Információs üzenetek, hibák, alkalmazásviselkedés |
| **Megőrzés** | Hosszú ideig, jogi követelmények alapján | Korlátozott ideig, teljesítményi igények alapján |
| **Struktúra** | Magasan strukturált, részletes metaadatokkal | Strukturálatlan vagy félig strukturált (JSON, szöveg) |

### 13.3.4. Az auditnapló tartalma

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

### 13.3.5. Nyomkövetés (Tracing)

#### TraceID

A **TraceID** egy egyedi azonosító, amely egy kérés vagy tranzakció teljes életciklusát követi nyomon egy elosztott rendszerben. Lehetővé teszi a kapcsolódó naplók és események összekapcsolását.

* **Formátum**: UUID
* **Generálás**: A munkafolyamat belépési pontján
* **Átvitel**: Fejlécekben (HTTP és AMQP) - `X-Trace-Id`
* **Automatikus továbbítás**: Minden belső kéréssel
* **Kereshetőség**: Teljes mértékben kereshető

#### SpanID

A **SpanID** egy egyedi azonosító, amely egy adott műveletet vagy tranzakciós egységet képvisel egy elosztott rendszeren belül.

* Míg a TraceID a teljes kérésfolyamatot követi nyomon
* A SpanID egy adott lépést vagy komponens-végrehajtást azonosít
* Egyetlen nyomvonal több spant is tartalmazhat
* Hierarchikusan vagy szekvenciálisan strukturálhatók

### 13.3.6. Implementáció

#### Technológiák

* **Fluent Bit** - Naplófeldolgozó és -továbbító
* **OpenSearch** - Elosztott, RESTful kereső- és analitikai motor
* **Kibana** - Adatvizualizációs műszerfal az OpenSearch-höz

#### OpenSearch kulcsfogalmai

* **Cluster** - Több OpenSearch csomópontból álló rendszer
* **Node** - Az OpenSearch egy példánya, amely a klaszter része
* **Index** - Logikai egység, amely adatokat tárol (hasonlóan egy relációs adatbázis táblájához)
* **Shard** - Egy index több részre osztása a skálázhatóság érdekében
* **Document** - Egy indexen belül tárolt egyedi adatobjektum (hasonlóan egy relációs adatbázis sorához)

## 13.4. Metrics
A metrikák numerikus adatok, amelyeket a rendszer teljesítményéről, erőforrás-használatáról (CPU, memória) és viselkedéséről gyűjtünk idősoros formában. A metrikák segítenek a trendek elemzésében, a teljesítményproblémák azonosításában és a kapacitástervezésben.
* **Prometheus:** A Prometheus egy nyílt forráskódú, idősoros adatbázis alapú monitoring és riasztási rendszer. Pull-alapú modellt használ, azaz periodikusan lekérdezi a metrikákat a monitorozott szolgáltatásoktól (endpointokról). Erőssége a nagy teljesítmény, a hatékony tárolás és a PromQL nevű, kifejező lekérdezőnyelv, amely komplex analízist és riasztási szabályok definiálását teszi lehetővé.
* **Grafana:** A Grafana egy nyílt forráskódú analitikai és vizualizációs platform, amely lehetővé teszi különböző adatforrások (pl. Prometheus, Loki, Elasticsearch) adatainak lekérdezését, elemzését és gyönyörű, interaktív dashboardokon való megjelenítését. A metrikák és logok vizualizálásának központi eszköze.

## 13.5. Alerts
A riasztások proaktívan értesítik az üzemeltető csapatot, ha a rendszerben előre definiált küszöbértékeket meghaladó vagy abnormális események történnek. A cél a problémák gyors észlelése és a beavatkozás, még mielőtt a felhasználók észlelnék a hibát. A riasztásokat általában a Prometheus (Alertmanager) vagy a Grafana segítségével konfigurálják.

## 13.6. Log Management Stacks
* **EFK Stack:** Az EFK (Elasticsearch, Fluentd, Kibana) stack egy népszerű, nyílt forráskódú megoldás a logok központi gyűjtésére, feldolgozására és vizualizálására. A **Fluentd** összegyűjti a logokat különböző forrásokból, az **Elasticsearch** egy kereshető indexet épít belőlük, a **Kibana** pedig egy webes felületet biztosít a logok böngészéséhez, elemzéséhez és dashboardok készítéséhez.
* **Loki:** A Grafana Labs által fejlesztett Loki egy horizontálisan skálázható, költséghatékony log aggregációs rendszer. A Prometheus által inspirált megközelítéssel csak a logok metaadatait (címkéit) indexeli, magát a log szövegét nem. Ezáltal rendkívül hatékony tárolást és gyors keresést tesz lehetővé, különösen a Grafana-val integrálva.

# 14. Technikai adósság és refaktorálás

A technikai adósság (technical debt) a fejlesztés során hozott, tudatos vagy nem tudatos kompromisszumok (pl. egy gyors, de nem optimális megoldás választása) felhalmozódott "költsége". Hosszú távon ez a "kölcsön" kamatozik: nehezíti a karbantartást, lassítja az új funkciók fejlesztését és növeli a hibák kockázatát. A **refaktorálás** az a folyamat, amely során a kód belső szerkezetét javítjuk anélkül, hogy a külső viselkedése megváltozna. A refaktorálás a technikai adósság "törlesztésének" egyik legfontosabb eszköze, amely tisztábbá, érthetőbbé és könnyebben bővíthetővé teszi a kódot.

