

# Using Open Football Data - Get Ready for the World Cup in Brazil 2014 


Football is the world's most popular sport and
the World Cup in Brazil kicking off next month in São Paulo on June 12th
 (in 38 days 3 hours 15 minutes and counting)
is the world's biggest (sport) event with 32 national teams
from all continents competing in 64 matches in 12 cities for the title.


## Where's the open football data? Let's ask the intertubes.
 
Now lets say you want to build a world cup match day widget for
your site using a web service (HTTP JSON API) that lets you query
for all teams, groups, matches, players, and so on.

Example: HTTP JSON API

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

Let's ask the intertubes and search for free open football data sets or web services,
for example,
let's google [`json world cup brazil`](http://www.google.com/search?q=json+world+cup+brazil)
or post a question on the open data stackexchange ['Q: Any Open Data Sets for the (Football) World Cup (in Brazil 2014)?'](http://opendata.stackexchange.com/questions/1791/any-open-data-sets-for-the-football-world-cup-in-brazil-2014)).

Nothing. Nada. Nichts. Niente. Zilch. Zero.
So what to do? Let's build an open football data project.


## What's `football.db?`

Let's welcome `football.db` -  public domain
football data sets offering free open football data
for the World Cup in Brazil 2014, the World Cup in Uruguay 1930 and more.

The open football project also sports a free self-hosted HTTP JSON API service
for football data, for example, to get started:

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







