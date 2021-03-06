This is a port of [react-enroute](https://github.com/tj/react-enroute) for [Preact](https://preactjs.com). It works exactly the same way, I only adapted the code style to mine as I am going to maintain this one. I have also reorganised the examples and added an example using hash history.

[![Build Status](https://travis-ci.org/adriantoine/preact-enroute.svg?branch=master)](https://travis-ci.org/adriantoine/preact-enroute)
[![codecov](https://codecov.io/gh/adriantoine/preact-enroute/branch/master/graph/badge.svg)](https://codecov.io/gh/adriantoine/preact-enroute)
[![Stable version](https://img.shields.io/npm/v/preact-enroute.svg?style=flat)](https://www.npmjs.com/package/preact-enroute)
[![Gemnasium](https://img.shields.io/gemnasium/adriantoine/preact-enroute.svg)](https://gemnasium.com/github.com/adriantoine/preact-enroute)

# preact-enroute

 Simple Preact router with a small footprint for modern browsers. This package is not meant to be a drop-in replacement for any router, just a smaller simpler alternative.

 See [path-to-regexp](https://github.com/pillarjs/path-to-regexp) for path matching, this is the same library used by Express.

 If you want to try it, play with it on [this CodePen (using hash history)](http://codepen.io/Alshten/pen/qaENkj), [on WebpackBin](http://www.webpackbin.com/NkS7tXIi-) or run the examples (see below).

## Installation

 ```
 $ npm install preact-enroute
 ```

## Examples

No nesting:

```js
render(
  <Router {...state}>
    <Route path="/" component={Index} />
    <Route path="/users" component={Users} />
    <Route path="/users/:id" component={User} />
    <Route path="/pets" component={Pets} />
    <Route path="/pets/:id" component={Pet} />
    <Route path="*" component={NotFound} />
  </Router>,
  document.querySelector('#app')
);
```

Some nesting:

```js
render(
  <Router {...state}>
    <Route path="/" component={Index} />

    <Route path="/users" component={Users}>
      <Route path=":id" component={User} />
    </Route>

    <Route path="/pets" component={Pets}>
      <Route path=":id" component={Pet} />
    </Route>

    <Route path="*" component={NotFound} />
  </Router>,
  document.querySelector('#app')
);
```

Moar nesting:

```js
render(
  <Router {...state}>
    <Route path="/" component={Index}>
      <Route path="users" component={Users}>
        <Route path=":id" component={User} />
      </Route>

      <Route path="pets" component={Pets}>
        <Route path=":id" component={Pet} />
      </Route>
    </Route>

    <Route path="*" component={NotFound} />
  </Router>,
  document.querySelector('#app')
);
```

## Developing

Build:

```
$ npm run build
```

Start pushState example:

```
$ npm run example-pushstate
```

Start hash example:

```
$ npm run example-hash
```

Running tests:

```
$ npm test
```
