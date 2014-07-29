---
layout: default
title: Frequently Asked Questions and Answers (FAQs)
---

# {{ page.title }}


## Download Pre-Built Copies or Build Your Own

#### Q: Where can I get (download) pre-built copies e.g. `football.db`, `worldcup.db`, `england.db` etc.?

A: You can get (download) pre-built single-file SQLite databases copies (working anywhere, that is, Windows, Mac, Linux, etc.)
on the [Build Releases](https://github.com/openfootball/build/releases) page.


#### Q: How can I get started building my own up-to-date copy using the latest datasets?

A: See the [How to Build Your Own Copy](http://openfootball.github.io/build.html) page
to get started building your own copy. Not really a tutorial (step-by-step guide). Sorry, still the early days.
Just start and if you have questions or commentary as you go along post
them to the forum / mailing list maybe someone can help you out. All the best.
Good luck. Bonus: Why not write a step-by-step build guide yourself and share
it with the world?



## Real-Time Result / Score HTTP JSON API Web Services

#### Q: Is there any HTTP JSON API service to get live scores for _[your event here]_ e.g. the World Cup 2014 in Brazil, the English Premier League 2015/16, the Euro 2016 in France, etc.?

A: `football.db` does **NOT OFFER ANY REAL-TIME LIVE** football results / scores services.

However, you can run your own HTTP JSON API service.
See the [`sport.db.api.starter` kit](https://github.com/sportdb/sport.db.api.starter) to get started, for example,
or try the [example HTTP JSON API service running on Heroku](http://footballdb.herokuapp.com).
(Note: The scores get updated once a day, that is, every 24 hours.)



#### Q: What's the update frequency of the datasets?

A: It's an open source (public domain) volunteer effort.
Datasets get updated when they get updated, that is, there's no schedule and no guarantee.
If you need updates today you have at least two options:

Option 1) Contribute your updates to the datasets.

Option 2) Clone the datasets and update your own private or public copies yourself.



## Export Formats (JSON, CSV, SQL)

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




## Apps, Apps, Apps

#### Q: Any real world apps using this?

A: There's no API key, there's no registration, there's no license for the datasets.
You're free to use whatever you need - no questions asked, no rights reserved.
If you're using the football.db datasets in your app, you're welcome to tell the world (on the mailing list/forum)
and you get listed here:

- [BITKUP.COM](http://bitkup.com) - new app for betting with Bitcoins on the Brazil's World Cup 2014 by Oriol Franquesa Cortés



{% include questions.md %}