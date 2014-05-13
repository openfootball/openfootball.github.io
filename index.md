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
        * [Euro / European Football Championship](#national-teams)
    * [Football Clubs](#clubs)
        * [Copa Libertadores](#clubs)
        * [Copa Sudamericana](#clubs)
        * [Champions League](#clubs)
        * [Europa League](#clubs)
* [Tables, Schema](#schema)
* [Talks - Slide Decks](#talks)
* [About, License](#license)
* [Questions? Comments?](#questions)
</div>


## What's `football.db`?   {#whatis}

A free open public domain football (soccer) database & schema
for use in any (programming) language
(e.g. uses plain text fixtures/data sets). Example:

~~~
### Teams

barcelona, Barcelona|FC Barcelona|Fútbol Club Barcelona, BAR, city:barcelona
madrid,    Real Madrid|Real Madrid CF,                   RMD, city:madrid
malaga,    Málaga|FC Málaga|Málaga CF|CF Málaga,         MAG, city:malaga
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

Example - FIFA World Cup 2014:

~~~
Group A  |  Brazil       Croatia              Mexico         Cameroon
Group B  |  Spain        Netherlands          Chile          Australia
Group C  |  Colombia     Greece               Côte d'Ivoire  Japan
Group D  |  Uruguay      Costa Rica           England        Italy
Group E  |  Switzerland  Ecuador              France         Honduras
Group F  |  Argentina    Bosnia-Herzegovina   Iran           Nigeria
Group G  |  Germany      Portugal             Ghana          United States
Group H  |  Belgium      Algeria              Russia         South Korea

Matchday 1  |  Thu Jun/12
Matchday 2  |  Fri Jun/13
..
(16) Round of 16            |  Sat Jun/28 - Tue Jul/1
(17) Quarter-finals         |  Fri Jul/4 - Sat Jul/5
(18) Semi-finals            |  Tue Jul/8 - Wed Jul/9
(19) Match for third place  |  Sat Jul/12
(20) Final                  |  Sun Jul/13


Group A:

(1) Thu Jun/12 17:00    Brazil - Croatia       @ Arena de São Paulo, São Paulo (UTC-3)
(2) Fri Jun/13 13:00    Mexico - Cameroon      @ Estádio das Dunas, Natal (UTC-3)

(17) Tue Jun/17 16:00   Brazil - Mexico        @ Estádio Castelão, Fortaleza (UTC-3)
(18) Wed Jun/18 18:00   Cameroon - Croatia     @ Arena Amazônia, Manaus (UTC-4)
...
~~~

Source: [`world-cup/2014/cup.txt`](https://github.com/openfootball/world-cup/blob/master/2014--brazil/cup.txt)



### America (South America; North America, Central America and the Caribbeans)

- CONMEBOL¹ Copa América

<!-- use "handmade" footnotes; always work no fallback needed -->

¹ CONMEBOL = South America; 

[More »](https://github.com/openfootball/copa-america)


- CONCACAF¹ Copa Oro / Gold Cup

<!-- use "handmade" footnotes; always work no fallback needed -->

¹ CONCACAF = North America, Central America and the Caribbeans

[More »](https://github.com/openfootball/north-america-gold-cup)



### Africa

- CAF Africa Cup of Nations

[More »](https://github.com/openfootball/africa-cup)

### Europe

- UEFA Euro / European Football Championship

[More »](https://github.com/openfootball/euro-cup)



## Football Clubs / Leagues and Tournaments  {#clubs}

### Intn'l Club Tournaments (Champions Leagues & Friends) 

#### Amercia (South America; North America, Central America and the Caribbeans)

- CONMEBOL¹ Copa Libertadores
- CONMEBOL¹ Copa Sudamericana

<!-- use "handmade" footnotes; always work no fallback needed -->

¹ CONMEBOL = South America; 

[More »](https://github.com/openfootball/copa-libertadores) | 
[More »](https://github.com/openfootball/copa-sudamericana)

- CONCACAF¹ Champions League 

<!-- use "handmade" footnotes; always work no fallback needed -->

¹ CONCACAF = North America, Central America and the Caribbeans

[More »](https://github.com/openfootball/north-america-champions-league)



#### Europe

- UEFA Champions League
- UEFA Europa League

[More »](https://github.com/openfootball/europe-champions-league)


Example - Champions League 2012/13:

~~~
####################################
# Champions League 2012/13 - Finalrunden

(8)  Achtelfinale Rückspiele  // Di./Mi., 5.+6./12.+13. Mär 2013

2013-03-05 20:45  Manchester United    1-2  Real Madrid
2013-03-05 20:45  Borussia Dortmund    3-0  Schachtar Donezk

2013-03-06 20:45  Paris Saint-Germain  1-1  Valencia
2013-03-06 20:45  Juventus             2-0  Celtic Glasgow

2013-03-12 20:45  Schalke 04           2-3  Galatasaray
2013-03-12 20:45  Barcelona            4-0  Milan

2013-03-13 20:45  Málaga               2-0  Porto
2013-03-13 20:45  Bayern München       0-2  Arsenal
...
~~~

Source: [`europe-champions-league/2012_13/cl_finals.txt`](https://github.com/openfootball/europe-champions-league/blob/master/2012_13/cl_finals.txt)


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



## Talks - Slide Decks  {#talks}

- [Using Open Football Data - Get Ready for the World Cup in Brazil 2014 w/ JavaScript](https://github.com/openfootball/openfootball.github.io/blob/master/talks/open_data_world_cup_with_js.md)  (Vienna.js, 2014)
- [Using Open Football Data - Get Ready for the World Cup in Brazil 2014 w/ Ruby](https://github.com/openfootball/openfootball.github.io/blob/master/talks/open_data_world_cup.md) (Vienna.rb, 2014)
- [`football.db` - Using Open Football Data in JavaScript](https://github.com/openfootball/openfootball.github.io/blob/master/talks/football_db_intro.md)  (Vienna.js, 2013)



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

[Sportbook](https://github.com/openbookie/sportbook) - Free, open source sports betting pool in Ruby on Rails (version 3.2 and up). 

[football.js](https://github.com/footballjs) - Free, open source football widgets - matchday, today's rounds, team of the day, etc.

Any others? Let us know on the [mailing list/forum](http://groups.google.com/group/opensport). Thanks!


## Alternatives

[openLigaDB](http://www.openligadb.de) -  free community-contributed sport results available via XML/SOAP HTTP web service; database not available for download

[SportsDB](http://www.sportsdb.org)  - archive (no more activity); open database schema for sports data (formerly known as XTOSS: The XML Team Open Sports Schema.)


Any others? Let us know on the [mailing list/forum](http://groups.google.com/group/opensport). Thanks!


## License {#license}

The `football.db` schema, data and scripts are dedicated to the public domain.
Use it as you please with no restrictions whatsoever.

{% include questions.md %}
