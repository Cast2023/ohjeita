Jos `test` haara on olemassa etä repossa, ja halutaan päivittää muutokset `test` haaran paikalliselle repolle  

    git fetch test  

Jos `test` ei ole olemassa, niin luodaan sen.
Kun luodaan  haarasta ‘master’ uuden `test` haaran, ja halutaan `test` haaran sisältö = `master` sisältöä luonnin jälkeen:

    git checkout -b test master

Nyt valitettavasti remote puolella git repo ei tiedä uusi haara test on luotu. Päivitetään se 
work work work ….

    git push -u origin test:test           (ensimmäinen test = paikallisen haaran nimi, toinen test = remote haara)

Testi lähtee käyntiin…..


Yleensä haarat ovat  

	- master  
	- development  
  	- feature_name_y  
	- feature_name_x  

Jos nyt `feature_name_x` ominaisuudet on hoidettu ja nyt halutaan yhdistää `feature_name_x` haara `development` haaralle.

    git checkout development 
    git merge feature_name_x

Jos ‘development’ on ihan edellä, meidän pitää päivittää muutokset ‘feature_name’ haaralle ensin, sitten aloitetaan ‘feature’ kehitystä. 
    
    git checkout feature_name
    git merge main –squash  (sqush vipu on tärkeä, koska se yhdistää ‘master’ haaran commit:it  yhdeksi commitiksi.)

Sitten kun 'feature_name_x'  haaran toteutukset on tehty. Voidaan tehdä pullrequest development haaralle.  Pullrequest on pyyntö, että joku ottaisi muutokset käyttöön tarkastuksen jälkeen.

Jos joku käydä katsomassa ‘pullrequest’, niin hän on ratkaistava mahdolliset ‘conflict’ ongelmat. Kun kaikki on hoidettu, hän voi sitten painaa ‘merge pull request’  painikettä, ja se on siinä. 
