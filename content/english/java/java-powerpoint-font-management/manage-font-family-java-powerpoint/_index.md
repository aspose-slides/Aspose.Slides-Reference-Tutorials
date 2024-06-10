---
title: Manage Font Family in Java PowerPoint
linktitle: Manage Font Family in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-powerpoint-font-management/manage-font-family-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import java.awt.*;
import java.io.File;


public class FontFamilyExample
{
    public static void main(String[] args)
    {
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create directory if it is not already present.
        boolean IsExists = new File(dataDir).exists();
        if (!IsExists)
            new File(dataDir).mkdirs();

        //ExStart:FontFamily
        // Instantiate Presentation Class
        Presentation pres = new Presentation();
        try
        {

            // Get first slide
            ISlide sld = pres.getSlides().get_Item(0);

            // Add an AutoShape of Rectangle type
            IAutoShape ashp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);

            // Remove any fill style associated with the AutoShape
            ashp.getFillFormat().setFillType(FillType.NoFill);

            // Access the TextFrame associated with the AutoShape
            ITextFrame tf = ashp.getTextFrame();
            tf.setText("Aspose TextBox");

            // Access the Portion associated with the TextFrame
            IPortion port = tf.getParagraphs().get_Item(0).getPortions().get_Item(0);

            // Set the Font for the Portion
            port.getPortionFormat().setLatinFont(new FontData("Times New Roman"));

            // Set Bold property of the Font
            port.getPortionFormat().setFontBold(NullableBool.True);

            // Set Italic property of the Font
            port.getPortionFormat().setFontItalic(NullableBool.True);

            // Set Underline property of the Font
            port.getPortionFormat().setFontUnderline(TextUnderlineType.Single);

            // Set the Height of the Font
            port.getPortionFormat().setFontHeight(25);

            // Set the color of the Font
            port.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            port.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);

            //Write the presentation to disk
            pres.save(dataDir + "pptxFont_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:FontFamily
    }
}

```
