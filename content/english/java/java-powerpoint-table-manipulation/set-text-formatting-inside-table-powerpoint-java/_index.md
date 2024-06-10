---
title: Set Text Formatting Inside Table in PowerPoint using Java
linktitle: Set Text Formatting Inside Table in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 20
url: /java/java-powerpoint-table-manipulation/set-text-formatting-inside-table-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class SetTextFormattingInsideTable
{
    public static void main(String[] args)
    {
        //ExStart:Se.getTextFormat().ingInsideTable
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Create an instance of Presentation class
        Presentation presentation = new Presentation(dataDir + "pres.pptx");
        try
        {
            ISlide slide = presentation.getSlides().get_Item(0);

            ITable someTable = (ITable) presentation.getSlides().get_Item(0).getShapes().get_Item(0); // let's say that the first shape on the first slide is a table

            // setting table cells' font height
            PortionFormat portionFormat = new PortionFormat();
            portionFormat.setFontHeight(25);
            someTable.setTextFormat(portionFormat);

            // setting table cells' text alignment and right margin in one call
            ParagraphFormat paragraphFormat = new ParagraphFormat();
            paragraphFormat.setAlignment(TextAlignment.Right);
            paragraphFormat.setMarginRight(20);
            someTable.setTextFormat(paragraphFormat);

            // setting table cells' text vertical type
            TextFrameFormat textFrameFormat = new TextFrameFormat();
            textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
            someTable.setTextFormat(textFrameFormat);


            presentation.save(dataDir + "result.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:Se.getTextFormat().ingInsideTable
    }
}



```
