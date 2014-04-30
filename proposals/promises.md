Promises
========

### What is the problem?

In calendar, we do a lot of things asynchronously like

1. xhr requests
2. idb operations
3. various platform api requests (ie alarms)

Asynchronous flow control can make code very difficult to write for readability and maintainability. Our async flow control is very "vanilla" in the calendar app. Most of it happens like so

```
function doAThenBThenC(done) {
  function a(some, params, ..., callback) {
    // ...
    callback();
  }

  function b(some, params, ..., callback) {
    // ...
    callback();
  }

  function c(some, params, ..., callback) {
  }

  a(foo, bar, baz, function() {
    b(foo, bar, baz, function() {
      c(foo, bar, baz, done);
    });
  });
}
```

which is sad.

### How badly is this hurting us? What is the priority of solving this?

Much of the code in the calendar app (like the alarm and sync controller code) is very difficult to follow because we don't have a proper abstraction for asynchronous flow control. Fixing this would make our code more maintainable and also more exemplary for third party web developers.

### What solution are we proposing?

Use an asynchronous flow control abstraction like promises or perhaps [caolan/async](https://github.com/caolan/async).

### Technical Notes

There is a lot of momentum for moving over to promises. If we use
promises, [Q](https://github.com/kriskowal/q) has a wonderful api for
flow control.

(DOM) Promises have landed in Firefox (with GC support if you forget to add catch) and the ES6 Promises likely will make their way into the JS engine soon... The only conern is workers last I checked they where not available there (this can easily be loaded into global scope)
