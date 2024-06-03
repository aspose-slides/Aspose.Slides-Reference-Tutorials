---
title: Create Scaling Factor Thumbnail
linktitle: Create Scaling Factor Thumbnail
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-shape-thumbnail-creation/create-scaling-factor-thumbnail/
---

## Complete Source Code
```java
package com.aspose.slides.examples.shapes;

import com.aspose.slides.Presentation;
import com.aspose.slides.ShapeThumbnailBounds;
import com.aspose.slides.examples.RunExamples;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;


public class CreateScalingFactorThumbnail
{
    public static void main(String[] args) throws IOException
    {
        //ExStart:CreateScalingFactorThumbnail
        // The path to the documents directory.
        String dataDir = RunExamples.getDataDir_Shapes();

        // Instantiate a Presentation class that represents the presentation file
        Presentation p = new Presentation(dataDir + "HelloWorld.pptx");
        try
        {
            // Create a full scale image
            BufferedImage bitmap = p.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail(ShapeThumbnailBounds.Shape, 1, 1);

            // Save the image to disk in PNG format
            ImageIO.write(bitmap, ".png", new File(dataDir + "Scaling Factor Thumbnail_out.png"));
        }
        finally
        {
            if (p != null) p.dispose();
        }
        //ExEnd:CreateScalingFactorThumbnail
    }
}





```
