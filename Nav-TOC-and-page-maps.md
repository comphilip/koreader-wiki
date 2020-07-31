Koreader supports advanced TOC with page maps ("real page numbers") if ebook format supports it, i.e. EPUB3. It enables that "real page numbers" etc. be shown on pages:

![](https://user-images.githubusercontent.com/24273478/77579495-b5c90f00-6eda-11ea-8367-e91771f3b819.png)

There's more options included:

- Fix lvRect:isRectInside(rc) with 0-width or 0-height rect - closes #5991
- TOC: parse EPUB3 nav toc, fallback to spine when no toc - closes #4915
- Parse and cache various hardcopy page list maps
- epub.css: hide EPUB3 <span epub:type="pagebreak"> content
cre.cpp: add a few PageMap helper functions.

Adds ReaderPageMap which will add a new menu (under TOC and Bookmarks) that will allow:
- to list source page numbers (like a TOC)
- to show visible page labels in the right margin
- to use these source page numbers in the footer, the TOC, the GoTo and SkimTo widgets, and to use the source page number in the standard bookmark and highlight initial text.
- (and to unwontfix and close #4521)

More on this could be found [here.](https://github.com/koreader/koreader/pull/6004)