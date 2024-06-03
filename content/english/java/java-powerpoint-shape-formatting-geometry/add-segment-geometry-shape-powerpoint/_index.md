---
title: Add Segment to Geometry Shape in PowerPoint
linktitle: Add Segment to Geometry Shape in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 19
url: /java/java-powerpoint-shape-formatting-geometry/add-segment-geometry-shape-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;

public class GeometryShapeAddSegment {

    public static void main(String[] args) throws Exception
    {
        //ExStart:GeometryShapeAddSegment

        // Output file name
        String resultPath = RunExamples.getOutPath() + "GeometryShapeAddSegment.pptx";

        Presentation pres = new Presentation();
        try
        {
            // Create new shape
            GeometryShape shape = (GeometryShape)pres.getSlides().get_Item(0).
                    getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 200, 100);
            // Get geometry path of the shape
            IGeometryPath geometryPath = shape.getGeometryPaths()[0];

            // Add two lines to geometry path
            geometryPath.lineTo(100, 50, 1);
            geometryPath.lineTo(100, 50, 4);

            // Assign edited geometry path to the shape
            shape.setGeometryPath(geometryPath);

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
