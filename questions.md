---
layout: default
title: Frequently Asked Questions and Answers (FAQs)
---

# {{ page.title }}

## Real-Time Result / Score Services

Q: Is there any API (web service) to get live scores for the World Cup 2014 in Brazil?

A: `football.db` does **NOT** offer any real-time live football results / scores services.


Q: What's the update frequency of the data sets?

A: It's an open source (public domain) volunteer effort.
Data sets get updated when they get updated, that is, there's no guarantee.
If you need updates today you have at least two options:

Option 1) Contribute your updates to the datasets.

Option 2) Clone the datasets and update your own private or public copies yourself.



## Download Pre-Built `football.db` Copy or Build Your Own `football.db` Copy


Q: Where can I get (download) pre-built `football.db`, `worldcup.cp` etc. copies?

A: You can get (download) pre-built single-file SQLite databases (working anywhere, that is, Windows, Mac, Linux, etc.)
copies on the [build release page](https://github.com/openfootball/build/releases).


Q: How can I get started building my own up-to-date copy using the latest data sets?

A: To build your own copy you can find
some basic build docu [here [1]](http://openfootball.github.io/build.html)
and [here [2]](https://github.com/openfootball/build).
Not really a tutorial (step-by-step guide). Sorry, still the early days.
Just start and if you have questions or commentary as you go along post
them to forum / mailing list maybe someone can help you out. All the best.
Good luck. Bonus: Why not write a step-by-step build guide yourself and share
it with the world?


## Export Formats (JSON, CSV, SQL)

Q: How can I get datasets in JSON, CSV, SQL or _[your data format here]_?

A: Get a copy of a pre-built `football.db` or `worldcup.db` etc.
It's a single-file SQLite database (working anywhere, that is, Windows, Mac, Linux, etc.).

Option 1) No coding required. Use your SQLite tool of choice to export to CSV, JSON, SQL
or _[your data format here]_.

Option 2) Write your own (little) script (in Ruby, Python, etc.) that exports
to CSV, JSON or _[your data format here]_. - Bonus: Share your code with the world.

<!--
Add Example Script in Ruby
-->


Q: How can I get datasets in JSON or CSV using _[your database here]_?

A: Load the datasets into your (SQL) database of choice (PostgreSQL, MySQL, etc.) and

Option 1) use your database tool of choice to export to CSV, JSON, SQL 
or _[your data format here]_ etc. or

Option 2) use your language of choice and wipe up some code to export to CSV, JSON 
or _[your data format here]_ etc.  - Bonus: Share your code with the world.




## Apps, Apps, Apps

Q: Any real world apps using this?

A: There's no API key, there's no registration, there's no license for the datasets.
     You're free to use whatever you need - no questions asked, no rights reserved.
   If you're using the football.db datasets in your app, you're welcome to tell the world (on the mailing list/forum)
    and you get listed here:

- [BITKUP.COM](http://bitkup.com) - new app for betting with Bitcoins on the Brazil's World Cup 2014 by Oriol Franquesa Cortés



{% include questions.md %}