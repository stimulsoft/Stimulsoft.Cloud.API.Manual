# Export

ExportSet-object contain information about settings for data exporting to more files formats. Each of these formats supports unique features, so different types of files there are different sets of settings.

Full description of the options can be found in the documentation here [https://www.stimulsoft.com/en/documentation/online/programming-manual/index.html?engine_exports.htm](https://www.stimulsoft.com/en/documentation/online/programming-manual/index.html?engine_exports.htm)

Any ExportSet-object contain fields 'Ident' and 'PageRange'.


Ident describes the format in which you want to export data. Values for this field listed in the table below. ExportSet Idents:


**Identifier**

**Description**

[PDF](PDF.md)

PDF-file

[XPS](XPS.md)

XPS-file

[PowerPoint](Power_Point.md)

MS PowerPoint presentation file

[HTML](HTML.md)

HTML-file

[Text](Text.md)

Text file

[RichText](RichText.md)

RichText file format (RTF)

[Word](Word.md)

MS Word document file

[OpenDocumentWriter](OpenDocumentWriter.md)

OpenDocument-file for Writer

[Excel](Excel.md)

MS Excel document file

[OpenDocumentCalc](OpenDocumentCalc.md)

OpenDocument-file for Calc

[Data](Data.md)

One of multiple data format

[Image](Image.md)

One of multiple image format

PageRange describes the pages of the report, which need to be processed. There are three possible values: All pages, Current page and selected pages or range of pages (see the table below). ExportSet PageRange:


**All**

**Current Page**

**Selected Pages (e.g. 1, 3, 5-7)**

`"PageRange": {},`

`"PageRange": {`

`"RangeType": 2`

`},`

`"PageRange": {`

`"RangeType": 3,`

`"PageRanges": "1,3,5-7"`

`},`
