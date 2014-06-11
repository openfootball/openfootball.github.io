
# Using the `football.db` single-file SQLite database

Step 0: Get a copy from the [build releases](https://github.com/openfootball/build/releases) pages.


Check if you have the sqlite3 shell/command line tool installed:

    $ sqlite3 -help
    3.6.22

To query use, for example:

    $ sqlite3 football.db
    sqlite> select * from teams;



## Appendix


What is SQLite?

- 2.000.000.000.000 installations. Public domain code.
- see PostgreSQL Conf Talk
- Works anywhere, that is, Window, Mac, Linux, etc.



Why use single-file SQLite 'binaries' instead of, for example, zip archives of data sets?

