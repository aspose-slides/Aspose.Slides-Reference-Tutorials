---
title: Apply Outer Shadow Effects in Java PowerPoint
linktitle: Apply Outer Shadow Effects in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import java.awt.*;
import java.io.File;


public class ApplyingOuterShadowEffects
{
    public static void main(String[] args)
    {
        //ExStart:ShadowEffects
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create directory if it is not already present.
        boolean IsExists = new File(dataDir).exists();
        if (!IsExists)
            new File(dataDir).mkdirs();

        // Instantiate a PPTX class
        Presentation pres = new Presentation();
        try
        {

            // Get reference of the slide
            ISlide sld = pres.getSlides().get_Item(0);

            // Add an AutoShape of Rectangle type
            IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);


            // Add TextFrame to the Rectangle
            aShp.addTextFrame("Aspose TextBox");

            // Disable shape fill in case we want to get shadow of text
            aShp.getFillFormat().setFillType(FillType.NoFill);

            // Add outer shadow and set all necessary parameters
            aShp.getEffectFormat().enableOuterShadowEffect();
            IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
            shadow.setBlurRadius(4.0);
            shadow.setDirection(45);
            shadow.setDistance(3);
            shadow.setRectangleAlign(RectangleAlignment.TopLeft);
            shadow.getShadowColor().setColor(Color.BLACK);

            //Write the presentation to disk
            pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:ShadowEffects
    }
}

```
