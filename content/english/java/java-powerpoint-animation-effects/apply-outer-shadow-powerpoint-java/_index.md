---
title: Apply Outer Shadow in PowerPoint with Java
linktitle: Apply Outer Shadow in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class ApplyOuterShadow
{
    public static void main(String[] args)
    {
        //ExStart:ApplyOuterShadow
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        try
        {
            // Get reference of a slide
            ISlide slide = presentation.getSlides().get_Item(0);

            // Add an AutoShape of Rectangle type
            IAutoShape ashp = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
            ashp.getFillFormat().setFillType(FillType.NoFill);

            // Add TextFrame to the Rectangle
            ashp.addTextFrame("Aspose TextBox");
            IPortion port = ashp.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
            IPortionFormat pf = port.getPortionFormat();
            pf.setFontHeight(50);

            // Enable InnerShadowEffect
            IEffectFormat ef = pf.getEffectFormat();
            ef.enableInnerShadowEffect();

            // Set all necessary parameters
            ef.getInnerShadowEffect().setBlurRadius(8.0);
            ef.getInnerShadowEffect().setDirection(90.0F);
            ef.getInnerShadowEffect().setDistance(6.0);
            ef.getInnerShadowEffect().getShadowColor().setB((byte) 189);

            // Set ColorType as Scheme
            ef.getInnerShadowEffect().getShadowColor().setColorType(ColorType.Scheme);

            // Set Scheme Color
            ef.getInnerShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);

            // Save Presentation
            presentation.save(dataDir + "WordArt_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:ApplyOuterShadow
    }
}

```
