---
title: Add Columns in Text Frame using Aspose.Slides for Java
linktitle: Add Columns in Text Frame using Aspose.Slides for Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 11
url: /java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class AddColumnsinTextFrame
{
    public static void main(String[] args)
    {

        //ExStart:AddColumnsinTextFrame
        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        String outPptxFileName = dataDir + "ColumnsTest.pptx";
        Presentation pres = new Presentation();
        try
        {
            IAutoShape shape1 = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
            TextFrameFormat format = (TextFrameFormat) shape1.getTextFrame().getTextFrameFormat();

            format.setColumnCount(2);
            shape1.getTextFrame().setText("All these columns are limited to be within a single text container -- " +
                    "you can add or delete text and the new or remaining text automatically adjusts " +
                    "itself to flow within the container. You cannot have text flow from one container " +
                    "to other though -- we told you PowerPoint's column options for text are limited!");
            pres.save(outPptxFileName, SaveFormat.Pptx);

            format.setColumnSpacing(20);
            pres.save(outPptxFileName, SaveFormat.Pptx);
            format.setColumnCount(3);
            format.setColumnSpacing(15);
            pres.save(outPptxFileName, SaveFormat.Pptx);

        }
        finally
        {
            if (pres != null) pres.dispose();
        }

        //ExEnd:AddColumnsinTextFrame
    }
}


```
