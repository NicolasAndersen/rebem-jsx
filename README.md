# babel-plugin-transform-rebem-jsx

[![npm](https://img.shields.io/npm/v/babel-plugin-transform-rebem-jsx.svg?style=flat-square)](https://www.npmjs.com/package/babel-plugin-transform-rebem-jsx)
[![travis](http://img.shields.io/travis/rebem/rebem-jsx.svg?style=flat-square)](https://travis-ci.org/rebem/rebem-jsx)
[![deps](http://img.shields.io/david/rebem/rebem-jsx.svg?style=flat-square)](https://david-dm.org/rebem/rebem-jsx)

[Babel plugin](https://babeljs.io/docs/plugins/) allowing you to use JSX with [reBEM](https://github.com/rebem/rebem).

## Install

```sh
$ npm i -S babel-plugin-transform-rebem-jsx
```

### `.babelrc`

```js
{
  "plugins": ["transform-rebem-jsx"]
}
```

## Usage

```js
<div block="beep"></div>
<div block="beep" elem="boop"></div>
<div block="beep" mods={{ foo: 'bar' }}></div>
<div block="beep" mix={{ block: 'boop' }}></div>
```

```html
<div class="beep"></div>
<div class="beep__boop"></div>
<div class="beep beep_foo_bar"></div>
<div class="beep boop"></div>
```

## Notes

### Environment

`process.env.NODE_ENV` must be available. For example in webpack you can do this with `DefinePlugin`:

```js
plugins: [
    new webpack.DefinePlugin({
        'process.env': {
            NODE_ENV: JSON.stringify(process.env.NODE_ENV)
        }
    })
]
```

### TODO
- [x] docs
- [ ] move tasks to start-runner
- [ ] actual tests
