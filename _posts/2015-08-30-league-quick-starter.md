---
layout: post
title:  "sport.db League Quick Starter Sample - Mauritius Premier League - Create Your Own Repo/League(s) from Scratch"
---

Added a new [sport.db quick starter sample](https://github.com/sportkit/mu-mauritius) 
using the Mauritius Premier League to get you started creating 
your own leagues/cups/etc. from scratch. 

You can test drive the quick starter sample with a single command e.g.:

```
$ sportdb build 
```

To start from scratch follow these six steps: 

- Step 1: Add all leagues 
- Step 2: Add all clubs 
- Step 3: Add all match fixtures and results 
- Step 4: Add the league season "front matter" settings 
- Step 5: Add a setups file list (also known as manifest) 
- Step 6: Add a datafile build script - That's it. Done. 

Using a file structure like: 

```
  ├── 2014-15              # 2014-15 season folder 
  |   ├── league-i.txt     #   match fixtures / results - matchdays  1-18 
  |   ├── league-ii.txt    #                            - matchdays 19-36 
  |   └── league.yml       #   "front matter" settings 
  ├── setups 
  |   └── all.txt          #   file list (manifest) 
  ├── leagues.txt          # all leagues 
  ├── clubs.txt            # all clubs 
  └── Datafile             # build script 
```

That's it. Now try: 

```
$ sqlite3 sport.db 

SQLite version 3.7.16 
Enter ".help" for instructions 
Enter SQL statements terminated with a ";" 

sqlite> select * from countries; 
1|Mauritius|mauritius|mu|1|MUS|||1261200|2040|||f|t|f|f| 

sqlite> select * from teams; 
1|joachim|Cercle de Joachim||CDJ|Cercle de Joachim SC|Joachim|1||t|||||f| 
2|chamarel|Chamarel SC||CHA|Chamarel|Chamarel Sport Club|1||t|||||f| 
```

and so on and so forth. 
