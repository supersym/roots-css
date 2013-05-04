Roots CSS
---------

Roots css is a terse, feature-rich css library built on top of stylus. It's a
child .... **this** is why I forked: I don't want everything else, already have
development stack but seems that is so much supported that you're told to use
the `roots` tool because its easier. No, no no... so I'm taking the stylus ;)
thanks - and now to incorp. in say, ....

### Example usage under express

```js
var connect = require('connect')
  , stylus = require('stylus')
  , roots = require('roots-css');

var server = connect();

function compile(str, path) {
  return stylus(str)
    .set('filename', path)
    .use(roots());
}

server.use(stylus.middleware({
    src: __dirname
  , compile: compile
}));
```

You should have access to all the roots mixins once this is done. Whoo!
