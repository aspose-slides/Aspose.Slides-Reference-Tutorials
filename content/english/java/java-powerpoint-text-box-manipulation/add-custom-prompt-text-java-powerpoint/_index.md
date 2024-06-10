---
title: Add Custom Prompt Text in Java PowerPoint
linktitle: Add Custom Prompt Text in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-text-box-manipulation/add-custom-prompt-text-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class AddCustomPromptText
{
    public static void main(String[] args)
    {

        //ExStart:AddCustomPromptText
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        Presentation pres = new Presentation(dataDir + "Presentation2.pptx");
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            for (IShape shape : slide.getSlide().getShapes()) // iterate through the slide
            {
                if (shape.getPlaceholder() != null && shape instanceof AutoShape)
                {
                    String text = "";
                    if (shape.getPlaceholder().getType() == PlaceholderType.CenteredTitle) // title - the text is empty, PowerPoint displays "Click to add title".
                    {
                        text = "Click to add custom title";
                    } else if (shape.getPlaceholder().getType() == PlaceholderType.Subtitle) // the same for subtitle.
                    {
                        text = "Click to add custom subtitle";
                    }

                    ((IAutoShape) shape).getTextFrame().setText(text);

                    System.out.println(String.format("Placeholder with text: {0}", text));
                }
            }

            pres.save(dataDir + "Placeholders_PromptText.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }


        //ExEnd:AddCustomPromptText

    }
}


```
