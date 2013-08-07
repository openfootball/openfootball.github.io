---
layout: default
title: Web Service / HTTP JSON API
---

# {{ page.title }}

<div class="toc" markdown="1">
Contents:

* [Web Service / HTTP JSON API](#webservice)
* [About, License - Questions? Comments?](#license)
</div>


## Web Service / HTTP JSON API    {#webservice}

Try the `football.db` HTTP JSON API running
on Heroku [`footballdb.herokuapp.com/api`](http://footballdb.herokuapp.com/api).

Example - List all games in a round for an event `/event/:key/round/:pos`:

~~~
GET /event/euro.2012/round/6

{
  "event": { "key":"euro.2012", "title":"Euro 2012" },
  "round": { pos": 6, "title": "Final" },
  "games":
  [
    {
    "team1_key": "esp",
    "team1_title": "Spain",
    "team1_code": "ESP",
    "team2_key": "ita",
    "team2_title": "Italy",
    "team2_code": "ITA",
    "play_at": "2012/07/01",
    "score1": 4,
    "score2": 0,
    "score1ot": null,
    "score2ot": null,
    "score1p": null,
    "score2p": null
    }
  ]
}
~~~


{% include questions.md %}

