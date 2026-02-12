---
date: '2026-02-12'
description: Lär dig hur du skapar diagram och hanterar diagram med Aspose.Slides
  för Java. Denna handledning visar hur du skapar ett grupperat stapeldiagram, hanterar
  dataserier och anpassar visualiseringen.
keywords:
- Aspose.Slides for Java
- Java charts
- clustered column chart
title: 'Hur man skapar diagram i Java med Aspose.Slides: En omfattande guide'
url: /sv/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man skapar diagram i Java med Aspose.Slides

## Så här skapar du diagram i Java: Introduktion
Att skapa dynamiska presentationer innebär ofta att visualisera data med diagram. Med **Aspose.Slides for Java** kan du enkelt **how to create chart** objekt, förbättra tydligheten och göra ett starkare intryck på din publik. Denna handledning guidar dig genom att installera biblioteket, lägga till ett **create clustered column chart**, hantera serier och villkorsstyrt invertera negativa datapunkter.

**Vad du kommer att lära dig**
- Hur du installerar Aspose.Slides for Java.
- Steg för att **create clustered column chart** i din presentation.
- Tekniker för att hantera diagramserier och datapunkter.
- Metoder för att villkorsstyrt invertera negativa datapunkter för bättre visualisering.
- Hur du sparar presentationen på ett säkert sätt.

### Quick Answers
- **What library is used?** Aspose.Slides for Java.
- **Which chart type is demonstrated?** Clustered column chart.
- **Can I invert negative values?** Yes, using `invertIfNegative`.
- **What Java version is required?** JDK 16 or later.
- **Is a license needed for production?** Yes, a valid Aspose license.

## Vad är ett grupperat stapeldiagram?
Ett grupperat stapeldiagram visar flera dataserier sida‑vid‑sida för varje kategori, vilket gör det enkelt att jämföra värden mellan grupper. Det är idealiskt för finansiella rapporter, försäljningsdashboards och alla situationer där du behöver kontrastera flera nyckeltal.

## Varför använda Aspose.Slides för diagramskapande?
- **Full control** över diagrammets utseende utan att förlita dig på PowerPoints UI.
- **Programmatic generation** möjliggör automatiserade rapporteringspipeline.
- **Cross‑platform** stöd säkerställer att din kod körs på alla Java‑kompatibla system.
- **Rich API** för fin‑granulär anpassning (färger, datalabels, inversion, osv.).

## Förutsättningar
1. **Nödvändiga bibliotek**
   - Aspose.Slides for Java (version 25.4 eller senare).

2. **Miljö**
   - JDK 16 eller nyare.
   - Maven eller Gradle för beroendehantering.

3. **Kunskap**
   - Grundläggande Java‑programmering.
   - Bekantskap med byggverktyg (Maven/Gradle).

## Installera Aspose.Slides för Java
### Maven Installation
Lägg till följande beroende i din `pom.xml`-fil:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle Installation
Lägg till följande rad i din `build.gradle`-fil:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct Download
Alternativt, ladda ner den senaste versionen från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### License Acquisition
- **Free Trial:** Utforska funktioner utan licens.
- **Temporary License:** Använd under utvärdering.
- **Full License:** Köp för produktionsdistributioner.

### Grundläggande initialisering
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Step‑by‑Step Guide

### Step 1: Create a Presentation and Add a Clustered Column Chart
I detta steg **how to create chart** objekt och placerar ett **create clustered column chart** på den första bilden.

```java
import com.aspose.slides.*;

String YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
Presentation pres = new Presentation();
try {
    // Add a clustered column chart at (50, 50) with width 600 and height 400.
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Step 2: Manage Chart Series
Nu rensar vi eventuella standardserier, lägger till en ny och fyller den med både positiva och negativa värden.

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    // Clear existing series and add a new one.
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
} finally {
    if (pres != null) pres.dispose();
}
```

### Step 3: Invert Negative Data Points Conditionally
Som standard inverterar inte Aspose.Slides negativa värden. Vi aktiverar inversion endast för de punkter som behöver det.

```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.ClusteredColumn,
        50, 50, 600, 400, true
    );
    
    IChartSeriesCollection series = chart.getChartData().getSeries();
    series.clear();
    series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
    
    // Add data points with varying values (positive and negative).
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2)
    );
    series.get_Item(0).getDataPoints().addDataPointForBarSeries(
        chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1)
    );
    
    // Set default inversion behavior
    series.get_Item(0).invertIfNegative(false);
    
    // Conditionally invert a specific data point
    IChartDataPoint dataPoint = series.get_Item(0).getDataPoints().get_Item(0);
    if (dataPoint.getValue() < 0) {
        dataPoint.invertIfNegative(true);
    }
} finally {
    if (pres != null) pres.dispose();
}
```

### Common Pitfalls & Tips
- **Forgot to dispose the `Presentation` object?** Always call `dispose()` in a `finally` block to free native resources.
- **Negative values not showing as inverted?** Ensure you call `invertIfNegative(true)` **after** adding the data point.
- **Chart size issues:** The coordinates (X, Y) and dimensions (width, height) are in points; adjust them to fit your slide layout.

## Frequently Asked Questions

**Q: Can I create other chart types with the same approach?**  
A: Yes, simply replace `ChartType.ClusteredColumn` with any other `ChartType` enum value (e.g., `Line`, `Pie`).

**Q: Do I need a license for development builds?**  
A: A temporary or evaluation license is required for full feature access; otherwise, the library works in trial mode with watermark limitations.

**Q: How do I export the presentation to PDF after adding charts?**  
A: Use `pres.save("output.pdf", SaveFormat.Pdf);` after you finish chart manipulation.

**Q: Is it possible to style individual columns (color, border)?**  
A: Yes, each `IChartDataPoint` provides formatting options such as `getFillFormat().setFillType(FillType.Solid)` and `getLineFormat()`.

**Q: What if I need to update the chart data after the presentation is saved?**  
A: Load the presentation again with `new Presentation("file.pptx")`, modify the chart data, and re‑save.

---

**Last Updated:** 2026-02-12  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}