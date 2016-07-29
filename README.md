cytoscape-node-resize
================================================================================


## Description
Provides grapples to resize nodes.

![Image of extension](img.png)



## Dependencies

 * Cytoscape.js ^2.7.0
 * oCanvas ^2.8.0


## Usage instructions

Download the library:
 * via npm: `npm install cytoscape-node-resize`,
 * via bower: `bower install cytoscape-node-resize`, or
 * via direct download in the repository (probably from a tag).

`require()` the library as appropriate for your project:

CommonJS:
```js
var cytoscape = require('cytoscape');
var nodeResize = require('oCanvas');

nodeResize( cytoscape, jQuery, oCanvas ); // register extension
```

AMD:
```js
require(['cytoscape', 'cytoscape-node-resize'], function( cytoscape, nodeResize, jQuery, oCanvas ){
  nodeResize( cytoscape, jQuery, oCanvas ); // register extension
});
```

Plain HTML/JS has the extension registered for you automatically, because no `require()` is needed.


## API

Only consists of initilization & default options.

```js
            cy.nodeResize({
                  padding: 20, // spacing between node and grapples/rectangle
            
                  grappleSize: 8, // size of square dots
                  grappleColor: "green", // color of grapples
            
                  boundingRectangle: true, // enable/disable bounding rectangle
                  boundingRectangleStroke: "1.5px red", // style bounding rectangle
            
                  minNodeSize: 15, // minimum width/height of node to be set
                  cursors: { // See http://www.w3schools.com/cssref/tryit.asp?filename=trycss_cursor
                    // May take any "cursor" css property
                    default: "default", // to be set after resizing finished or mouseleave
                    nw: "nw-resize",
                    n: "n-resize",
                    ne: "ne-resize",
                    e: "e-resize",
                    se: "se-resize",
                    s: "s-resize",
                    sw: "sw-resize",
                    w: "w-resize"
                  }
             });
```


## Emitted Events
`cy.on("resizestart", function(e, type){ })`

`cy.on("resizeend", function(e, type){ })`


`type` param can be `topleft`, `topcenter`, `topright`, `centerright`, 
`bottomright`, `bottomcenter`, `bottomleft`, `centerleft`


## Publishing instructions

This project is set up to automatically be published to npm and bower.  To publish:

1. Set the version number environment variable: `export VERSION=1.2.3`
1. Publish: `gulp publish`
1. If publishing to bower for the first time, you'll need to run `bower register cytoscape-node-resize https://github.com/iVis-at-Bilkent/cytoscape.js-node-resize.git`

## Team

  * [Selim Firat Yilmaz](https://github.com/mrsfy), [Ugur Dogrusoz](https://github.com/ugurdogrusoz) of [i-Vis at Bilkent University](http://www.cs.bilkent.edu.tr/~ivis)