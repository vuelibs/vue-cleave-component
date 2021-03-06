# Vue Cleave Component

[![vue-js](https://img.shields.io/badge/vue.js-2.x-brightgreen.svg?maxAge=604800)](https://vuejs.org/)
[![downloads](https://img.shields.io/npm/dt/vue-cleave-component.svg)](http://npm-stats.com/~packages/vue-cleave-component)
[![npm-version](https://img.shields.io/npm/v/vue-cleave-component.svg)](https://www.npmjs.com/package/vue-cleave-component)
[![github-tag](https://img.shields.io/github/tag/ankurk91/vue-cleave-component.svg?maxAge=1800)](https://github.com/ankurk91/vue-cleave-component/)
[![license](https://img.shields.io/github/license/ankurk91/vue-cleave-component.svg?maxAge=1800)](https://yarnpkg.com/en/package/vue-cleave-component)
[![build-status](https://travis-ci.org/ankurk91/vue-cleave-component.svg?branch=master)](https://travis-ci.org/ankurk91/vue-cleave-component)
[![codecov](https://codecov.io/gh/ankurk91/vue-cleave-component/branch/master/graph/badge.svg)](https://codecov.io/gh/ankurk91/vue-cleave-component)

Vue.js v2.x component for [Cleave.js](http://nosir.github.io/cleave.js/) 

## Demo on [JSFiddle](https://jsfiddle.net/ankurk91/aza302c7/)

## Features
* Reactive ``v-model`` value
    - You can change input value programmatically 
* Reactive [options](https://github.com/nosir/cleave.js/blob/master/doc/options.md) 
    - You can change config options dynamically
    - Component will watch for any changes and redraw itself
    - You are suggested to modify config via [Vue.set](https://vuejs.org/v2/api/#Vue-set)
* Compatible with [Bootstrap](http://getbootstrap.com/), [Bulma](http://bulma.io/) or any other CSS framework
* Option to disable `raw` mode to get masked value 

## Installation
```bash
# npm
npm install vue-cleave-component --save

# Yarn
yarn add vue-cleave-component
```

## Usage
```html
<template>
  <div>
    <cleave v-model="cardNumber" :options="options" class="form-control" name="card"></cleave>
  </div>
</template>

<script>
  import Cleave from 'vue-cleave-component';
    
  export default {    
    data () {
      return {
        cardNumber: null, 
        options: {
          creditCard: true,
          delimiter: '-',
        }      
      }
    },
    components: {
      Cleave
    }
  }
</script>
```

### As plugin
```js
  import Vue from 'vue';
  import Cleave from 'vue-cleave-component';
  Vue.use(Cleave);
```
This will register a global component `<cleave>` 

## Available props
The component accepts these props:

| Attribute        | Type                   | Default     | Description      |
| :---             | :---:                  | :---:       | :---             |
| v-model / value  | String / Number / null | `null`      | Set or Get input value (required) |
| options          | Object                 | `{}`        | Cleave.js [options](https://github.com/nosir/cleave.js/blob/master/doc/options.md) |
| raw              | Boolean                | `true`      | When set to `false`; emits formatted value with format pattern and delimiter |
| type             | String                 | `text`      | Set input type; for eg: `tel` |

## Install in non-module environments (without webpack)
* Include required files
```html
<!-- cleave.js -->
<script src="https://cdn.jsdelivr.net/npm/cleave.js@1"></script>
<!-- Vue.js -->
<script src="https://cdn.jsdelivr.net/npm/vue@2.5"></script>
<!-- Lastly add this package -->
<script src="https://cdn.jsdelivr.net/npm/vue-cleave-component@2"></script>
```
* Use the component anywhere in your app like this
```html
<main id="app">  
    <cleave v-model="card" :options="options"></cleave> 
</main>
<script>
  // Initialize global component
  Vue.use(VueCleave);
  
  new Vue({
    el: '#app',
    data: {
      card: null,
      options: {
        creditCard: true,
      }
    },    
  });
</script>
```

## Run examples on your localhost
* Clone this repo
* You should have node-js `>=6.10` and yarn `>=1.x` pre-installed
* Install dependencies `yarn install`
* Run webpack dev server `yarn start`
* This should open the demo page at ``http://localhost:9000`` in your default web browser

### Testing
* This package is using [Jest](https://github.com/facebook/jest) and [vue-test-utils](https://github.com/vuejs/vue-test-utils) for testing.
* Tests can be found in `__test__` folder
* Execute tests with this command `yarn test`

## Changelog
Please see [CHANGELOG](CHANGELOG.md) for more information what has changed recently.

## License
[MIT](LICENSE.txt) License
