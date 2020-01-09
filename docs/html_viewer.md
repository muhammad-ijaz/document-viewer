---
id: html_viewer
title: Document Viewer - HTML Viewer
sidebar_label: HTML Viewer
custom_edit_url: https://github.com/bobkovalex/groupdocs_docs/blob/master/docs/html_viewer.md
---

## Document viewer - HTML Viewer
Document viewer can operate in different rendering modes, HTML, Image and PDF (see [Features Overview](https://wiki.lisbon.dynabic.com/display/viewer/Features+Overview) for more information).
This article will describe on how to view documents in HTML mode with HTML Viewer.

In HTML rendering mode all pages of the source documents are rendered as separate HTML pages. 

For HTML rendering mode following [HtmlViewOptions](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/htmlviewoptions) are available:
* [HtmlViewOptions.ForEmbeddedResources](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/htmlviewoptions/methods/forembeddedresources) - all resources such as styles, fonts, and graphics are integrated into an HTML pages.
  * Pros: No external files which makes more convenient to save result to a stream.
  * Cons: Larger page size and as a result slower loading and rendering of an HTML document in a browser.
* [HtmlViewOptions.ForExternalResources](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/htmlviewoptions/methods/forexternalresources) - all the resources, such as styles, fonts, and graphics are external.
  * Pros: Smaller page size as a page includes only markup and links to external resources. Faster HTML document loading and rendering in a browser as browsers can load multiple external resources simultaneously.
  * Cons: External files, since all resources will be stored next to an HTML page or in a specific directory.

With GroupDocs.Viewer for .NET API HTML rendering became simple and intuitive. Just follow these steps:
* Create a new instance of the [Viewer](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer/viewer) class and pass the source document path as a constructor parameter.
* Instantiate the [HtmlViewOptions](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/htmlviewoptions) object according to your requirements (for embedded or external HTML resources) and specify saving path format for rendered document pages.
* Call View method of [Viewer](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer/viewer) class instance and pass [HtmlViewOptions](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/htmlviewoptions) to it. 

## Document viewer - HTML Viewer (embedded resources)

The following code shows how to render document to HTML with embedded resources.

```CS
using (Viewer viewer = new Viewer("sample.docx"))
{
   // The file path format e.g. 'page_{0}.html'
   string filePathFormat = "page-{0}.html";
   HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(filePathFormat);
   viewer.View(options);
}
```

## Document viewer - HTML Viewer (external resources)

The following code shows how to render document to HTML with external resources.

```CS
using (Viewer viewer = new Viewer("sample.docx"))
{
    // The file path format e.g. 'page_{0}.html'
    string filePathFormat = "page-{0}.html";
    // The resource file path format e.g. 'page_{0}_{1}'
    string resourceFilePathFormat = "page_{0}_{1}"; 
    // The resource URL format e.g. 'page_{0}_{1}' or "http://contoso.com/page_{0}/resource_{1}"
    string resourceUrlFormat = "page_{0}_{1}";
 
    HtmlViewOptions options = HtmlViewOptions.ForExternalResources(filePathFormat, resourceFilePathFormat, resourceUrlFormat);
    viewer.View(options);
}
```