---
layout: post
title:  "sportdb Update v1.9.3 - Added Better Squads Reader (Auto-Creates Missing Players)"
---


What's news? sportdb command line updates: 

The squads (rosters)reader will now auto-add missing players.
Try it, for example, using the World Cup 1930 squads e.g.:

~~~
$ rake update DATA=history     # reads all world cups from 1930 to 2010 
~~~

Squads get added to the rosters join table (one record per player) 
and missing players get auto-added to the persons table. Still a little rough and early stage.

