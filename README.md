<!--

@license Apache-2.0

Copyright (c) 2023 The Stdlib Authors.

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

# toAccessorArray

[![NPM version][npm-image]][npm-url] [![Build Status][test-image]][test-url] [![Coverage Status][coverage-image]][coverage-url] <!-- [![dependencies][dependencies-image]][dependencies-url] -->

> Convert an array-like object to a minimal array-like object supporting the accessor protocol.

<!-- Section to include introductory text. Make sure to keep an empty line after the intro `section` element and another before the `/section` close. -->

<section class="intro">

</section>

<!-- /.intro -->

<!-- Package usage documentation. -->



<section class="usage">

## Usage

To use in Observable,

```javascript
toAccessorArray = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-to-accessor-array@umd/browser.js' )
```
The previous example will load the latest bundled code from the umd branch. Alternatively, you may load a specific version by loading the file from one of the [tagged bundles](https://github.com/stdlib-js/array-base-to-accessor-array/tags). For example,

```javascript
toAccessorArray = require( 'https://cdn.jsdelivr.net/gh/stdlib-js/array-base-to-accessor-array@v0.0.1-umd/browser.js' )
```

To vendor stdlib functionality and avoid installing dependency trees for Node.js, you can use the UMD server build:

```javascript
var toAccessorArray = require( 'path/to/vendor/umd/array-base-to-accessor-array/index.js' )
```

To include the bundle in a webpage,

```html
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/array-base-to-accessor-array@umd/browser.js"></script>
```

If no recognized module system is present, access bundle contents via the global scope:

```html
<script type="text/javascript">
(function () {
    window.toAccessorArray;
})();
</script>
```

#### toAccessorArray( arr )

Converts an array-like object to a minimal array-like object supporting the accessor protocol.

```javascript
var arr1 = [ 1, 2, 3 ];

var arr2 = toAccessorArray( arr1 );
// returns <AccessorArray>

var v = arr2.get( 1 );
// returns 2

var bool = ( arr2 === arr1 );
// returns false
```

If the provided array-like object already supports the accessor protocol, the function returns the input array unchanged.

```javascript
var Complex128Array = require( '@stdlib/array-complex128' );

var arr1 = new Complex128Array( 10 );
// returns <Complex128Array>

var arr2 = toAccessorArray( arr1 );
// returns <Complex128Array>

var bool = ( arr2 === arr1 );
// returns true
```

</section>

<!-- /.usage -->

<!-- Package usage notes. Make sure to keep an empty line after the `section` element and another before the `/section` close. -->

<section class="notes">

</section>

<!-- /.notes -->

<!-- Package usage examples. -->

<section class="examples">

* * *

## Examples

<!-- eslint no-undef: "error" -->

```html
<!DOCTYPE html>
<html lang="en">
<body>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/array-complex128@umd/browser.js"></script>
<script type="text/javascript" src="https://cdn.jsdelivr.net/gh/stdlib-js/array-base-to-accessor-array@umd/browser.js"></script>
<script type="text/javascript">
(function () {

// Define a function for printing the contents of an array and which assumes accessor protocol support:
function printArray( name, x ) {
    var i;
    for ( i = 0; i < x.length; i++ ) {
        console.log( '%s[%d] = %s', name, i, x.get( i ).toString() );
    }
}

// Create an array of complex numbers:
var buf = [ 0, 0, 0, 0, 1, 0, 2, 0, 0, 0, 0, 0, 0, 0, 0, 0, 3, 0, 0, 0 ];
var cmplx = new Complex128Array( buf );

// Create an array of the real components:
var real = [ 0, 0, 1, 2, 0, 0, 0, 0, 3, 0 ];

// Ensure the arrays support the accessor protocol to allow for uniform iteration:
cmplx = toAccessorArray( cmplx );
real = toAccessorArray( real );

// Print the contents of each array:
printArray( 'complx', cmplx );
printArray( 'real', real );

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

[npm-image]: http://img.shields.io/npm/v/@stdlib/array-base-to-accessor-array.svg
[npm-url]: https://npmjs.org/package/@stdlib/array-base-to-accessor-array

[test-image]: https://github.com/stdlib-js/array-base-to-accessor-array/actions/workflows/test.yml/badge.svg?branch=v0.0.1
[test-url]: https://github.com/stdlib-js/array-base-to-accessor-array/actions/workflows/test.yml?query=branch:v0.0.1

[coverage-image]: https://img.shields.io/codecov/c/github/stdlib-js/array-base-to-accessor-array/main.svg
[coverage-url]: https://codecov.io/github/stdlib-js/array-base-to-accessor-array?branch=main

<!--

[dependencies-image]: https://img.shields.io/david/stdlib-js/array-base-to-accessor-array.svg
[dependencies-url]: https://david-dm.org/stdlib-js/array-base-to-accessor-array/main

-->

[chat-image]: https://img.shields.io/gitter/room/stdlib-js/stdlib.svg
[chat-url]: https://gitter.im/stdlib-js/stdlib/

[stdlib]: https://github.com/stdlib-js/stdlib

[stdlib-authors]: https://github.com/stdlib-js/stdlib/graphs/contributors

[umd]: https://github.com/umdjs/umd
[es-module]: https://developer.mozilla.org/en-US/docs/Web/JavaScript/Guide/Modules

[deno-url]: https://github.com/stdlib-js/array-base-to-accessor-array/tree/deno
[umd-url]: https://github.com/stdlib-js/array-base-to-accessor-array/tree/umd
[esm-url]: https://github.com/stdlib-js/array-base-to-accessor-array/tree/esm
[branches-url]: https://github.com/stdlib-js/array-base-to-accessor-array/blob/main/branches.md

[stdlib-license]: https://raw.githubusercontent.com/stdlib-js/array-base-to-accessor-array/main/LICENSE

</section>

<!-- /.links -->