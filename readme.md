#Basic introduction into WebComponents

1. https://code.tutsplus.com/courses/use-web-components-in-vanilla-javascript/lessons/use-web-components-in-vanilla-javascript

2. WebComponents consist of 4 technologies - Templates, Custom Elements, the Shadow DOM, and HTML Imports

3. Most of these features are not yet fully supported in all browsers

```
var template = document.currentScript.ownerDocument.querySelector('template');

var progressIndicatorProto = Object.create(HTMLElement.prototype);

progressIndicatorProto.createdCallback = function () {
  var root = this.createShadowRoot();
  root.appendChild(document.importNode(template.content, true));
}

var progressIndicator = document.registerElement ('progress-indicator', {
  prototype: progressIndicatorProto
});
```
