---
layout: default
title: Welcome
---

# {{ page.title }}

<div class="toc" markdown="1">
Contents:

* [What's `football.db`?](#whatis)
* [Web Admin Site](#webadmin)
* [Leagues and Tournaments](#national-teams)
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
* [More](#more)
* [Talks - Slide Decks](#talks)
* [About, License](#license)
* [Questions? Comments?](#questions)
</div>


## What's `football.db`?   {#whatis}

A free and open public domain football database & schema
for use in any (programming) language (e.g. uses plain datasets).

**Dataset Examples**

```
### Teams

barcelona, Barcelona|FC Barcelona|Fútbol Club Barcelona, BAR
madrid,    Real Madrid|Real Madrid CF,                   RMD
malaga,    Málaga|FC Málaga|Málaga CF|CF Málaga,         MAG
...
```


```
### Matches

Quarter-finals - 1st Leg

[Tue Apr/1]
  20.45   FC Barcelona        1-1  Atlético Madrid     @ Camp Nou, Barcelona
            [Neymar 71'; Diego 56']
  20.45   Manchester United   1-1  Bayern München      @ Old Trafford, Manchester
            [Vidić 58'; Schweinsteiger 67']
[Wed Apr/2]
  20.45   Real Madrid         3-0  Borussia Dortmund   @ Santiago Bernabéu, Madrid
            [Bale 3' Isco 27' Ronaldo 57']
  20.45   Paris Saint-Germain 3-1  Chelsea FC          @ Parc des Princes, Paris
            [Lavezzi 4' Luiz 61' (o.g.) Pastore 90+3'; Hazard 27' (pen.)]

...
```

**Schema Diagram**

![](i/footballdb-models.png)


## Web Admin Site Example {#webadmin}

Try the `football.db` web admin app running
on Heroku [`footballdb.herokuapp.com`](http://footballdb.herokuapp.com).



## National Teams / Leagues and Tournaments   {#national-teams}

### World

- FIFA World Cup
- FIFA World Cup Qualifiers
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
...


Group A:

(1) Thu Jun/12 17:00 Brazil  3-1 (1-1)  Croatia    @ Arena de São Paulo, São Paulo (UTC-3)
                      [Neymar 29', 71' (pen.) Oscar 90+1'; Marcelo 11' (o.g.)]

(2) Fri Jun/13 13:00 Mexico  1-0 (0-0)  Cameroon   @ Estádio das Dunas, Natal (UTC-3)
                      [Oribe Peralta 61']

...

Match for third place

(63) Sat Jul/12 17:00 Brazil  0-3 (0-2)  Netherlands   @ Estádio Nacional Mané Garrincha, Brasília (UTC-3)
                       [-; Robin Van Persie 3' (pen.) Daley Blind 17' Georginio Wijnaldum 90+1']

Final

(64) Sun Jul/13 16:00 Germany  1-0 a.e.t. (0-0, 0-0)  Argentina  @ Estádio do Maracanã, Rio de Janeiro (UTC-3)
                        [Mario Götze 113']
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
##############################
# Champions League 2012/13

Round of 16 - 2nd Leg // Tu+We, 5.+6./12.+13. Mar 2013

[Tue Mar/5]
  20.45 Manchester United  1-2  Real Madrid        @ Old Trafford, Manchester
          [S. Ramos 48' (o.g.); L. Modric 66' C. Ronaldo 69']
  20.45 Borussia Dortmund  3-0  Schachtar Donezk   @ Signal Iduna Park, Dortmund
          [F. Santana 31' M. Götze 37' J. Blaszczykowski 59']
[Wed Mar/6]
  20.45 Paris Saint-Germain  1-1  Valencia         @ Parc des Princes, Paris
           [E. Lavezzi 66'; Jonas 55']
  20.45 Juventus             2-0  Celtic Glasgow   @ Juventus Stadium, Turin
           [A. Matri 24' F. Quagliarella 65']

[Tue Mar/12]
  20.45 Schalke 04        2-3  Galatasaray      @ Veltins-Arena, Gelsenkirchen
           [R. Neustädter 17' M. Bastos 63'; Hamit Altintop 37' Burak Yilmaz 42' U. Bulut 95']
  20.45 Barcelona         4-0  Milan            @ Camp Nou, Barcelona
           [L. Messi 5', 40' D. Villa 55' Jordi Alba 92']
[Wed Mar/13]
  20.45 Málaga            2-0  Porto            @ La Rosaleda, Málaga
           [Isco 43' R. Santa Cruz 77']
  20.45 Bayern München    0-2  Arsenal          @ Allianz Arena, München
           [-; Giroud 3' L. Koscielny 86']
...
~~~

Source: [`europe-champions-league/2012-13/cl_finals.txt`](https://github.com/openfootball/europe-champions-league/blob/master/2012-13/cl_finals.txt)


### National Leagues & Cups

#### Europe

- Österreichische Bundesliga + ÖFB Cup
- English Premier League
- Deutsche Bundesliga
- Spanish La Liga

#### North America

- México Primera División Apertura + Clausura

#### South America

- Campeonato Brasileiro Série A

and more.


## More {#more}

- [Starter Kits](https://github.com/sportkit)
- [football.js (Widgets)](https://github.com/footballjs)    
- [The Free World Football Almanac](https://github.com/footballbook)


## Talks - Slide Decks  {#talks}

- [Using Open Football Data - Get Ready for the World Cup in Brazil 2014 w/ JavaScript](https://github.com/geraldb/talks/blob/master/open_data_world_cup_with_js.md)  (Vienna.js, 2014)
- [Using Open Football Data - Get Ready for the World Cup in Brazil 2014 w/ Ruby](https://github.com/geraldb/talks/blob/master/open_data_world_cup.md) (Vienna.rb, 2014)
- [`football.db` - Using Open Football Data in JavaScript](https://github.com/geraldb/talks/blob/master/football_db_intro.md)  (Vienna.js, 2013)



## Real World Usage

[sport.db Web Admin](https://github.com/sportdb/sport.db.admin) - `sport.db` Web Admin Tool in Ruby on Rails (version 3.2 and up).

[Sportbook](https://github.com/openbookie/sportbook) - Free, open source sports betting pool in Ruby on Rails (version 3.2 and up).

[football.js](https://github.com/footballjs) - Free, open source football widgets - matchday, today's rounds, team of the day, etc.

Any others? Let us know on the [mailing list/forum](http://groups.google.com/group/opensport). Thanks!


## Alternatives

See the [`awesome-football`](https://github.com/planetopendata/awesome-football) page at the Planet Open Data.



## Alumnis - Thank You!

_Thanks for helping with match updates! Come back soon._

{% include thanks.html %}

<!-- break -->



## License {#license}

The `football.db` schema, data and scripts are dedicated to the public domain.
Use it as you please with no restrictions whatsoever.

{% include questions.md %}
