---
id: version-19.12.0-get_supported_file_formats
title: Get Supported File Formats
custom_edit_url: https://github.com/bobkovalex/groupdocs_docs/blob/master/docs/get_supported_file_formats.md
original_id: get_supported_file_formats
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