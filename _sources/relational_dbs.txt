.. include:: global.rst

====================
Relational Databases
====================

Relational database management systems (RDBMS) are well-understood and
predictable in function and performance. They are suitable for rapid
development - with basic normalized modelling, a small, performant schema can
be created in minutes. Transactional RDBMS set the standard for data integrity
for other data stores.

All of my experience with RDBMS has been with `PostgreSQL`_, so I will refer
to Postgres throughout this article, rather than RDBMS, although much
still applies to other RDBMS.

Small
=====

Postgres is not particularly "small" in the sense of code, written with
700K source lines of code (`Postgres SLOC`_). However, compared to `MySQL`_ at 1.7M
(`MySQL SLOC`_), Postgres may be considered the lightweight open-source RDBMS.

.. _Postgres SLOC: http://www.ohloh.net/p/postgres/analyses/latest/languages_summary

.. _MySQL SLOC: http://www.ohloh.net/p/mysql/analyses/latest/languages_summary

Less mature and featureful DBMS may be smaller, but not by much: `MongoDB`_
with 500K (`Mongo SLOC`_), `Cassandra`_ with 200K (`Cassandra SLOC`_).

.. _Mongo SLOC: http://www.ohloh.net/p/mongodb/analyses/latest/languages_summary

.. _Cassandra SLOC: http://www.ohloh.net/p/cassandra/analyses/latest/languages_summary

Another aspect of "small" is ease of deployment and operation. Postgres
is installable from package managers for every Linux server distribution in
common use. It requires very little configuration, although it is recommended
to change a handful of parameters to maximize use of available resources for
the given workload - this can be automated with `pgtune`_. For production
deployment, streaming replication and automated backups are also recommended
configuration, but not particularly difficult to set up. Postgres is also
available as a database-as-a-service from `Heroku`_ and `Open Hosting`_, among
others.

.. _pgtune: https://github.com/gregs1104/pgtune

`Monitoring`_ can be accomplished with standard Unix tools, as well as with plain
SQL queries on special statistics tables. Additionally, there are web-based
monitoring tools available, such as this `plugin for New Relic`_
and this `plugin for Scout`_.

.. _Monitoring: http://www.postgresql.org/docs/9.2/static/monitoring.html

.. _plugin for New Relic: http://newrelic.com/plugins/boundless/109

.. _plugin for Scout: https://scoutapp.com/plugin_urls/371-postgresql-monitoring

Simple
======

Programming constructs for relational databases can be divided in four groups:

 - SELECT
 - Data Manipulation (DML, such as INSERT, UPDATE, DELETE)
 - Data Definition (DDL, such as CREATE, ALTER)
 - Procedural Languages, such as PL/pgSQL

Of these, the first three are lightweight, declarative SQL constructs that
express operations on the data and schema very succinctly. The last, procedural
languages, are usually reserved for custom functions and extensions that cannot
be expressed in pure SQL, such as trigger functions.

All of these constructs can either be tested directly in an interactive psql
terminal session, or for longer statements, written to a file that can be loaded
into an interactive session. The psql terminal allows for extremely rapid
development: SELECT queries can be executed and the results viewed immediately.
DDL can be tested and refined iteratively with ALTER statements. DML
can be tested as many times as necessary within a BEGIN/ROLLBACK block, which
wraps the statements in a transaction that is rolled back after the results can
be inspected.

Promiscuous
===========

There are mature drivers for Postgres for every popular rapid development
platform.  In particular, `pyscopg`_ for Python, `ruby-pg`_ for Ruby, and
`clojure.java.jdbc`_ for Clojure, and `node-postgres`_ for Node.js.

.. _pyscopg: http://www.initd.org/psycopg/

.. _ruby-pg: https://bitbucket.org/ged/ruby-pg/wiki/Home

.. _clojure.java.jdbc: https://github.com/clojure/java.jdbc

.. _node-postgres: https://github.com/brianc/node-postgres

Postgres can also play nicely with other data stores through the use of
`foreign data wrappers`_, which allow records in other data stores to be
accessed through Postgres.

.. _foreign data wrappers: http://wiki.postgresql.org/wiki/Foreign_data_wrappers

Postgres has a thriving community of users, third-party tool and extension
developers, and consultants. The `mailing lists`_ are very active and contain
within their archives a huge quantity of searchable help info. A very large
number of Postgres-related projects are hosted on `github`_.

.. _mailing lists: http://www.postgresql.org/community/lists/

.. _github: https://github.com/search?q=postgresql+OR+postgres

