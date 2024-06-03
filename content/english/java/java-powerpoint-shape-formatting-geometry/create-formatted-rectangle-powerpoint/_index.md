---
title: Create Formatted Rectangle in PowerPoint
linktitle: Create Formatted Rectangle in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 18
url: /java/java-powerpoint-shape-formatting-geometry/create-formatted-rectangle-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;

import java.awt.*;
import java.io.File;


public class FormattedRectangle
{
    public static void main(String[] args)
    {
        //ExStart:FormattedRectangle
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create directory if it is not already present.
        boolean IsExists = new File(dataDir).exists();
        if (!IsExists)
            new File(dataDir).mkdirs();

        // Instantiate Prseetation class that represents the PPTX
        Presentation pres = new Presentation();
        try
        {

            // Get the first slide
            ISlide sld = pres.getSlides().get_Item(0);

            // Add autoshape of rectangle type
            IShape shp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 150, 150, 50);

            // Apply some formatting to rectangle shape
            shp.getFillFormat().setFillType(FillType.Solid);
            shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));

            // Apply some formatting to the line of rectangle
            shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
            shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
            shp.getLineFormat().setWidth(5);

            //Write the PPTX file to disk
            pres.save(dataDir + "RectShp2_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:FormattedRectangle
    }
}

```
