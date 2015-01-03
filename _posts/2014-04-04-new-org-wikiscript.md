---
layout: post
title: "New Org - `wikiscript` - Open Data Scripts for Wikipedia (e.g `football.squads.ruby` - World Cup 2014 Squads Update)"
---

Added a new GitHub org, that is, [`wikiscript`](https://github.com/wikiscript)
that collects scripts that let you turn free-style or semi-structured 
wiki text into open structured data. 

A first example is the new [football squads reader](https://github.com/wikiscript/football.squads.ruby)
that reads in a wikitext page e.g 

~~~
{% raw %}
{{nat fs player|no=1|pos=GK|name=[[Jefferson de Oliveira 
Galvão|Jefferson]]|age={{Birth date and 
age2|2014|6|12|1983|1|2|df=y}}|caps=9|club=[[Botafogo de Futebol e 
Regatas|Botafogo]]|clubnat=BRA}} 
{{nat fs player|no=2|pos=DF|name=[[Dani Alves]]|age={{Birth date and 
age2|2014|6|12|1983|5|6|df=y}}|caps=74|club=[[FC 
Barcelona|Barcelona]]|clubnat=ESP}} 
...
{% endraw %}
~~~

and outputs all squads files in the `football.db` format:

~~~
(1)  GK   Jefferson        #   9, Botafogo (BRA)
(2)  DF   Dani Alves       #  74, Barcelona (ESP)
... 
~~~

