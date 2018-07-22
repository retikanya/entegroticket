End Users represent your customers or clients. After your help desk has be in operation for some time, your help desk is likely to have tens or hundreds of end users. To assist in managing them, osTicket is outfitted with a User Directory and Organization manger which can be used to find and organize your end users into smaller groups.

A végfelhasználók képviselik a cégeket vagy ügyfeleit. Miután a help desk egy ideje működik, a help desk-nek valószínűleg sok végfelhasználója lesz. 
Ahhoz, hogy segítséget nyújthasson nekik, biztosítani kell a Felhasználók  és Szervezetek kezelését. E feladatokvégzések kapcsán a végfelhasználókat kisebb csoportokba rendezheti.

# (Vég)Felhasználói lista
A ügyfélszolgálat minden hibajegyének minden tulajdonosa végfelhasználóként jelenik meg. A végfelhasználók elérhetők a Felhasználói könyvtárban. 
A könyvtár támogatja a keresést és a rendezést, hogy segítséget nyújtson a rendszer egyes végfelhasználói számára. 
A listából az egyes felhasználói rekordokat meg lehet tekinteni, amely lehetővé teszi a felhasználói profil információinak, jegyeinek, szervezetének és bejelentkezési (hitelesítési) információinak megtekintését és kezelését.

## Custom Data
Minden végfelhasználóhoz kapcsolódik egy "Kapcsolatfelvételi információ" űrlap. 
A végfelhasználói adatlaphoz további plusz mezőket kapcsolhatunk, amely lehetővé teszi tetszőleges adatok hozzárendelését és bevitelét az egyes végfelhasználók számára. 
A végfelhasználói rekordhoz társított egyéni adathalmazok szabálykritériumokként használhatják az új jegyek jegyszűrő rendszerét.

# Szervezetek
Minden végfelhasználó csak egy szervezethez tartozhat egyszerre, de természetesen a kapcsolat bármikor módosítható.
A szervezetek lehetővé teszik a végfelhasználók egyszerű csoportosítását logikai egységekké, 
amelyek általában a külső csoportok és szervezetek képviselői, amelyekhez tartoznak.

## Elsődleges kapcsolat
A szervezeteknek lehet egy vagy több elsődleges kapcsolattartója, amelyek az adott szervezet fő kapcsolattartói. 
Ezek az elsődleges kapcsolatok automatikusan együttműködő végfelhasználóként működnek az új jegyeken a céghez kapcsolt hibajegyeken.
Ez akkor hasznos, ha a Szervezet egyes tagjait (pl vezetőket), értesíteni kell a Szervezet bármely tagja által létrehozott hibajegyekről..

## Account Manager
A szervezetek kijelölhetnek egy munkatársat vagy csapatot, amelyhez a szervezet összes jegyét automatikusan hozzárendelik - ez lesz az Account Manager. 
Ez akkor lehet hasznos, ha egyetlen ügynököt vagy csapatot következetesen használnak, hogy támogatást nyújtson az adott szervezetek számára.

Az Account Manager az új hibajegyek riasztásának célpontja is lesz egyben, az új hibajegyek létrehozásakor. 
Ezt az automatikus hozzárendelés helyett használhatja, hogy a Fiókkezelőt figyelmeztesse az adott szervezet összes új hibajegyére.

## Egyéni adatok 
A végfelhasználókhoz hasonlóan, a szervezet mindegyikének van egy "Szervezetinformáció" űrlapja, 
és bármilyen további egyéni mező is csatolható. 
A szervezethez társított egyéni adatok szabálykritériumként használhatók az új jegyek jegyszűrő rendszerével.

## Email Domain
A szervezetek egy vagy több kapcsolódó e-mail tartományt is tartalmazhatnak. 
Amikor új végfelhasználók jönnek létre, és ha az e-mail domainje megfelel az egyik szervezeti e-mail domainnek, az újonnan létrehozott végfelhasználó automatikusan társul a szervezethez.

# Regisztráció és Authentikáció
Az osTicket számos konfigurációs lehetőséget kínál, amelyek lehetővé teszik a végfelhasználók számára a jegyekhez való hozzáférést.

## Regisztrációs módok
Jelenleg az osTicket ügyfél regisztrációjának hat módja van. 
A regisztrációkat a  *Regisztráció szükséges* és *Regisztrációs mód* kapcsolók szabályozzák az alábbiak szerint:

Regisztráció szükséges  | Regisztrációs mód  | Eredmény
-----------------------|----------------------|---------
Nem   | Nyilvános | Regisztráció ajánlott, de nem kötelező az új hibajegy nyitásához
Igen  | Nyilvános | Regisztráció és bejelentkezés szükséges az új hibajegyekhez
Nem   | Privát   | Bárki létrehozhat hibajegyet, de csak a munkatársak regisztrálhatják a céghez (accounts?)
Igen  | Privát   | Felhasználók csak meghívókon keresztül férhetnek hozzá
Nem   | Tiltott  | Senki nem regisztrálhat cégeket, de bárki létrehozhat új hibajegyeket (így működött a v1.9 előtt)
Igen  | Tiltott  | A portálon keresztül új hibajegyek nem hozhatók létre

## Jelszó reset

When registration of end users is not Disabled, they can be assigned a password — either by an Agent or one they setup and manage themselves. osTicket provides a password reset mechanism via email to allow end users to reset the password without requesting assistance from an Agent. However, Agents also have the capability to manually reset an end user's password.

Ha a végfelhasználók regisztrációja nincs letiltva, jelszóhoz rendelhető - akár egy ügynök, akár egy általuk beállított és kezelt. 
Az osTicket e-mailben jelszó-visszaállító mechanizmust biztosít, amely lehetővé teszi a végfelhasználók számára, 
hogy jelszót állítsanak vissza anélkül, hogy segítséget kérnének egy ügynöktől. 
Az ügynökök azonban képesek arra, hogy kézzel állítsák vissza a végfelhasználó jelszavát.

### Jelszó szabályok
Az osTicket nem visszafordítható jelszó kódolást használ a végfelhasználói jelszavak tárolására. 
Az eredeti jelszó visszaállítása senkinek nem lehetséges. Ha a jelszó elveszett, új jelszót kell beállítani. 
A jelszavak kódolása egy nagyon lassú hash algoritmussal történik, amely védelmet nyújt az erőszakos támadásokkal szemben.

**Fontos!** A jelszó továbbítása a végfelhasználó böngészője és a HTTP szerver között a titkosítás és kódolás nélkül történik. 
Ezért fontos a rendszer HTTPS (HTTP SSL-vel) alapú használata a bejelentkezési oldalon 
vagy a teljes webhelyen, így a jelszó véletlenszerűen nem kerül nyilvánosságra.

## Authentication Extensions
Az osTicket további csatlakoztatható hitelesítési rendszerek használatát is biztosítja. 
A beépített jelszó-hitelesítési rendszer mellett az LDAP-hitelesítést és az oAuth-hitelesítést is támogatja, 
amely támogatja a jelenlegi jelszókezelő rendszereket, például az LDAP, a Kerberos, 
a Microsoft® Active Directory és a Google Plus+ használatát végfelhasználói bejelentkezéseknél.

Továbbá, az osTicket támogatja az importálási adatokat az Ön távoli hitelesítési adatbázisaiból, így az olyan információk, 
mint a végfelhasználó neve, e-mail címe és más egyéni adatok, importálhatók, amikor a végfelhasználó első alkalommal jelentkezik be az ügyfélportálra.

## Vendégek
A rendszer mindig támogatja a vendég üzemmódban való működését, függetlenül a konfigurált regisztrációs módtól. 
Amikor a munkatársunk válaszol egy hibajegyre, vagy más automatikus levelezést küld a végfelhasználónak, egy hivatkozás elhelyezhető el az e-mail sablonban 
(alapértelmezés szerint ez benne található), amely lehetővé teszi a végfelhasználó számára, hogy közvetlenül hozzáférjen az adott jegyhez. 
Ez a hozzáférés engedélyezett, függetlenül attól, hogy regisztrálva van-e a felhasználó vagy sem, és függetlenül attól, hogy bejelentkezett-e vagy sem. 
Továbbá, a link egyetlen kattintással hozzáférést biztosít a jegyhez, anélkül, hogy a végfelhasználótól további információkat kérne.

## Hozzáférés a hibajegy száma és az email cím segítségével
Az osTicket lehetővé teszi a végfelhasználók számára, hogy felkeressék az ügyfélportált, és ellenőrizzék a jegy állapotát. 
Ez történhet anélkül is, hogy regisztrálna és bejelentkezne a portálra. 
A végfelhasználó megadhatja az e-mail címét és a jegy számát. Ezután a rendszer amennyiben az adott számú ticket az érintett felhasználóhoz van regisztrálva (email cím egyezik), 
egy hitelesítő e-mail-t küld az érintett címre a közvetlen elérést biztosító linkkel.

