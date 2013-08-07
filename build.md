---
layout: default
title: How To Build Your Own Copy
---

# {{ page.title }}

<div class="toc" markdown="1">
Contents:

* [Build Your Own `football.db` Copy](#build)
* [Questions? Comments?](#questions)
</div>



## Build Your Own `football.db` Copy {#build}

To build your own `football.db` copy from the plain text fixtures
use the sportdb command line tool. Example:

Step 1:  Get a copy of the `world.db` fixtures

    $ git clone git://github.com/geraldb/world.db.git

Step 2:  Get a copy of the `at-austria` fixtures

    $ git clone git://github.com/openfootball/at-austria.git

Step 3:  Let's build the `football.db`

    $ sportdb setup --include ./at-austria --worldinclude ./world.db

That's it. For more see the [`sportdb` command line tool project](https://github.com/geraldb/sport.db.ruby)
for more.




{% include questions.md %}
