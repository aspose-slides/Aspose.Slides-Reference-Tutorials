---
title: Change SmartArt Layout in PowerPoint with Java
linktitle: Change SmartArt Layout in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 19
url: /java/java-powerpoint-smartart-manipulation/change-smartart-layout-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;



public class ChangeSmartArtLayout
{
    public static void main(String[] args)
    {
        //ExStart:ChangeSmartArtLayout
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation presentation = new Presentation();
        try
        {
            // Add SmartArt BasicProcess 
            ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicBlockList);

            // Change LayoutType to BasicProcess
            smart.setLayout(SmartArtLayoutType.BasicProcess);

            // Saving Presentation
            presentation.save(dataDir + "ChangeSmartArtLayout_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:ChangeSmartArtLayout
    }
}


```
