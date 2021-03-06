require.directory
=================

[![Build Status](https://travis-ci.org/fmmartins/require.directory.svg?branch=v1.0.0)](https://travis-ci.org/fmmartins/require.directory)

Looking for `require()`'ing entire directories recursively into a single object?

This module provides an utility that exposes directories as objects that you can use. 

This folder structure:

    routes/
      foo.js
      bar.json
      folder/
        baz.jsx

Becomes this:
    
    var routes = {
      foo: {},
      bar: {},
      folder: {
        baz: {}
      }
    };

### Installation

    npm i require.directory --save

### Usage

    var requireDirectory = require('require.directory');
    var routes = requireDirectory('./routes', { extensions: ['.js', '.json']});

    console.log(routes)
    // => { foo: { .. }, bar: { .. }, folder: { baz: { .. } } } 

### Options
`extensions`: array of file extensions to load (default: `.js`, `.json`, `.jsx`)


### Roadmap
* Accept array of paths to load multiple directories at once
* Add `flatten` option so that all required files have depth 1
