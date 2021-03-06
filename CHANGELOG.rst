=========
Changelog
=========

1.3.0
=====

Refactors
---------

* Merge the fmn.sse repository into the fmn repository.

* Merge the fmn.web repository into the fmn repository.

Rule Changes
------------

* Taskotron rules: Particular tasks can now be matched using wildcards (PR #197).

* Taskotron rules: add abicheck as a critical task (PR #198).

Performance Improvements
------------------------

* Loading rules is now cached in memory which speeds up user creation by several
  orders of magnitude: creating 100 users went from 221 seconds to 3.3
  (Issue #191).

* The map of rule strings to rule Python objects is now cached which improves
  preference loading time by approximately an order of magnitude.

Bugfixes
--------

* Fix a bug where cache regions were configured to never expire cached keys
  (Issue #194).


1.2.1
=====

1.2.1 is a bug fix release.

Bugfixes
--------

* Stop trying to shuffle preferences in the worker consumer (#181)


1.2.0
=====

Features
--------

* Emails now contain headers to indicate to clients that they are auto-
  generated. This should stop them from auto-responding (#165).

* New rules for the Module Build Service (#174).

Bugfixes
--------

* Be fault-tolerant towards missing 'owner' field in copr msgs (commit d46464e06).

* Messages that can't be sent are now requeued (#169).

* Update to the generic rule for packages to account for namespaces in pkgdb2 (#177).


1.1.0
=====

* Introduce an fmn-createdb script


1.0.0
=====

* Documentation is now available `online <https://fmn.readthedocs.io/>`_.

* Merge the fmn.lib, fmn.consumer, and fmn.rules repositories. The changelogs
  for those projects since the last release of each is included below.
  - https://github.com/fedora-infra/fmn.lib/
  - https://github.com/fedora-infra/fmn.rules/

* The FMN consumer now requeues messages it failed to send with the IRC backend
  (https://github.com/fedora-infra/fmn.consumer/pull/96).

* There is now a Server-Sent Events backend for the FMN consumer
  (https://github.com/fedora-infra/fmn.consumer/pull/92 and
  https://github.com/fedora-infra/fmn.lib/pull/62).

* Emails are now split up into 20MB chunks if necessary
  (https://github.com/fedora-infra/fmn.consumer/pull/88).

* The digest producer is now run in a separate process
  (https://github.com/fedora-infra/fmn.consumer/pull/86).

* The API for ``handle_batch`` in the consumer has changed to accept a list
  of message dictionaries rather than ``QueuedMessage`` objects
  (https://github.com/fedora-infra/fmn.consumer/pull/86)
