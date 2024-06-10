---
title: Add Animation Effect in Paragraph with Aspose.Slides for Java
linktitle: Add Animation Effect in Paragraph with Aspose.Slides for Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-powerpoint-animation-effects/add-animation-effect-paragraph/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class AnimationEffectinParagraph
{
    public static void main(String[] args)
    {
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        //ExStart:AnimationEffectinParagraph
        Presentation presentation = new Presentation(dataDir + "Presentation1.pptx");
        try
        {
            // select paragraph to add effect
            IAutoShape autoShape = (IAutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0);
            IParagraph paragraph = autoShape.getTextFrame().getParagraphs().get_Item(0);

            // add Fly animation effect to selected paragraph
            IEffect effect = presentation.getSlides().get_Item(0).getTimeline().getMainSequence().addEffect(paragraph, EffectType.Fly, EffectSubtype.Left, EffectTriggerType.OnClick);


            presentation.save(dataDir + "AnimationEffectinParagraph.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }


        //ExEnd:AnimationEffectinParagraph
    }
}


```
