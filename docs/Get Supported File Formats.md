---
id: Get Supported File Formats
title: Get Supported File Formats
---

## Get supported file formats

GroupDocs.Viewer allows to get the list of all supported file formats by following the below steps:
* Call GetSupportedFileTypes method of FileType class;
* Enumerate through the collection of FileType objects.

The following code sample demonstrates how to get supported file formats list.

```CS
IEnumerable<FileType> supportedFileTypes = FileType
    .GetSupportedFileTypes()
    .OrderBy(f => f.Extension);
 
foreach (FileType fileType in supportedFileTypes)
    Console.WriteLine(fileType);
```