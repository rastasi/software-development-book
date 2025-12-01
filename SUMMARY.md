# Szoftver termékfejlesztés - Összefoglaló

## Absztrakt

A szoftverfejlesztés iteratív, rugalmas és gyorsan skálázható folyamat. Az agilis módszertan (Scrum, Kanban), a backlog-kezelés, a DoR/DoD, a szoftverarchitektúra, a CI/CD, az UX-UI tervezés és a monitoring együttesen biztosítják a minőségi termékfejlesztést.

A hardver-szoftver különbség lényege: a szoftver gyorsan javítható ("omelet"), a hardver nem ("spacewalk"). A szoftver iterációkat tudatosan kell összehangolni a hardver lassabb ciklusaival.

---

## Projektmenedzsment

### PM eszközök és kommunikáció

PM eszközök (Trello, Jira, Redmine, YouTrack, ClickUp, Asana) segítik a feladatkezelést és riportolást. Kommunikációs csatornák (Google Workspace, Microsoft 365, Slack, Discord) biztosítják a csapatszintű együttműködést.

> Pro tip: szánjuk rá az időt a választásra, nézzünk videókat az adott termékről, használjuk ki az ingyenes trial időszakokat és próbáljuk ki, melyik áll a csapatnak leginkább kézre. Egy élő projektet átmigrálni egyik rendszerből a másikba nem lehetetlen, de költséges feladat.

> Pro tip: Ne próbáljuk meg a privát közösségi média fiókjainkat és azoknak üzenetküldőit ilyen célra használni. Ellehetetleníti a későbbi bővítést és teret ad a véletlen adatszivárgásnak (könnyű rossz helyre megosztani egy dokumentumot például)

### Alapfogalmak

**Projekt**: Időben behatárolt, egyedi célra irányuló tevékenységcsoport.

> Megjegyzés: Egy termék fejlesztését is hívhatjuk projektnek és a PM rendszerekben egy projektben kezelhetjük a termék teljes életciklusát, ugyanakkor lehetőségünk van egy termék nagyobb fejlesztési etapj-it külön projektként kezelni.

**Business**: A termék vízióját megfogalmazó személy(ek).

> Megjegyzés: Egy néhány fős startup csapat esetén elképzelhető, hogy a szoftvert kivitelező személy egyben a business része is. Azi ilyen kalapok meghatározása azonban segít a kommunikációban és a későbbi skálázódásban.

**Issue típusok**: Epic (gyűjtőkártya), Story (feature kérés), Task (alegység), Test, Bug, Spike (kutatás).

> Pro tip: Próbáljuk meg a lehető leginkább az Agile által előírt hámashoz (Epic-Story-Task) tartani magunkat és csak indukolt esetben térjünk el tőle. Gyakori hiba a kező projektmenedzsmentben a komplexitás felesleges növelése a feladattípusok túlszaporításával.

**Board**: Vizuális tábla a feladatok státuszának követésére (To Do, In Progress, Done). Külön board-ok lehetnek: Grooming, Implementation, Troubleshooting.

> Pro tip: Egy jó praktika lehet egy projektben külön board-ot tartani a tervezésnek (Grooming), kivitelezésnek (Implementation) és hibakezelésnek (Troubleshooting).

### DoR és DoD

**Definition of Ready (DoR)**: Ellenőrzőlista, hogy egy feladat bevehető-e a sprintbe.

**Definition of Done (DoD)**: Kritériumok, amelyeknek teljesülnie kell a "kész" státuszhoz (működő kód, tesztek, review, dokumentáció).

> Pro tip: Csak olyan pontot rakjunk a DoD dokumentációba amit valóban képesek is vagyunk betartani. A cél nem az, hogy papírforma szerint mintaprojektünk legyen, hanem az, hogy olyan ellenörzőlistánk legyen ami valóban segítséget nyújt a kódminőség javulásához.

> Megjegyzés: Az AC-t írhatja a projektmenedzser és a fejlesztő is, ez megegyezés kérdése.A Projektmenedzser azt írja le, "mit szeretnék látni", a fejlesztő pedig azt, hogy "így tudod letesztelni amit leprogramoztam".

### Ceremóniák

Daily standup, Grooming meeting, Sprintforduló, Retrospective meeting.

> Pro tip: Csak olyan meeting-et tartjunk meg, aminek érezzük az értelmét. Azért retrospektívet tartani hetente, hogy elmondhassuk, hogy mi agilisek vagyunk, puszta időpazarlás. Ahogy daily standup-ot is lehet, érdemes csak heti kétszer tartani, a többi napon pedig írásban egyeztetni. A csapatnak mérlegelnie kell, hogyan lesznek efektívek a megbeszélések és hogyan nem mennek a megvalósítás kárára.

### SDLC

Az SDLC (Software Development Life Cycle) szakaszai: követelményanalízis, tervezés, implementáció, tesztelés, telepítés, karbantartás. A folyamat: üzleti igények → UX/UI design → műszaki spec → grooming → prioritizálás → kódolás → tesztelés → kiadás → utókövetés.

> Pro tip: Mindig a valóságból induljunk ki! Egy pár hetes-hónapos csapatnak nincsenek kialakult SDLC folyamatai. Várjuk meg, míg kialakul egy rend és írjuk le. Ez után ezt a leírást rövid iterációkban változtatva változtathatunk, javíthatunk céges szokásainkon!

---

## Fejlesztés

### Technology Stack

A stack a nyelveket, keretrendszereket, adatbázisokat jelenti. Fontos: csapat szakértelme, közösségi támogatás, trendek.

> Pro tip: Egy termék programnyelvének megválasztása a cég CTO-jának talán legfontosabb döntése. Míg ügyes programozói praktikákkal keretrendszerek között lehetséges a migrálás, egyik nyelvről a másikra való átállás a termék teljes újraírását jelenti.

> Megjegyzés: A fenti példák erős általánosításnak tűnhetnek és természetesen adad üdítő kivétel is szép számmal.

> Megjegyzés: a szoftver startup-ok nagy része a termék platformjaként mobilapplikációval támogatott webalkalmazásokat mint SaaS terméket fejleszt.

### Termék architektúra

**Monolith**: Egyetlen kódbázis, egyszerűbb fejlesztés. Típusai: egyprocesszes, moduláris, elosztott monolit.

**Microservices**: Komponálhatóság, DDD, információelrejtés. Kihívások: komplexitás, költségek, csatolás.

> Pro tip:  Általános best practice, hogy az MVP monolitikus legyen, mert egyszerűbb, gyorsabb fejlesztést és könnyebb karbantartást tesz lehetővé. Mikroszolgáltatás-alapú architektúrával kezdeni a fejlesztést akkor érdemes, ha  kezdetektől fontos a magas terhelhetőség és skálázhatóság és a csapat rendelkezik a szükséges szakértelemmel a komplexebb rendszer kezeléséhez.

**SPA vs MPA**: SPA egyetlen HTML-oldal dinamikus frissítéssel (React, Vue, Angular). MPA külön oldalak szerverről (Django, Rails, Laravel).

> Pro tip: A réteg szeparációt kiválóan támogatja egy komplex rendszer esetén az SPA megközelítés. A megjelenítés és a logika így garantáltan elválik egymástól így a felhasználó interfészek részére erősen javallott. Ám olyan alacsony komplexitású és a felhasználó elé nem kerülő felületeken mint a backoffice interfészek, alkalmazhatunk MPA megközelítést. Például Ruby on Rails backend kiszolgálhat egy Vue alapú SPA frontend-et, ugyanakkor egy ActiveAdmin modullal egy backoffice-t.

### Program architektúrák

Rétegek (layers), DTO-k, Dependency Injection biztosítják az átlátható adatáramlást és modularitást.

> Pro tip: A fontos, hogy konzekvens és dokumentált elveink és megoldásaink legyenek. Nem szükségszerű, hogy Model-Repository-Service-Controller rétegződést használjunk, ha az adott nyelv adott keretrendszerében más a best practise. Ami számít, az a következetesség, hogy egységes képet mutasson a kódbázis.

---

## Minőségbiztosítás

**Tech debt**: Kompromisszumok felhalmozott költsége. **Refaktorálás**: Belső struktúra javítása külső viselkedés változtatása nélkül.

> Pro tip: Adjuk meg az időt a refaktorációnak. Ha kell, vonjunk be külső szakértőt, aki egy tisztább, skálázhatóbb irányba segít terelni minket. A gyakorlatban az MVP-ket NEM írjuk újra egy tőkebevonás és csapatbővítés után. Érdemes tehát úgy hozzáállni az MVP-hez, hogy azt fogjuk továbbvinni az exit-ig.

**Code review**: Kód átnézése beolvasztás előtt.

> Pro tip: A code review egy időigényes folyamat. Minél jobban dokumentált elvek szerint programozik a csapatunk, annál könnyebb a review is, mert csak a valós fejlesztésre: az adatstruktúrákra (model layer, DTO properties) és az üzleti logikára (service layer) kell fókuszálni.

**Pair programming**: Két fejlesztő együtt (driver + navigator).

> Pro tip: A szoftverzervezés és fejlesztés immáron több mint fél évszázados múltra tekint vissza. A tiszta, érthető és karbantartható kód hosszú távon mindig megtérül. A minél hamarabbi iterációkat kergetve nem hesegethetjük el a komplex rendszerek gondolatát és cserélhetjük fel quick&dirty megoldásokra.

---

## UX/UI tervezés

**Prototipizálás**: Wireframe-ek és kattintható prototípusok készítése tesztelésre.

> Pro tip: Ezen a ponton és csakis ezen a ponton megtehetjük, hogy egy kattintható prototípust mesterséges intelligencia segítségével hozunk létre (példul: Lovable). Ezt azonban semmiképp ne keverjük össze az MVP-vel. A jelenlegi LLM-ek nem képesek olyan kódminőségben komplex programokat előállítani, amelyek megbízhatóak, fenntarthatóak. Természetesen használhatjuk a programozáshoz a különböző AI tool-okat de csakis alapos átnézést követően engedjük be a bódosításokat kódbázis főáramába.

**Használhatósági tesztek**: Valós felhasználók tesztelnek előre meghatározott feladatokat.

---

## Verziókezelés

**Branch nevek**: feature/, epic/, hotfix/, release/ előtagok.

> Megjegyzés: Ahány ház, annyi szokás. Vannak cégek ahol a készítő felhasználónevét adják prefix-nek, máshol a fenti felsorláshoz hasonló előtagokat választanak de eltérő elnevezéssel (pl. feature helyett feat, hotfix helyett fix)

**Feature branch életciklus**: Létrehozás → WIP PR → Review → Merge (squash).

> Pro tip: Fontos megjegyezni, hogy ez csak egy módszer, nem aranyszabály. A saját igények szerinti workflow a működő workflow.

---

## Tesztelés

**Unit test**: Izolált részek gyors ellenőrzése.
**Integration test**: Komponensek együttes működése.
**E2E test**: Teljes felhasználói útvonalak szimulálása.

> Pro tip: Az automata tesztek megvalósítása valóban elengedhetetlen előfeltétele a gyors kiadásnak. A gondolat, hogy "majd minden kiadás előtt végignyomkodjuk, nem nincs idő tesztet írni" gyakori tévedés. A jó tesztlefedettség növeli a megbízhatóságot, felhasználóink kisebb eséllyel hagyják el a terméket, mondván, hogy "ez egy bugos vacak".

---

## Üzemeltetés

### Hosting

Kategóriák: self-hosted (saját/bérelt gép), bérelt VM, bérelt cloud, menedzselt cloud, provider-függő megoldások.

> Pro tip: Óvakodjunk a vendor-lock-in-től. Igyekezzünk olyan megoldásokat találni amik minden szolgáltatónál futnak, páldául valamilyen Kubernetes cluster-t. Különböző vendor-specific futtatókörnyezetek között költséges a mozgás, minden vendor-nak érdeke az, hogy náluk maradjunk, ezért nem könnyíti meg a helyzetünket.

### Pipeline (CI/CD)

Build → Test → Deploy automatizált lépéssorozat (Jenkins, GitLab CI/CD).

> Pro tip: Az MVP production-ba állítására egy egyszerű pipeline-ra mindenképp szükség van. A pipeline biztosítja a szabványosított release-eket, amikre a kezdeti időszakban valószínűleg gyakran szükség lesz. Válasszunk egyszerű, platformfüggetlen megoldást.

### Release menedzsment

**Canary release**: Új verzió kis szegmensnek először.
**Blue-green deployment**: Két párhuzamos környezet, gyors átváltás.
**Feature flag**: Funkciók feltételes aktiválása telepítés nélkül.

### Monitoring

**Megfigyelhetőség**: Logok, metrikák, trace-ek alapján a rendszer belső állapotának megértése.

**Naplófájlok**: EFK Stack (Elasticsearch, Fluentd, Kibana) vagy Loki a központi gyűjtéshez.

> Megjegyzés: Természetesen választhatunk más eszközket is. Ami fontos, hogy könnyen, gyorsan megjeleníthető metrikáink legyenek, amelyeket könnyen kezelhetnek a szoftverfejlesztéshez és devops-hoz kevésbé értő kollégák is.

**Audit trail**: Időrendi eseménynaplózás (Ki? Mit? Mikor? Hol?). TraceId és SpanId a nyomkövetéshez.

**Metrikák**: Prometheus + Grafana, Mixpanel felhasználói viselkedéshez.

**Riasztások**: Prometheus Alertmanager, Grafana Alerts, Sentry, Nagios.

---

## Dokumentáció

Központi, visszakereshető, naprakész dokumentáció. Lejárati kategóriák: Top Priority (30 nap), Normál (180 nap), Non-expire.

> Pro tip: A lényeg: a dokumentáció legyen átlátható, egységes felépítésű, visszakereshető, és olyan rendszerben tárolt, amely támogatja a rendszeres karbantartást és a lejárati logikát.
