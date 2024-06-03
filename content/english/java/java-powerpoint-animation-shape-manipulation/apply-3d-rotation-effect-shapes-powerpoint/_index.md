---
title: Apply 3D Rotation Effect on Shapes in PowerPoint
linktitle: Apply 3D Rotation Effect on Shapes in PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 12
url: /java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;


public class Apply3DRotationEffectOnShape
{
    public static void main(String[] args)
    {
        //ExStart:Apply3DRotationEffecrOnShapes
        // The path to the documents directory.                    
        String dataDir = "Your Document Directory";

        // Create an instance of Presentation class
        Presentation pres = new Presentation();
        IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);

        autoShape.getThreeDFormat().setDepth((short) 6);
        autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
        autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
        autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);

        autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
        autoShape.getThreeDFormat().setDepth((short) 6);
        autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
        autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
        autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);


        pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
        //ExEnd:Apply3DRotationEffecrOnShapes
    }
}


```
