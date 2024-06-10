---
title: Add Text Box on Slide Programmatically with Java
linktitle: Add Text Box on Slide Programmatically with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 24
url: /java/java-powerpoint-text-font-customization/add-text-box-slide-programmatically-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import java.io.File;


public class TextBoxOnSlideProgram
{
    public static void main(String[] args)
    {
        //ExStart:TextBoxOnSlideProgram
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create directory if it is not already present.
        boolean IsExists = new File(dataDir).exists();
        if (!IsExists)
            new File(dataDir).mkdirs();

        // Instantiate PresentationEx
        Presentation pres = new Presentation();
        try
        {

            // Get the first slide
            ISlide sld = pres.getSlides().get_Item(0);

            // Add an AutoShape of Rectangle type
            IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);

            // Add TextFrame to the Rectangle
            ashp.addTextFrame(" ");

            // Accessing the text frame
            ITextFrame txtFrame = ashp.getTextFrame();

            // Create the Paragraph object for text frame
            IParagraph para = txtFrame.getParagraphs().get_Item(0);

            // Create Portion object for paragraph
            IPortion portion = para.getPortions().get_Item(0);

            // Set Text
            portion.setText("Aspose TextBox");

            // Save the presentation to disk
            pres.save(dataDir + "TextBox_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:TextBoxOnSlideProgram
    }
}

```
