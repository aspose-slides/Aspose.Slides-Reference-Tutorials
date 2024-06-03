---
title: Get Light Rig Effective Data in PowerPoint
linktitle: Get Light Rig Effective Data in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 25
url: /java/java-powerpoint-shape-formatting-geometry/get-light-rig-effective-data-powerpoint/
---

## Complete Source Code
```java
package com.aspose.slides.examples.shapes;

import com.aspose.slides.IThreeDFormatEffectiveData;
import com.aspose.slides.Presentation;
import com.aspose.slides.examples.RunExamples;


public class GetLightRigEffectiveData
{
    public static void main(String[] args)
    {

        //ExStart:GetLightRigEffectiveData

        // The path to the documents directory.
        String dataDir = RunExamples.getDataDir_Shapes();

        Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
        try
        {
            IThreeDFormatEffectiveData threeDEffectiveData = pres.getSlides().get_Item(0).getShapes().get_Item(0).getThreeDFormat().getEffective();

            System.out.println("= Effective light rig properties =");
            System.out.println("Type: " + threeDEffectiveData.getLightRig().getLightType());
            System.out.println("Direction: " + threeDEffectiveData.getLightRig().getDirection());


        }
        finally
        {
            if (pres != null) pres.dispose();
        }

        //ExEnd:GetLightRigEffectiveData
    }
}


```
