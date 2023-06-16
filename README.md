<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

Mælt er með því að setja upp nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) fyrst og síðan `direnv allow` eftir að farið er inn í möppuna ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) verður keyrt sjálfkrafa eftir að farið er inn í möppuna).

Merkingin er: Kínversk þýðing á japönsku, kóresku, ensku, enskri þýðingu á öll önnur tungumál. Ef þú vilt aðeins styðja kínversku og ensku geturðu bara skrifað `zh: en` .

Merkingin er: Kínversk þýðing á japönsku, kóresku, ensku, enskri þýðingu á öll önnur tungumál. Ef þú vilt aðeins styðja kínversku og ensku geturðu bara skrifað `zh: en` .

* [framenda kóða](https://github.com/xxai-art/web)
* [Tungumálapakkar fyrir síðuna í heild sinni](https://github.com/xxai-art/web/tree/main/i18n)
* [Tungumálapakkar fyrir innskráningareiningar](https://github.com/wacpkg/user/tree/main/ui.i18n)
* [Heimasíða Fjöltyng skjöl](https://github.com/xxai-doc)

Framhlið forritunarmálið er [@w5/coffee_plus](http://npmjs.com/@w5/coffee_plus) , sem bætir við nokkrum eiginleikum byggt á coffeescript setningafræðinni, sjá [./coffee_plus.md](./coffee_plus.md) .

## Alþjóðavæðing vefsíðna og skjala

Byggðu á eftirfarandi 3 verkefnum

* [@w5/mdt](https://www.npmjs.com/package/@w5/mdt)

  Viðskeytið er `.mdt` , þú getur notað setningafræði svipað og `<+ ./coffee_plus/import.js>` til að vísa í utanaðkomandi skrár og búið til markdown með viðskeytinu `.md` .

* [@w5/trmd](https://www.npmjs.com/package/@w5/trmd)

  Markdown þýðing mun ekki þýða kóða og tengla og geymir þýddar setningar í skyndiminni. Ef þýðingunni er breytt en upprunalega textanum er ekki breytt mun það ekki skrifa yfir breytinguna á þýðingunni að framkvæma hana aftur.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Tungumálaskrár til að þýða vefsíður sem mynda `yaml` .

### Leiðbeiningar um skjalaþýðingu sjálfvirkni

Sjá kóðageymslu [xxai-art/doc](https://github.com/xxai-art/doc)

Mælt er með því að setja upp nodejs, [direnv](https://direnv.net) , [bun](https://github.com/oven-sh/bun) fyrst og síðan `direnv allow` eftir að farið er inn í möppuna ( [.envrc](https://github.com/xxai-art/doc/blob/main/.envrc) verður keyrt sjálfkrafa eftir að farið er inn í möppuna).

Til að forðast stóra kóðagrunninn sem þýddur var yfir á hundruð tungumála bjó ég til sérstakan kóðagrunn fyrir hvert tungumál og stofnaði stofnun til að geyma kóðagrunninn

Að stilla umhverfisbreytuna `GITHUB_ACCESS_TOKEN` og keyra síðan [create.github.coffee](https://github.com/xxai-art/doc/blob/main/create.github.coffee) mun sjálfkrafa búa til kóðageymsluna.

Auðvitað geturðu líka sett það í kóðagrunn.

Þýðingarhandrit tilvísun [run.sh](https://github.com/xxai-art/doc/blob/main/run.sh)

Handritskóðinn er túlkaður sem hér segir:

[bunx](https://bun.sh/docs/cli/bunx) kemur í staðinn fyrir npx, sem er hraðari. Auðvitað, ef þú ert ekki með bun uppsett geturðu notað `npx` í staðinn.

`bunx mdt zh` gefur `.mdt` í zh möppunni sem `.md` , sjá 2 tengdu skrárnar hér að neðan

* [coffee_plus.mdt](https://github.com/xxai-doc/zh/blob/main/coffee_plus.mdt)
* [coffee_plus.md](https://github.com/xxai-doc/zh/blob/main/coffee_plus.md)

`bunx i18n` er kjarnakóði fyrir þýðingar (ef þú ert aðeins með `nodejs` uppsett, en `bun` og `direnv` eru ekki uppsett, geturðu líka keyrt `npx i18n` til að þýða).

Það mun flokka [i18n.yml](https://github.com/xxai-art/doc/blob/main/i18n.yml) , uppsetning `i18n.yml` í þessu skjali er sem hér segir:

```
en:
zh: ja ko en
```

Merkingin er: Kínversk þýðing á japönsku, kóresku, ensku, enskri þýðingu á öll önnur tungumál. Ef þú vilt aðeins styðja kínversku og ensku geturðu bara skrifað `zh: en` .

Sá síðasti er [gen.README.coffee](https://github.com/xxai-art/doc/blob/main/gen.README.coffee) , sem dregur út innihaldið á milli aðaltitils og fyrsta undirtitils `README.md` hvers tungumáls til að búa til færslu `README.md` . Kóðinn er mjög einfaldur, þú getur skoðað hann sjálfur.

Google API er notað fyrir ókeypis þýðingar. Ef þú hefur ekki aðgang að Google skaltu stilla og stilla proxy, eins og:

```
export https_proxy=http://127.0.0.1:7890 http_proxy=http://127.0.0.1:7890 all_proxy=socks5://127.0.0.1:7890
```

Þýðingarforritið mun búa til þýtt skyndiminni í `.i18n` möppu, vinsamlegast athugaðu það með `git status` og bættu því við kóðageymsluna til að forðast endurteknar þýðingar.

Vinsamlegast keyrðu `bunx i18n` í hvert skipti sem þú breytir þýðingunni til að uppfæra skyndiminni.

Ef upprunalega textanum og þýðingunni er breytt á sama tíma verður skyndiminni ruglað saman, þannig að ef þú vilt breyta geturðu aðeins breytt einum og keyrt síðan `bunx i18n` til að uppfæra skyndiminni.
