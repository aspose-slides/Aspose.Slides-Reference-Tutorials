---
title: Hide Information from Chart in Java Slides
linktitle: Hide Information from Chart in Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: 
type: docs
weight: 13
url: /java/java-slides-customization-and-formatting/hide-information-chart-java-slides/
---

## Complete Source Code
```java
        // The path to the documents directory.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation();
        try
        {
            ISlide slide = pres.getSlides().get_Item(0);
            IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
            //Hiding chart Title
            chart.setTitle(false);
            ///Hiding Values axis
            chart.getAxes().getVerticalAxis().setVisible(false);
            //Category Axis visibility
            chart.getAxes().getHorizontalAxis().setVisible(false);
            //Hiding Legend
            chart.setLegend(false);
            //Hiding MajorGridLines
            chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
            for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
            {
                chart.getChartData().getSeries().removeAt(i);
            }
            IChartSeries series = chart.getChartData().getSeries().get_Item(0);
            series.getMarker().setSymbol(MarkerStyleType.Circle);
            series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
            series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
            series.getMarker().setSize(15);
            //Setting series line color
            series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
            series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
            series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
            pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
