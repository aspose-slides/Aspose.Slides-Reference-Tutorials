---
title: Get Effective Font Values in Java PowerPoint
linktitle: Get Effective Font Values in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-font-management/get-effective-font-values-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class GetEffectiveValues
{
    public static void main(String[] args)
    {

        //ExStart:GetEffectiveValues
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
        try
        {
            IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().get_Item(0);

            ITextFrameFormat localTextFrameFormat = shape.getTextFrame().getTextFrameFormat();
            ITextFrameFormatEffectiveData effectiveTextFrameFormat = localTextFrameFormat.getEffective();

            IPortionFormat localPortionFormat = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat();
            IPortionFormatEffectiveData effectivePortionFormat = localPortionFormat.getEffective();
        }
        finally
        {
            if (pres != null) pres.dispose();
        }

        //ExEnd:GetEffectiveValues


    }
}


```
