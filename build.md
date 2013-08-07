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

That's it For more see the [`sportdb` command line tool project](https://github.com/geraldb/sport.db.ruby)
for more.


### Use Build Script (Rakefile)

As an alternative you can use a build script (Rakefile) to build your own `football.db` copy.

Example - Rakefile:

~~~
BUILD_DIR = "./build"
  
FOOTBALL_DB_PATH = "#{BUILD_DIR}/football.db"

DB_CONFIG = {
  :adapter   =>  'mysql',
  :database  =>  FOOTBALL_DB_PATH
}

directory BUILD_DIR

task :clean do
  rm FOOTBALL_DB_PATH if File.exists?( FOOTBALL_DB_PATH )
end

task :env => BUILD_DIR do
 require 'worlddb'  
 require 'sportdb'
 require 'logutils/db'

 LogUtils::Logger.root.level = :info

 pp DB_CONFIG
 ActiveRecord::Base.establish_connection( DB_CONFIG )
end

task :create => :env do
  LogDb.create
  WorldDb.create
  SportDb.create
end
  
task :importworld => :env do
  WorldDb.read_setup( 'setups/sport.db.admin', '../world.db', skip_tags: true )  # populate world tables
  # WorldDb.stats
end

task :importsport => :env do
  SportDb.read_setup( 'setups/all', '../openfootball/at-austria' )
  # SportDb.stats
end

desc 'footballdb - build from scratch'
task :build => [:clean, :create, :importworld, :importsport] do
  puts 'Done.'
end 
~~~


## Troubleshooting

### Error - `sportdb: command not found`

If you get the error:

    sportdb: command not found

Double check if you have the `spordb` command line tool installed. Use the `gem` command; issue:

    gem list sportdb
    
If not listed install the gem; issue:

    gem install sportdb



{% include questions.md %}
