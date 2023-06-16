<p align="center"><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/logo.svg"/></a><br/><a href="https://xxai.art"><img src="https://cdn.jsdelivr.net/gh/xxai-art/doc/xxai.svg"/></a></p><p align="center"><a href="https://github.com/xxai-art/doc#readme"><img alt="I18N" src="https://cdn.jsdelivr.net/gh/wactax/img/t.svg"/></a>　<a href="https://groups.google.com/u/0/g/xxai-art"><img alt="Google Groups" src="https://cdn.jsdelivr.net/gh/wactax/img/g-groups.svg"/></a></p>

# xxAI.art

Hluti af kóða vefsíðunnar er opinn uppspretta, velkomið að hjálpa til við að fínstilla þýðinguna.

## framenda kóða

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

  Markdown þýðing mun ekki þýða kóða og tengla og geymir þýddar setningar í skyndiminni. Ef þýðingunni er breytt en upprunalega textanum er ekki breytt, mun það ekki skrifa yfir breytinguna á þýðingunni að framkvæma hana aftur.

* [@w5/i18n](https://www.npmjs.com/package/@w5/i18n)

  Tungumálaskrár til að þýða vefsíður sem mynda `yaml` .
