---
title: Format Text Inside Table Column in PowerPoint using Java
linktitle: Format Text Inside Table Column in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-powerpoint-table-formatting-updates/format-text-inside-table-column-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class TextFormattingInsideTableColumn
{
    public static void main(String[] args)
    {
        // ExStart.getTextFormat().ingInsideTableColumn
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create an instance of Presentation class
        Presentation pres = new Presentation(dataDir + "SomePresentationWithTable.pptx");
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);

            ITable someTable = (ITable) pres.getSlides().get_Item(0).getShapes().get_Item(0); // let's say that the first shape on the first slide is a table

            // setting first column cells' font height
            PortionFormat portionFormat = new PortionFormat();
            portionFormat.setFontHeight(25);
            someTable.getColumns().get_Item(0).setTextFormat(portionFormat);

            // setting first column cells' text alignment and right margin in one call
            ParagraphFormat paragraphFormat = new ParagraphFormat();
            paragraphFormat.setAlignment(TextAlignment.Right);
            paragraphFormat.setMarginRight(20);
            someTable.getColumns().get_Item(0).setTextFormat(portionFormat);

            // setting second column cells' text vertical type
            TextFrameFormat textFrameFormat = new TextFrameFormat();
            textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
            someTable.getColumns().get_Item(0).setTextFormat(portionFormat);

            pres.save(dataDir + "result.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }

        // ExEnd.getTextFormat().ingInsideTableColumn
    }
}



```
