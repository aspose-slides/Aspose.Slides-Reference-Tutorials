---
title: Clone Slide to End within Same Presentation
linktitle: Clone Slide to End within Same Presentation
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 16
url: /java/java-powerpoint-slide-cloning-techniques/clone-slide-end-within-same-presentation-powerpoint/
---

## Complete Source Code
```java
package com.aspose.slides.examples.slides.crud;

import com.aspose.slides.ISlideCollection;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.examples.RunExamples;


public class CloneWithinSamePresentationToEnd
{
    public static void main(String[] args)
    {
        //ExStart:CloneWithinSamePresentationToEnd
        // The path to the documents directory.
        String dataDir = RunExamples.getDataDir_Slides_Presentations_CRUD();

        // Instantiate Presentation class that represents a presentation file
        Presentation pres = new Presentation(dataDir + "CloneWithinSamePresentationToEnd.pptx");
        try
        {

            // Clone the desired slide to the end of the collection of slides in the same presentation
            ISlideCollection slds = pres.getSlides();

            slds.addClone(pres.getSlides().get_Item(0));

            // Write the modified presentation to disk
            pres.save(dataDir + "Aspose_CloneWithinSamePresentationToEnd_out.pptx", SaveFormat.Pptx);

        }
        finally
        {
            if (pres != null) pres.dispose();
        }
        //ExEnd:CloneWithinSamePresentationToEnd
    }
}

```
