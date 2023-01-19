### Näin luot itsellesi uuden SSH-avaimen (Linux-terminaalissa):

1. Avaa terminaali ja surffaa .ssh/ -hakemistoon. Tämä ei ole pakollinen vaihe, mutta oletettavasti sinulla on jo muitakin avaimia, esimerkiksi GitHubiin, joten näin ollen kaikki avaimet ovat kätevästi samassa paikassa.

```bash
cd /home/<username>/.ssh
```

2. Kirjoita komento ssh-keygen.

```bash
ssh-keygen
```

3. Generaattori kysyy sinulta, mihin tiedostoon haluat avaimesi tallennettavan. Koska ollaan jo .ssh/ -hakemistossa, riittää nimetä pelkkä tiedosto. Käytä sellaista nimeä, millä erotat avaimen muista avaimista, esimerkiksi “cast” tai “ohtuprojekti”.

4. Seuraavaksi sinulta kysytään salasanaa, jolla avain suojataan. Salasana ei ole pakollinen, mutta erittäin suositeltava, sillä mikäli avaimesi varastettaisiin, tarvitsisi sen salasanakin olla tiedossa, että sitä pystyisi käyttämään. Salasana kysytään varmuuden vuoksi vielä kirjoitusvirheiden varalta uudestaan.

5. Valmista tuli, nyt sinulla on uusi avainpari valitsemassasi hakemistossa! Voit varmistaa asian listaamalla hakemiston kaikki tiedostot:

    ```bash
    ls -la
    ```

    jolloin hakemistossa tulisi näkyä tiedostot <valitsemasi_avaimen_nimi> sekä <valitsemasi_avaimen_nimi>.pub

    Näistä tiedostoista .pub -päätteinen tiedosto on public key, joka laitetaan serverille. Tiedoston voi avata millä tahansa tekstieditorilla, tai sen sisällön voi tulostaa terminaalissa komennolla:

    ```bash
    cat <valitsemasi_avaimen_nimi>.pub
    ```

    Toimita tämä tuloste serverille tai siitä vastaavalle henkilölle. Kun avain on serverillä, toimii avain esimerkiksi seuraavalla tavalla:

    ```bash
    ssh -i /home/<username>/.ssh/<valitsemasi_avaimen_nimi> <username>@<serverin_osoite> 
    ```

    Esimeriksi vielä hieman selkeämpi komento, mikäli käyttäjätunnus olisi “erkki”, serverin osoite “esimerkki.fi” ja avaimen nimi “cast”:

    ```bash
    ssh -i /home/erkki/.ssh/cast erkki@esimerkki.fi
    ```

    tai mikäli ollaan edelleen valmiiksi .ssh/ -hakemistossa, riittää osoittaa pelkkää avaintiedostoa:

    ```bash
    ssh -i cast erkki@esimerkki.fi
    ```

    Aina serverillä ei ole välttämättä olemassa selkokielistä nimeä, mutta ip-osoitteen kanssa homma toimii samalla tavalla:

    ```bash
    ssh -i cast erkki@91.155.266.666
    ```
