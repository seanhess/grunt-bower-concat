# Bower components concatenator for Grunt [![Build Status](https://travis-ci.org/sapegin/grunt-bower-concat.png)](https://travis-ci.org/sapegin/grunt-bower-concat)

Automatic concatenation of installed [Bower](https://github.com/twitter/bower) components in right order.


## Installation

This plugin requires Grunt 0.4.

```
$ npm install grunt-bower-concat --save-dev
```


## Configuration

Add somewhere in your `Gruntfile.js`:

```javascript
grunt.loadNpmTasks('grunt-bower-concat');
```

Inside your `Gruntfile.js` file add a section named `bower_concat`. See Parameters section below for details.


### Parameters

#### dest

Type: `String`.

Name of file where result of concatenation will be saved.

#### exclude

Type: `String|Array`, optional.

List of components you want to exclude.

```js
exclude: [
	'jquery',
	'modernizr'
]
```

#### include

Type: `String|Array`, optional.

By default bower-concat will include all installed in project components. Using `include` option you can manually specify which components should be included.

```js
include: [
	'underscore',
	'backbone'
]
```

#### dependencies

Type: `Object`, optional.

Unfortunately not all Bower components list their dependencies. If comoponents concatenates in wrong order use this option to manually specify dependencies for that components.

```js
dependencies: {
  'underscore': 'jquery',
  'mygallery': ['jquery', 'fotorama']
}
```

#### bowerOptions

Type: `Object`, optional.

Bower specific options that will be passed in during the bower.commands calls.

```js
bowerOptions: {
  relative: false
}
```


### Config Example

``` javascript
bower_concat: {
  all: {
    dest: 'build/_bower.js',
    exclude: [
    	'jquery',
    	'modernizr'
    ],
    dependencies: {
      'underscore': 'jquery',
      'backbone': 'underscore',
      'jquery-mousewheel': 'jquery'
    },
    bowerOptions: {
      relative: false
    }
  }
}
```

## Changelog

The changelog can be found in the Changelog.md file.

---

## License

The MIT License, see the included `License.md` file.
