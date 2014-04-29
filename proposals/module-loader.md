Module Loader 2.0
=================

### What is the problem?

We currently use a bit of a half-baked dependency resolution system in calendar. It's confusing and undocumented and doesn't do the build-time optimizations that r.js does.

### How badly is this hurting us? What is the priority of solving this?

It is too difficult to know what's included where in calendar. This isn't the highest priority suggestion, but it may be one of the simpler changes.

### What solution are we proposing?

Use a third-party module loader like r.js so that each bit of our code can require and export dependencies clearly and declaratively.

### Technical Notes

require.js is a strong candidate since :jrburke is the maintainer and it's already widely used within gaia.
