---
title: Set External Workbook With Update Chart Data in Java Slides
linktitle: Set External Workbook With Update Chart Data in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 20
url: /java/java-slides-data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
            IChartData chartData = chart.getChartData();
            chartData.setExternalWorkbook("http://path/doesnt/exists", false);
            pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
