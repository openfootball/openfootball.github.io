---
layout: default
title: Frequently Asked Questions and Answers (FAQs)
---

# {{ page.title }}

<div class="toc" markdown="1">
Contents:

* [Download Pre-Built Copies or Build Your Own](#downloads)
* [Real-Time Result / Score HTTP JSON API Web Services](#services)
* [Contribute / Update Match Scores, Schedules, Leagues](#contribute)
* [League Standings / Stats](#stats)
* [Text Formtas (Match Schedule / Player / Squads Mini Languages)](#formats)
* [Export Formats (JSON, CSV, SQL)](#export)
* [Apps, Apps, Apps](#apps)
* [Questions? Comments?](#questions)
</div>




## Download Pre-Built Copies or Build Your Own  {#downloads}

#### Q: Where can I get (download) pre-built copies e.g. `football.db`, `worldcup.db`, `england.db` etc.?

A: You can get (download) pre-built single-file SQLite databases copies (working anywhere, that is, Windows, Mac, Linux, etc.)
on the [Build Releases](https://github.com/openfootball/build/releases) page.


#### Q: How can I get started building my own up-to-date copy using the latest datasets?

A: See the [How to Build Your Own Copy](http://openfootball.github.io/build.html) page
to get started building your own copy. Not really a tutorial (step-by-step guide). Sorry, still the early days.
Just start and if you have questions or commentary as you go along post
them to the [forum / mailing list](http://groups.google.com/group/opensport)
maybe someone can help you out. All the best.
Good luck. Bonus: Why not write a step-by-step build guide yourself and share
it with the world?



## Real-Time Result / Score HTTP JSON API Web Services  {#services}

#### Q: Is there any HTTP JSON API service to get live scores for _[your event here]_ e.g. the World Cup 2014 in Brazil, the English Premier League 2015/16, the Euro 2016 in France, etc.?

A: `football.db` does **NOT OFFER ANY REAL-TIME LIVE** football results / scores services.

However, you can run your own HTTP JSON API service.
See the [`sport.db.starter` kits](https://github.com/sportkit) to get started, for example,
or try the [example HTTP JSON API service running on Heroku](http://footballdb.herokuapp.com).
(Note: The scores get updated once a day, that is, every 24 hours.)



#### Q: What's the update frequency of the datasets?

A: It's an open source (public domain) volunteer effort.
Datasets get updated when they get updated, that is, there's no schedule and no guarantee.
If you need updates today you have at least two options:

Option 1) Contribute your updates to the datasets.

Option 2) Clone the datasets and update your own private or public copies yourself.



## Contribute / Update Match Scores, Schedules, Leagues    {#contribute}

#### Q: How can I contribute / update match scores, schedules, leagues, etc.?

A: Your contributions are welcome.
It works like a wiki, that is, the datasets are plain text documents that anybody can update
(if you're an openfootball team member - you can update it directly in your browser or push your commits;
otherwise you may use a pull request).

For example, to add the result for the Brazil vs Croatia match:

~~~
Thu Jun/12 17:00   Brazil  vs  Croatia 
~~~

change the line to:

~~~
Thu Jun/12 17:00   Brazil  3-1 (1-1)  Croatia
~~~

Bonus: Let's add the goal getters too. Example:

~~~
Thu Jun/12 17:00   Brazil  3-1 (1-1)  Croatia
                     [Neymar 29', 71' (pen.) Oscar 90+1';  Marcelo 11' (o.g.)]
~~~

That's it.



## League Standings / Stats    {#stats}

#### Q: How can I add league standings / tables (e.g. number of matches played, won-drawn-lost, goals scored, etc.)?

A: That's the big plus using structured data. You can (auto-)calculate
league standings using SQL queries and updates.
Another big plus: Your standings will be always up-to-date (just recalculate - if out-of-date). 

Note, you can use the built-in sportdb standing calculations. Still early and rough.
For auto-calculating all league standings use, for example, in your build script:

~~~
EventStanding.recalc!   # and for all groups
GroupStanding.recalc!
~~~

You can see the calc "engine" code here [\[1\]](https://github.com/sportdb/sport.db.ruby/blob/master/lib/sportdb/calc.rb).
The "engine" calculates:

- `pos` (ranking e.g. 1st place, 2nd place etc.)
- `played` (matches played)
- `won`
- `drawn`
- `lost`
- `goals_for`
- `goals_against`
- `pts` (points e.g. +3 for wins, +1 for draws etc.)


Standing tables in the sportdb schema include:

- `AlltimeStanding` / `AlltimeStandingEntry`
- `EventStanding` / `EventStandingEntry`
- `GroupStanding` / `GroupStandingEntry`

For example, using the world cup datasets you can (auto-)calculate the all time standings:

~~~
 1  Brazil (BRA)                 97   67  15  15  210:88   216  19
 2  Germany (GER)                99   60  19  20  206:117  199  17
 3  Italy (ITA)                  80   44  21  15  126:74   153  17
 4  Argentina (ARG)              70   37  13  20  123:80   124  15
 5  England (ENG)                59   26  19  14   77:52    97  13
 6  Spain (ESP)                  56   28  12  16   88:59    96  13
 7  France (FRA)                 54   25  11  18   96:68    86  13
 8  Netherlands (NED)            43   22  10  11   71:44    76   9
 9  Uruguay (URU)                47   18  12  17   76:65    66  11
10  Sweden (SWE)                 46   16  13  17   74:69    61  11
...
~~~


## Text Formtas (Match Schedule / Player / Squads Mini Languages)   {#formats}

#### Q: What kind of text format are you using? Why not use CSV, JSON, or _[your data format here]_?

A: Most `football.db` documents use "standard" plain text formats such as
comma-separated values or key-value pairs with some exceptions.

The match schedules use a mini structured data language. Example:

~~~
Group A    |  Brazil    Croatia       Mexico     Cameroon
Group B    |  Spain     Netherlands   Chile      Australia
...

Matchday 1 |  Thu Jun/12
Matchday 2 |  Fri Jun/13
...

Group A:

(1) Thu Jun/12 17:00   Brazil  3-1 (1-1)  Croatia    @ Arena de São Paulo, São Paulo
                        [Neymar 29', 71' (pen.) Oscar 90+1'; Marcelo 11' (o.g.)]
...

Final

(64) Sun Jul/13 16:00  Germany  1-0 a.e.t. (0-0, 0-0)  Argentina  @ Estádio do Maracanã, Rio de Janeiro
                        [Mario Götze 113']
~~~


The player documents use a mini structured data language. Example:

~~~
Júlio César|Júlio César SOARES DE ESPINDOLA,     3 Sep 1979, 186
T. Silva|Thiago SILVA|Thiago EMILIANO DA SILVA, 22 Sep 1984, 183
David Luiz|David Luiz MOREIRA MARINHO,          22 Apr 1987, 189
Marcelo|Marcelo VIEIRA DA SILVA JUNIOR,         12 May 1988, 174
Dante|Dante BONFIM COSTA SANTOS,                18 Oct 1983, 188
~~~


The squads / lineups documents use a mini structured data language. Example:

~~~
(12)  GK  Júlio César           #  79, Toronto (CAN)
 (3)  DF  Thiago Silva          #  45, Paris Saint-Germain (FRA)
 (4)  DF  David Luiz            #  35, Chelsea (ENG)
 (6)  DF  Marcelo               #  30, Real Madrid (ESP)
(13)  DF  Dante                 #  12, Bayern Munich (GER)
~~~

Bonus Exercise: Try to write by hand the schedule for the English Premier League -
week-by-week - 380 matches all together, for example?
Are you enjoying writing the match schedule in JSON? in CSV? in XML? in _[your data format here]_?
Why not post an example (e.g. a link to a gist or to your document)
to the [forum / mailing list](http://groups.google.com/group/opensport) for comparison?

Now retry the exercise using the new mini language designed for making
hand-crafting schedules as easy as possible. Any difference?



#### Q: Why? Why? Why?

A: The dataset sources are plain old text documents designed to be easy-to-read and easy-to-write.
The idea is to make it work like a wiki, that is, just plain old text documents anyone can update.

Why like a wiki?

Question - What's the best source for open "unstructured" football information in the real world in 2014?
Of course, the Wikipedia! See, for example,
the [World Cup 2014](http://en.wikipedia.org/wiki/2014_FIFA_World_Cup) page,
the [World Cup 2014 squads](http://en.wikipedia.org/wiki/2014_FIFA_World_Cup_squads) page,
or the [World Cup 2014 Qualifiers](http://en.wikipedia.org/wiki/2014_FIFA_World_Cup_qualification) page.

Thus, the idea is - why not build on what works and build a wiki for "structured" data e.g.

- Wikipedia     - wiki w/ free-form text => mostly unstructured data
- `football.db` - wiki w/ mostly free-form text => always 100% structured data (ready for easy loading into SQL tables with a 100% data accuracy guarantee)



#### Q: What about Wikidata - Wikipedia's Data Project?

A: [Wikidata](http://www.wikidata.org) is a great initiative.
Wikidata like the `football.db` uses "license-free" data, that is, data dedicated to the public domain.

Thus, an idea (and goal) is to work on syncying the data
(from Wikidata to `football.db` and from `football.db` to Wikidata).
Still very early. If you're interested in making it happen or if you have any ideas, suggestions or insights,
say hello on the [forum / mailing list](http://groups.google.com/group/opensport). 



## Export Formats (JSON, CSV, SQL)    {#export}

#### Q: How can I get datasets in JSON, CSV, SQL or _[your data format here]_?

A: Get a copy of a pre-built database e.g. `football.db`, `worldcup.db` etc. 
It's a single-file SQLite database (working anywhere, that is, Windows, Mac, Linux, etc.).

Option 1) No coding required. Use your SQLite tool of choice to export to CSV, JSON, SQL
or _[your data format here]_.

Option 2) Write your own (little) script (in Ruby, Python, etc.) that exports
to CSV, JSON or _[your data format here]_. - Bonus: Share your scripts with the world.

<!--
Add Example Script in Ruby
-->


#### Q: How can I get datasets in JSON, CSV or _[your data format here]_ using _[your database here]_ e.g. PostgreSQL, MySQL, etc.?

A: Load the datasets into your (SQL) database of choice e.g. PostgreSQL, MySQL, etc. and

Option 1) use your database tool of choice to export to CSV, JSON, SQL 
or _[your data format here]_ etc. or

Option 2) use your language of choice and wipe up some code to export to CSV, JSON 
or _[your data format here]_ etc.  - Bonus: Share your code with the world.




## Apps, Apps, Apps    {#apps}

#### Q: Any real world apps using this?

A: There's no API key, there's no registration, there's no license for the datasets.
You're free to use whatever you need - no questions asked, no rights reserved.
If you're using the football.db datasets in your app, you're welcome to tell the world (on the [mailing list/forum](http://groups.google.com/group/opensport))
and you get listed here:

- [Major League Soccer Almanac](http://mls-almanac.herokuapp.com) - [(Source)](https://github.com/cecomp64/mls-almanac) query-able, historical data for Major League Soccer in the US and Canada by Carl-Erik Svensson 

<!--  no longer availabe?
- [BITKUP.COM](http://bitkup.com) - new app for betting with Bitcoins on the Brazil's World Cup 2014 by Oriol Franquesa Cortés
-->


{% include questions.md %}
