---
layout: post
title: "Added `football.db` Quick Starter Datafile Templates - `$ sportdb new <name>`"
---

The sportdb command line tool now includes a new quick starter
template command to (auto-)download Datafile scripts from the new
[`openfootball/datafile` registry](https://github.com/openfootball/datafile). 

For example, to build yourself a copy of the `worldcup2014.db` type: 

~~~
$ sportdb new worldcup2014 
~~~

The new command will run these steps: 

- Step 1: Download `worldcup2014.rb` Datafile (from GitHub) to your 
    working folder as `./Datafile`
- Step 2: Run the `sportdb` build command 
    - Step 2.a: Download all datasets listed in the Datafile as zip 
       archives (from GitHub) to `./tmp`
    - Step 2.b: Create the "empty" database, that is, table structure, 
       indexes, etc. (schema) 
    - Step 2.c: Read in all datasets from the zip archives in `./tmp` (no need to unpack) 

That's it. All done and setup with a single command. Still early and rough. 

PS: The first quick starter Datafile templates include:
  
- `worldcup`   => All World Cups 1930-2014
- `en`         => English Premier Leagues
- `en2014-15`  => English Premier League 2014/15
- `cl2014-15`  => (European) Champions League 2014/15
