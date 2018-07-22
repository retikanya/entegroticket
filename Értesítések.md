Az osTicket támogatja az automatikus üzenetek küldését mind a Végfelhasználók, mind az Munkatársak számára a jegy életciklusa során.

# Automatikus válaszadás a végfelhasználóknak
Az automatikus válaszadók engedélyezhetők, hogy a tájékoztassák a végfelhasználókat a hibajegyek életciklusa során. 
Engedélyezhetőek vagy letilthatók globálisan, de bármelyik részleg vagy hibajegy kategória (témakör) esetén is le lehetnek tiltva.

## Jegyek létrehozása során
Az Új hibajegy értesítő küldhető a Végfelhasználóknak, amikor új jegyet hoznak létre. Automatikus értesítést engedélyezhetünk a Végfelhasználók által létrehozott hibajegyekhez, valamint a belsőleg létrehozott jegyekhez.

## Végfelhasználói email beérkezése során
Az új üzenet értesítése akkor is küldhető, ha a végfelhasználók emailt küldenek létrehozandó hibajegyként vagy hibajegy tulajdonosként 
vagy együttműködő partnerként. A végfelhasználók levelezését "osCommerce" üzeneteknek nevezik; ezért a "New Message Autoresponse" név. 
Az üzenet visszaigazolásaként a hibajegyen résztvevők (a többi résztvevő, beleértve a hibajegy tulajdonosát is) 
automatikus választ kaphatnak. Amikor az automatikus választ küldjük a résztvevőknek, a help desk hasonlóan fog működni a legtöbb "emailben" levélben.

## Mennyiségi korlát értesítés
A mennyiségi korlát (Overlimit) értesítés automatikusan elküldhető a Végfelhasználóknak, ha elérik vagy meghaladják az egy Végfelhasználó által engedélyezett 
hibajegyek számát a rendszerben. Ez hasznos arra, hogy a végfelhasználó tudja, hogy több hibajegy nem adható fel addíg, amíg legalább az egyik megnyitott 
jegyet nem sikerül megoldani.


# Értesítések a Munkatársak számára
Riasztások és értesítések küldhetők a munkatársaknak is a jegyek életciklusa során zajló eseményekhez. 
Engedélyezhetőek vagy letilthatók globálisan, de bármely részleg szinten is le lehetnek tiltva.

Minden értesítés esetén a címzettek duplikálódhatnak, de a rendszer figyeli, hogy egy munkatárs ne kapjon ugyanazon eseményről a több értesítést 
(pl. egy részlegvezető is tagja a részlegnek).
Ezenkívül az esemény kiváltó munkatárs nem kapja meg a riasztást (pl. egy munkatárs belső megjegyzést tesz közzé, 
akkor enek a munkatársnak nem kerül elküldésre a belső figyelmeztetés).

## Részleg figyelmeztetések kiterjesztése
A részlegtagoknak küldött értesítések kiterjeszthetők a bővített hozzáférési csoporton keresztül hozzáféréssel rendelkező tagokra. 
Minden részlegnek van egy beállítása a "Címzettek" részlegszintre. Ha az "Részleg és a csoport tagjai" beállításra van állítva, 
azok a megbízottak, akik a hozzátartozó csoporton keresztül hozzáférnek a részleghez, szintén értesülnek a részleg 
tagjainak küldött figyelmeztetésekről.

## Értesítések a hibajegy tevékenységekhez

### Új hibajegy
Az Új hibajegy értesítés indul, amikor új hibajegyet hoznak létre. Engedélyezhető a Rendszergazdák, az Részlegvezető és/vagy a részleg tagjai számára. 
Abban az esetben, ha a jegyet automatikusan hozzárendeli egy munkatárshoz vagy egy csapathoz, akkor a részleg tagjai **nem kapják meg** az új hibajegyről az értesítést.

### Új üzenet
Az *Új üzenet* értesítést indul, amikor egy új üzenet érkezik a végfelhasználótól és egy meglévő jegyhez csatolódik. Engedélyezhető, hogy az utolsó válaszadónak (az utolsó válaszadónak), a részlegvezetőnek és/vagy az aktuálisan kijelölt munkatársnak kerüljön elküldésre.

### Új belső megjegyzés
A *Belső megjegyzés* értesítést indul, ha egy új belső megjegyzés kerül a jegyhez hozzáadásra. 
Engedélyezhető, hogy az utolsó válaszadónak (az utolsó válaszadónak), a részlegvezetőnek és/vagy az aktuálisan kijelölt munkatársnak kerüljön elküldésre.

### Hibajegy felelős hozzárendelés
A *Hibajegy felelős hozzárendelés* értesítés kerül elküldésre az újonan kijelölt munkatársnak, amikor hibajegyeket rendelnek hozzá. 
Engedélyezhető az újonnan kinevezett munkatárs, az újonnan kijelölt részleg vezetője és/vagy az újonnan kijelölt csapat tagjai számára kerüljön elküldésre.

### Hibajegy átadás
A *Hibajegy átadás* értesítés elküldésére kerül sor, amikor hibajegyet átadnak. Engedélyezhető a kijelölt munkatárs, részlegvezető és/vagy a kijelölt csapat tagjai számára kerüljön elküldésre.

### Lejárt hibajegy értesítés
A *Lejárt hibajegy* értesítés kerül elküldésre, amikor a jegy SLA időpontja lejár. 
Alapértelmezés szerint az adminisztrátorok e-mail értesítést kapnak. 
Engedélyezhető továbbá, hogy a kijelölt munkatárs, részlegvezető és/vagy a kijelölt csapat tagjai számára kerüljön elküldésre.

## Rendszer riasztások
Számos rendszerszintű figyelmeztetés küldhető az adminisztrátorok e-mail címre.

### System Errors
Ha *System Errors* lép fel, mint pl. Az e-mailek lekérése, mindig a rendszer adminisztrátorok e-mail címére kerülnek az értesítések.

### SQL Errors
Ha váratlan *SQL hibák* jelentkeznek, általában váratlan programozási hibák miatt az adminisztrátorok e-mail címére kerülnek az értesítések.

### Excessive login attempts
Ha az *munkatársak* és a *végfelhasználók* túlságosan sikertelenül hitelesítik magukat, az adminisztrátorok e-mail címére kerülnek az értesítések. 
Ez hasznos a hitelesített brute forcing és egyéb hitelesítési rendellenességek felderítésére.