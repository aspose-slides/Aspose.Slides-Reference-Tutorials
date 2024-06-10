---
title: Manage Line Spacing in Java PowerPoint
linktitle: Manage Line Spacing in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-text-paragraph-management/manage-line-spacing-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class LineSpacing
{
    public static void main(String[] args)
    {
        //ExStart:LineSpacing

        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create an instance of Presentation class
        Presentation presentation = new Presentation(dataDir + "Fonts.pptx");

        // Obtain a slide's reference by its index
        ISlide sld = presentation.getSlides().get_Item(0);

        // Access the TextFrame
        ITextFrame tf1 = ((IAutoShape) sld.getShapes().get_Item(0)).getTextFrame();

        // Access the Paragraph
        IParagraph para1 = tf1.getParagraphs().get_Item(0);

        // Set properties of Paragraph
        para1.getParagraphFormat().setSpaceWithin(80);
        para1.getParagraphFormat().setSpaceBefore(40);
        para1.getParagraphFormat().setSpaceAfter(40);
        // Save Presentation
        presentation.save(dataDir + "LineSpacing_out.pptx", SaveFormat.Pptx);
        //ExEnd:LineSpacing
    }
}

```
