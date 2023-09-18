---
title: Chart Recover Workbook in Java Slides
linktitle: Chart Recover Workbook in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 17
url: /java/java-slides-data-manipulation/chart-recover-workbook-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        String pptxFile = dataDir + "ExternalWB.pptx";
        String outPptxFile = RunExamples.OutPath + "ExternalWB_out.pptx";
        LoadOptions lo = new LoadOptions();
        lo.getSpreadsheetOptions().setRecoverWorkbookFromChartCache(true);
        Presentation pres = new Presentation(pptxFile, lo);
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            pres.save(outPptxFile, SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
