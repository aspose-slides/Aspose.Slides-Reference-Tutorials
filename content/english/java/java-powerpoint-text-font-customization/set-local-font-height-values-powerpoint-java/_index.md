---
title: Set Local Font Height Values in PowerPoint using Java
linktitle: Set Local Font Height Values in PowerPoint using Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 17
url: /java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class SetLocalFontHeightValues
{
    public static void main(String[] args)
    {


        //ExStart:SetLocalFontHeightValues
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation pres = new Presentation();
        try
        {
            IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
            newShape.addTextFrame("");
            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().clear();

            IPortion portion0 = new Portion("Sample text with first portion");
            IPortion portion1 = new Portion(" and second portion.");

            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);

            System.out.println("Effective font height just after creation:");
            System.out.println("Portion #0: " + portion0.getPortionFormat().getEffective().getFontHeight());
            System.out.println("Portion #1: " + portion1.getPortionFormat().getEffective().getFontHeight());

            pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);

            System.out.println("Effective font height after setting entire presentation default font height:");
            System.out.println("Portion #0: " + portion0.getPortionFormat().getEffective().getFontHeight());
            System.out.println("Portion #1: " + portion1.getPortionFormat().getEffective().getFontHeight());

            newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);

            System.out.println("Effective font height after setting paragraph default font height:");
            System.out.println("Portion #0: " + portion0.getPortionFormat().getEffective().getFontHeight());
            System.out.println("Portion #1: " + portion1.getPortionFormat().getEffective().getFontHeight());

            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);

            System.out.println("Effective font height after setting portion #0 font height:");
            System.out.println("Portion #0: " + portion0.getPortionFormat().getEffective().getFontHeight());
            System.out.println("Portion #1: " + portion1.getPortionFormat().getEffective().getFontHeight());

            newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);

            System.out.println("Effective font height after setting portion #1 font height:");
            System.out.println("Portion #0: " + portion0.getPortionFormat().getEffective().getFontHeight());
            System.out.println("Portion #1: " + portion1.getPortionFormat().getEffective().getFontHeight());

            pres.save(dataDir + "SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }

        //ExEnd:SetLocalFontHeightValues

    }
}


```
