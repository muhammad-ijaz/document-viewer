---
id: version-19.12.0-get_file_information
title: Get File Information
custom_edit_url: https://github.com/bobkovalex/groupdocs_docs/blob/master/docs/get_file_information.md
original_id: get_file_information
---

## Get file information

GroupDocs.Viewer for .NET API allows you to extract file information from different document types through ViewInfo class which will include following properties:
* [FileType](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.results/viewinfo/properties/filetype)
* [PageCount](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.results/viewinfo/properties/pages)

For the following document types GroupDocs.Viewer provides additional information:
* Archive files - collection of folders inside archive [see [Get View Info for Archive File](https://wiki.lisbon.dynabic.com/display/viewer/Get+View+Info+for+Archive+File));
* CAD drawings - collection of layouts and layers (see [Get View Info for CAD Drawing](https://wiki.lisbon.dynabic.com/display/viewer/Get+View+Info+for+CAD+Drawing)); 
* Outlook data files - collection of folders inside data file (see [Get View Info for Outlook Data File](https://wiki.lisbon.dynabic.com/display/viewer/Get+View+Info+for+Outlook+Data+File));
* PDF documents - flag that indicates whether document printing is allowed or not (see [Get View Info for PDF Document](https://wiki.lisbon.dynabic.com/display/viewer/Get+View+Info+for+PDF+Document));
* MS Project documents - project start/end dates (see [Get View Info for MS Project Document](https://wiki.lisbon.dynabic.com/display/viewer/Get+View+Info+for+MS+Project+Document)).

## Get file information for the file from local disk

```CS
using (Viewer viewer = new Viewer("sample.pdf"))
{
    ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForHtmlView());
    Console.WriteLine("Document type is: " + info.FileType);
    Console.WriteLine("Pages count: " + info.Pages.Count);
}
```

## Get file information for the file from stream

```CS
using (Viewer viewer = new Viewer(() => File.OpenRead("sample.pdf")))
{
    ViewInfo info = viewer.GetViewInfo(ViewInfoOptions.ForHtmlView());
    Console.WriteLine("Document type is: " + info.FileType);
    Console.WriteLine("Pages count: " + info.Pages.Count);
}
```
