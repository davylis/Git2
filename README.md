## Harjoitus 5

### Viedään projekti GitHub-palveluun.

- Lisää GitHubiin tyhjä repositorio
- Älä anna GitHubin tehdä sinne mitään, ei edes README-tiedostoa!
- Mitä GitHub-repositoriosivulla näkyy?
```ohjeet etärepon tekemiseen```
- Konfiguroi uusi repositorio paikallisen repositoriosi etärepositorioksi nimelle origin.
- Puske paikallisen repositorion master-haara GitHubiin.
- Mitä GitHub-repositoriosivulla nyt näkyy? Mitä haaroja näet GitHubissa, entä paikallisessa repositoriossasi?
```molemmissa näkyy sama main haara```
- GitHub-palvelun web-käyttöliittymässä voi myös tehdä muutoksia repositorioon. Luo GitHubin käyttöliittymässä jokin uusi tiedosto ja talleta muutos.
-Etärepositoriossa on nyt eri sisältö kuin paikallisessa repositoriossasi. Hae muutokset paikalliseen repositorioon ja mene katsomaan niitä:
```
git fetch     # muutokset haetaan muttei yhdistetä
git checkout origin/master 
```
Mikä muuttui?
```
Työtila näyttää nyt sen version, joka on GitHubissa
```
-Palaa master-haaraan. Mitä komento status sanoo?
```
Se näyttää, että olet ajantasalla, mutta etärepossa on uusia committeja.
```
-Yhdistä origin/master-haaran muutokset. Mitä komento status nyt sanoo?
```
Updating 548cb05..87b5005
Fast-forward
 gitfile.txt | 1 +
 1 file changed, 1 insertion(+)
 create mode 100644 gitfile.txt
``` 

## Harjoitus 6

### Harjoitellaan ohjelmiston kehittämistä ja muutosten synkronointia verkkopalvelussa sijaitsevan etärepositorion kanssa.

- Tähän tehtävään saat virtuaalisen tiimikaverin. Hän jatkokehittää aiemmissa harjoituksissa laadittua sovellusta kanssasi.

- Tehtävän suorittamiseksi on repositorioosi tehtävä valmisteluja. Anna seuraavat komennot:

```
git remote add actions https://github.com/mruonavaara/git-actions.git
git fetch actions main
git merge actions/main --allow-unrelated-histories
``` 

- Harjoitus perustuu aiemmin tehtyihin harjoituksiin, ja sen tekemisessä tarvitaan kaikkien aiempien osioiden oppeja!

- Kehitätte Hello-sovellusta projektitiimissä. Olette sopineet seuraavat versionhallintakäytännöt:
```
    Kukin tekee omat muutoksensa aina ensin haaraan nimeltä develop.
    Päähaaraan viedään vain versioita, jotka on testattu ja yhteisesti todettu valmiiksi.
```

- Projektissa seuraavaksi lisätään sovellukseen toiminta, jolla käyttäjälle näytetään kellonaika. Sait tehtäväksesi lisätä nappulan, jolla käyttäjä voi pyytää näyttämään kellonajan.

- Versionhallintakäytännön mukaisesti siirry haaraan develop. Sitä ei vielä ole, joten se pitää luoda.
```
    git switch -c develop

    Sitä ei ole etärepositoriossakaan, viedään se sinne.

    git push -u origin develop # -u on sama kuin --set-upstream
``` 

- Lisää html-tiedostoon <main>-osioon nappulaelementti päivämäärää ja kellonaikaa varten sekä nappula, jota painamalla tiedot näytetään:
```
<div id="datetime"></div>
<button>Mitä kello on?</button>
```
- Nappula ei vielä toimi, mutta ei huolta, tiimikaverisi toteuttaa sen toiminnallisuuden.

- Testaa sivu. Kun olet tyytyväinen lopputulokseen, talleta muutokset develop-haaraan.

- Vie develop-haara GitHub-palvelussa olevaan etärepositorioon.

- Huomaat, että tiimikaverisi on tehnyt nappulatoiminnallisuuden (mistä?). = commit-viestiin ohjeet

- Liitä JavaScript-tiedosto ohjelmaasi lisäämällä <body>-osion loppuun
```
<script src="scripts.js"></script>
```
- Hän on kirjannut talletuskommenttiin myös ohjeet, miten toiminnallisuus liitetään nappulaan.

- Liitä toiminnallisuus nappulaan ja testaa, että nappula toimii.

- Kun olet tyytyväinen sivun toimintaan, talleta muutos ja vie se yhteiseen kehityshaaraan.

- Toteat, että perusnappula näyttää ankealta. Määritä sille paremmat tyylimääritykset CSS-tiedostoon, esim.
```
button {
  background-color: blue;
  color: white;
  margin: 10px;
  padding: 8px;
  border-radius: 8px;
}
```
- Testaa sivu.

- Kun olet tyytyväinen lopputulokseen, talleta muutokset develop-haaraan ja vie etärepositorioon.

- Scrum-kokouksessa aamulla päätettiin muuttaa toimintaa niin, että kellonaika näytetäänkin jatkuvasti. Tiimikaverisi on jo ehtinyt toteuttaa JavaScript-toiminnallisuuden, sinun tehtäväksesi sovittiin tarpeettomaksi käyneen nappulan poistaminen.

- Hae tiimikaverisi muutokset ja poista kaikki nappulaan liittyvä tarpeeton koodi, testaa, että kaikki toimii.

- Kun muutos on valmis, vie se yhteiseen kehityshaaraan.

- Seuraavassa Scrum-kokouksessa todetaan, että ominaisuus on valmis esiteltäväksi sprintin katselmoinnissa develop-haaran uusimman version mukaisena.

- Yhdistä se päähaaraan. Muista viedä päähaarakin etärepositorioon!

## Harjoitus 7

### Yhdistämispyynnöt

- Git-palvelut tarjoavat toiminnallisuutta, jossa Git-repositorihin voi tehdä yhdistämispyyntöjä (pull request, merge request). Yhdistämispyyntö on ehdotus repositorion ylläpitäjille yhdistää pyynnön tekijän laatimat muutokset repositorion johonkin haaraan.

- Yhdistämispyyntöihin voidaan liittää tietoja muutoksesta, kehittäjät voivat keskustella siitä, yhdistämispyyntöä voidaan jatkokehittää, ja muutospyynnöille voidaan määrittää katselmointityönkulkuja.

- Kaikki Git-palvelut tarjoavat samanlaisen toiminnallisuuden. Tässä materiaalissa eismerkkinä käytetään GitHub-palvelun yhdistämispyyntöjä.
- Yhdistämispyynnön tekeminen

- Pyynnön oleelliset tiedot ovat:
```
    mistä repositoriosta ja haarasta muutoksia ehdotetaan
    mihin repositorioon ja haaraan ne haluttaisiin mukaan
    muutoksen otsikko ja kuvaus
```
- Pyyntö tehdään siis haaralle. Tavallisimmin ehdotettava muutos tehdään ominaisuushaaraan, joka asetetaan yhdistämispyynnön lähdehaaraksi. Kohdehaarana on jokin projektissa sovittu yhteinen haara.

- Yhdistämispyynnölle annetaan lisäksi
```
    otsikko, jolla se esitetään listauksissa, ja
    pyynnön käsittelijöitä varten kuvaus, mikä muutos on ja miksi sitä ehdotetaan.
```
- Seuraavassa esimerkissä tehdään yhdistämispyyntö GitHub-palvelussa.

- Ensin ehdotettava muutos on tehtävä paikallisesti. Sille tehdään ominaisuushaara ja viedään muutokset siihen. Ominaisuushaara täytyy viedä etärepositorioon GitHub-palvelussa, jotta sille voidaan tehdä yhdistämispyyntö.

```
git switch -c muutospyynnot
git add .
git commit -m "Lisää luku muutospyynnöistä"
git push -u origin muutospyynnot
```

- Kun haara näkyy etärepositoriossa, yhdistämispyyntö voidaan tehdä GitHubin web-käyttöliittymässä.

- Yhdistämispyyntö voidaan kohdistaa yhdelle tai useammalle repositorion ylläpitäjälle käsiteltäväksi tai katselmoitavaksi. - Tällöin he saavat notifikaation pyynnöstä.

- Yhdistämispyyntöä voidaan kommentoida, ja siitä käyty keskustelu tallentuu yhdistämispyyntöön. Yhdistämispyyntöä voidaan myös täydentää, siis tehdä uusia talletuksia sen haaraan.

- Kun pyyntöön ollaan tyytyväisiä, se voidaan hyväksyä. Tässä tapauksessa yhdistäminen onnistuu automaattisesti. Jos muutos aiheuttaisi konflikteja, ne olisi ensin ratkaistava.

- Yhdistämisen tuloksena syntyy uusi talletus etärepositorioon.

- Kun yhdistämispyynnön ominaisuushaara on yhdistetty, haara voidaan poistaa etärepositoriosta.

- Paikallinen repositorio pitää nyt päivittää, sillä uudet muutokset ovat vasta etärepositoriossa. Huomaa, että yhdistämispyynnön haara on vielä tallella paikallisesti, se pitää poistaa erikseen.
```
# git switch master
Your branch is behind 'origin/master' by 3 commits, and can be fast-forwarded.
  (use "git pull" to update your local branch)
# git pull         
Updating 473853e..9fe0f50
Fast-forward
 docs/assets/pr_create_form.png      | Bin 0 -> 47869 bytes
 docs/assets/pr_feature_branch.png   | Bin 0 -> 41894 bytes
 docs/assets/pr_list.png             | Bin 0 -> 22471 bytes
 docs/muita_toimintoja.md            |   2 +-
 "docs/muutospyynn\303\266t.md"      |  38 ++++++++++++++++++++++++++++++++++++
 docs/versionhallinta_projektissa.md |   4 +---
 mkdocs.yml                          |   4 +++-
 7 files changed, 43 insertions(+), 5 deletions(-)
# git branch
* master
  muutospyynnot
# git branch -d muutospyynnot
```
### Yhdistämispyynnöt repositoriosta toiseen
- Edellisessä esimerkissä yhdistämispyyntöjä tehtiin yhden repositorion sisällä. Pyyntöjä on mahdollista tehdä myös eri repositorioiden kesken.

- Tällöin yhdistämispyynnön tekijällä on oltava Git-palvelussa oma versio repositoriosta, johon muutoksia halutaan ehdottaa, ja ehdotettava muutoshaara tehdään tähän repositorioon.

- Git-palvelut tarjoavat fork-toiminnon, jolla voi yhdellä klikkauksella luoda itselleen oman version toisesta repositoriosta. Kehittäjällä on siis aina kaksi versiota kohderepositoriosta: Git-palvelussa oleva fork-repositorio sekä paikallinen repositorio, jossa muutoksia työstetään ja jonka etärepositorio fork on.

- Repositorioiden käyttöoikeuksien pitää olla määritelty niin, että sekä yhdistämispyynnön tekijä että vastaanottajat näkevät toistensa repositoriot. Jos ne ovat julkisia, näin on aina.
Avoimen lähdekoodin versionhallinta

- Avoimen lähdekoodin projekteissa kuka tahansa voi itsenäisesti kehittää projektiin muutoksia. Ei kuitenkaan ole mahdollista antaa suoria muutosoikeuksia repositorioihin kenelle tahansa. Tällöin käytetään forking-työnkulkua:
```
    Kehittäjä tekee Git-palvelussa fork-repositorion projektin virallisesta repositoriosta. Virallinen repositorio on julkinen, niinpä oma fork on myös julkinen.
    Hän kloonaa fork-repositorion koneelleen. Tässä repositoriossa tehdään oma kehitys.
    Jotta oma kopio voisi pysyä ajan tasalla virallisen repositorion muutosten kanssa, myös virallinen repositorio on konfiguroitava paikallisen repositorion etärepositorioksi. Tapana on antaa etärepositorion nimeksi upstream
    Uusi kehitys tehdään ominaisuushaaraan.
    Ominaisuushaara viedään omaan fork-repositorioon.
    Kehittäjä avaa uuden yhdistämispyynnön viralliseen repositorioon. Lähdehaaraksi asetetaan fork-repositorion ominaisuushaara.
    Virallisen repositorion ylläpitäjä käsittelee yhdistämispyynnön. Hän yhdistää pyynnön haaran ensin omaan paikalliseen repositorioonsa testatakseen sen, ja hyväksyy tai sulkee yhdistämispyynnön. Pyynnöstä voidaan käydä keskustelua ja pyyntöhaaraa voidaan kehittää edelleen.
    Jos pyyntö hyväksyttiin, kehittäjän täytyy päivittää omien repositorioidensa sisällöt vastaamaan virallisen repositorion uutta sisältöä. Hän siis tuo oman muutoksensa upstream-etärepositoriosta takaisin siinä haarassa, johon se virallisessa repositoriossa yhdistettiin. Nythän se on virallista sisältöä!
```
