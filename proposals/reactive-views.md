Reactive Views
==============

### What is the problem?

We maintain a *lot* of code in calendar that simply listens for changes to model data and then performs "imperative" operations on the DOM. This is (perhaps unnecessary) complexity which creates a lot of frontend bugs.

### How badly is this hurting us? What is the priority of solving this?

The calendar frontend regularly has lots of papercut-level bugs from code paths we get wrong. The calendar frontend has a lot of code that's very tightly coupled together which hurts maintainability. This is high priority.

### What solution are we proposing?

Use a library like

+ angularjs
+ emberjs
+ knockoutjs
+ ripplejs
+ vuejs

so we can write our views declaratively and shed the imperative DOM updating code.

### Technical Notes

There are potential, important-to-consider performance issues here (one of them is the impact on startup time). We should do some benchmarking and performance investigation first.
