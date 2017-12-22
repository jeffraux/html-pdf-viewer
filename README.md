# html-pdf-viewer
Client-side rendering of html to pdf with display and save options

## Getting Started

#### NPM

Install html-pdf-viewer and its dependencies using NPM with `npm install --save html-pdf-viewer`.

## Import

```js
import htmlpdfviewer from 'html-pdf-viewer';
```

## Usage

Simplest way:

```js
var element = document.getElementById('element-to-print');

htmlpdfviewer(element);
```

## Options

html-pdf-viewer can be configured by adding an optional `options` parameter: `htmlpdfviewer(<source>, {<options>});`

```js
var element = document.getElementById('element-to-print');

htmlpdfviewer(element, {
  margin:       1,
  filename:     'myfile.pdf',
  image:        { type: 'jpeg', quality: 0.98 },
  html2canvas:  { dpi: 192, letterRendering: true },
  jsPDF:        { unit: 'in', format: 'letter', orientation: 'portrait' },
  output:       { mode: 'display', container: '#iframeId', height: 800 }
});
```

The `options` parameter has the following optional fields:

|Name        |Type            |Default                       |Description                                                                                                 |
|------------|----------------|------------------------------|------------------------------------------------------------------------------------------------------------|
|margin      |number or array |0                             |PDF margin (in jsPDF units). Can be a single number, `[top&bottom, left&right]`, or `[top, left, bottom, right]`. |
|filename    |string          |'file.pdf'                    |The default filename of the exported PDF.                                                                   |
|image       |object          |{type: 'jpeg', quality: 0.95} |The image type and quality used to generate the PDF.                                                        |
|enableLinks |boolean         |true                          |If enabled, PDF hyperlinks are automatically added ontop of all anchor tags.                                |
|html2canvas |object          |{ }                           |Configuration options sent directly to `html2canvas` ([see here](https://html2canvas.hertzen.com/documentation.html#available-options) for usage).|
|jsPDF       |object          |{ }                           |Configuration options sent directly to `jsPDF` ([see here](http://rawgit.com/MrRio/jsPDF/master/docs/jsPDF.html) for usage).|
|output      |object          |{ }                           |Configuration options for saving/displaying the pdf. `mode`: `save` or `display`. `container`: Iframe element id on where you want to display the PDF. `height`: Display height of the iframe. |

## Credits

[Jefferson Aux](https://github.com/jeffraux)

## License

[The MIT License](http://opensource.org/licenses/MIT)

Copyright (c) 2017 Jefferson Aux