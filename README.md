# seqr

### Tech Overview
- [x] genomics intro
- [x] PyCharm, vim
- [x] React, Redux
  - [ ] Redux advanced tutorial
- [x] PostgresSQL
- [ ] Django, Django ORM
- [ ] Python, JavaScript
- [ ] seqr source code

### Week 1 06/25/19 - 06/28/19
#### Done
- finished reading the genomics intro
- finished react, redux tutorial
- finsihed PostgresSQL tutorial
- working on Django ORM
- read ui, pages of the source code
- read through issues with my name tag

### Progess
- ready to start on some minor fixed like increasing the size of the image etc.
- git branches, test, pull request, review process
- need a refresher on python and javascript (not systematically learned the language, 
should I follow a textbook or just stackoverflow as I go)?

### Meeting Notes
- git branching: master and dev
  - one branch per ticket
  - branch off dev
  - pull from dev
  - pr push from dev
  - add review when you are done
  - queue up a couple of tickets
  - master is just for deploy
- JS
  - Ex6 JavaScript (linker, pure js, will caught by the linker)
- Pull request
  - clean ui 
  - run the ui test and the server test (auto test on PR also)
   - pr/push test one of them failing is fine
  - pass Codacy review (fix the minor errors)
  - approval
  - only then merge the pull request
- style
  - break into sub-functions _private (python conventional)
    - don't explicitly test or export _underscore_function
  - code should be self-explanatory 
  - intuitively why something need to be done
  - strange decision decision
 - Add test for prs
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
  - Add gnomad sort frequency (both in ui and server, learning ticket)
  - Assign cases to analysts (larger, create a new db model)