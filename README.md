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
