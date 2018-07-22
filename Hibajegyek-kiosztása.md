# Hibajegyek kiosztása
Amikor egy hibajegyet hoz létre, az adminisztrációs beállítások alapján a jegyeket hozzárendelheti a szervezeti egységekhez (részlegek), csoportokhoz és/vagy munkatárshoz. Minden hibajegyet kötelezően egy részleghez rendelnek. A nem jegyzett jegyeket a munkatársaknak kézzel, hibajegyek igénylésével vagy válaszadással lehet kijelölni. A hibajegyek automatikusan hozzárendelhetők a kategória, a részleg beállítások és a hibajegyszűrők alapján.

## Részlegek
Az osTicket részlegei a szokásos szervezeti struktúrát követik; A munkatársak pontosan egy "elsődleges" részleghez rendelhetők, és a részlegeknek lehet egy menedzserük. A részlegek az oszTicket hozzáférés-vezérlés elsődleges meghatározói. A részlegek segítik a hibajegyek listájának megtekintésének szabályozását a felületen. A hibajegyeket csak egy részlegre lehet irányítani; azonban a hibajegyek áthelyezhetők a részlegek között a kezelés és a láthatóság megváltoztatására.

## Hibajegy kategóriák (témakörök)
A hibajegy kategória (témakörök) a támogatási kérelem jellegét határozza meg. A kategória segíti a hibajegyeket a részlegeknek kiosztani és prioritást meghatározni anélkül, hogy a végfelhasználónak kellene kiválasztania azokat. Ez a megoldás lehetővé teszi, hogy a hibajegyeket a belsõ információk kiadása nélkül lehessen felvenni és automatikusan kiosztani. Ennek eredményeképpen a végfelhasználóknak nem kell megérteniük a belső szervezeti felépítést vagy munkafolyamatokat, mielőtt benyújtanák a támogatási kérelmet.

A hibajegy kategóriák (témakörök) teljesen testreszabhatók és támogatják a fastruktúra kialakítását.

A hibajegy kategóriák (témakörök) választása mindig szükséges, amikor új jegyeket nyitunk akár az ügyfélportálon akár belülről. A hibajegy kategóriák (témakörök) társíthatók e-mail fiókokkal, és megadhatók a jegyek API-n keresztül történő létrehozásakor.

## Hibajegy szűrők
A létrehozott hibajegyeket a létrehozás előtt számos jegyszűrővel át lehet alakítani. Ez kiváló módja annak, hogy egy munkatársat, részleget vagy csapatot állítsanak be a hibajegyhez. A jegyszűrők olyan konfigurálható szabályok, amelyek ha megfelelnek bizonyos adatoknak a hibajegyen, (pl. a végfelhasználói adatok, a szervezeti adatok, a jegyadatok, az egyéni űrlapadatok stb.), akkor a fenti kritériumoknak megfelelő jegyek egy vagy több műveletet alkalmazhatnak, ideértve a jegy visszautasítását, egy adott részlegre történő átirányítást, egy adott munkatárshoz vagy csapathoz való hozzárendelést, a prioritás vagy az SLA beállítását, vagy ideértve akár egy automatizált válaszadást.

## Hozzárendelés
A hibajegyeket adott esetben egy munkatársnak és/vagy egy csapatnak automatikusan kioszthatjuk, amikor a jegyet a kiválasztott hibajegy kategória (témakör) beállításai alapján hozzák létre. Ezenkívül az automatikus hozzárendelést konfigurált jegyszűrővel is elvégezheti.

A hibajegyek bármikor áthelyezhetők más munkatársra vagy csapatra. Egy munkatárs magához vehet egy még nem kiosztott jegyet.
