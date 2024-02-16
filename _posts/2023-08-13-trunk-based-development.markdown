---
layout: post
title: "Trunk based development"
comments: true
date: 2021-07-22 21:07:00 +0530
categories: jekyll update
---

These are my notes while learning about Trunk based development (TBD) for presenting a talk.
Its taken from several articles and books. I'll try adding the references soon.

<br/>

1. Quick feedback loop - instantly you know what was wrong because of limited changes, hence easy to revert and go back to stable
2. CI on a branch is not CI. In true sense, CI cannot be done without trunk based - “Code on separate branches is not integrated”
3. Code quality is higher and design is better on trunk based. Because your design has to have abstractions
where you can hide the behavior from outside.
4. Not easy to merge big branches to master
5. Impossible if someone just merged a long living branch to master, and now you have to integrate your code with it,
figure out the problem if you’re lucky enough to know there’s a problem(having good safety net)
6. Small changes without breaking existing functionality need to be learnt by team
   1. Introduce new code from service layer without exposing the route
   2. Behind a feature toggle
   3. New api not consumed from frontend
7. Code review done in retrospective is less useful. Adopt pair/mob programming to integrate feedback in the first place

<br/><br/>

**Notes from Clare’s book**

1. Better quality 
   1. Easier to add code that brings value
2. Happy developers 
3. Small steps: The smaller the step the faster is it to understand what went wrong and fix it
4. Fast integration, fast feedback, fewer queues
5. Reducing risk: Even is something goes wrong, you can revert and recreate from scratch 
6. Improved Culture 
7. Prerequisites 
    1. Enthusiasm 
    2. Time 
    3. Flexibility 
    4. Help
8. Commit freq
9. Push freq
10. Build and Run tests before pushing
11. Need to have a really good automation suite integrated with the pipeline
12. Rollbacks should be easy
13. Fast build time
    1. Separate fast tests than slower, then improve the slow tests
    2. Questions the dependencies that need rebuild each time 
    3. Local feedback should be fast too
14. Minimize dependencies
15. The authors of Accelerate assert, CI requires “relentless work to simplify systems architecture on an ongoing basis to ensure that this automation isn’t prohibitively expensive to create and maintain
16. Throw things away
17. Feature flags
18. Pipeline always has to be green. Number 1 priority of the team. No use of having tests that fail

<br/><br/>

**Problems in TBD**

1. When you want to run an experiment or debug or bugfix, you want to write ugly code that would never make it to the main. But more often, it happens that you want some parts of the branch to be merged and then again merge hell
2. Not paying attention to the pipeline
3. Not Running tests locally after merge
4. Effectively practicing CTBD takes a certain amount of team maturity and skill. If you don’t already work in tiny chunks, commit frequently, write tests in tandem with code, run tests every time you commit, and generally write code in a way that’s designed to be merged several times a day, you’ll need to create those habits as part of your journey to trunk-based development
5. Reduce friction. Spend a moment when you see friction, think about ways of reducing or removing it
6. Help people build muscle memory. Coding katas
7. No blame shame. Honest culture
8. Use Information Radiators
9. Collaboration - Mob /Pair
10. Don’t branch! Don’t branch! any form of branching runs counter, in principle, to the ideas of Continuous Integration
11. A branch is, by design, intended to hide change in one part of the code from other developers



{% include disqus.html %}






