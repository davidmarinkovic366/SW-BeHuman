# Be Human:pray: website

Projekat na temu povezivanja ljudi kojima je neophodna pomoc, i ljudi
koji zele da pruze pomoc.

Tehnologije koriscene za implementaciju:
- **:computer: Backend:** - **Node.js & Express.js**
- **:tv: Frontend:** - **React.js, Redux & MaterialUI**

Kao baza podataka koriscen je **MongoDB**.

## Priprema za pokretanje

Pre pokretanja, potrebno da preuzmemo sve pakete neophodne za funkcionisanje aplikacije, pa unutar foldera :file_folder: "Aplikacija/***backend***", "Aplikacija/***frontend***" i "Aplikacija/***socket***" otvorimo novu instancu terminala i pokrenemo komandu:

```bat
npm install
```

Pre pokretanja same aplikacije, neophodno je prvo pokrenuti bazu podataka, postoji mogucnost koriscenja besplatne verzije MongoDB instance baze podataka na: *https://www.mongodb.com/cloud/atlas/register*. 

Nakon kreiranja naloga i besplatne instance baze podataka, potrebno je kreirati novi fajl sa nazivom "**.env**" unutar "Aplikacija/***backend***" foldera, i u njega dodati sledeci sadrzaj:

```js
DATABASE_URL=[database_name]
TOKEN_KEY=[random_generated_key]
REFRESH_KEY=[random_generated_key]
```

> :information_source: Vrednosti **TOKEN_KEY** i **REFRESH_KEY** se koriste za kreiranje **JSONWebToken** objekta koje aplikacija koristi za autentifikaciju i autorizaciju korisnika, ove vrednosti mozemo da generisemo rucno, a preporuka je koriscenje stringa sa 64 :heavy_plus_sign: karaktera.
>
> :warning: Naravno, ove dve vrednosti bi trebale da budu **razlicite**.

## :checkered_flag: Pokretanje

Nakon sto smo zavrsili sa povezivanjem baze podataka, pokrecemo **redom** kroz terminal:
1. :computer: Backend deo
2. :link: Sockets
3. :tv: Frontend deo

Naredbom: 

```bat
npm start
```

Nakon startovanja frontend-a, moguce je pristupiti aplikaciji koriscenjem pretrazivaca na adresu: *http://localhost:3000*

> :information_source: Socket predstavlja posebnu instancu servera koji koristimo za prenosenje obavestenja o porukama :incoming_envelope: i notifikacije :newspaper: na koje je korisnik prijavljen, kako bi omogucili real-time :stopwatch: osvezavanje poruka i notifikacija :mailbox_with_mail:.


> :heavy_exclamation_mark: Nije moguce kreirati **admina** kao korisnika sa Register stranice, vec je potrebno nakon kreiranja obicnog korisnika, otvoriti bazu podataka, naci korisnika i rucno promeniti polje "*isAdministrator*" sa **false** :arrow_right: **true**;