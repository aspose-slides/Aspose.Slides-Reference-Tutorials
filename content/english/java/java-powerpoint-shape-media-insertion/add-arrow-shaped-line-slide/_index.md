---
title: Add Arrow Shaped Line to Slide
linktitle: Add Arrow Shaped Line to Slide
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-powerpoint-shape-media-insertion/add-arrow-shaped-line-slide/
---

## Complete Source Code
```java


import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;

import java.awt.*;
import java.io.File;


public class AddArrowShapedLineToSlide
{
    public static void main(String[] args)
    {
        //ExStart:AddArrowShapedLineToSlide
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create directory if it is not already present.
        boolean IsExists = new File(dataDir).exists();
        if (!IsExists)
            new File(dataDir).mkdirs();

        // Instantiate PresentationEx class that represents the PPTX file
        Presentation pres = new Presentation();
        try
        {

            // Get the first slide
            ISlide sld = pres.getSlides().get_Item(0);

            // Add an autoshape of type line
            IAutoShape shp = sld.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);

            // Apply some formatting on the line
            shp.getLineFormat().setStyle(LineStyle.ThickBetweenThin);
            shp.getLineFormat().setWidth(10);

            shp.getLineFormat().setDashStyle(LineDashStyle.DashDot);

            shp.getLineFormat().setBeginArrowheadLength(LineArrowheadLength.Short);
            shp.getLineFormat().setBeginArrowheadStyle(LineArrowheadStyle.Oval);

            shp.getLineFormat().setBeginArrowheadLength(LineArrowheadLength.Long);
            shp.getLineFormat().setEndArrowheadStyle(LineArrowheadStyle.Triangle);

            shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
            shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Maroon));

            //Write the PPTX to Disk
            pres.save(dataDir + "LineShape2_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:AddArrowShapedLineToSlide
    }
}

```