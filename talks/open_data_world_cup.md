title:  Using Open Football Data - Get Ready for the World Cup in Brazil w/ Ruby



# Using Open Football Data - Get Ready for the World Cup in Brazil w/ Ruby

### Agenda




# World Cup in Brazil 2014

When:
- 25 (match)days  -- 12 June - 13 July

Where:
- 12 cities  -- Rio de Janeiro, São Paulo, Brasília, ...

Teams:
- 32 teams --  Brazil, Belgium, Japan, Costa Rica, Ghana, ...

Matches:
- 64 matches

The world's biggest sport event



# The State of Open Data - World Cup in Brazil 2014

Q: Where can I get the teams, groups, match schedule (fixtures),
players, stadiums lets say in CSV, SQL, JSON?

Q: Where can I download lets say `world-cup-2014.db`?

Let's search (google):

- `open data world cup brazil`  or
- `json world cup brazil`

Nothing. Nada. Nichts. Niente. Zilch. Zero.



# The State of Open Data - World Cup in Brazil 2014 (Cont.)


### Official FIFA Site -- ([`fifa.com/worldcup`](http://www.fifa.com/worldcup)):

=> No open data. Offers a booklet¹ (PDF) for download for official match schedule.

¹) Single page, really w/ six FIFA Partners, eight FIFA World Cup Sponsors
and another six National Supporters.


### Wikipedia -- ([`en.wikipedia.org/wiki/2014_FIFA_World_Cup`](http://en.wikipedia.org/wiki/2014_FIFA_World_Cup)):

Pro: Best source; open data license or public domain (license-free);
everything available for download (page dumps, etc).

Cons: Mostly free-form text, that is, no structured data and no web service. 


# What now? Options

1) Screen scrap FIFA site with web crawler? Why not?

2) Try to convert free-form text from Wikipedia into structured data? Why not?

3) Do-It-Yourself: Build a wikipedia for structured data? Why not?



# Do-It-Yourself -- Let's Build `football.db` - Open Football Data


Q: What Wiki Package to Use?

MediaWiki? Semantic MediaWiki? MoinMoin? DokuWiki? PeanutButterWiki?


Q: What Source Format to Use?

XML, JSON, YAML, SEXPS (S-Expressions), RDF Triplets,
CSV (Comma-Separated Values), TOML (Tom's Obvious, Minimal Language)?



# Do-It-Yourself -- `github.com/openfootball`  (Cont.)


Q: What Wiki Package to Use?

A: Git (and GitHub)


Why Git?

- Distributed is the new centralized
- Fast version control
- Local branching on the cheap
- Everything is local
- Free and open source

Learn more @ [git-scm.com](`http://git-scm.com`)


Why GitHub?

- Build <del>software</del> data better, together. 

Learn more @ [github.com](`http://github.com`)

xxx add screenshot here xxx



# Do-It-Yourself -- What is CSV (Comma-Separated Values)?

Q: What Source Format to Use?

A: Keep it as simple as possible. (Source is hand-crafted not machine-generated.)

<del>XML</del>, <del>JSON</del>, <del>YAML</del>, <del>SEXPS (S-Expressions)</del>,
<del>RDF Triplets</del>,
CSV (Comma-Separated Values), <del>TOML (Tom's Obvious, Minimal Language)</del>


[`teams.txt`](https://github.com/openfootball/euro-cup/blob/master/teams.txt):

~~~
### Teams

gre, Greece,       GRE, gr
ned, Netherlands,  NED, nl
ger, Germany,      GER, de
por, Portugal,     POR, pt
esp, Spain,        ESP, es
ita, Italy,        ITA, it
cro, Croatia,      CRO, hr
eng, England,      ENG, en
...
~~~


# Do-It-Yourself --- What's missing in CSV? What's CSV v2?

What's missing?

- No comments
- No blank lines
- No multi-line records
- No data types (or text patterns or field tags / markers)
- No unordered fields (that is, fields depend on position) or variable number of fields per record
- No default/inherited values

Let's fix it. Welcome CSV v2 ([`github.com/csv2`](https://github.com/csv2)).


[`south-america/br-brazil--stadiums.txt`](https://github.com/openfootball/stadiums/blob/master/south-america/br-brazil--stadiums.txt):

~~~
### Stadiums

[maracana]
  Maracanã|Estádio do Maracanã, 1950
  76_935
  Rio de Janeiro, RJ
  en.wikipedia: Estádio_do_Maracanã


[corinthians]
  Corinthians|Arena Corinthians|Arena de São Paulo, 2014
  68_000
  São Paulo, SP
  en.wikipedia: Arena_Corinthians

...
~~~


# Do-It-Yourself -- Mini Language for Football Fixtures

DSL - Domain-Specific Language 

[`world-cup/2014/cup.txt`](https://github.com/openfootball/world-cup/blob/master/2014/cup.txt):

~~~
##################################
#  World Cup 2014 Brazil

# -- Groups

Group A  |  Brazil       Croatia      Mexico         Cameroon
Group B  |  Spain        Netherlands  Chile          Australia
Group C  |  Colombia     Greece       Côte d'Ivoire  Japan
Group D  |  Uruguay      Costa Rica   England        Italy
Group E  |  Switzerland  Ecuador      France         Honduras
Group F  |  Argentina    Bosnia-Herzegovina  Iran    Nigeria
Group G  |  Germany      Portugal     Ghana          United States
Group H  |  Belgium      Algeria      Russia         South Korea


# -- Group A

Matchday 1 / Group A

(1) Thu Jun/12 17:00 Brazil - Croatia   @ Arena de São Paulo, São Paulo (UTC-3)

Matchday 2 / Group A

(2) Fri Jun/13 13:00 Mexico - Cameroon  @ Estádio das Dunas, Natal (UTC-3)
~~~



# Ruby, Ruby, Ruby -- `sportdb` Ruby gem

Import any fixtures:

- "Classic" Comma
- "Modern" Comma  plus
- Mini Language for Football

into any SQL database. Example:


Step 1: Get a copy of the data

~~~
$ git clone git://github.com/openmundi/world.db.git
$ git clone git://github.com/openfootball/world-cup.git
~~~

Step 2: Let's build the `world-cup-2014.db`

~~~
$ sportdb setup --include ./world-cup --worldinclude ./world.db
~~~

That's it.


# Models - 

see beer db models   


# Web Service




# Web Apps, Books, 






# Appendix:  Beer? Wine? Alpine Ski? Formula 1?




# Appendix: License -- What is Public Domain?  Why Public Domain?

CC0 - Creative Commons 0 (Zero)