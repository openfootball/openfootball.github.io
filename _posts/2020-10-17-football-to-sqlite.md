---
layout: post
title:  "New `football-to-sqlite` build tool - load / read football.txt match datafiles (e.g. English Premier League) into a SQLite database"
---

Inspired by the [datasette
{`db`,`dbf`,`markdown`,`geojson`,`shapefile`}`-to-sqlite` series](https://docs.datasette.io/en/stable/ecosystem.html) 
added the missing [`football-to-sqlite` tool](https://github.com/sportdb/football.db/tree/master/football-to-sqlite) that - surprise,
surprise - lets you load / read football.txt match datafiles (e.g.
English Premier League, German Bundesliga, Spanish La Liga 2020/21,
etc.) into a sqlite database.

Usage:

Run this tool against match files in the Football.TXT format like so:

```
$ football-to-sqlite england.db 2020-21\1-premierleague.txt
```

or pass in more than one match file:

```
$ football-to-sqlite england.db 2020-21\1-premierleague.txt \
                                2020-21\2-championship.txt \
                                2020-21\3-league1.txt \
                                2020-21\4-league2.txt \
                                2020-21\5-nationalleague.txt
```

Note: If the single-file SQLite database (and its tables, views &
indices) do not (yet) exist, they get auto-created on the first run.

Note: You can use `football2sqlite` as an alias / alternate name.

**Pipes & Standard Input (STDIN)**

You can use any command line tool to download match files and pipe
(via stdin) into this tool like so:

```
$ curl https://raw.githubusercontent.com/openfootball/world-cup/master/2018--russia/cup.txt
| football-to-sqlite worldcup.db
```

Enjoy the beautiful game. 
