canvas-to-tiff
==============

Converts a HTML5 canvas bitmap to a TIFF file (blob, data-uri, array)
that can be saved on user's computer or transferred to server.

The TIFF file is standard compliant (baseline) and support RGB + alpha channel.


Features
--------

- Fast and small!
- All operations are asynchronous and non-blocking
- Supports alpha channel
- Can convert Canvas to TIFF as ArrayBuffer
- Can convert Canvas to TIFF as Blob
- Can convert Canvas to TIFF as Data-URI
- Saves in both big-endian (default) and little-endian (option) format
- Arbitrary DPI for both X and Y directions can be set using options.
- No dependencies
- Documented source incl. HTML version (see docs/ folder)


Install
-------

**canvas-to-tiff** can be installed in various ways:

- Bower: `bower install canvas-to-tiff`
- Git using HTTPS: `git clone https://github.com/epistemex/canvas-to-tiff.git`
- Git using SSH: `git clone git@github.com:epistemex/canvas-to-tiff.git`
- Download [zip archive](https://github.com/epistemex/canvas-to-tiff/archive/master.zip) and extract.
- [canvastotiff.min.js](https://raw.githubusercontent.com/epistemex/canvas-to-tiff/master/canvastotiff.min.js)


Usage
-----

**canvas-to-tiff** is easy to use. Just include the script in header 
or before the script section in your HTML file.

To convert the canvas to a TIFF file, call:

    CanvasToTIFF.toDataURL(canvas, function(uri) {
        // uri is a Data-URI that can be used as source for images etc.
        // uri = "data:image/tiff;base64, ...etc...";
    });

A faster option to Data-URIs is using Blobs:

    CanvasToTIFF.toBlob(canvas, function(blob) {
        // blob object can be converted to an objectURL and then
        // set as source for images, or as download target:
        var url = URL.createObjectURL(blob);
    });

For convenience, a direct Canvas to ObjectURL method is included:

    CanvasToTIFF.toObjectURL(canvas, function(url) {
        // can be used as source for image or download target
    });

To convert it to an ArrayBuffer that can be sent over the net:

    CanvasToTIFF.toArrayBuffer(canvas, function(buffer) {
        // buffer is ArrayBuffer with the TIFF file
    });

Setting an error handler (before calling other operations):

    CanvasToTIFF.setErrorHandler(myErrorHandlerFunc);

**NOTE:** As with with ordinary canvas, cross-origin resource sharing 
(CORS) requirements must be fulfilled.


Issues
------

See the [issue tracker](https://github.com/epistemex/canvas-to-tiff/issues) for details.


License
-------

Released under [MIT license](http://choosealicense.com/licenses/mit/). You may use this class in both commercial and non-commercial projects provided that full header (minified and developer versions) is included.


*&copy; Epistemex 2015-2016*
 
![Epistemex](http://i.imgur.com/wZSsyt8.png)
