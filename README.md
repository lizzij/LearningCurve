M# seqr

### Tech Overview
- [x] genomics intro
- [x] PyCharm, vim
- [x] React, Redux
  - [ ] Redux advanced tutorial
- [x] PostgresSQL
- [ ] Django, Django ORM
- [ ] Python, JavaScript
- [ ] seqr source code

## Week 1
06/25/19 - 06/28/19
#### Done
- finished reading the genomics intro
- finished react, redux tutorial
- finished PostgresSQL tutorial
- working on Django ORM
- read ui, pages of the source code
- read through issues with my name tag

### Progress
- ready to start on some minor fixed like increasing the size of the image etc.
- git branches, test, pull request, review process
- need a refresher on python and javascript (not systematically learned the language,
should I follow a textbook or just stackoverflow as I go)?

### Meeting Notes
- git branching: master and dev
  - one branch per ticket
  - branch off dev
  - pull from dev
  - PR push from dev
  - add review when you are done
  - queue up a couple of tickets
  - master is just for deploy
- JS
  - ES6 JavaScript (linker, pure js, will caught by the linker)
- Pull request
  - clean ui
  - run the ui test and the server test (auto test on PR also)
  - pr/push test one of them failing is fine
  - pass Codacy review (fix the minor errors)
  - approval
  - only then merge the pull request
- style
  - break into sub-functions `_private` (python conventional)
    - don't explicitly test or export `_underscore_function`
  - code should be self-explanatory
  - intuitively why something need to be done
  - strange decision decision
 - Add test for PRs
   - server side are okay
     - if new end-points are added, definitely write tests for them
     - if modifying the end-point, add test (do not need to add the sort test, cos exists already)
     - large things add test
     - public utility function add test
     - (ask before pr)
    - ui test
      - create new component, create new test
      - currently only shallow rendering without crashing test (don't need to add a .test.js test)
      - some selector has robust test (selector.test.js - then add a test)
      - connected components use different test style
- timeline: > 2 wks, < 3 months
  - Increase the size of pedigree image in Inheritance search (maybe, lighter)
  - Allow multiple expanded search categories
  - Add gnomAD sort frequency (both in ui and server, learning ticket)
  - Assign cases to analysts (larger, create a new db model)

## Week 2
06/24/19 - 06/29/19

### How to do a PR?
- start a new feature-branch ```git checkout -b <feature-branch>``` then ```git pull origin dev```
- build the feature
- add necessary test (client side: add/change end-points)
- client and server test (comment out lines 436-445 in ```seqr/settings.py```)
- pull latest dev branch ```git pull origin dev```
- push feature-branch ```git push --set-upstream origin <feature-branch>```
- go to the feature-branch on github and issue a PR pull request to **dev (not master)**
- fix any failing tests and pull + push again
- wait for feedback (work on multiple branches), fix (iterate this step until code review is passed)
- click the green "Merge pull request" button :)
- don't close out ticket until deployed

### Plan
1. 06/24 ~~Increase the size of pedigree image in Inheritance search~~
2. 06/25 ~~Allow multiple expanded search categories~~
3. 06/26 ~~Add gnomAD sort frequency (both in ui and server, learning ticket)~~
4. 06/28 Assign cases to analysts (larger, create a new db model)
5. 07/01 Edit variant notes in-line
6. 07/03 Show saved variant breakdown for family on family/ variant pages
7. 07/05 Allow variant notes to be saved as gene notes

### Note to self for week 2
- Progress:
  - 2 PR, 1 code review
  - to goal? missed 2 PRs, started on 1 later one (missed ~1.5 PRs)
- Good:
  - can calm down adn do work at desk
  - know people and places
  - more familiar with code base and tech stack
- Bad:
  - balance social & work
  - do more tutorials! get into the code faster (become fluent in py and
  can work as a full-stack web dev first)
- In general:
  - don't slack off as time goes by...
  - but don't let the stress get to you either
  - iterate and improve
- Looking forward:  
  - start off day with tutorials, end off day with leetcode (?)
  - code more, make more mistakes, **ask A LOT more questions (but google first tho)**
  - make more friends, have more fun

## Week 3
07/01 - 07/07
### Goal
- Add gnomAD sort frequency (both in ui and server, learning ticket)
- Assign cases to analysts (larger, create a new db model)
- Edit variant notes in-line
- Show saved variant breakdown for family on family/ variant pages
- Allow variant notes to be saved as gene notes

## Week 4
07/08 - 07/14
### Goal
Meet kpi!
- Assign cases to analysts (larger, create a new db model)
- Edit variant notes in-line
- Show saved variant breakdown for family on family/ variant pages
- Allow variant notes to be saved as gene notes

### Note to self:
In case you can't remember where you left off yesterday:
- Copy-paste coding is a horrible, horrible thing!
- You should not be using `project`, but should be using `family`
- Another difference is project : collaborator = 1 : n, while family : analyst = 1 : 1
  - thus, you should simplify the implementation and
  - remove unnecessary parameters

## Week 7

### Reflection for week 5, 6
A blur really.
- finished all tickets
- started large project

General reflection for 1.5 month (6 weeks) point:
- Goal and timeline for the entire coop
  - tech understanding of Django, react
  - other area
  - med??
  - get to know ppl
  - figure out what I wanna do with life
  - leetcoding
  - personal projects and hackathons

### Goal for week 7
- get back on track
- stop eating at your desk ...
- finish large project

## Week 8
- finish all backlogs
- finish medium project success story staff page
- read about compound heterozygosity

## Week 9
Aug 12 - Aug 17
- social, leetcode and personal projects
- start on compound het project

### Goal for week 9
- solid start (background reading) for compound het project
- know what you want and how to get there
- be awake and prepared

## Week 10
Aug 19 - 23 (25)
- start Safari book series

## Week 11
Aug 26 - 30 (1)
- Goal: finish compound hets project
- Booklist: start, measure speed
- other: deliver POR

## Week 12
Sept 3 - 5
- meeting background knowledge
  - for profit gene sequencing companies: XCode, 23andMe, Ancestry DNA, FTDNA, MyHeritage DNA, Gene for Good, Helix
  - BioHackathon ideas
    - variant facts: allow patients and families to subscribe to updates about pathogenicity of certain vairant by signing up and getting emails
    - using Clinvar adn the McArthur lab parser

## Week 13
Sept 9 - 13 (15)
- 收心！
- 拿个奖，秋招
- finish the larger project

## Week 14
Sept 16 - 22
- hard deadline: Web morning code review
- in 2 days: debug, test and hopefully finish dashboard

## Week 15
Sept 23 - 27 (29)
- Ship bug free, high qulity code that does what it's supposed to do

## Week 16
Oct 1 - 4 (6)
- Finish compound hets and start on search
- Compound Hets project progress checklist
  - fix CRUD
    - use helper for checking if is compound het in reducer
    - fix test and add edge cases test
  - check if database migration is done correctly
    - (!!! check download discovery sheet as well)
  - main and secondary
    - break multi family compound hets into different lists
    - select the rest as secondary gene
  - fix download in search page
  - resolve UI console errors
  - forward compatible with xbrowse
  - run `reset_cached_variant` after deploying

## Week 17
Oct 7 - 11 (13)
- Merge (refactor, make minor adjustments) compound hets...
- Notes from seqr lab meeting
  - data pipeline
    - memorization
    - I/O CPU bound, resource applocation
    - Airflow

## Week 18
Oct 15 - 18 (20)
- implement everything first
- ask throughout Wed, Thur, Fri
