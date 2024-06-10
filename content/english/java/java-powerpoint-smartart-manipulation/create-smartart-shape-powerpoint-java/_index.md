---
title: Create SmartArt Shape in PowerPoint using Java
linktitle: Create SmartArt Shape in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-powerpoint-smartart-manipulation/create-smartart-shape-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import java.io.File;


public class CreateSmartArtShape
{
    public static void main(String[] args)
    {
        //ExStart:CreateSmartArtShape
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create directory if it is not already present.
        boolean IsExists = new File(dataDir).exists();
        if (!IsExists)
            new File(dataDir).mkdirs();
        // Instantiate the presentation
        Presentation pres = new Presentation();
        try
        {

            // Access the presentation slide
            ISlide slide = pres.getSlides().get_Item(0);

            // Add Smart Art Shape
            ISmartArt smart = slide.getShapes().addSmartArt(0, 0, 400, 400, SmartArtLayoutType.BasicBlockList);

            // Saving presentation
            pres.save(dataDir + "SimpleSmartArt_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:CreateSmartArtShape
    }
}

```
