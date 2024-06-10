---
title: Highlight Text in PowerPoint with Java
linktitle: Highlight Text in PowerPoint with Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-powerpoint-text-highlighting-fallback-rules/highlight-text-powerpoint-java/
---

## Complete Source Code
```java


import com.aspose.slides.*;


import java.awt.*;


public class HighlightText
{
    public static void main(String[] args)
    {

        //ExStart:HighlightText
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation presentation = new Presentation(dataDir + "SomePresentation.pptx");
        ((AutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0)).getTextFrame().highlightText("title", new Color(PresetColor.LightBlue));
        TextHighlightingOptions tmp0 = new TextHighlightingOptions();
        tmp0.setWholeWordsOnly(true); // highlighting all words 'important'
        ((AutoShape) presentation.getSlides().get_Item(0).getShapes().get_Item(0)).getTextFrame().highlightText("to", new Color(PresetColor.Violet), tmp0); // highlighting all separate 'the' occurrences
        presentation.save(dataDir + "SomePresentation-out2.pptx", SaveFormat.Pptx);

        //ExEnd:HighlightText
    }
}


```
