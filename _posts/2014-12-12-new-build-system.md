---
layout: post
title:  "New `football.db` Build System - Welcome `./Datafile`"
---

The sportdb command line tool includes a new build system (as a new and easier all-in-one option). 

To try it - use the new Datafile - a mini language a.k.a. domain-specific language (DSL)
that lets you setup new `football.db`s in minutes. 

For example, to setup a football.db for the World Cup 2014 use: 

`./Datafile`: 

~~~
world 'openmundi/world.db', setup: 'countries' 

football 'openfootball/national-teams' 
football 'openfootball/world-cup', setup: '2014' 
~~~

Now run 

~~~
$ sportdb build 
~~~

The new build command will look for the `./Datafile` script in your working folder and 

- Step 1) Download all datasets as zip archives (from GitHub) to `./tmp`
- Step 2) Create all database tables 
- Step 3) Read/import all datasets from the zip archives in `./tmp` (no need to unpack) 

That's it.  Still early and rough.
