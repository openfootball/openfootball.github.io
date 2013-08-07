---
layout: default
title: Welcome
---

# {{ page.title }}

<div class="toc" markdown="1">
Contents:

* [What's `football.db`?](#whatis)
* [Web Admin Site](#webadmin)
* [Leaguges and Tournaments](#national-teams)
    * [National Teams](#national-teams)
        * [World Cup](#national-teams)
        * [Copa América](#national-teams)
        * [Copa Oro / Gold Cup](#national-teams)
        * [European Football Championship (Euro)](#national-teams)
    * [Football Clubs](#clubs)
        * [Copa Libertadores](#clubs)
        * [Copa Sudamericana](#clubs)
        * [Champions League](#clubs)
        * [Europa League](#clubs)
* [Tables, Schema](#schema)
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
madrid,    Real Madrid|Real Madrid CF, RMD, city:madrid
malaga,    Málaga|FC Málaga|Málaga CF|CF Málaga,   MAG, city:malaga
...
~~~

~~~
### Matches

2013-03-12 20:45  Schalke 04      2-3  Galatasaray
2013-03-12 20:45  Barcelona       4-0  Milan

2013-03-13 20:45  Málaga          2-0  Porto
2013-03-13 20:45  Bayern München  0-2  Arsenal
...
~~~



## Web Admin Site {#webadmin}

Try the `football.db` web admin app running
on Heroku [`footballdb.herokuapp.com`](http://footballdb.herokuapp.com).



## National Teams / Leagues and Tournaments   {#national-teams}

### World

- FIFA World Cup
- FIFA World Cup Quali
- FIFA Confederations Cup

[More »](https://github.com/openfootball/world-cup)

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

Source: [`world-cup/2010/cup.txt`](https://github.com/openfootball/world-cup/blob/master/2010/cup.txt)



### America (South America; North America, Central America and the Caribbeans)

- CONMEBOL [^1] Copa América
- CONCACAF [^2] Copa Oro / Gold Cup

<!-- todo check footnotes - do they work w/ fallback? -->

[^1]: CONMEBOL = South America
[^2]: CONCACAF = North America, Central America and the Caribbeans


[More »](https://github.com/openfootball/america-cup)


### Africa

- CAF Africa Cup of Nations

[More »](https://github.com/openfootball/africa-cup)

### Europe

- UEFA European Football Championship (Euro)

[More »](https://github.com/openfootball/euro-cup)



## Football Clubs / Leagues and Tournaments  {#clubs}

### Intn'l Club Tournaments (Champions Leagues & Friends) 

#### Amercia (South America; North America, Central America and the Caribbeans)

- CONMEBOL Copa Libertadores
- CONMEBOL Copa Sudamericana
- CONCACAF Champions League 

[More »](https://github.com/openfootball/america)


#### Europe

- UEFA Champions League
- UEFA Europa League

[More »](https://github.com/openfootball/europe)


Matches Example - `club/europe/2012_13/cl_ii.txt`

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

Source: [`europe/2012_13/cl_finals.txt`](https://github.com/openfootball/europe/blob/master/2012_13/cl_finals.txt)


### National Leagues & Cups

#### Europe

- Österreichische Bundesliga + ÖFB Cup
- English Permier League
- Deutsche Bundesliga
- Spanish La Liga
- Romania Liga 1

#### North America

- México Primera División Apertura + Clausura

#### South America

- Campeonato Brasileiro Série A

and more.



## Tables, Schema  {#schema}

The `football.db` includes the following tables:

* teams
* games
* events
    * events_teams (join table)
* rounds
* groups
    * groups_teams (join table)
* leagues
* seasons
* players
* rosters (join table)
* goals

(add schema pic here)




## Real World Usage

[sport.db Web Admin](https://github.com/geraldb/sport.db.admin) - `sport.db` Web Admin Tool in Ruby on Rails (version 3.2 and up).

[Sportbook](https://github.com/geraldb/sportbook) - Free, open source sports betting pool in Ruby on Rails (version 3.2 and up). 

[football.js](https://github.com/geraldb/football.js) - Free, open source football widgets - matchday, today's rounds, team of the day, etc.

Any others? Let us know on the [mailing list/forum](http://groups.google.com/group/opensport). Thanks!


## Alternatives

[openLigaDB](http://www.openligadb.de) -  free community-contributed sport results available via XML/SOAP HTTP web service; data/database not available for download

[SportsDB](http://www.sportsdb.org)  - archive (no more activity); open database schema for sports data (formerly known as XTOSS: The XML Team Open Sports Schema.)


Any others? Let us know on the [mailing list/forum](http://groups.google.com/group/opensport). Thanks!


## License {#license}

The `football.db` schema, data and scripts are dedicated to the public domain.
Use it as you please with no restrictions whatsoever.


{% include questions.md %}
