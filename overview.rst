===========
Merge Steps
===========

Extracted from the wiki docs and existing script

m-b -> m-r
==========

inputs
------
- source repo: m-b
- dest repo: m-r
- source branch: default (hard coded or assumed)
- dest branch: default (hard coded or assumed)
- hg user: user to commit as (old input)
- source version: hash for head of default in source repo (computed)
- dest version: hash for head of default in dest repo (computed)
- notification list: r-d, Standard8, Callek

merge code
----------
- close trees (wiki)
- verify tree closed (new)
- notify merge started (new)
- clobber release builders (wiki)
- clone (old)
- tag source repo (old)
- push source repo (manual)
- tag dest repo (old)
- pull source repo tip (from tag) into dest repo (old)
- update -C working directory (old)
- commit dest repo using debugsetparents (old)

update configs
--------------
- mar channel ids - no bail on fail (old)
- branding - no bail on fail (old)
- l10n supported locales (manual)
- review diff (manual)
- commit dest repo (old)
- push dest repo (manual)

merge l10n
----------


finish
------
- notify notification list that merge complete (new)
- open the beta tree (new)


merge day
=========

Repeated for m-a => m-b & m-c => m-a

inputs
------
- source repo: m-a, then m-c
- dest repo: m-b, then m-a
- source branch: default (hard coded or assumed)
- dest branch: default (hard coded or assumed)
- hg user: user to commit as (old input)
- source version: hash for head of default in source repo (computed)
- dest version: hash for head of default in dest repo (computed)
- notification list: r-d, Standard8, Callek
- old aurora version: old version of aurora

pre start
---------
- file bug to throttle off aurora updates from ``old aurora version``
  (relman)
- make sure trees green and aurora patches landed (relman)


merge code
----------
- run IDL change search, send to relman as beta1 blocker using ``old
  aurora version`` (new)
- clone repos (new)
- configure repos to push (new)
- enable certain extensions in each repo (new)
- close trees (manual)
- pause vcs2vcs sync for gecko.git & gecko-dev.git (manual)
  (how to handle in mozharness?)

References
==========

existing merge helper script:
    https://github.com/mozilla/relman-tools/blob/master/merge-day-scripts/beta2release.py

existing wiki docs:
    https://wiki.mozilla.org/Release_Management/Merge_Documentation

merge process details:
    http://mozilla.github.io/process-releases/draft/development_specifics/index.html#branching

