hit: git + heroku
=================

`hit` is a command line utility which adds a subtle amount of Heroku knowledge to `git`.

This is a really bad fork of [defunkt/hub](https://github.com/defunkt/hub) for personal use.

Normal:

    $ hit clone floating-fog-9348

    Expands to:
    $ git clone git@heroku.com:floating-fog-9348.git

hub requires you have `git` installed and in your `$PATH`. It also
requires Ruby 1.8.6+ or Ruby 1.9.1+. No other libraries necessary.


Install
-------

### RubyGems

`hit` can also be installed as a RubyGem:

    $ gem install hit

### Source

You can also install from source:

    $ git clone git://github.com/kennethreitz/hit.git
    $ cd hit
    $ rake install prefix=/usr/local


Commands
--------

The following commands now have superpowers:

### git clone

    $ hit clone floating-fog-9348
    > git clone git@heroku.com:floating-fog-9348.git

### git remote add

    $ hit remote add floating-fog-9348
    > git remote add heroku git@heroku.com:floating-fog-9348.git

    $ hit remote add staging floating-fog-9348
    > git remote add staging git@heroku.com:floating-fog-9348.git


Configuration
-------------

If you prefer using the HTTPS protocol for Heroku repositories instead of the git
protocol for read and ssh for write, you can set "hit.protocol" to "https".

For example:

    $ git clone floating-fog-9348
    < git clone >

    $ git config --global hit.protocol https
    $ git clone floating-fog-9348
    < https clone >
