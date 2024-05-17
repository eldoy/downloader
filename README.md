# Getti Downloader

Download, extract and stream files from the Internet.

## Install
```
npm i getti
```

## Require

```js
var getti = require('getti')()
```

## Usage

### Minimal usage:

Downloads, extracts, and streams the JSON file. Returns the final JSON object.

```js
var json = await getti('http://sample.url/sample.json.gz')
```

Downloads, extracts, converts to JSON, and streams the final JSON file. Returns the final JSON object.

```js
var json = await getti('http://sample.url/sample.csv.gz')
```

### Map results:

It is possible to use a callback, and return the value of your choice.

```js
var json = await getti('http://sample.url/sample.json.gz', (value) => {
  return value.name
})
```

Use a non-returning callback to avoid memory issues for large files.

```js
var json = await getti('http://sample.url/sample.json.gz', () => {})
```

### Provide file type:

For URLs that do not include the file extension, include this information in your request. Supported types are `json`, `json.gz`, `csv`, and `csv.gz`.

```js
var json = await getti({ url: 'http://sample.url/sample', type: 'json' })
```

### Bypass logs:
```js
var getti = require('getti')({ quiet: true })
```
or
```js
var json = await getti({
  url: 'http://sample.url/sample.json.gz',
  quiet: true
})
```

MIT Licensed. Enjoy!

Created by [Eldøy Projects](https://eldoy.com)