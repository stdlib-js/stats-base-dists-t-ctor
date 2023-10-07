<!--

@license Apache-2.0

Copyright (c) 2018 The Stdlib Authors.

Licensed under the Apache License, Version 2.0 (the "License");
you may not use this file except in compliance with the License.
You may obtain a copy of the License at

   http://www.apache.org/licenses/LICENSE-2.0

Unless required by applicable law or agreed to in writing, software
distributed under the License is distributed on an "AS IS" BASIS,
WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied.
See the License for the specific language governing permissions and
limitations under the License.

-->


<details>
  <summary>
    About stdlib...
  </summary>
  <p>We believe in a future in which the web is a preferred environment for numerical computation. To help realize this future, we've built stdlib. stdlib is a standard library, with an emphasis on numerical and scientific computation, written in JavaScript (and C) for execution in browsers and in Node.js.</p>
  <p>The library is fully decomposable, being architected in such a way that you can swap out and mix and match APIs and functionality to cater to your exact preferences and use cases.</p>
  <p>When you use stdlib, you can be absolutely certain that you are using the most thorough, rigorous, well-written, studied, documented, tested, measured, and high-quality code out there.</p>
  <p>To join us in bringing numerical computing to the web, get started by checking us out on <a href="https://github.com/stdlib-js/stdlib">GitHub</a>, and please consider <a href="https://opencollective.com/stdlib">financially supporting stdlib</a>. We greatly appreciate your continued support!</p>
</details>

# Student's T

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Student's t distribution constructor.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

To use in Observable,

```javascript
T = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/stats-base-dists-t-ctor@umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var T = require( 'path/to/vendor/umd/stats-base-dists-t-ctor/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/stats-base-dists-t-ctor@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.T;
})();
</script>
```

#### T( \[v] )

Returns a [Student's t][t-distribution] distribution object.

```javascript
var t = new T();

var mu = t.mean;
// returns NaN
```

By default, `v = 1.0`. To create a distribution having a different degrees of freedom `v`, provide a parameter value.

```javascript
var t = new T( 4.0 );

var mu = t.mean;
// returns 0.0
```

* * *

## t

A [Student's t][t-distribution] distribution object has the following properties and methods...

### Writable Properties

#### t.v

Degrees of freedom of the distribution. `v` **must** be a positive number.

```javascript
var t = new T( 2.0 );

var v = t.v;
// returns 2.0

t.v = 3.0;

v = t.v;
// returns 3.0
```

* * *

### Computed Properties

#### T.prototype.entropy

Returns the [differential entropy][entropy].

```javascript
var t = new T( 4.0 );

var entropy = t.entropy;
// returns ~1.682
```

#### T.prototype.kurtosis

Returns the [excess kurtosis][kurtosis].

```javascript
var t = new T( 4.0 );

var kurtosis = t.kurtosis;
// returns Infinity
```

#### T.prototype.mean

Returns the [expected value][expected-value].

```javascript
var t = new T( 4.0 );

var mu = t.mean;
// returns 0.0
```

#### T.prototype.median

Returns the [median][median].

```javascript
var t = new T( 4.0 );

var median = t.median;
// returns 0.0
```

#### T.prototype.mode

Returns the [mode][mode].

```javascript
var t = new T( 4.0 );

var mode = t.mode;
// returns 0.0
```

#### T.prototype.skewness

Returns the [skewness][skewness].

```javascript
var t = new T( 4.0 );

var skewness = t.skewness;
// returns 0.0
```

#### T.prototype.stdev

Returns the [standard deviation][standard-deviation].

```javascript
var t = new T( 4.0 );

var s = t.stdev;
// returns ~1.414
```

#### T.prototype.variance

Returns the [variance][variance].

```javascript
var t = new T( 4.0 );

var s2 = t.variance;
// returns 2.0
```

* * *

### Methods

#### T.prototype.cdf( x )

Evaluates the [cumulative distribution function][cdf] (CDF).

```javascript
var t = new T( 2.0 );

var y = t.cdf( 0.5 );
// returns ~0.667
```

#### T.prototype.logcdf( x )

Evaluates the natural logarithm of the [cumulative distribution function][cdf] (CDF).

```javascript
var t = new T( 2.0 );

var y = t.logcdf( 0.5 );
// returns ~-0.405
```

#### T.prototype.logpdf( x )

Evaluates the natural logarithm of the [probability density function][pdf] (PDF).

```javascript
var t = new T( 2.0 );

var y = t.logpdf( 0.8 );
// returns ~-1.456
```

#### T.prototype.pdf( x )

Evaluates the [probability density function][pdf] (PDF).

```javascript
var t = new T( 2.0 );

var y = t.pdf( 0.8 );
// returns ~0.233
```

#### T.prototype.quantile( p )

Evaluates the [quantile function][quantile-function] at probability `p`.

```javascript
var t = new T( 2.0 );

var y = t.quantile( 0.5 );
// returns 0.0

y = t.quantile( 1.9 );
// returns NaN
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

* * *

<section class="examples">

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/stats-base-dists-t-ctor@umd/browser.js"></script>
<script type="text/javascript">
(function () {

var t = new T( 2.0 );

var mu = t.mean;
// returns 0.0

var mode = t.mode;
// returns 0.0

var s2 = t.variance;
// returns Infinity

var y = t.cdf( 0.8 );
// returns ~0.746

})();
</script>
</body>
</html>
```

</section>

<!-- /.examples -->

<!-- Section to include cited references. If references are included, add a horizontal rule *before* the section. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="references">

</section>

<!-- /.references -->

<!-- Section for related `stdlib` packages. Do not manually edit this section, as it is automatically populated. -->

<section class="related">

</section>

<!-- /.related -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->


<section class="main-repo" >

* * *

## Notice

This package is part of [stdlib][stdlib], a standard library for JavaScript and Node.js, with an emphasis on numerical and scientific computing. The library provides a collection of robust, high performance libraries for mathematics, statistics, streams, utilities, and more.

For more information on the project, filing bug reports and feature requests, and guidance on how to develop [stdlib][stdlib], see the main project [repository][stdlib].

#### Community

[![Chat][chat-image]][chat-url]

---

## License

See [LICENSE][stdlib-license].


## Copyright

Copyright &copy; 2016-2023. The Stdlib [Authors][stdlib-authors].

</section>

<!-- /.stdlib -->

<!-- Section for all links. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="links">

[npm-image]: http://img.shields.io/npm/v/@stdlib/stats-base-dists-t-ctor.svg
[npm-url]: https://npmjs.org/package/@stdlib/stats-base-dists-t-ctor

[test-image]: https://github.com/stdlib-js/stats-base-dists-t-ctor/actions/workflows/test.yml/badge.svg?branch=main
[test-url]: https://github.com/stdlib-js/stats-base-dists-t-ctor/actions/workflows/test.yml?query=branch:main

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/stats-base-dists-t-ctor/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/stats-base-dists-t-ctor?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/stats-base-dists-t-ctor.svg
[dependencies-url]: https://david-dm.org/stdlib-js/stats-base-dists-t-ctor/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://app.gitter.im/#/room/#stdlib-js_stdlib:gitter.im

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/stats-base-dists-t-ctor/tree/deno
[umd-url]: https://github.com/stdlib-js/stats-base-dists-t-ctor/tree/umd
[esm-url]: https://github.com/stdlib-js/stats-base-dists-t-ctor/tree/esm
[branches-url]: https://github.com/stdlib-js/stats-base-dists-t-ctor/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/stats-base-dists-t-ctor/main/LICENSE

[t-distribution]: https://en.wikipedia.org/wiki/Student%27s_t-distribution

[cdf]: https://en.wikipedia.org/wiki/Cumulative_distribution_function

[pdf]: https://en.wikipedia.org/wiki/Probability_density_function

[quantile-function]: https://en.wikipedia.org/wiki/Quantile_function

[entropy]: https://en.wikipedia.org/wiki/Entropy_%28information_theory%29

[expected-value]: https://en.wikipedia.org/wiki/Expected_value

[kurtosis]: https://en.wikipedia.org/wiki/Kurtosis

[median]: https://en.wikipedia.org/wiki/Median

[mode]: https://en.wikipedia.org/wiki/Mode_%28statistics%29

[skewness]: https://en.wikipedia.org/wiki/Skewness

[standard-deviation]: https://en.wikipedia.org/wiki/Standard_deviation

[variance]: https://en.wikipedia.org/wiki/Variance

</section>

<!-- /.links -->
