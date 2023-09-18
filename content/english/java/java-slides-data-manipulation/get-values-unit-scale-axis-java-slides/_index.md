---
title: Get Values and Unit Scale from Axis in Java Slides
linktitle: Get Values and Unit Scale from Axis in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 20
url: /java/java-slides-data-manipulation/get-values-unit-scale-axis-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 100, 100, 500, 350);
            chart.validateChartLayout();
            double maxValue = chart.getAxes().getVerticalAxis().getActualMaxValue();
            double minValue = chart.getAxes().getVerticalAxis().getActualMinValue();
            double majorUnit = chart.getAxes().getHorizontalAxis().getActualMajorUnit();
            double minorUnit = chart.getAxes().getHorizontalAxis().getActualMinorUnit();
            // Saving presentation
            pres.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
