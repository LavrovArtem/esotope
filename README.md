#esotope
[![Build Status](https://api.travis-ci.org/inikulin/esotope.svg)](https://travis-ci.org/inikulin/esotope)

*ECMAScript code generator on steroids*

This project has been started as a fork of [escodegen](https://github.com/Constellation/escodegen) with intention to
speed up the original code. *escodegen* is a great project, however it was a constant bottleneck in our project, where we are doing
a real-time JavaScript code instrumentation. When nearly 70% of the original code was rewritten, it became clear that it
cannot be issued as a PR to the original repo and I decided to leave it as a standalone project. Currently esotope is x2
times faster than escodegen in node v0.10.x, and x4.5 times faster in node v0.11.x ([benchmark](https://github.com/inikulin/esotope/tree/master/benchmark)).
However in production we've seen x10 times performance gain in some cases.

##Install
**Node:**
```
$ npm install esotope
```

**Browser:**

Drop [esotope.js](https://raw.githubusercontent.com/inikulin/esotope/master/esotope.js) on page

```
<script src="esotope.js"></script>
```

then *esotope* will be available via `window.esotope`.

Or you can require it as the [RequireJS](http://requirejs.org/) module.



##Usage
In general *esotope* can be used as a drop-in replacement for *escodegen*. So for the API-reference go to
[escodegen API page](https://github.com/Constellation/escodegen/wiki/API).

However, there are some missing features that
did not fit well into new design and were sacrificed for speed:

* Comments attachment
* Source maps

So, if you need comments or source maps you should fallback to *escodegen*.

Also, Mozilla-specific obsolete ES6 syntax support has been removed (`moz.starlessGenerator`, `moz.parenthesizedComprehensionBlock`,
`moz.comprehensionExpressionStartsWithAssignment` options).

##Testing
*esotope* inherits test suite from *escodegen*. To run tests (make sure you have [gulp](https://github.com/gulpjs/gulp/) installed):
```
$ gulp test
```

##Questions or suggestions?
If you have any questions, please feel free to create an issue [here on github](https://github.com/inikulin/esotope/issues).

##Author
[Ivan Nikulin](https://github.com/inikulin) (ifaaan@gmail.com)
