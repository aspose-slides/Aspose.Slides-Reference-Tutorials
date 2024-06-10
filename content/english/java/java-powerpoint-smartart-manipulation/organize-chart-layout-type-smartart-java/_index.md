---
title: Organize Chart Layout Type in SmartArt using Java
linktitle: Organize Chart Layout Type in SmartArt using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class OrganizeChartLayoutType
{
    public static void main(String[] args)
    {
        //ExStart:OrganizeChartLayoutType
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation presentation = new Presentation();
        try
        {
            // Add SmartArt BasicProcess 
            ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);

            // Get or Set the organization chart type 
            smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);

            // Saving Presentation
            presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:OrganizeChartLayoutType
    }
}


```
