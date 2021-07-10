# PDF Annotations

Highlighting in PDFs was extended in [2021.03](https://github.com/koreader/koreader/pull/7411) and [2021.04](https://github.com/koreader/koreader/pull/7457).
Since then, the highlights and the text embedded in them (which KOReader uses for labeling bookmarks) can be written to PDF annotations.
The embedded text is written to the "annotation contents", which PDF viewers might render as a popup that can be opened.
Below, the terms "highlight" and "bookmark" refer to KOReader's internal management of highlighted text, whereas "annotation" refers to annotations embedded in a PDF file.

The most obvious use case for this feature is reviewing PDF documents, adding comments, and sending a PDF with the embedded comments to other people.

## What does work

1. Open a PDF document.
2. Verify that Settings -> Document -> Save document (write highlights into PDF) is set to "Prompt" or "Always".
3. Then, you can do a combination of the following steps:
  - Long-tap a word to highlight it.
  - Tap a highlight, select "Edit" and change the text (The popup is titled "Rename bookmark").
  - Tap a highlight, select "Delete" to remove the highlight.
4. Close the document, e.g. by opening the file browser. 
If you set the setting in step 2 to "Prompt", you will be asked whether you want the save the document (and write the highlights to the PDF).
5. The highlights created since opening the document will be written as annotations to the PDF file. 
If you changed the highlight text, the edited text will be written to the PDF annotations as well.

- If you open the document again, the PDF annotations as well as the KOReader highlights will be rendered. 
You can interact with the KOReader highlights, and upon saving the document the changes will be written to the PDF annotations.
  - If you delete a highlight and save the document, the according PDF annotation will be deleted.
  - If you change the text of a highlight and save the document, the edited text will be written to the PDF annotation.

## What does not work

- If you created, edited, or changed highlights while "Save document" was set to "Disable", these changes will never be written to the PDF.
- If KOReader quits without closing the document properly, it will not write any annotations.
- Annotations that were created outside of KOReader cannot be interacted with in KOReader.
