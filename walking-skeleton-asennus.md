# Walking Skeletonin lokaali asennus

Tarvitset Walking Skeletonin lokaalia käyttöä varten seuraavat sovellukset:

- postgreSQL [Asennusohje](https://github.com/hy-tsoha/local-pg)
- npm [Asennusohje](https://github.com/nvm-sh/nvm)

## Backendin asennus

1. Avaa postgreSQL komennolla `psql`. Kirjoita komento `CREATE DATABASE "cast";`.
2. Varmista, että postgreSQL on aktiivisena (seuraa Tsoha-kurssimateriaalin ohjeita tarvittaessa).
3. Siirry kansioon cast_backend/ ja etsi tiedosto cast_backend/settings.py. Vaihda kohtaan `DATABASE` käyttäjätunnukseksi oma postgres-käyttäjätunnuksesi.
4. Suorita terminaalissa komento `python3 -m venv venv`
5. Suorita terminaalissa komento `source venv/bin/activate`
6. Suorita terminaalissa komento `pip install -r requirements.txt`
7. Suorita terminaalissa komento `python3 manage.py makemigrations`
8. Suorita terminaalissa komento `python3 manage.py migrate`
9. Nyt kaikki on valmista. Käynnistä sovellus komennolla `python3 manage.py runserver`

## Frontendin asennus

1. Siirry kansioon frontend/ ja aja komento `npm install`
2. Käynnistä sovellus komennolla `npm -dev start`
