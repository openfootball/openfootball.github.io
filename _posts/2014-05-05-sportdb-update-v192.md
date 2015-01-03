---
layout: post
title: "sportdb Update v1.9.2 - Added Match Goals Reader e.g. `[Messi 3', 45+1']` etc."
---


What's news? sportdb command line updates: 

The match schedule reader now will add goals (plus auto-add missing 
players). All still a little rough but working without any (extra) configuration. Example: 

~~~
(1) Thu Jun/12 17:00   Brazil 3-1 (1-1) Croatia       @ Arena de São Paulo, São Paulo
        [Neymar 29', 71' (pen.) Oscar 90+1';  Marcelo 11' (o.g.)] 
~~~

The reader will add four goal records (see the table goals w/ fields such as 
`player_id`, `team_id`, `minute`, `offset`, `score1`, `score2` etc.): 

~~~
1 |   Marcelo  11'   (o.g.)   1-0   Croatia (Team 2) 
2 |   Neymar   29'            1-1   Brazil  (Team 1) 
3 |   Neymar   71'   (pen.)   2-1   Brazil  (Team 1) 
4 |   Oscar    90'+1'         3-1   Brazil  (Team 1)
~~~
