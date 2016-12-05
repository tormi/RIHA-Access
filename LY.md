## Rollihaldur. I iteratsioon. Lähteülesanne

#### 1 Lähtekohad

Uue RIHA rollihalduse vajadused ja loodav tehniline lahendus on spetsifitseeritud dokumentides, edaspidi _spetsifikatsioonides_:

- "RIHA rollihaldus. Äriprotsess" [1] [https://github.com/e-gov/RIHA-Access/blob/master/Roles.md](https://github.com/e-gov/RIHA-Access/blob/master/Roles.md)
- "RIHA rollihaldus. Tehniline lahendus" [2] [https://github.com/e-gov/RIHA-Access/blob/master/Specification.md](https://github.com/e-gov/RIHA-Access/blob/master/Specification.md)

Spetsifikatsioonid väljendavad Tellija hetke parimat teadmist. Tellija on püüdnud esitada võimalikult kogu tööde teostamiseks vajaliku informatsiooni. Spetsifikatsioone ei tule siiski käsitada lõplike ja muutumatutena. Võimalikud üleskerkivad küsimused lahendatakse töö käigus, Täitja ja Tellija koostöös, seades prioriteetideks ühelt poolt Tellija ärivajaduste rahuldamise ja teiselt poolt kokkulepitud töömahus püsimisi.

Spetsifikatsioone hoitakse ajakohasena. Kui kokku ei lepita teisiti, siis spetsifikatsioone täiendab Tellija, kasutades Täitja esitatud teavat.

#### 2  Arendusmeetod
Rollihalduri tarkvara arendatakse agiilselt, jagades tööd kaheks, vajadusel ka enamaks iteratsiooniks. Käesolev lähteülesanne hõlmab I iteratsiooni töid. II iteratsiooni tööd täpsustatakse I iteratsiooni valmides.

Iteratsiooni pikkuseks on neli (4) nädalat, millest esimese 2 nädala lõpuks peab töötav kood olema põhijoontes valmis kirjutatud. 3-4. nädalal testitatakse ja täiendatakse koodi ning viiakse tarkvara dokumenteerimine lõpule.

#### 3 Tööd

Teostamisele tulevad ülalnimetatud spetsifikatsioonides määratletud tarkvara arendustööd, edaspidi _tööd_, I interatsioonina, koosseisus:

1. Rollihalduri teostus
  - arendada rakendus, vastavalt arhitektuurijoonisele [2, joonis 1]
  - rakendus peab teostama kasutuslood [1]:
    - 6.1 Kasutaja autoriseerimine
    - 6.2 Rollihalduri määramine (alternatiivvoog ja abivoog, põhivoogu  mitte, sest Esindusõiguse tuvastajat I iteratsioonis ei teostata)
    - 6.3 Rolli määramine (nii põhi- kui ka abivood)
    - 6.4 Rolli RIHA HALDUR määramine (leida minimaalse keerukusega, kuid toimiv lahendus)

Kõik tarkvara arendustööd sisaldavad nõuete- ja asjakohast analüüsi, projekteerimist, testimist ja dokumenteerimist.

Tööd ei sisalda:

1. Autentimisteenuse loomist. (Kasutada saab RIA poolt loodavat autentimisteenust)
2. Esindusõiguse tuvastaja teostamist (jääb kaalumisele II iteratsioonis)
3. Rollihalduri liidestamist RIHA kesksüsteemiga (liidestamine tehakse järgmistes iteratsioonides, RIHA kesksüsteemi komponentide valmides)

#### 4 Tehnilised nõuded

1. Rollihalduri alustehnoloogiana kasutada OpenLDAP [3].
  1. Analüüsida, kohandada ja täiendada vastavalt RIHA rollihalduse äriprotsessi nõuetele.
  2. Päring "rollide tuvastamisele" ja vastus "rollid tuvastatud" teostada vastavalt LDAP protokollile.
2. Kõik kasutuslood peavad olema korralikult testitud
  1. Koostada testistrateegia dokument, testilood, valmistada ette testiandmed, lõpuks esitada testiraport.
3. Tarkvara publitseerida avalikult https://github.com/e-gov/RIHA-Access.
  1. Jälgida, et avalikult publitseeritud tarkvara ei sisalda konfidentsiaalset teavet.

#### Viited

[1] [RIHA rollihaldus. Äriprotsess](Roles.md)

[2] [RIHA rollihaldus.Tehniline lahendus](Specification.md)

[3] OpenLDAP, http://www.openldap.org/
