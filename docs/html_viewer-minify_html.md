---
id: html_viewer-minify_html
title: HTML Viewer - Minify HTML
custom_edit_url: https://github.com/bobkovalex/groupdocs_docs/blob/master/docs/html_viewer-minify_html.md
---

## HTML Viewer - Minify HTML

When you are looking for the ways to optimize the rendering of documents into HTML, one of the solutions you might want to use is the compression of the output content (HTML, CSS, and SVG). This solution is suitable in case you are providing your content from the web server over the internet. The lower the content user has to download, the faster he will see the rendered document.

### The Solution

GroupDocs.Viewer provides a new [Minify](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/htmlviewoptions/properties/minify) property of the [HtmlViewOptions](https://apireference.groupdocs.com/net/viewer/groupdocs.viewer.options/htmlviewoptions) class, that lets you get output content minified. Minification removes comments, extra white-spaces, and other unneeded characters without breaking the content structure. As a result, the page becomes smaller in size and loads faster. The following example demonstrates how to minify output content when rendering MS Word document into HTML.

The following code sample shows how to enable minification.

```CS
string outputDirectory = @"C:\output\MinifyHtmlDocument";
string pageFilePathFormat = Path.Combine(outputDirectory, "page_{0}.html");
using (Viewer viewer = new Viewer("sample.docx"))
{
    HtmlViewOptions options = HtmlViewOptions.ForEmbeddedResources(pageFilePathFormat);
    options.Minify = true;
    viewer.View(options);
}
```

> This setting will not compress the content as significantly as this might be achieved using Gzip compression (that should be enabled and configured from your web server). But it still might be valuable and can be used as additional optimization in combination with Gzip compression.
 
### Details Behind Minification

The process of minification almost in all cases provides the output that looks identically with original content in all browsers, but minified HTML content does not pass strict HTML validation. Here is the list of technics that lay behind the minification process.

#### HTML Minification
* Comments (except when they contain IE conditional statements) are completely removed
* Conditional comments are compressed
* Spaces and line breaks inside the tags and between the tags are removed
* Document type declaration is simplified to `<!DOCTYPE html>` and all HTML tag properties are removed
* Protocol declarations like http:, https: and javascript: are removed from path values
* Multiple spaces between words (except when they occur inside the pre or textarea tag) are replaced with single space
* Quotes around tag property values (except inline events) are removed
* Default attributes for `<script>`, `<style>` and `<link>` tags are removed
* Boolean attributes are simplified, therefore `<input type="text" disabled="disabled">` becomes `<input type=text disabled>`

#### CSS Minification
* The embedded CSS content is minified when the Minify setting is on.
* Remove all insignificant white-space.
* Remove all comments.
* Remove all unnecessary semicolon separators.
* Reduce color values.
* Reduce integer representations by removing leading and trailing zeros.
* Remove unit specifiers from numeric zero values.