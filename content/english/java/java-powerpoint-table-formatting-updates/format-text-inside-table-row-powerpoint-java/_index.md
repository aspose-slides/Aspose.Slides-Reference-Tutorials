---
title: Format Text Inside Table Row in PowerPoint with Java
linktitle: Format Text Inside Table Row in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-table-formatting-updates/format-text-inside-table-row-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class TextFormattingInsideTableRow
{
    public static void main(String[] args)
    {
        // ExStart.getTextFormat().ingInsideTableRow
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create an instance of Presentation class
        Presentation presentation = new Presentation(dataDir + "SomePresentationWithTable.pptx");
        try
        {
            ISlide slide = presentation.getSlides().get_Item(0);

            ITable someTable = (ITable) presentation.getSlides().get_Item(0).getShapes().get_Item(0); // let's say that the first shape on the first slide is a table

            // setting first row cells' font height
            PortionFormat portionFormat = new PortionFormat();
            portionFormat.setFontHeight(25f);
            someTable.getRows().get_Item(0).setTextFormat(portionFormat);

            // setting first row cells' text alignment and right margin in one call
            ParagraphFormat paragraphFormat = new ParagraphFormat();
            paragraphFormat.setAlignment(TextAlignment.Right);
            paragraphFormat.setMarginRight(20);
            someTable.getRows().get_Item(0).setTextFormat(paragraphFormat);

            // setting second row cells' text vertical type
            TextFrameFormat textFrameFormat = new TextFrameFormat();
            textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
            someTable.getColumns().get_Item(0).setTextFormat(textFrameFormat);

            presentation.save(dataDir + "result.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }

        // ExEnd.getTextFormat().ingInsideTableRow
    }
}



```
