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
