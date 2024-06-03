---
title: Create Shape Thumbnail in PowerPoint
linktitle: Create Shape Thumbnail in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-powerpoint-shape-thumbnail-creation/create-shape-thumbnail-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.Presentation;
import com.aspose.slides.examples.RunExamples;

import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;


public class CreateShapeThumbnail
{
    public static void main(String[] args) throws IOException
    {
        //ExStart:CreateShapeThumbnail
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Instantiate a Presentation class that represents the presentation file
        Presentation presentation = new Presentation(dataDir + "HelloWorld.pptx");
        try
        {
            // Create a full scale image
            BufferedImage bitmap = presentation.getSlides().get_Item(0).getShapes().get_Item(0).getThumbnail();
            // Save the image to disk in PNG format
            ImageIO.write(bitmap, ".png", new File(dataDir + "Shape_thumbnail_out.png"));
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:CreateShapeThumbnail
    }
}




```
