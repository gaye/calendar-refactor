Logging 2.0
===========

### What is the problem?

It is too hard to figure out what state the calendar app is in. The email app has great logging facilities and it helps us figure out what's going on when we're debugging or QA sends bugs our way.

### How badly is this hurting us? What is the priority of solving this?

Both frontend and backend debugging in calendar are difficult. Backend debugging is perhaps slightly easier since the networking tools give you a lot of information about the DAV requests and responses, but it's difficult to know what's going on, for instance, with IndexedDb.

### What solution are we proposing?

Decide what state is important to log for debugging purposes, turn on logging by default, and make sure that we're logging the important debugging info everywhere.
