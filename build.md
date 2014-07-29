---
layout: default
title: How to Build Your Own Copy
---

# {{ page.title }}


<div class="toc" markdown="1">
Contents:

* [Use Build Script (`/build`)](#build)
* [Use Shell Script (`/build-shell`)](#build-shell)
* [Do-It-Yourself - Write Your Own Script from Scratch](#build-diy)
* [Troubleshooting](#troubleshooting)
* [Questions? Comments?](#questions)
</div>


You have at least three options:


## Option 1  - Use Build Script (`/build`)    {#build}


Use the Ruby make build tool, that is, rake. Example:

~~~
$ rake build DATA=en   # let's build all leagues n seasons for England
~~~

See the [`/build` repo](https://github.com/openfootball/build) to get started.




## Option 2  - Use Shell Script (`/build-shell`)   {#build-shell}

Use a shell script to build your own up-to-date `football.db` copy from the latest plain text datasets. Example:

~~~
$ ./downloadAndBuild.sh
~~~

See the [`/build-shell` repo](https://github.com/openfootball/build-shell) to get started.




## Option 3  - Do-It-Yourself - Write Your Own Script from Scratch     {#build-diy}

Write your own build script from scratch. See the documentation to get started.




## Troubleshooting   {#troubleshooting}

### Error "sportdb: command not found"

If you get the error "sportdb: command not found" double check if you have the `sportdb` command line tool installed.
Use the `gem` command; type:

~~~
$ gem list sportdb
~~~

If not listed install the gem; type:

~~~
$ gem install sportdb
~~~

{% include questions.md %}




<!--

  clean up - move to docs???

## Build Your Own `football.db` Copy {#build}

Use the `sportdb` command line tool to build your own `football.db` copy from plain text fixtures.
Example:

Step 1:  Get a copy of the `world.db` fixtures

    $ git clone git://github.com/openmundi/world.db.git

Step 2:  Get a copy of the `at-austria` fixtures

    $ git clone git://github.com/openfootball/at-austria.git

Step 3:  Let's build the `football.db`

    $ sportdb setup --include ./at-austria --worldinclude ./world.db

That's it For more see the [`sportdb` command line tool project](https://github.com/geraldb/sport.db.ruby).
-->
