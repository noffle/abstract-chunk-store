# abstract-chunk-store

A test suite and interface you can use to implement a chunk based storage backend

```
npm install abstract-chunk-store
```

## API

#### `chunkStore.put(index, chunkBuffer, [cb])`

Add a new chunk to the storage. Index should be an integer.

#### `chunkStore.get(index, [options], cb)`

Retrieve a chunk stored. Index should be an integer.
Options include:

``` js
{
  offset: chunkByteOffset,
  length: byteLength
}
```

If the index doesn't exist in the storage an error should
be returned

## Test Suite

Publishing a test suite as a module lets multiple modules all ensure compatibility since
they use the same test suite.

To use the test suite from this module you can `require('abstract-chunk-store/tests')`.

An example of this can be found in the
[memory-chunk-store](https://github.com/mafintosh/memory-chunk-store) test suite.

To run the tests simply pass your test module (`tap` or `tape` or any other compatible
modules are supported) and your store's constructor (or a setup function) in:

```js
var tests = require('abstract-chunk-store/tests')
tests(require('tape'), require('your-custom-chunk-store'))
```

## License

MIT
