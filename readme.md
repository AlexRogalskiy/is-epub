# is-epub [![Build Status](https://travis-ci.org/sindresorhus/is-epub.svg?branch=master)](https://travis-ci.org/sindresorhus/is-epub)

> Check if a Buffer/Uint8Array is [EPUB](https://en.wikipedia.org/wiki/EPUB)


## Install

```
$ npm install is-epub
```


## Usage

##### Node.js

```js
const readChunk = require('read-chunk');
const isEpub = require('is-epub');
const buffer = readChunk.sync('unicorn.epub', 0, 58);

isEpub(buffer);
//=> true
```

##### Browser

```js
const xhr = new XMLHttpRequest();
xhr.open('GET', 'unicorn.epub');
xhr.responseType = 'arraybuffer';

xhr.onload = () => {
	isEpub(new Uint8Array(this.response));
	//=> true
};

xhr.send();
```


## API

### isEpub(buffer)

Accepts a Buffer (Node.js) or Uint8Array.

It only needs the first 58 bytes.


## Related

- [file-type](https://github.com/sindresorhus/file-type) - Detect the file type of a Buffer/Uint8Array


## License

MIT © [Sindre Sorhus](https://sindresorhus.com)
