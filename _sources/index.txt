.. include:: global.rst

==============
sprin's re dev
==============

is an encapsulation of my approach to development. It tries to convey the
benefits of lightweight constructs not just in code, but in system design,
project organization, team communication, and infrastructure. It is a reaction
to the contrast of the successes of lightweight in close proximity to the
failures of heavyweight.

Three recurring motifs of lightweight approaches are:

 - Smallness
 - Simplicity
 - Promiscuity

These guiding virtues can be used to achieve speed of implementation,
high performance, robust and maintainable architecture, and elegant and
empathic human interfaces. This last quality is the most important, and
more focus can be given to user experience when less time is spent ensuring
the other qualities. With lightweight's emphasis on unfettered composability of
small components, the possibilities to also deliver a radically better
experience through novel compositions are significantly greater.

Strategy
========

A big part of strategy is tool choice. The tools chosen must not only be
sufficient to achieve the desired functional outcome, but also have qualities
that allow a developer to take the simplest, quickest path to implementation.

Data Stores
-----------

Relational databases continue to offer tangible advantages over newer
datastores that promise ease-of-development and/or ease-of-scaling.
While scaling into the terabyte range may become a challenge with
relational databases, the argument of development ease falls apart when
denormalized data stores cannot cope with new querying requirements, or
suffer from data integrity issues as the application evolves. The article on
:doc:`relational_dbs` goes in to depth about why a relational database is a good tool
for lightweight development.

