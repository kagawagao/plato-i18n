# PLATO-I18N

> :globe_with_meridians: A Simple I18n Plugin for Vue

[![Travis](https://img.shields.io/travis/crossjs/plato-i18n.svg?style=flat-square)](https://travis-ci.org/crossjs/plato-i18n)
[![Coveralls](https://img.shields.io/coveralls/crossjs/plato-i18n.svg?style=flat-square)](https://coveralls.io/github/crossjs/plato-i18n)
[![dependencies](https://david-dm.org/crossjs/plato-i18n.svg?style=flat-square)](https://david-dm.org/crossjs/plato-i18n)
[![devDependency Status](https://david-dm.org/crossjs/plato-i18n/dev-status.svg?style=flat-square)](https://david-dm.org/crossjs/plato-i18n#info=devDependencies)

## Usage

### install plugin

``` js
import Vue from 'vue'
import I18n from 'plato-i18n'

Vue.use(I18n, {
  // set global resources
  data () {
    // return json
    // could use vuex.store for reactive
    return {
      a: {
        b: 'c{d}e'
      }
    }
  }
})
```

### set resources in components

``` js
export default {
  name: 'App',
  // optional
  i18n: {
    // set local resources
    // would OVERRIDE global resources
    data () {
      return {
        a: {
          b: 'c[0]e'
        }
      }
    }
  }
}
```

### use resources in components

``` vue
<template>
{{__('a.b', { d: 'D' })}}
<!-- or -->
{{__('a.b', ['D'])}}
</template>
```
