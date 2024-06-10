---
title: Change SmartArt State in PowerPoint with Java
linktitle: Change SmartArt State in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 21
url: /java/java-powerpoint-smartart-manipulation/change-smartart-state-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.ISmartArt;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.SmartArtLayoutType;



public class ChangeSmartArtState
{
    public static void main(String[] args)
    {
        //ExStart:ChangeSmartArtState
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation presentation = new Presentation();
        try
        {
            // Add SmartArt BasicProcess 
            ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.BasicProcess);

            // Get or Set the state of SmartArt Diagram
            smart.setReversed(true);
            boolean flag = smart.isReversed();

            // Saving Presentation
            presentation.save(dataDir + "ChangeSmartArtState_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:ChangeSmartArtState

    }
}


```
