Interop Tests
=============

### What is the problem?

It is a long, manual process to test our interoperability with different DAV providers. We expect for the number of providers that we support to grow over time and it will become increasingly difficult to improve our sync facilities and add new features like invitations.

### How badly is this hurting us? What is the priority of solving this?

Compatibility with Yahoo! broke completely for a couple months and we didn't notice. This is high priority.

### What solution are we proposing?

Add automated tests which can be used

1. to monitor our compliance with supported servers
2. as a diagnostic tool for debugging sync issues

### Technical Notes

This can be difficult to write on top of ui interactions. This might be a better fit for backend integration tests.
