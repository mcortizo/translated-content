---
title: Zoom de página inteira
slug: Mozilla/Firefox/Releases/3/Full_page_zoom
tags:
  - Extensões
  - Firefox 3
  - XUL
translation_of: Mozilla/Firefox/Releases/3/Full_page_zoom
original_slug: Mozilla/Firefox/Releases/3/Zoom_de_página_inteira
---
{{FirefoxSidebar}}

{{ Gecko_minversion_header("1.9") }}

Zoom de página inteira (ou apenas fullzoom) é um novo recurso do [Firefox 3](/en/Firefox_3_for_developers "en/Firefox_3_for_developers").

### Exemplo (XUL:browser)

O exemplo a seguir demonstra o uso da janela atual do navegador. Esse é o uso típico de uma extensão do Firefox.

```
var zoom = ZoomManager.getZoomForBrowser(gBrowser.selectedBrowser);
ZoomManager.enlarge();
ZoomManager.setZoomForBrowser(gBrowser.selectedBrowser, ZoomManager.MIN);
```

### Exemplo (XUL:iframe)

Nota: Isso provavelmente está desatualizado.

Você pode usar o recurso fullZoom para um [XUL:iframe](/en/XUL/iframe "en/XUL/iframe") também. No entanto, como um iframe não tem uma propriedade markupDocumentViewer, precisamos obtê-la primeiro:

```
var zoom = 1.5;
var iframe = document.getElementById("authorFrame");
var contViewer = iframe.docShell.contentViewer;
var docViewer = contViewer.QueryInterface(Components.interfaces.nsIMarkupDocumentViewer);
docViewer.fullZoom = zoom;
```

### References

- Extensão de zoom de página por Ted Mielczarek [fullpagezoom.xpi](http://ted.mielczarek.org/code/mozilla/fullpagezoom.xpi) para os últimos Firefox 3.0 nightlies
- [Glazoom extension](https://addons.mozilla.org/en-US/firefox/addon/6489) por Daniel Glazman para Firefox 3.0
- O [bugzilla bug](https://bugzilla.mozilla.org/show_bug.cgi?id=4821) sobre fullZoom.
- `nsIMarkupDocumentViewer` documentação da interface.