---
layout: default
title: News and Updates
---

# {{ page.title }}


## New Repo - `/docs` - for Documentation (Articles, Tips & Tricks, Notes, Examples, etc.)

Added a new repo, that is, [`/docs`](https://github.com/openfootball/docs) - to collect 
all the documentation in one place and make it easier to contribute.
Still in an early stage the first pages include:

- Intro - football.db - What? Why? 
- SQL Queries Examples 
- HTTP JSON API Intro 

Thanks again to Joe Kampschmidt for the first docu contribution,
that is, notes on a couple of SQL query examples for the world cup.


## sportdb Update v1.9.4 - Adds `clubs.txt`, Week 1 Round Headers, `en/2013-14/pl.txt`, etc.

What's news? sportdb command line tool updates:

- Added `clubs.txt` as an alternative for `teams.txt` (recommended for football clubs
    otherwise clubs might get flagged as national teams and not as clubs). 
- Added `2013-14` as an alternative for `2013_14` in your 
    fixture path (e.g. `2013-14/1-premierleague-i.txt` now works).
- Added Week 1 or Week 5 and so on in your match schedule (in 
    English/en) for matchday/round headers. 


## New Org - `football.csv` - Football Match Data in CSV (Comma-Separated Values) Format e.g. `Arsenal, Liverpool, 2-0, 1-0`

Added a new GitHub org, that is, [`football.csv`](https://github.com/footballcsv),
that collects football match data in the CSV (comma-separated  values) format for easy (re)use and started adding all seasons for the English Premier League, the Football League (Championship, League One, League Two), etc.
to the new [`/en-england`](https://github.com/footballcsv/en-england) repo.



## New Country Repo - `/ch-confoederatio-helvetica` - for Switzerland incl. Super League 2014/15 etc.

Added a new country repo, that is, [`/ch-confoederatio-helvetica`](https://github.com/openfootball/ch-confoederatio-helvetica) -
for Switzerland (Schweiz, Suisse, Svizzera, Svizra) incl. Lichtenstein.
Added the Super League Match Schedule for 2014/15. Example: 

~~~
Spieltag 1 

[Sa 19.7.] 
  17.45   FC Aarau       1:2 (0:2)  FC Basel             @ Brügglifeld, Aarau
            [Schultz 85'; Embolo 15' Aliji 38'] 
  20.00   FC St. Gallen  2:2 (1:1)  BSC Young Boys       @ AFG Arena, St. Gallen
              [Cavusevic 14' Gajic  52' (ET); Kubo 23' Afum 90' ] 
...
~~~


## New Season - English Premier League 2014/15 Schedule (and Some Club Squads e.g. `arsenal.txt`) Added

Added the new 2014/15 season for the English Premier League plus
started adding the squad players for Arsenal, as an example: 

~~~
(1)     Wojciech Szczęsny (POL)    GK  2007-

(3)     Kieran Gibbs               DF  2007-
(4)     Per Mertesacker (GER)      DF  2011-
(5)  (c) Thomas Vermaelen (BEL)    DF  2009-
(6)     Laurent Koscielny (FRA)    DF  2010- 
(18)    Nacho Monreal (ESP)        DF  2013- 
(25)    Carl Jenkinson             DF  2011- 

(7)     Tomáš Rosický (CZE)        MF  2006-  
(8)     Mikel Arteta (ESP)         MF  2011-
(10)    Jack Wilshere (ENG)        MF  2008-
(11)    Mesut Özil (GER)           MF  2013-
(16)    Aaron Ramsey (WAL)         MF  2008-
(19)    Santi Cazorla (ESP)        MF  2012-
(20)    Mathieu Flamini (FRA)      MF  2013-
(24)    Abou Diaby (FRA)           MF  2006-
(35)    Gedion Zelalem (GER)       MF  2013-
        Francis Coquelin (FRA)     MF  2008-

(9)     Lukas Podolski (GER)       FW  2012-
(12)    Olivier Giroud (FRA)       FW  2012-
(14)    Theo Walcott               FW  2006-
(15)    Alex Oxlade-Chamberlain    FW  2011-
(17)    Alexis Sánchez (CHI)       FW  2014-
...
~~~


## sportdb Update v1.9.3 - Added Better Squads Reader (Auto-Creates Missing Players)

What's news? sportdb command line updates: 

The squads (rosters)reader will now auto-add missing players.
Try it, for example, using the World Cup 1930 squads e.g.:

~~~
$ rake update DATA=history     # reads all world cups from 1930 to 2010 
~~~

Squads get added to the rosters join table (one record per player) 
and missing players get auto-added to the persons table. Still a little rough and early stage.



## New Repo - `/build-shell` - for Building your own `football.db` Copy using Shell Scripts

Added new repo, that is, [`/build-shell`](https://github.com/openfootball/build-shell) for
building your own up-to-date `football.db` copy from the latest datasets using shell scripts.
Thanks to Joe Kampschmidt to get it all started and the write-up and the shell script.



## New Command Line Tool - `ojogo` gem - Who's Playing Today?

Added new command line tool, that is, [`ojogo`](https://github.com/sportdb/ojogo.ruby)
that prints today's matches for the World Cup 2014 in Brazil
using the football.db HTTP JSON API service. For example, typing on Jun/29 

~~~
$ ojogo    # defaults to today's world cup 2014 matches 
~~~

will print 

~~~
Netherlands (NED) vs Mexico (MEX) 
Costa Rica (CRC) vs Greece (GRE) 
~~~


## sportdb Update v1.9.2 - Added Match Goals Reader e.g. `[Messi 3', 45+1']` etc.

What's news? sportdb command line updates: 

The match schedule reader now will add goals (plus auto-add missing 
players). All still a little rough but working without any (extra) configuration. Example: 

~~~
(1) Thu Jun/12 17:00   Brazil 3-1 (1-1) Croatia       @ Arena de São Paulo, São Paulo
        [Neymar 29', 71' (pen.) Oscar 90+1';  Marcelo 11' (o.g.)] 
~~~

The reader will add four goal records (see the table goals w/ fields such as 
`player_id`, `team_id`, `minute`, `offset`, `score1`, `score2` etc.): 

~~~
1 |   Marcelo  11'   (o.g.)   1-0   Croatia (Team 2) 
2 |   Neymar   29'            1-1   Brazil  (Team 1) 
3 |   Neymar   71'   (pen.)   2-1   Brazil  (Team 1) 
4 |   Oscar    90'+1'         3-1   Brazil  (Team 1)
~~~


## New Org - `wikiscript` - Open Data Scripts for Wikipedia (e.g `football.squads.ruby` - World Cup 2014 Squads Update)

Added a new GitHub org, that is, [`wikiscript`](https://github.com/wikiscript)
that collects scripts that let you turn free-style or semi-structured 
wiki text into open structured data. 

A first example is the new [football squads reader](https://github.com/wikiscript/football.squads.ruby)
that reads in a wikitext page e.g 

~~~
{% raw %}
{{nat fs player|no=1|pos=GK|name=[[Jefferson de Oliveira 
Galvão|Jefferson]]|age={{Birth date and 
age2|2014|6|12|1983|1|2|df=y}}|caps=9|club=[[Botafogo de Futebol e 
Regatas|Botafogo]]|clubnat=BRA}} 
{{nat fs player|no=2|pos=DF|name=[[Dani Alves]]|age={{Birth date and 
age2|2014|6|12|1983|5|6|df=y}}|caps=74|club=[[FC 
Barcelona|Barcelona]]|clubnat=ESP}} 
...
{% endraw %}
~~~

and outputs all squads files in the `football.db` format:

~~~
(1)  GK   Jefferson        #   9, Botafogo (BRA)
(2)  DF   Dani Alves       #  74, Barcelona (ESP)
... 
~~~


## New Org - `rsssf` -  RSSSF (Rec.Sport.Soccer Statistics Foundation) Archive Data Imports for `football.db`

Added a new GitHub org, that is, [`rsssf`](https://github.com/rsssf) - hosting
RSSSF archive data that you can read into your SQL database of choice (SQLite, PostgreSQL, etc.).
Still early and a little rough - as always expect surprises. 

What's the [RSSSF (Rec.Sport.Soccer Statistics Foundation)](http://www.rsssf.com)?

The RSSSF collects and offers football league tables from all over the world in plain text. Example: 

~~~
Round 1
[May 25]
Vasco da Gama   1-0 Portuguesa
 [Carlos Tenório 47']
Vitória         2-2 Internacional
 [Maxi Biancucchi 2', Gabriel Paulista 11'; Diego Forlán 29', Fred 63']
Corinthians     1-1 Botafogo
 [Paulinho 73'; Rafael Marques 24']
... 
~~~

