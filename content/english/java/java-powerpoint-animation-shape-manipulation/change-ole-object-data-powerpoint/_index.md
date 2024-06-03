---
title: Change OLE Object Data in PowerPoint
linktitle: Change OLE Object Data in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

## Complete Source Code
```java
package com.aspose.slides.examples.shapes;

import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;


public class ChangeOLEObjectData
{
    public static void main(String[] args) throws Exception
    {
        //ExStart:ChangeOLEObjectData
        // The path to the documents directory.
        String dataDir = RunExamples.getDataDir_Shapes();

        Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);

            OleObjectFrame ole = null;

            // Traversing all shapes for Ole frame
            for (IShape shape : slide.getShapes())
            {
                if (shape instanceof OleObjectFrame)
                {
                    ole = (OleObjectFrame) shape;
                }
            }

            if (ole != null)
            {
                ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
                try
                {
                    // Reading object data in Workbook
                    Workbook Wb = new Workbook(msln);

                    ByteArrayOutputStream msout = new ByteArrayOutputStream();
                    try
                    {
                        // Modifying the workbook data
                        Wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
                        Wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
                        Wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
                        Wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);

                        OoxmlSaveOptions so1 =
                                new OoxmlSaveOptions(com.aspose.cells.SaveFormat.XLSX);

                        Wb.save(msout, so1);

                        // Changing Ole frame object data
                        IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(),
                                ole.getEmbeddedData().getEmbeddedFileExtension());
                        ole.setEmbeddedData(newData);
                    }
                    finally
                    {
                        if (msout != null) msout.close();
                    }
                }
                finally
                {
                    if (msln != null) msln.close();
                }
            }

            pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }

        //ExEnd:ChangeOLEObjectData
    }
}

```
