# juicer

Squeeze metadata out of a directory full of markup and media files.

## Installation

Download node at [nodejs.org](http://nodejs.org) and install it, if you haven't already.

```sh
npm install zeke/juicer --save
```

## What it does

- Finds all HTML and markdown files in a given directory.
- Supports [clean URLs](https://surge.sh/help/using-clean-urls-automatically)
- Extracts HTML Frontmatter from HTML and Markdown files
- Extracts color palettes from images
- Extracts EXIF data from images


```
juicer
   ✓ is a function
   ✓ expects a directory and a callback function (76ms)
   sections
     ✓ is an object
     ✓ has one section for each top-level content directory
     each section
       ✓ contains pages
   pages
     ✓ is an object
     ✓ includes .md files
     ✓ includes .markdown files
     ✓ includes .html files
     ✓ removes "index" suffix
     ✓ is case insensitive when finding files
     each page
       ✓ infers `section` from top-level directory
       ✓ has a relativePath
       ✓ ingests HTML frontmatter
       ✓ converts markdown into HTML in `content.processed`
       ✓ preserves original content in `content.original`
       title
         ✓ is derived from HTML frontmatter
         ✓ falls back to <title> tag, if present
         ✓ falls back lastly to titlecased basename
       isIndex
         ✓ is true if file is a directory index
         ✓ is false if file is NOT a directory index
       images
         ✓ builds an images object with a key for each image in the page's directory
         ✓ can be an svg
         ✓ can be a jpg
         ✓ can be a gif
         - includes width and height dimensions for each image
         - includes exif data, if available
         - includes color data, if available
       section
         ✓ is derived from top-level directory
         ✓ is null for top-level files
```

## Tests

```sh
npm install
npm test
```

## Dependencies

- [exif](https://github.com/gomfunkel/node-exif): A node.js library to extract Exif metadata from images.
- [html-frontmatter](https://github.com/zeke/html-frontmatter): Extract key-value metadata from HTML comments
- [lodash](https://github.com/lodash/lodash): The modern build of lodash modular utilities.
- [marky-markdown](https://github.com/npm/marky-markdown): The thing npm uses to clean up READMEs and other markdown files
- [titlecase](https://github.com/rvagg/titlecase): Intelligently converting strings to title case (an enhanced fork of David Gouch&#39;s library)
- [walkdir](https://github.com/soldair/node-walkdir): Find files simply. Walks a directory tree emitting events based on what it finds. Presents a familliar callback/emitter/a+sync interface. Walk a tree of any depth.

## Dev Dependencies

- [cheerio](https://github.com/cheeriojs/cheerio): Tiny, fast, and elegant implementation of core jQuery designed specifically for the server
- [mocha](https://github.com/mochajs/mocha): simple, flexible, fun test framework
- [standard](https://github.com/feross/standard): JavaScript Standard Style


## License

ISC

_Generated by [package-json-to-readme](https://github.com/zeke/package-json-to-readme)_
