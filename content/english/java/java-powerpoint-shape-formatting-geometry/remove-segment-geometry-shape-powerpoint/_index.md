---
title: Remove Segment from Geometry Shape in PowerPoint
linktitle: Remove Segment from Geometry Shape in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 22
url: /java/java-powerpoint-shape-formatting-geometry/remove-segment-geometry-shape-powerpoint/
---

## Complete Source Code
```java
package com.aspose.slides.examples.shapes;

import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;

public class GeometryShapeRemoveSegment {

    public static void main(String[] args) throws Exception {
        //ExStart:GeometryShapeAddSegment

        // Output file name
        String resultPath = RunExamples.getOutPath() +  "GeometryShapeRemoveSegment.pptx";

        Presentation pres = new Presentation();
        try
        {
            // Create new shape
            GeometryShape shape = (GeometryShape)pres.getSlides().get_Item(0).
                    getShapes().addAutoShape(ShapeType.Heart, 100, 100, 300, 300);

            // Get geometry path of the shape
            IGeometryPath path = shape.getGeometryPaths()[0];

            // remove segment
            path.removeAt(2);

            // set new geometry path
            shape.setGeometryPath(path);

            // Save the presentation
            pres.save(resultPath, SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }

        //ExEnd:GeometryShapeAddSegment
    }

}

```
