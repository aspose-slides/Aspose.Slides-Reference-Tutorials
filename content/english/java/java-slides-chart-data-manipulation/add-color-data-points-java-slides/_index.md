---
title: Add Color to Data Points in Java Slides
linktitle: Add Color to Data Points in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 10
url: /java/java-slides-chart-data-manipulation/add-color-data-points-java-slides/
---

## Complete Source Code
```java
        Presentation pres = new Presentation();
        try
        {
            // The path to the documents directory.
            String dataDir = "Your Document Directory";
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
            IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
            dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
            IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
            branch1Label.getDataLabelFormat().setShowCategoryName(false);
            branch1Label.getDataLabelFormat().setShowSeriesName(true);
            branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
            branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
            IFormat steam4Format = dataPoints.get_Item(9).getFormat();
            steam4Format.getFill().setFillType(FillType.Solid);
            steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//TODO
            pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
