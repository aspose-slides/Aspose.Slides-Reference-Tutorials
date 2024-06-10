---
title: Lock Aspect Ratio in PowerPoint using Java
linktitle: Lock Aspect Ratio in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 16
url: /java/java-powerpoint-table-manipulation/lock-aspect-ratio-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.ITable;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;



public class LockAspectRatio
{
    public static void main(String[] args)
    {
        //ExStart:LockAspectRatio
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation pres = new Presentation(dataDir + "pres.pptx");
        try
        {
            ITable table = (ITable) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            System.out.println("Lock aspect ratio set: " + table.getGraphicalObjectLock().getAspectRatioLocked());

            table.getGraphicalObjectLock().setAspectRatioLocked(!table.getGraphicalObjectLock().getAspectRatioLocked()); // invert

            System.out.println("Lock aspect ratio set: " + table.getGraphicalObjectLock().getAspectRatioLocked());

            pres.save(dataDir + "pres-out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:LockAspectRatio

    }
}


```
