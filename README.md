# async-each

No-bullshit, ultra-simple, 35-lines-of-code async parallel forEach function for JavaScript.

We don't need junky 30K async libs. Really.

For browsers and node.js.

## Installation
* Just include async-each before your scripts.
* `npm install async-each` if you’re using node.js.
* `bower install async-each` if you’re using [Bower](http://bower.io).

## Usage

* `each(array, iterator, callback);` — `Array`, `Function`, `(optional) Function`
* `iterator(item, next)` receives current item and a callback that will mark the item as done. `next` callback receives optional `error, transformedItem` arguments.
* `callback(error, transformedArray)` optionally receives first error and transformed result `Array`.

```javascript
var each = require('async-each');
each(['a.js', 'b.js', 'c.js'], fs.readFile, function(error, contents) {
  if (error) console.error(error);
  console.log('Contents for a, b and c:', contents);
});

// Alternatively in browser:
asyncEach(list, fn, callback);
```

## License

[MIT](https://github.com/paulmillr/mit) (c) 2016 Paul Miller (http://paulmillr.com)
