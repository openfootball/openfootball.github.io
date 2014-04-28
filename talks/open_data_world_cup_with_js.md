title:  Using Open Football Data - Get Ready for the World Cup in Brazil 2014 w/ Ruby


# Using Open Football Data - Get Ready for the World Cup in Brazil 2014 w/ JavaScript

### Agenda


# Basics - What's the World Cup in Brazil 2014 (June/12th - July/13rd)?

Starts in

## 43 days 3 hours 15 minutes

The World's Biggest (Sport) Event

## 32 teams 64 matches 25 matchdays 12 cities

- 32 teams --  Australia, Iran, Japan, South Korea,
   Algeria, Cameroon, Ghana, Ivory Coast, Nigeria,
   Costa Rica, Honduras, Mexico, United States,
   Argentina, Brazil, Chile, Colombia, Ecuador,
   Uruguay, Belgium, Bosnia and Herzegovina,
   Croatia, England, France, Germany,
   Greece, Italy, Netherlands, Portugal,
   Russia, Spain, Switzerland

- 12 cities  -- Rio de Janeiro, São Paulo, Brasília, Fortaleza,
  Belo Horizonte, Porto Alegre, Salvador, Recife,
  Cuiabá, Manaus, Natal, Curitiba




# Basics - What's Open Data? - Terms of Use

Open (Free) Data    <==>   Copyright © FIFA 2014. All Rights Reserved.

Example 1:

- A Free One-Page Booklet (PDF) Download for the Match Schedule from [FIFA.com](http://fifa.com/worldcup).
    - Copyright © FIFA 2014. All Rights Reserved.

![](i/fifa-match-schedule-download.png)



# Basics - What's Open Data? - Terms of Use (Cont.)

Open (Free) Data    <==>   Copyright © FIFA 2014. All Rights Reserved.

Example 2:

- A Free SQLite DB Download for the Match Schedule from [`github.com/openfootball`](https://github.com/openfootball/build/releases).
    - Public Domain. No Copyright. No License. No Rights Reserved. 

![](i/worldcup2014-db-download.png)

Q: Best "License" for Open Data?

A: Public Domain (No License. No Copyright. No Rights Reserved.) [1]

Q: Why?

A: Keep it simple. [2]

[1] also sometimes "rebranded" or known as Creative Commons Zero (CC0) or Unlicense.
[2] Full "License" Text: The data, schema and scripts are dedicated to the public domain. Use it as you please with no restrictions whatsoever.



# Basics - What's Structured Data? Ex. FIFA Web Page

Structured Data <==> Free-Style Text

Example 1:

- Match Schedule on FIFA Website

![](i/fifa-match-schedule.png)



# Basics - What's Structured Data?  Ex. FIFA Web Page (Cont.)

Structured Data <==> Free-Style Text

Example 1:

- Match Schedule on FIFA Website
    - Show Source (Try Screen Scrapping Document Object Model? Why? Why Not?)

![](i/fifa-match-schedule-inside.png)



# Basics - What's Structured Data?  Ex. Wikipedia

Structured Data <==> Free-Style Text

Example 2:

- Match Schedule on Wikipedia

![](i/wikipedia-worldcup.png)



# Basics - What's Structured Data?  Ex. Wikipedia (Cont.)

Structured Data <==> Free-Style Text

Example 2:

- Match Schedule on Wikipedia
    - Show Source (Try Scrapping Free-Style Text? Why? Why Not?)

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
{{main|2014 FIFA World Cup Group A}}
{{Fb cl2 header navbar}}
{{Fb cl2 team |t={{fb|BRA}} |w=0 |d=0 |l=0 |gf=0 |ga=0 |bc=}}
{{Fb cl2 team |t={{fb|CRO}} |w=0 |d=0 |l=0 |gf=0 |ga=0 |bc=|border=green}}
{{Fb cl2 team |t={{fb|MEX}} |w=0 |d=0 |l=0 |gf=0 |ga=0 |bc=}}
{{Fb cl2 team |t={{fb|CMR}} |w=0 |d=0 |l=0 |gf=0 |ga=0 |bc=}}
|}

{{Football box
|date=12 June 2014
|time=17:00
|team1={{fb-rt|BRA}}
|score=[[2014 FIFA World Cup Group A#Brazil v Croatia|Match 1]]
|report=
|team2={{fb|CRO}}
|goals1=
|goals2=
|stadium=[[Arena Corinthians|Arena de São Paulo]], [[São Paulo]]
|attendance=
|referee=
}}
{{Football box
|date=13 June 2014
|time=13:00
|team1={{fb-rt|MEX}}
|score=[[2014 FIFA World Cup Group A#Mexico v Cameroon|Match 2]]
|report=
|team2={{fb|CMR}}
|goals1=
|goals2=
|stadium=[[Arena das Dunas]], [[Natal, Rio Grande do Norte|Natal]]
|attendance=
|referee=
}}
~~~



# Basics - What's Structured Data?  - "Classic" Format Options

Structured Data <==> Free-Style Text

"Classic" Structured Data Formats:

- JSON (Yeah!)
- CSV Comma-Separated Values
- SQL
- XML
- YAML
- RDF Triplets
- and others



# Basics - What's Structured Data? - "New" Format Options

Structured Data <==> Free-Style Text

but also

"New" Structured Data Formats:

- DSLs,
    - that is, Mini Languages for Structured Data
       - (ex. Open Football Match Schedule Language)

~~~
(1) Thu Jun/12 17:00   Brazil - Croatia    @ Arena de São Paulo, São Paulo (UTC-3)
(2) Fri Jun/13 13:00   Mexico - Cameroon   @ Estádio das Dunas, Natal (UTC-3)
~~~

([Source: openfootball/world-cup/2014/cup.txt](https://github.com/openfootball/world-cup/blob/master/2014/cup.txt))

Q: Why?

A: Best of both worlds, that is, looks almost like free-form plain text but
offers a 100-% data accuracy guarantee (when loading into SQL tables, for example).


# Basics - What's Structured Data? - "New" Format Options

Mini Languages for Structured Data - Open Football Match Schedule Language

Example:

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

([Source: openfootball/world-cup/2014/cup.txt](https://github.com/openfootball/world-cup/blob/master/2014/cup.txt))









