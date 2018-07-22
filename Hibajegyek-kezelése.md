A rendszer egyik legfontosabb célja, hogy segítsen kezelni a Végfelhasználói kéréseket, megkönnyítve ezzel azok megtalálását, megoldását és egymáshoz való kapcsolódását.

# Hibajegy gyűjtők
Az osTicket a hibajegyeket listákba (nézetekbe) rendezi, amelyek kisebb csoportokban listázzák a jegyeket.

## Nyitott hibajegyek
A megynyitott hibajegyek, amelyek egy munkatárs válaszára várnak, a *Megnyitott* listában vannak elhelyezve.

## Megválaszolt hibajegyek
Azok a hibajegyek, amelyekre egy munkatárs már válaszolt, a *Válaszolt* sorban helyezik el. Itt azok a hibajegyek találhatók, amelyek a végfelhasználó válaszára várnak. Amikor egy végfelhasználó (vagy Tulajdonos vagy Együttműködő) új üzenetet küld, a hibajegy visszatér a *Megnyitott* sorba.

## Saját hibajegyek
A *Saját hibjegyek* tartalmazzák a nyitott jegyek listáját, amelyeket munkatársként rendeltek hozzá. Vagyis a közvetlenül az Önhöz rendelt hibajegyek, nem pedig egy csapat, amelyen részt vesz.

## Lejárt hibajegyek
A hibajegyek konfigurált esedékességi dátummal rendelkezhetnek, és rendelkezhetnek a kapcsolódó szolgáltatási szint megállapodással (SLA) is, amely automatikus esedékességi dátumot hoz létre. Ha az esedékesség határideje lejár, a hibajegyet megjelölik, mint késett, a figyelmeztető jelzést elküldik a megfelelő munkatársnak, és a hibajegy megjelenik a lejárt hibajegyek listában.

## Lezárt hibajegyek
A *Lezárt hibajegyek* listában szereplő hibajegyek a megoldott vagy lezárt hibajegyeket tartalmazzák. Ha a lezárt hibajegyet újra megnyitják, akkor visszatér a nyitott hibajegyek listába.

# Keresés
A jegyeket tartalmazó sorok tartalmaznak egy alapvető keresőmezőt, amely a jegyek számának, valamint a végfelhasználó nevének és e-mail címének keresésére alkalmas. 
A bővebb keresési funkció segítségével a hibajegyekben sokkal rugalmasabb kritériumok alapján keresni:
  * Kulcsszó
  * Aktuális állapot
  * Aktuális felelős
  * Kategória és Részleg
  * Létrehozás dátuma
  * Egyéni mezők adatai