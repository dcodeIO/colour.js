![colour.js - ANSI terminal colors](https://raw.github.com/dcodeIO/colour.js/master/colour.png)
===========

This fork of colour.js doesn't extend the String prototype.


A cored, fixed, documented and optimized version of the popular [colors.js](https://github.com/Marak/colors.js). Can be
used as a drop-in replacement, also works correctly in the browser, provides a CSS mode and has been compiled through
Closure Compiler using advanced optimizations. Additionally, nearly every issue and pull request on the original has
been incorporated.

Installation
------------
`npm install colour`

Usage
-----
This package provides a set of methods that apply terminal colors to your texts.
Available styles are:

* **Emphasis:** bold, italic, underline, inverse
* **Colors:** yellow, cyan, white, magenta, green, red, grey, blue
* **Sequencers:** rainbow, zebra, random

#### Example

```js
var colour = require('colour');
console.log(colour.green('hello')); // outputs green text
console.log(colour.red(colour.underline('i like cake and pies'))) // outputs red underlined text
console.log(colour.inverse('inverse the color')); // inverses the color
console.log(colour.rainbow('OMG Rainbows!')); // rainbow (ignores spaces)
```

Custom themes
-------------
Its also possible to define your own themes. Example:

```js
var colour = require('colour');
colour.setTheme({
  silly: 'rainbow',
  input: 'grey',
  verbose: 'cyan',
  prompt: 'grey',
  info: 'green',
  data: 'grey',
  help: 'cyan',
  warn: ['yellow', 'underline'], // Applies two styles at once
  debug: 'blue',
  error: 'red bold' // Again, two styles
});

console.log(colour.error("this is an error")); // outputs bold red text
console.log(colour.warn("this is a warning")); // outputs underlined yellow text
```

Console, browser and browser-css mode
-------------------------------------
```js
var colour = require('colour');
...
colour.mode = 'none'; // No colors at all
colour.mode = 'console'; // Adds terminal colors (default on node.js)
colour.mode = 'browser'; // Adds HTML colors (default in browsers)
colour.mode = 'browser-css'; // Adds special CSS (see examples/example.css)
```

More features
-------------
* node.js/CommonJS compatible
* RequireJS/AMD compatible
* Browser/shim compatible
* Closure Compiler [externs included](https://github.com/dcodeIO/colour.js/blob/master/externs/colour.js)
* Zero dependencies

Credits
-------
Based on work started by Marak (Marak Squires), cloudhead (Alexis Sellier), mmalecki (Maciej Małecki), nicoreed (Nico
Reed), morganrallen (Morgan Allen), JustinCampbell (Justin Campbell) and ded (Dustin Diaz).

License
-------
The MIT-License (MIT)
