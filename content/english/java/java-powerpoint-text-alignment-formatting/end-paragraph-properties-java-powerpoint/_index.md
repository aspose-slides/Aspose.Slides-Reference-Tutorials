---
title: End Paragraph Properties in Java PowerPoint
linktitle: End Paragraph Properties in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-powerpoint-text-alignment-formatting/end-paragraph-properties-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class EndParaGraphProperties
{
    public static void main(String[] args)
    {
        //ExStart:EndParaGraphProperties
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 10, 10, 200, 250);

            Paragraph para1 = new Paragraph();
            para1.getPortions().add(new Portion("Sample text"));

            Paragraph para2 = new Paragraph();
            para2.getPortions().add(new Portion("Sample text 2"));
            PortionFormat endParagraphPortionFormat = new PortionFormat();
            endParagraphPortionFormat.setFontHeight(48);
            endParagraphPortionFormat.setLatinFont(new FontData("Times New Roman"));
            para2.setEndParagraphPortionFormat(endParagraphPortionFormat);

            shape.getTextFrame().getParagraphs().add(para1);
            shape.getTextFrame().getParagraphs().add(para2);

            pres.save("Your Output Directory" + "pres.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
    }
    //ExEnd:EndParaGraphProperties
}



```
