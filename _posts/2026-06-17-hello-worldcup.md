---
layout: post
title:  "Hello, World Cup 2026!"
---

Long time no news. Let's restart and celebrate the World Cup 2026 kick-off in Mexico, the United States and Canada.

Did you know? While it's usually just me (Gerald Bauer) writing and generation match schedules (incl. fixtures, results, reports, & more) 
in the Football.TXT format - it's great to see that [Salah Salim](https://github.com/salah23222) 
has generated live world cup fixtures & results in Football.TXT, see [wcup2026.org/football.php](https://wcup2026.org/football.php).
Reading:

```
= FIFA World Cup 2026

# Schedule & results
# Source:  https://wcup2026.org  (auto-generated, kept in sync with live results)
# Data:    openfootball schedule + ESPN/FIFA live results
# Format:  football.txt  (https://github.com/openfootball)
# Updated: 2026-06-17 14:36 UTC

Group A:  Mexico   South Africa   South Korea   Czech Republic
Group B:  Canada   Bosnia & Herzegovina   Qatar   Switzerland
Group C:  Brazil   Morocco   Haiti   Scotland
Group D:  USA   Paraguay   Australia   Turkey
Group E:  Germany   Curaçao   Ivory Coast   Ecuador
Group F:  Netherlands   Japan   Sweden   Tunisia
Group G:  Belgium   Egypt   Iran   New Zealand
Group H:  Spain   Cape Verde   Saudi Arabia   Uruguay
Group I:  France   Senegal   Iraq   Norway
Group J:  Argentina   Algeria   Austria   Jordan
Group K:  Portugal   DR Congo   Uzbekistan   Colombia
Group L:  England   Croatia   Ghana   Panama

▪ Matchday 1
Thu Jun 11
  Mexico                2-0 (1-0)  South Africa            @ Mexico City
  South Korea           2-1 (0-0)  Czech Republic          @ Guadalajara (Zapopan)

...

▪ Final
Sun Jul 19
  W101                  v          W102                    @ New York/New Jersey (East Rutherford)
```

and a quick lexer & parser check with `fbtree` reads:

```
[<Heading1 FIFA World Cup 2026>,
 <BlankLine>,
 <BlankLine>,
 <GroupDef Group A teams=["Mexico", "South Africa", "South Korea", "Czech Republic"]>,
 ...
 <MatchLine L101 v L102 geo=["Miami (Miami Gardens)"]>,
 <RoundOutline Final, level=1>,
 <DateHeader {:m=>7, :d=>19, :wday=>7}>,
 <MatchLine W101 v W102 geo=["New York/New Jersey (East Rutherford)"]>]
   104 MatchLine(s)

[[:OK, "https://wcup2026.org/football.php", "199 tree node(s)"]]
OK   no parse errors found in 1 datafile(s)
```

That's history in the making. The world's first world cup with live Football.TXT coverage & support! 
