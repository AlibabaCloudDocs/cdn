# HTMLStream API

This topic provides information about the HTMLStream API operation and solutions to errors that may occur when you call HTMLStream.

## Rewriter

The rewriter is used to register the object that you want to rewrite. The object is specified in an array that consists of two elements. Description of the array:

-   The first element in the array must be of the string type or null.
    -   String: specifies an element selector that is used to locate an element or tag.
    -   null: specifies that the rewriter applies to an entire document.

        **Note:** In most cases, you do not need to apply the rewriter to an entire document. If the rewriter is applied to an entire document, it cannot locate elements.

-   The second element in the array must be a JavaScript object. This object is returned to the callback function that you have registered.

    If you choose to use an element selector, the callback function is named the Element callback function. If you choose to use a document selector, the callback function is named the Document callback function.


**Note:** You can set one or more rewriters for the HTMLStream operation. You can set multiple element selectors but only one document selector.

## Syntax of element selectors

The element selector syntax is a subset of the CSS selector syntax. The programming language of an element selector may be different from that of a CSS selector. The following list describes the syntax of element selectors:

-   `*`: specifies all elements or tags.
-   `div`: specifies the tag named `div`. You can specify other tag names in this format. HTML and custom tags are supported.
-   `E#id`: specifies the tag named E. The ID of the tag is specified by `id`.
-   `E.Class`: specifies the tag named E. The class of the tag is specified by `Class`.
-   `E[attr]`: specifies the tag named E. The properties of the tag include the name attr.
-   Element properties:

-   `E[attr="a"]`: specifies the tag named E. The properties of the tag include attr, which is set to a. The value is case-sensitive.
-   `E[attr^="a"]`: specifies the tag named E. The properties of the tag include attr, which is set to a. The value is not case-sensitive.
-   `E[attr$="a"]`: specifies the tag named E. The properties of the tag include attr whose value ends with a.
-   `E[attr^="a"]`: specifies the tag named E. The properties of the tag include attr whose value starts with a.
-   `E[attr*="a"]`: specifies the tag named E. The properties of the tag include attr whose value contains a.
-   `E[attr|="a"]`: specifies the tag named E. The properties of the tag include attr whose values start with a- and are separated with commas \(,\). Example: en-ch, en-us.
-   Order between elements:

-   `E F`: specifies the tag named F, which exists in the parent element named E.
-   `E > F`: specifies the tag named F whose parent element is the tag named E.
-   `E:not(S)`: specifies the tag named E. S is another element selector. Tag E can be selected only when the selector is set to false.

## Callback functions for element selectors

The following table describes the callback functions supported by element selectors.

|Callback function|Description|Function signature|
|-----------------|-----------|------------------|
|element|A non-asynchronous callback function that is called after the selected elements are completely parsed.|The signature of the callback function is function\(e\). This signature is carried in the Element object. For more information, see [Element](/intl.en-US/EdgeRoutine/Introduction to EdgeRoutine/HTMLStream/Arguments.md).|
|comments|A non-asynchronous callback function that is called when the selected elements have comments.|The signature of the callback function is function\(e\). This signature is carried in the Comments object. For more information, see [Comments](/intl.en-US/EdgeRoutine/Introduction to EdgeRoutine/HTMLStream/Arguments.md).|
|text|A non-asynchronous callback function that is called when the text returned to the callback function is parsed.|The signature of the callback function is function\(e\). This signature is carried in the TextChunk object. For more information, see [TextChunk](/intl.en-US/EdgeRoutine/Introduction to EdgeRoutine/HTMLStream/Arguments.md).**Note:** This callback function may be called multiple times. When HTMLStream reads chunks of text from the raw HTML data and each time a chunk is parsed, this callback function is called. If you want to view the complete text, you must load all the text chunks and merge them. |

**Note:** An element selector can exclude all the preceding callback functions. In this case, the relevant elements are printed without the need to be processed. If you want to modify only a specific chunk of the text, register the required callback function.

## Document selector

A document selector manages a specified document. To use a document selector, set the first element in the rewriter array to null. In the HTMLStream operation, you can configure only one document selector.

## Callback functions for document selectors

The callback functions for document selectors are similar to those for element selectors. The following table describes the callback functions supported by document selectors.

|Callback function|Description|Function signature|
|-----------------|-----------|------------------|
|doctype|A non-asynchronous callback function that is called when the document type declaration \(DOCTYPE\) in the specified document is parsed.|The signature of the callback function is function\(e\). This signature is carried in the Doctype object. For more information, see [Doctype](/intl.en-US/EdgeRoutine/Introduction to EdgeRoutine/HTMLStream/Arguments.md).|
|comments|A non-asynchronous callback function that is called when the specified document has comments.|The signature of the callback function is function\(e\). This signature is carried in the Comments object. For more information, see [Comments](/intl.en-US/EdgeRoutine/Introduction to EdgeRoutine/HTMLStream/Arguments.md).|
|text|A non-asynchronous callback function that is called when the specified document has text nodes.|The signature of the callback function is function\(e\). This signature is carried in the TextChunk object. For more information, see [TextChunk](/intl.en-US/EdgeRoutine/Introduction to EdgeRoutine/HTMLStream/Arguments.md).**Note:** This callback function may be called multiple times. When HTMLStream reads chunks of text from the raw HTML data and each time a chunk is parsed, this callback function is called. If you want to view the complete text, you must load all the text chunks and merge them. |
|docend|A non-asynchronous callback function that is called after the specified document is completely parsed. This callback function appends content such as debugging information to the end of the HTML document as annotations. You can use this information to troubleshoot and track errors.|The signature of the callback function is function\(e\). This signature is carried in the Docend object. For more information, see [Docend](/intl.en-US/EdgeRoutine/Introduction to EdgeRoutine/HTMLStream/Arguments.md).|

## Solutions to exceptions

Exceptions that are thrown by the preceding callback functions are caught by ER. Meanwhile, HTMLStream stops processing HTML streams and propagates the exception to the outer layers.

-   If the reader.read method is called in HTMLStream, the exceptions are thrown again.
-   If the reader.read method is called in HTMLStream when ER is running, ER hides the exceptions. For example, if the exceptions occur when ER returns a response to a client, the response is interrupted and the client receives only a part of the response. This is because HTMLStream treats data as streams. In this case, the stream may be interrupted before all the data is returned to the client. The way HTMLStream processes exceptions is similar to that of TransformStream. TransformStream also writes and reads data as streams.

