---
title: Effect Text Box Paragraph in Java PowerPoint
linktitle: Effect Text Box Paragraph in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 16
url: /java/java-powerpoint-text-box-manipulation/effect-text-box-paragraph-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class EffectTextBoxParagraph
{
    public static void main(String[] args)
    {
        //ExStart:EffectTextBoxParagraph
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "Test.pptx");
        try
        {
            ISequence sequence = pres.getSlides().get_Item(0).getTimeline().getMainSequence();
            IAutoShape autoShape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().get_Item(1);

            for (IParagraph paragraph : autoShape.getTextFrame().getParagraphs())
            {
                IEffect[] effects = sequence.getEffectsByParagraph(paragraph);

                if (effects.length > 0)
                    System.out.println("Paragraph \"" + paragraph.getText() + "\" has " + effects[0].getType() + " effect.");
            }
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:EffectTextBoxParagraph
    }
}


```
