---
id: version-19.12.0-image_viewer
title: Document Viewer - Image Viewer
sidebar_label: Image Viewer
custom_edit_url: https://github.com/bobkovalex/groupdocs_docs/blob/master/docs/image_viewer.md
original_id: image_viewer
---

## Document viewer - Image Viewer
Document viewer can operate in different rendering modes, HTML, Image and PDF (see Features Overview for more information).
This article will describe on how to view documents in Image mode with Image Viewer.

Image Viewer provides [PngViewOptions](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/pngviewoptions) and [JpgViewOptions](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/jpgviewoptions) classes to set specific options for rendering the document into desired image format.
Here are the steps for rendering into image with GroupDocs.Viewer API:
* Create new instance of [Viewer](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer/viewer) class and pass source document path as a constructor parameter.
* Instantiate the [PngViewOptions](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/pngviewoptions) or [JpgViewOptions](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/jpgviewoptions) object according to your requirements and specify saving path format for rendered document pages.
* Call [View](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer/viewer/methods/view) method of [Viewer](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer/viewer) class instance and pass [PngViewOptions](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/pngviewoptions) or [JpgViewOptions](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/jpgviewoptions) to it. 

## Document Viewer - Image Viewer (PNG) 

This example shows how to render each document page into PNG image.
```CS
using (Viewer viewer = new Viewer("sample.docx"))
{
    PngViewOptions options = new PngViewOptions("page-{0}.png");
    viewer.View(options);
}
```

## Document Viewer - Image Viewer (JPG)

This example shows how to render each document page into JPG image.
```CS
using (Viewer viewer = new Viewer("sample.docx"))
{
    JpgViewOptions options = new JpgViewOptions("page-{0}.jpg");                  
    viewer.View(options);
}
```