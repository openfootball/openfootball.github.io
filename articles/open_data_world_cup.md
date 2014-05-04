

# Using open football data: Get ready for the World Cup in Brazil 2014.


Football is the world's most popular sport and
the World Cup in Brazil - kicking off next month in São Paulo on June 12th
(in 38 days 3 hours 15 minutes and counting) - 
is the world's biggest (sport) event with 32 national teams
from six continents competing in 64 matches in 12 cities for the championship title.


## Where's the open football data? Let's ask the intertubes.
 
Now lets say you want to build a world cup match day widget for
your site using a web service (HTTP JSON API) that gets
you all teams, groups, matches, players, and so on.

Example - HTTP JSON API:

~~~
GET /event/worldcup.2014/teams

{
  "event": {
    "key":   "worldcup.2014", "title": "World Cup 2014"
  },
  "teams": [
    { "key": "gre", "title": "Greece",      "code": "GRE" },
    { "key": "ned", "title": "Netherlands", "code": "NED" },
    { "key": "ger", "title": "Germany",     "code": "GER" },
    { "key": "por", "title": "Portugal",    "code": "POR" },
    ...
  ]
}
~~~

Ideally, there's a free service using open football data from the world football federation,
from the world's sport cable channels, from the world's sport newspapers, and so on.
Let's ask the intertubes to find out the state of open football data in the real world - 
let's google [`json world cup brazil`](http://www.google.com/search?q=json+world+cup+brazil)
or post a question on the open data stackexchange ['Q: Any Open Data Sets for the (Football) World Cup (in Brazil 2014)?'](http://opendata.stackexchange.com/questions/1791/any-open-data-sets-for-the-football-world-cup-in-brazil-2014).

Nothing. Nada. Nichts. Niente. Zilch. Zero.
So what? Let's build an open football data project.



## What's `football.db?`

Let's welcome `football.db`. An open football data project
offering - suprise, suprise - free open public domain
football data for the World Cup in Brazil 2014, and more.

![](i/worldcup2014-db-download.png)

The open football project also sports a free self-hosted HTTP JSON API service
for football data, for example. Get started in two steps:

- Step 1: Download the `worldcup2014.db` SQLite Database
- Step 2: Serve up teams, rounds, matches, etc. via HTTP JSON API using the `sportdb` command line tool

~~~
$ sportdb serve
~~~

Services available include:

- `/event/world.2014/teams`    -- List all teams
- `/event/world.2014/rounds`   -- List all rounds (matchdays)
- `/event/world.2014/round/20` -- List all matches in a round e.g. - 20th Round (=> Final) 

~~~
GET /event/world.2014/round/1

{
  "event": { "key": "world.2014", "title": "World Cup 2014" },
  "round": { "pos": 1, "title": "Matchday 1" },
  "games": [
    {
      "team1_key": "bra",
      "team1_title": "Brazil",
      "team1_code": "BRA",
      "team2_key": "cro",
      "team2_title": "Croatia",
      "team2_code": "CRO",
      "play_at": "2014/06/12",
      "score1": null,
      "score2": null,
      "score1ot": null,
      "score2ot": null,
      "score1p": null,
      "score2p": null
    }
  ]
}
~~~

## How does it work?  Distributed is the new centralized

The open football data project collects public domain data sets
in plain old text files that you store on your hard disk
and that you can share with a distributed version tracker (that is, git repos)
with your friends or the world.
A free public domain command line tool (that is, `sportdb`)
lets you read the plain text data sets into your SQL database of choice 
(for example, MySQL, PostgreSQL, SQLite, etc).


![](i/github-openfootball-worldcup.png)

###  Example: `europe/teams.txt` - Comma-separated values

Let's look at a plain text file for national teams in Europe, for example:

~~~
############
# UEFA (Union of European Football Associations)
# - 54 members

aut, Austria, AUT, at, fifa|uefa
bel, Belgium, BEL, be, fifa|uefa
cyp, Cyprus,  CYP, cy, fifa|uefa
...
~~~

(Source:  [europe/teams.txt](https://github.com/openfootball/national-teams/blob/master/europe/teams.txt))

The plain text file uses the comma-separated values (CSV) format
with some extras for comments, blank lines, etc.


###  Example: `worldcup/2014/cup.txt` -  Mini football data language 

For match schedules the open football project use a new strutured data format,
that is, a new domain-specific language (DSL).

Example - Open Football Match Schedule Language:

~~~
(1) Thu Jun/12 17:00   Brazil - Croatia    @ Arena de São Paulo, São Paulo (UTC-3)
(2) Fri Jun/13 13:00   Mexico - Cameroon   @ Estádio das Dunas, Natal (UTC-3)
~~~

(Source:  [world-cup/2014/cup.txt](https://github.com/openfootball/world-cup/blob/master/2014--brazil/cup.txt))


Why invent yet another data format?
The new mini language for structured football match schedule data
offers you the best of both worlds, that is,
1) looks n feels like free-form plain text - easy-to-read and easy-to-write -
2) but offers a 100-% data accuracy guarantee (when loading into SQL tables, for example).

The mini language also includes
 support for groups, matchdays, grounds, and more. Example:

~~~
############################
# World Cup 2014 Brazil

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
Matchday 3  |  Sat Jun/14
...

(16) Round of 16            |  Sat Jun/28 - Tue Jul/1
(17) Quarter-finals         |  Fri Jul/4 - Sat Jul/5
(18) Semi-finals            |  Tue Jul/8 - Wed Jul/9
(19) Match for third place  |  Sat Jul/12
(20) Final                  |  Sun Jul/13


Group A:

(1) Thu Jun/12 17:00   Brazil - Croatia       @ Arena de São Paulo, São Paulo (UTC-3)
(2) Fri Jun/13 13:00   Mexico - Cameroon      @ Estádio das Dunas, Natal (UTC-3)

(17) Tue Jun/17 16:00   Brazil - Mexico        @ Estádio Castelão, Fortaleza (UTC-3)
(18) Wed Jun/18 18:00   Cameroon - Croatia     @ Arena Amazônia, Manaus (UTC-4)

(33) Mon Jun/23 17:00   Cameroon - Brazil      @ Brasília (UTC-3)
(34) Mon Jun/23 17:00   Croatia  - Mexico      @ Recife (UTC-3)


Group B:

(3) Fri Jun/13 16:00   Spain - Netherlands     @ Arena Fonte Nova, Salvador (UTC-3)
(4) Fri Jun/13 18:00   Chile - Australia       @ Arena Pantanal, Cuiabá (UTC-4)

(19) Wed Jun/18 16:00   Spain - Chile             @ Estádio do Maracanã, Rio de Janeiro (UTC-3)
(20) Wed Jun/18 13:00   Australia - Netherlands   @ Estádio Beira-Rio, Porto Alegre (UTC-3)

(35) Mon Jun/23 13:00   Australia - Spain         @ Curitiba (UTC-3)
(36) Mon Jun/23 13:00   Netherlands - Chile       @ São Paulo (UTC-3)
...
~~~

Interested?  Find out more at the [project site](https://github.com/openfootball)
or post your questions or comments to the [forum/mailing list](http://groups.google.com/group/opensport). Thanks.



## Appendix: Basics - What's (Not) Open (Structured) Data?


What's (Not) Open (Structured) Data?

Example 1:

- A Free One-Page Booklet (PDF) Download for the Match Schedule from [`fifa.com`](http://fifa.com/worldcup/matches).
  - Copyright © FIFA 2014. All Rights Reserved.

![](i/fifa-match-schedule-download.png)

Example 2a:

- Match Schedule on FIFA Website

![](i/fifa-match-schedule.png)

Example 2b:

- Match Schedule on FIFA Website (Source - Document Object Model Tree)

![](i/fifa-match-schedule-inside.png)

Example 3a:

- Match Schedule on Wikipedia

![](i/wikipedia-worldcup.png)

Example 3b:

- Match Schedule on Wikipedia (Source - Plain Text or Mediawiki Text)

Cut-n-Paste Text:

~~~
12 June 2014  17:00   Brazil    Match 1   Croatia    Arena de São Paulo, São Paulo
13 June 2014  13:00   Mexico    Match 2   Cameroon   Arena das Dunas, Natal
17 June 2014  16:00   Brazil    Match 17  Mexico     Estádio Castelão, Fortaleza
18 June 2014  19:00   Cameroon  Match 18  Croatia    Arena Amazônia, Manaus
23 June 2014  17:00   Cameroon  Match 33  Brazil     Estádio Nacional Mané Garrincha, Brasília
23 June 2014  17:00   Croatia   Match 34  Mexico     Arena Pernambuco, Recife
~~~

Wikipedia Source:

~~~
===Group A===
{{{{main|2014 FIFA World Cup Group A}}}}
{{{{Fb cl2 header navbar}}}}
{{{{Fb cl2 team |t={{{{fb|BRA}}}} |w=0 |d=0 |l=0 |gf=0 |ga=0 |bc=}}}}
{{{{Fb cl2 team |t={{{{fb|CRO}}}} |w=0 |d=0 |l=0 |gf=0 |ga=0 |bc=|border=green}}}}
{{{{Fb cl2 team |t={{{{fb|MEX}}}} |w=0 |d=0 |l=0 |gf=0 |ga=0 |bc=}}}}
{{{{Fb cl2 team |t={{{{fb|CMR}}}} |w=0 |d=0 |l=0 |gf=0 |ga=0 |bc=}}}}
|}

{{{{Football box
|date=12 June 2014
|time=17:00
|team1={{{{fb-rt|BRA}}}}
|score=[[2014 FIFA World Cup Group A#Brazil v Croatia|Match 1]]
|report=
|team2={{{{fb|CRO}}}}
|goals1=
|goals2=
|stadium=[[Arena Corinthians|Arena de São Paulo]], [[São Paulo]]
|attendance=
|referee=
}}}}
{{{{Football box
|date=13 June 2014
|time=13:00
|team1={{{{fb-rt|MEX}}}}
|score=[[2014 FIFA World Cup Group A#Mexico v Cameroon|Match 2]]
|report=
|team2={{{{fb|CMR}}}}
|goals1=
|goals2=
|stadium=[[Arena das Dunas]], [[Natal, Rio Grande do Norte|Natal]]
|attendance=
|referee=
}}}}
~~~

