---
title: Custom Rotation Angle for Text Frame in Java PowerPoint
linktitle: Custom Rotation Angle for Text Frame in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 14
url: /java/java-powerpoint-text-box-manipulation/custom-rotation-angle-text-frame-java-powerpoint/
---

## Complete Source Code
```java


import com.aspose.slides.*;



public class CustomRotationAngleTextframe
{
    public static void main(String[] args)
    {
        //ExStart:CustomRotationAngleTextframe

        // The path to the documents directory.
        String dataDir = "Your Document Directory";

        // Create an instance of Presentation class
        Presentation presentation = new Presentation();

        IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 300);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);

        series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
        series.getLabels().getDefaultDataLabelFormat().getTextFormat().getTextBlockFormat().setRotationAngle(65);

        chart.setTitle(true);
        chart.getChartTitle().addTextFrameForOverriding("Custom title").getTextFrameFormat().setRotationAngle(-30);

        // Save Presentation
        presentation.save(dataDir + "textframe-rotation_out.pptx", SaveFormat.Pptx);
        //ExEnd:CustomRotationAngleTextframe
    }
}

```
