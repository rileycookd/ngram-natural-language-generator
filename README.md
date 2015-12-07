[![NPM version][npm-image]][npm-url] [![Build Status][travis-image]][travis-url] [![Dependency Status][daviddm-url]][daviddm-image]

# ngram-natural-language-generator

Takes in text/file(s)/stream(s) and generates random sentences that sound like they could have been in the original text using a bigram generator.

# Usage

## Commandline

```bash
$ ./index.js samples/jaberwocky.txt
```

## Javascript

From file:

```javascript
var generator = require('ngram-natural-language-generator');

generator({
	filename: 'samples/jabberwocky.txt',
	model: {
		maxLength: 100,
		minLength: 50
	}
}, function(err, sentence){
	console.log(sentence);
	// One two. Callooh. Beware the borogoves And the claws that bite the Jabberwock my
	// beamish boy. One two. One two. And through the mome raths outgrabe. And stood The
	// frumious Bandersnatch. He took his joy. And the borogoves And the claws that bite the
	// wabe All mimsy were the Jabberwock with eyes of flame Came whiffling through and the
	// slithy toves Did gyre and through The Jabberwock. Twas brillig and shun The Jabberwock
	// my son. Beware the borogoves And the mome raths outgrabe. Beware the Jabberwock. Come
	// to my son.
});
```

From text:

```javascript
var generator = require('ngram-natural-language-generator');

generator({
	text: 'Colorless green ideas sleep furiously.',
	model: {
		maxLength: 100,
		minLength: 50
	}
}, function(err, sentence){
	console.log(sentence);
});
```

From web url:

```javascript
var generator = require('ngram-natural-language-generator');
var http = require('http');

http.get('http://www.jabberwocky.com/carroll/jabber/jabberwocky.html', function(res) {
	generator({
		stream: res
	}, function(err, sentence){
		console.log(sentence);
	});
});

```

[npm-url]: https://npmjs.org/package/ngram-natural-language-generator
[npm-image]: https://badge.fury.io/js/ngram-natural-language-generator.svg
[travis-url]: https://travis-ci.org/cesine/ngram-natural-language-generator
[travis-image]: https://travis-ci.org/cesine/ngram-natural-language-generator.svg?branch=master
[daviddm-url]: https://david-dm.org/cesine/ngram-natural-language-generator.svg?theme=shields.io
[daviddm-image]: https://david-dm.org/cesine/ngram-natural-language-generator
