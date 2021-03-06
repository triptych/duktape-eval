# duktape-eval

A safe **eval** library based on WebAssembly build of [Duktape](https://duktape.org/).

[Demo](https://gh.maple3142.net/maple3142/duktape-eval/ae198189baf244ff062901475e8877637d265df3/example/example.html) | [Source code of Demo](https://github.com/maple3142/duktape-eval/blob/master/example/example.html)

## Usage

In node:

```js
const { getInstance } = require('duktape-eval')
getInstance().then(mod => {
	console.log(mod.eval('1+1')) // 2
})
```

In browser:

```html
<script src="https://cdn.jsdelivr.net/gh/maple3142/duktape-eval/duktapeEval.js"></script>
<script>
duktapeEval.getInstance().then(mod => {
	console.log(mod.eval('1+1')) // 2
})
</script>
```

## Q&A

### What can it runs?

Whatever [Duktape](https://duktape.org/) can run. Basically ES5 syntax and some ES6, ES7 capabilities.

### How can I pass data to it?

`JSON.stringify` is your friend.

### How can I return data from it?

Just like normal `eval`, for example `var a={};a.prop=1;a` will return `{ prop: 1 }`. But keep in mind, only JSON serializable data can be returned.

### How big is this?

Script size: 348kB
Gzipped size: 154kB
