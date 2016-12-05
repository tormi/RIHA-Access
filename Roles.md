# RIHA rollihaldus

spetsifikatsioon

v0.2, 05.12.2016

Sisukord

- [1 Käsitlusala](#1-k%C3%A4sitlusala)
- [2 Mõisted ja lühendid](#2-m%C3%B5isted-ja-l%C3%BChendid)
- [3 Olulised viited](#3-olulised-viited)
- [4 Rollihalduse põhimõtted ja disaini eesmärgid](#4-rollihalduse-p%C3%B5him%C3%B5tted-ja-disaini-eesm%C3%A4rgid)
- [5 Rollid](#5-rollid)
- [6 Protsessid (e kasutuslood)](#6-protsessid-e-kasutuslood)
- [6.1 Kasutaja autoriseerimine](#61-kasutaja-autoriseerimine)
- [6.2 Rollihalduri määramine](#62-rollihalduri-m%C3%A4%C3%A4ramine)
- [6.3 Rolli määramine](#63-rolli-m%C3%A4%C3%A4ramine)
- [6.4 Rolli RIHA HALDUR määramine]()
- [7 Õigused](#7-%C3%95igused)
- [8 Rollide ülekandmine vanast RIHAst](#8-rollide-%C3%BClekandmine-vanast-rihast)
- [Muutelugu](#muutelugu)

## 1 Käsitlusala

Dokument:

- modelleerib RIHAs kasutajatele antavaid rolle (käsitledes lühidalt ka õigusi)
- spetsifitseerib rollide esialgse nimekirja
- spetsifitseerib rollide ja õiguste haldusprotsessid (kasutaja lisamine, rolli andmine jms)
- spetsifitseerib sisulised üldnõuded rolli- ja õiguste halduse teostusele.

## 2 Mõisted ja lühendid

| mõiste | seletus |
|--------|---------|
| _RIHA kasutaja_, ka lihtsalt _kasutaja_  | inimene, kes kasutab RIHA kesksüsteemi (RIHA kesksüsteemi avalehe, kirjeldusmooduli või muu kasutajaliidest omava komponendi kaudu); samuti RIHA Rollihalduri (tarkvarakomponendi) inimkasutaja. Kasutaja ei tarvitse olla autenditud ega omada RIHAs rolle | 
| _esindusõigusega isik_ | asutuse vm juriidilise isiku esindamise õigust omav inimene; esindusõigus tehakse kindlaks päringuga Äriregistrisse |
| _roll_ | RIHA kasutajale omistatud roll |
| _õigus_ | RIHA kasutaja õigus teha RIHA mõnes komponendis mõnda toimingut; õigus on seotud ühelt poolt rolliga ja teiselt poolt toimingu objekti tüübiga, mõnel juhul ka konkreetse objektiga |
| _RIHA_ | Hajusa ülesehitusega, erinevaid funktsioone täitvatest komponentidest koosnev infosüsteem. RIHAs tehakse kättesaadavaks riigi infosüsteemi metaandmeid ja tehakse mitmesuguseid menetlustoiminguid. RIHA kesksüsteemi haldab RIA. Asutused kasutavad nii enda juurde paigaldatud komponente kui ka RIHA kesksüsteemi teenuseid |
| _RIHA haldur_ | RIA (kui RIHA kesksüsteemi haldaja) töötaja, kes täidab mitmesuguseid RIHA haldustoiminguid |
| _RIHA kesksüsteem_ | Hajusa RIHA komponendid, mis on paigaldatud RIA kontrolli all olevasse taristusse ja mille talitluse abil hallatakse RIHA või osutatakse teenust RIA-välistele RIHA komponentidele | 
| _Rollihaldur_ | RIHA komponent, mis võimaldab anda RIHA kasutajatele rolle ja tuvastada rolli(de) olemasolu autenditud kasutajal |
| _rollihaldur_, ka _asutuse rollihaldur_ ja _asutuse RIHA haldur_ | RIHA kasutava asutuse töötaja, kes haldab (annab ja võtab ära) asutuse töötajate rolle. Mõiste on sarnane vana RIHA mõistega "asutuse RIHA haldur" |
| _asutus_ | käesolevas dokumendis mõistetakse asutuse all asutust, aga samuti ettevõtet vm juriidilist isikut, kellel on vajadus või kes soovib RIHA kasutada viisil, mis nõuab rollide ja õiguste omamist RIHA kesksüsteemis |
| _kooskõlastavate asutuste nimekiri_ | nimekiri asutustest (nt AKI, Statistikaamet jt), kelle rollihalduril on õigus määrata inimesele rolli `KOOSKÕLASTAJA`; nimekiri teostatakse konfiguratsioonifailina |
| _autoriseerimine_ | käesolevas dokumendis kasutatakse tähenduses: kasutajale antud rollide edastamine rakendusele, tehakse pärast kasutaja autentimist |

## 3 Olulised viited

- [1] [RIHA üldvaade](https://github.com/e-gov/RIHA-API/blob/master/docs/YLDVAADE.md#riha-%C3%BCldvaade)
- [2] [RIHA pääsuhaldus](Specification.md). Spetsifikatsioon. 
- [3] Eesti.ee autentimisteenus v 0.9 (8.06.2016)
- [4] [RIHA MVP](https://e-gov.github.io/RIHA-API/MVP)
- [5] [Autentija](Autentija.md)

## 4 Põhimõtted ja disaini eesmärgid

RIHA rollihalduses on põhimõtteks:

- Ainult minimaalselt vajalik keerukus
  - keerukas rollihaldus on koormav ja kasutajad tegelikult ei vaja seda
  - vana RIHA rollihaldus on liiga keerukas
- Teha kõigepealt lihtne, aga töötav lahendus; tulevikus, kui tõesti vaja, alles siis täiendada.

## 5 Rollid

Rollide esialgne nimekiri:

| roll        | seletus |
|-------------|------------|
| `RIA HALDUR` | RIA töötaja, kes täidab mitmesuguseid RIHA haldustoiminguid |
| `ROLLIHALDUR` |  asutuse esindusõigusega isiku poolt määratud isik, kes saab anda asutuse RIHA kasutajatele rolle ja neid ära võtta |
| `KIRJELDAJA`  | asutuse töötaja, kellel on õigus kirjeldus RIHA kesksüsteemi lisada, muuta ja eemaldada |
| `KOOSKÕLASTAJA` | isik, kes saab RIHAs anda kooskõlastusi |

Uue RIHA moodulite arendamise käigus lisandub rolle. Millised täpselt, see selgub vastavate moodulite analüüsis. Eelkõige võin rolle lisanduda seoses X-tee toimingutega. 

## 6 Protsessid (e kasutuslood)

## 6.1 Kasutaja autoriseerimine
1. Kasutaja siseneb RIHAsse - avalehele.
2. Kasutaja autenditakse (esialgu Autentija [5], tulevikus eesti.ee autentimisteenuse abil).
3. Avaleht pärib Rollihaldurist autenditud kasutaja rollid.
  1. Rollihaldus tagastab isiku kõik rollid.
  2. Kui isikul on rolle mitmes asutuses, siis tagastatakse kõigi asutustega seotud rollid, asutuste kaupa.

## 6.2 Rollihalduri määramine
(põhivoog)

1. Esindusõigusega isik siseneb RIHAsse - avalehele.
2. Autendib end (esialgu Autentija [5], tulevikus eesti.ee autentimisteenuse abil).
3. Valib avalehel toimingu "RIHAga liitumine".
4. Suunatakse Rollihalduri kasutajaliidesesse.
5. Rollihaldur pöördub Esindusõiguse tuvastaja poole, viimane teeb päringuga Äriregistrisse kindlaks asutused, keda isik esindab.
6. Mitme asutuse korral valib inimene, keda ta esindab.
7. Esindusõigusega isik määrab ühe isiku asutuse rollihalduriks.

(abivoog: rollihalduri vahetamine)

1. Esindusõigusega isik määrab asutuse rollihalduriks teise inimese.

(abivoog: rollihalduri eemaldamine)

1. Esindusõigusega isik eemaldab rollihalduri.

## 6.3 Rolli määramine

Märkus. Rolli `ROLLIHALDUR` määramine vt "Rollihalduri määramine".

Märkus. Rolli `RIHA HALDUR` määramine vt "RIHA halduri määramine".

(põhivoog)

1. Rollihaldur siseneb RIHAsse - avalehele
2. Autendib end - eesti.ee autentimisteenuses.
3. Valib avalehel toimingu "Rollide haldamine".
4. Suunatakse Rollihalduri kasutajaliidesesse.
5. Rollihaldurile esitatakse nimekiri asutuse töötajatest koos rollidega.
6. Rollihaldur määrab inimese, sisestades isikukoodi ja nime.
7. (NICE TO HAVE) Päringuga Rahvastikuregistrisse kontrollitakse andmete õigsust.
8. Rollihaldur määrab inimesele rolli.

(abivoog)

1. Rollihaldur eemaldab inimeselt rolli

(abivoog)

1. Rollihaldur eemaldab inimese koos kõigi tema rollidega

(abivoog)

1. Rollihaldur annab inimesele teise rolli

Ärireeglid:

1. Rolli `KOOSKÕLASTAJA` saab määrata ainult kooskõlastavate asutuste nimekirja kuuluvas asutuses. 

## 6.4 Rolli RIHA HALDUR määramine

Rolli RIHA HALDUR määramine lahendatakse lähtudes RIA asutusesisesest rollide ja õiguste haldamise korrast ja tehnilisest keskkonnast.

## 7 Õigused
Rollidega seotud õiguste haldus on iga RIHA komponendi enda siseasi; õiguste teavet ei tsentraliseerita.

## 8 Rollide ülekandmine vanast RIHAst

1. Tehakse analüüs (väikesemahuline) ja hinnatakse ülekandmise keerukust.
2. Hinnangu alusel otsustatakse, kas projekteeritakse ja teostatakse rolliteabe ülekandmine (skriptide abil) või korraldatakse uues RIHAs rollide moodustamine "nullist peale".

## Muutelugu

| kp | muudatus |
|------------|--------------------------------------------------------|
| 05.12.2016 | Lisatud roll RIHA HALDUR; mitmeid väiksemaid täiendusi |


