---
title: Align Paragraphs in PowerPoint using Java
linktitle: Align Paragraphs in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 17
url: /java/java-powerpoint-text-paragraph-management/align-paragraphs-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class ParagraphsAlignment
{
    public static void main(String[] args)
    {
        //ExStart:ParagraphsAlignment
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Instantiate a Presentation object that represents a PPTX file
        Presentation pres = new Presentation(dataDir + "ParagraphsAlignment.pptx");
        try
        {

            // Accessing first slide
            ISlide slide = pres.getSlides().get_Item(0);

            // Accessing the first and second placeholder in the slide and typecasting it as AutoShape
            ITextFrame tf1 = ((IAutoShape) slide.getShapes().get_Item(0)).getTextFrame();
            ITextFrame tf2 = ((IAutoShape) slide.getShapes().get_Item(1)).getTextFrame();

            // Change the text in both placeholders
            tf1.setText("Center Align by Aspose");
            tf2.setText("Center Align by Aspose");

            // Getting the first paragraph of the placeholders
            IParagraph para1 = tf1.getParagraphs().get_Item(0);
            IParagraph para2 = tf2.getParagraphs().get_Item(0);

            // Aligning the text paragraph to center
            para1.getParagraphFormat().setAlignment(TextAlignment.Center);
            para2.getParagraphFormat().setAlignment(TextAlignment.Center);

            //Writing the presentation as a PPTX file
            pres.save(dataDir + "Centeralign_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:ParagraphsAlignment
    }
}

```
