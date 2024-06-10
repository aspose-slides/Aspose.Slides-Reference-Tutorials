---
title: Add Custom Child Nodes in SmartArt using Java
linktitle: Add Custom Child Nodes in SmartArt using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-powerpoint-smartart-manipulation/add-custom-child-nodes-smartart-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class CustomChildNodesInSmartArt
{
    public static void main(String[] args)
    {
        //ExStart:CustomChildNodesInSmartArt
        String dataDir = "Your Document Directory";

        // Load the desired the presentation
        Presentation pres = new Presentation(dataDir + "AccessChildNodes.pptx");
        try
        {
            ISmartArt smart = pres.getSlides().get_Item(0).getShapes().addSmartArt(20, 20, 600, 500, SmartArtLayoutType.OrganizationChart);

            // Move SmartArt shape to new position
            ISmartArtNode node = smart.getAllNodes().get_Item(1);
            ISmartArtShape shape = node.getShapes().get_Item(1);
            shape.setX(shape.getX() + (shape.getWidth() * 2));
            shape.setY(shape.getY() - (shape.getHeight() / 2));

            // Change SmartArt shape's widths
            node = smart.getAllNodes().get_Item(2);
            shape = node.getShapes().get_Item(1);
            shape.setWidth(shape.getWidth() + (shape.getWidth() / 2));

            // Change SmartArt shape's height
            node = smart.getAllNodes().get_Item(3);
            shape = node.getShapes().get_Item(1);
            shape.setHeight(shape.getHeight() + (shape.getHeight() / 2));

            // Change SmartArt shape's rotation
            node = smart.getAllNodes().get_Item(4);
            shape = node.getShapes().get_Item(1);
            shape.setRotation(90);

            pres.save(dataDir + "SmartArt.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:CustomChildNodesInSmartArt
    }
}

```
