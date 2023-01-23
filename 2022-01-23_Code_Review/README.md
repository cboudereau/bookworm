# What to look for in a code review

![title](https://raw.githubusercontent.com/cboudereau/bookworm/main/2022-01-23_Code_Review/Title.png)

## The author : Trisha Gee
 - Java Champion
 - Author
 - Developer Advocate @ JetBrains

## About this Book
 ### Sources
 - [Jetbrains blog (link is dead)](https://blog.jetbrains.com/upsource/category/practices/)
 - [JetBrains GitHub repository (also dead)](https://github.com/jetbrains/jetbrains-books-examples/whattolookforinacodereview)

## Introduction (1)
 - [Jeff Atwood's Coding horror blog](https://blog.codinghorror.com/code-reviews-just-do-it/)
### What to look for ?
 - Formatting
 - Style
 - Naming
 - Test coverage
  - Reduce [cognitive load](https://en.wikipedia.org/wiki/Cognitive_load)
 - Automated vs Human reviews
#### Design
 - Fit with overall architecture
 - (2)[SOLID](https://en.wikipedia.org/wiki/SOLID)
 - (2)[DDD](https://en.wikipedia.org/wiki/Domain-driven_design)
 - Code reuse / refactoring opportunity
 - YAGNI / KISS principle : Extreme Programming
#### Readability / Maintainability
 - Understand new code
 - (6)Happy / Exceptional cases
#### Functionality
 - (7)Documentation : tests (automated)
#### Have you though about...?
 - Security
 - Regulatory requirements
 - (7) Are not covered (why ?)
 - Project documentation impact
 - (8)UI interaction checks (error message)
 - Configuration vs Hard coded values

## Tests
 - Focus on important code (core)
 - Catch uncovered new blocks
 - Meaning of test ?
 - Test is code to maintain, it should follow the same code rules
 - Granularity (unit > ... > end to end)
 - Edge cases
   - (9)Cardinality (null, 1, N)
   - Types
 - Limitations (accidental vs intentional)
 - Keep intention with a test
 - Type/Level
   - Benchmark
   - End to End (QA, ...)
 - Security
 - Performance Tests
 - Pair Programming : Reviewers can write tests too

## Performance
 - Requirements
 - Fit actual implementation vs expected performance
 - (10)Performance fix
 - Not all code requires performance : Performance vs Readability
 - Network cost : (10)Batch and number of calls
 - Locks
 - Memory Leaks
 - Boundings / Life cycle of data (add / remove from list)
 - Resource Management (connections, streams, ...)
 - Configuration Pools
   - Use Default config first
   - Compare config performance when needed
 - Code smells
   - Reflection / Timeoouts
 - (11)Parallelism

## (13)Data Structures
 - Pitfalls (Stream api)
 - Choose the right one
 - (14)Optional

## (2)SOLID Principles 

## Security
 - Automation
 - (15)Reduce dependencies

## Tooling
 - Upsource

## Correctness
 - Wrong Data structure
 - Race conditions
 - Locks
 - (12)Caching issues

## Sum up
### Culture
 - Share
   - Dev env
     - IDE configs
     - CI/CD checks

### Personal references
 - (1) How about reviewing a full codebase ?
   - Working effectively with legacy code
 - (2)SOLID/DDD, reduce cognitive load, ... > Functional Programming
   - Blue Book by Eric Evans
   - Red Book
   - Domain modeling made functional
 - (3)Software design pattern
   - Software design ANTI pattern
 - (4)Extreme Programming
 - (5)How about Code Complexity metrics ?
 - (6)Exception vs Error : Golang procedural > Code complexity > Generics > Functional Programming (vavr java, fsharp, rust, scala, ...) 
 - (7)How about Property Based Testing ?
 - (8)Does this change requires QA sync (Tres Amigos) ?
 - (9) Type Driven Development > Functional Programming
 - (10) Brendan Gregg Flamegraphs' / [Humans are terrible at guessing about performance](https://github.com/flamegraph-rs/flamegraph#humans-are-terrible-at-guessing-about-performance)
 - (11) [Concurrency is not Parallelism by Rob Pike](https://www.youtube.com/watch?v=oV9rvDllKEg)
 - (12) [TwoHardThings](https://martinfowler.com/bliki/TwoHardThings.html)
 - (13) [Optional](https://fsharpforfunandprofit.com/posts/the-option-type/)
 - (14) [Big-O Cheat Sheet](https://www.bigocheatsheet.com/) and [Sort](https://www.youtube.com/playlist?list=PLZh3kxyHrVp_AcOanN_jpuQbcMVdXbqei)
 - (15) [Dependabot](https://docs.github.com/en/enterprise-server@3.4/admin/configuration/configuring-github-connect/enabling-dependabot-for-your-enterprise)