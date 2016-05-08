# musje [![NPM version][npm-image]][npm-url] [![Dependency Status][depstat-image]][depstat-url]

Musje - 123 jianpu music processor.

Musje consists of

- parser
- model
- renderer
- player

Checkout http://jianpu.github.io/musje/demo/ for demo.

## Install

Musje depends on Snap.js for rendering and MIDI.js for playing.
It shall have bower support in the future.

## Usage

```js
var score = musje.parse(musjeString);
score.render(svgSelector, layoutOptions);
score.play();
score.stop();
```

Another way to build a song is using JavaScript object `obj` or
JSON `jsonString`.

```js
var obj = {
  head: {
    title: 'the title',
    composer: '...'
  },
  parts: [{
    measures: [
      { data: [musicData11, musicData12, ...] },  // a measure
      { data: [musicData21, musicData22, ...] },  // another measure
      ...
    ]
  }, {
    measures: [
      data for the second part
    ]
  }]
};
var score = musje.score(obj or jsonString);
```

## Documentation

http://jianpu.github.io/musje/doc/


## Develop

### Install

Install node.js first, and install `gulp` globally
```
npm install -g gulp
```

Clone this repo, and in the project folder run
```
npm install
```


### Build

Build the musje library.
```
gulp build-musje
```

Build the musje documentation.
```
gulp build-doc
```

Build both the musje library and documentation.
```
gulp build
```

Or watch the documentation build during development.
```
gulp watch-doc
```


### Demo

Serve and watch demo of the musje library with live-reload, useful for the developing process.

```
gulp
```
or
```
gulp watch-demo
```


[npm-url]: https://npmjs.org/package/musje
[npm-image]: https://badge.fury.io/js/musje.png

[depstat-url]: https://david-dm.org/jianpu/musje
[depstat-image]: https://david-dm.org/jianpu/musje.png
