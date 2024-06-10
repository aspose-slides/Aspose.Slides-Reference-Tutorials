---
title: Effective Text Frame Format Data in Java PowerPoint
linktitle: Effective Text Frame Format Data in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 15
url: /java/java-powerpoint-font-management/effective-text-frame-format-data-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.IAutoShape;
import com.aspose.slides.ITextFrameFormat;
import com.aspose.slides.ITextFrameFormatEffectiveData;
import com.aspose.slides.Presentation;



public class GetTextFrameFormatEffectiveData
{
    public static void main(String[] args)
    {

        //ExStart:GetTextFrameFormatEffectiveData

        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "Presentation1.pptx");
        try
        {
            IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().get_Item(0);

            ITextFrameFormat textFrameFormat = shape.getTextFrame().getTextFrameFormat();
            ITextFrameFormatEffectiveData effectiveTextFrameFormat = textFrameFormat.getEffective();


            System.out.println("Anchoring type: " + effectiveTextFrameFormat.getAnchoringType());
            System.out.println("Autofit type: " + effectiveTextFrameFormat.getAutofitType());
            System.out.println("Text vertical type: " + effectiveTextFrameFormat.getTextVerticalType());
            System.out.println("Margins");
            System.out.println("   Left: " + effectiveTextFrameFormat.getMarginLeft());
            System.out.println("   Top: " + effectiveTextFrameFormat.getMarginTop());
            System.out.println("   Right: " + effectiveTextFrameFormat.getMarginRight());
            System.out.println("   Bottom: " + effectiveTextFrameFormat.getMarginBottom());

        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:GetTextFrameFormatEffectiveData

    }
}


```
