---
layout: default
title: Welcome
---

# {{ page.title }}

<div class="toc" markdown="1">
Contents:

* [What's `football.db`?](#whatis)
* [Web Admin App](#webadmin)
* [Web Service / HTTP JSON API](#webservice)
* [Leagues and Tournaments / National Teams](#national-teams)
* [Intn'l Club Tournaments (Champions Leagues & Co.)](#clubs-intnl)
* [National Club Leagues & Cups](#clubs)
* [Tables, Schema](#schema)
* [Command Line Tool - Build Your Own `football.db` Copy](#build)
* [Talks - Slide Decks](#talks)
* [About, License - Questions? Comments?](#license)
</div>


## What's `football.db`?   {#whatis}

A free open public domain football (soccer) database & schema
for use in any (programming) language
(e.g. uses plain text fixtures/data sets). Example:

~~~
### Teams

barcelona, Barcelona|FC Barcelona|Fútbol Club Barcelona, BAR, city:barcelona
~~~


~~~
### Matches

2013-03-12 20:45  Barcelona  4-0  Milan
~~~


### Teams Example - `es/teams.txt`

~~~
################################
# Primera División de España - La Liga

barcelona, Barcelona|FC Barcelona|Fútbol Club Barcelona,  BAR, city:barcelona
espanyol,  Espanyol Barcelona|Real CD Espanyol,  ESP, city:barcelona

madrid,    Real Madrid|Real Madrid CF, RMD, city:madrid
atletico,  Atlético Madrid|Club Atlético de Madrid,   ATL, city:madrid
getafe,    Getafe|Getafe CF|Getafe Club de Fútbol,    GET, city:madrid 
rayo,      Rayo Vallecano|Rayo Vallecano de Madrid, RAY, city:madrid

realbetis, Real Betis Sevilla|Real Betis|Real Betis Balompié, BET, city:sevilla
sevilla,   Sevilla|Sevilla FC|Sevilla Fútbol Club, SEV, city:sevilla

valencia,  Valencia|FC Valencia|CF Valencia|Valencia CF, VAL, city:valencia
levante,   Levante|Levante UD|Levante Unión Deportiva, LEV, city:valencia

malaga,    Málaga|FC Málaga|Málaga CF|CF Málaga,   MAG, city:malaga
athletic,  Athletic Bilbao,              ATH,   city:bilbao
granada,   Granada|Granada CF|Granada Club de Fútbol, GRA, city:granada
osasuna,   Osasuna|CA Osasuna|Club Atlético Osasuna, OSA, city:pamplona
...
~~~

Source: [`es/teams.txt`](https://github.com/openfootball/es-espana/blob/master/teams.txt)



### Matches Example - `club/europe/2012_13/cl_ii.txt`

~~~
####################################
# Champions League 2012/13 - Finalrunden

(8)  Achtelfinale Rückspiele  // Di./Mi., 5.+6./12.+13. Mär 2013

2013-03-05 20:45  Manchester United  1-2  Real Madrid
2013-03-05 20:45  Borussia Dortmund  3-0  Schachtar Donezk

2013-03-06 20:45  Paris Saint-Germain  1-1  Valencia
2013-03-06 20:45  Juventus             2-0  Celtic Glasgow

2013-03-12 20:45  Schalke 04  2-3  Galatasaray
2013-03-12 20:45  Barcelona  4-0  Milan

2013-03-13 20:45  Málaga  2-0  Porto
2013-03-13 20:45  Bayern München  0-2  Arsenal
...
~~~

Source: [`club/europe/2012_13/cl_ii.txt`](https://github.com/openfootball/europe-clubs/blob/master/2012_13/cl_ii.txt)



## Leagues and Tournaments / National Teams  {#national-teams}

### World

- FIFA World Cup 2010, 2014
- FIFA World Cup Quali 2014
- FIFA Confederations Cup 2009, 2013

### America (North/Central America and the Caribeans, South America)

- CONCACAF Copa Oro / Gold Cup 2011, 2013
- CONMEBOL Copa América 2011, 2015

### Europe

- UEFA European Football Championship (Euro) 2012, 2008


Example - FIFA World Cup 2010:

~~~
###########
# Groups

Group A  |  South Africa    Mexico              Uruguay          France
Group B  |  Argentina       Nigeria             South Korea      Greece
Group C  |  England         United States       Algeria          Slovenia
Group D  |  Germany         Australia           Serbia           Ghana
Group E  |  Netherlands     Denmark             Japan            Cameroon
Group F  |  Italy           Paraguay            New Zealand      Slovakia
Group G  |  Brazil          North Korea         Côte d'Ivoire    Portugal
Group H  |  Spain           Switzerland         Honduras         Chile


################
# Group A

Matchday 1 / Group A

(1) Fr  2010-06-11 16:00    South Africa - Mexico     1-1
(2) Fr  2010-06-11 20:30    Uruguay - France   0-0

...
~~~

Source: [`world/2010/cup.txt`](https://github.com/openfootball/world/blob/master/2010/cup.txt)



## Intn'l Club Tournaments (Champions Leagues & Friends) {#clubs-intnl}

### Amercia (North/Central America and the Caribeans, South America)

- CONCACAF Champions League 2011/12, 2012/13
- CONMEBOL Copa Sudamericana 2012
- CONMEBOL Copa Libertadores 2012, 2013

### Europe

- UEFA Champions League 2011/12, 2012/13
- UEFA Europa League 2011/12



## National Club Leagues & Cups  {#clubs}

### Europe

- Österreichische Bundesliga 2011/12, 2012/13
- ÖFB Cup 2011/12, 2012/13
- English Permier League 2012/13
- Deutsche Bundesliga 2012/13
- Romania Liga 1 2012/13

### North America

- México Primera División Apertura 2012, Clausura 2013

### South America

- Campeonato Brasileiro Série A

Anything missing? Add your leagues, teams, fixtures and more.



## Web Admin App {#webadmin}

Try the `football.db` Web Admin app running
on Heroku [`footballdb.herokuapp.com`](http://footballdb.herokuapp.com).


## Web Service / HTTP JSON API    {#webservice}

Try the `football.db` HTTP JSON API running
on Heroku [`footballdb.herokuapp.com/api`](http://footballdb.herokuapp.com/api).

Example - List all games in a round for an event `/event/:key/round/:pos`:

~~~
GET /event/euro.2012/round/6

{
  "event": { "key":"euro.2012", "title":"Euro 2012" },
  "round": { pos": 6, "title": "Final" },
  "games":
  [
    {
    "team1_key": "esp",
    "team1_title": "Spain",
    "team1_code": "ESP",
    "team2_key": "ita",
    "team2_title": "Italy",
    "team2_code": "ITA",
    "play_at": "2012/07/01",
    "score1": 4,
    "score2": 0,
    "score1ot": null,
    "score2ot": null,
    "score1p": null,
    "score2p": null
    }
  ]
}
~~~


## Tables, Schema  {#schema}

The `football.db` includes the following tables:

* teams
* games
* events
  * events_teams (join table)
* rounds
* groups
  * groups_teams (join table)


(add schema pic here)



## Command Line Tool - Build Your Own `football.db` Copy {#build}

To build your own `football.db` copy from the plain text fixtures
use the sportdb command line tool. Example:

Step 1:  Get a copy of the `world.db` fixtures

    $ git clone git://github.com/geraldb/world.db.git

Step 2:  Get a copy the `at-austria` fixtures

    $ git clone git://github.com/openfootball/at-austria.git

Step 3:  Let's build the `football.db`

    $ sportdb setup --include ./at-austria --worldinclude ./world.db

That's it. For more see the [`sportdb` command line tool project](https://github.com/geraldb/sport.db.ruby)
for more.



## Real World Usage

[sport.db Web Admin](https://github.com/geraldb/sport.db.admin) - `sport.db` Web Admin Tool in Ruby on Rails (version 3.2 and up).

[Sportbook](https://github.com/geraldb/sportbook) - A free, open source sports betting pool in Ruby on Rails (version 3.2 and up). 


## Alternatives

[SportsDB](http://www.sportsdb.org)  - open database schema for sports information (formerly known as XTOSS: The XML Team Open Sports Schema.)

[openLigaDB](http://www.openligadb.de) -  community-based sport results



## License {#license}

The `football.db` schema, data and scripts are dedicated to the public domain.
Use it as you please with no restrictions whatsoever.


{% include questions.md %}
