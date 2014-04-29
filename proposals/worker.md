Worker 2.0
==========

### What is the problem?

Too much work happens in the main thread. This makes calendar slow. Calendar should be fast! The main thread should be a UI that sends actions to and receives data from a worker and does nothing else. In addition this effort would help promote modularity and decoupling in the calendar app (and possibly a nice platform api down the road).

### How badly is this hurting us? What is the priority of solving this?

// TODO

### What solution are we proposing?

Move everything that isn't a view or a controller out into the worker.

### Technical Notes

Not much to do here until IDB is available in worker
threads (see [bug 701634](https://bugzilla.mozilla.org/show_bug.cgi?id=701634)).
