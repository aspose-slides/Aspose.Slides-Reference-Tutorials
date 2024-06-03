---
title: Clone Slide into Specified Section in PowerPoint
linktitle: Clone Slide into Specified Section in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-powerpoint-slide-cloning-techniques/clone-slide-specified-section-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;


public class CloneSlideIntoSpecifiedSection
{
    public static void main(String[] args)
    {

        //ExStart:CloneSlideIntoSpecifiedSection

        String dataDir = RunExamples.getDataDir_Slides_Presentations_CRUD();

        IPresentation presentation = new Presentation();
        try
        {

            presentation.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 200, 50, 300, 100);
            presentation.getSections().addSection("Section 1", presentation.getSlides().get_Item(0));

            ISection section2 = presentation.getSections().appendEmptySection("Section 2");

            presentation.getSlides().addClone(presentation.getSlides().get_Item(0), section2);


            presentation.save(dataDir + "CloneSlideIntoSpecifiedSection.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (presentation != null) presentation.dispose();
        }
        //ExEnd:CloneSlideIntoSpecifiedSection

    }


}


```
