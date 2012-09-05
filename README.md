Lasa
====

Introduction
------------

Lasa is a simple script for monitoring bits and pieces of your Linux system.
It pales in comparison to real monitoring software like Nagios and Zabbix, but
its aim is to be useful for non-root users who want to stay well-informed about
the systems they work with.

Installation
------------

Nothing to it, just put lasa in your path and it's ready to go.

You probably want to make a ~/.lasa.d directory where you can store your
typical checks. Otherwise, you can pass them in on standard input or specify
some other configuration directory with -c.

Running
-------

    $ lasa

Running with no arguments will run the configured checks and print out anything
that fails. Use -v for output of what passed and failed, or -d for debug
output on top of that.

    $ lasa -m me@me.com

Normally lasa writes a report to standard output. You can have it mailed out
instead with -m. This only sends a report if there is a failure somewhere.

DSL
---

Lasa uses a dumb DSL to specify checks. Run lasa with -S to see the syntax.
Some examples:

    fs exists /data01
    dir exists /var/spool/foo
    daemon httpd
    file exists /etc/something.conf

Put one check per file in your configuration directory. Naming a file with the
suffix ".off" will turn it off, i.e., get it skipped.


