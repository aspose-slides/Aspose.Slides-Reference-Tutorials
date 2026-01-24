---
date: '2026-01-24'
description: Steg‑för‑steg‑guide för att skapa spridningsdiagram i Java med Aspose.Slides,
  lägga till datapunkter i spridningsdiagram och arbeta med flera serier i spridningsdiagram.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Skapa spridningsdiagram i Java med Aspose.Slides – Anpassa och spara
url: /sv/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa spridningsdiagram i Java med Aspose.Slides

I den här handledningen kommer du att **create scatter chart java** projekt från början, lägga till datapunkter spridning, och lära dig hur kataloginställning, presentationinitialisering, diagramskapande, datahantering, marköran Anpassatera flera serier i ett spridningsdiagram  
- Spara den färdiga presentationen  

Låt oss komma igång med förutsättningarna.

## Snabba svar
- **Vad är det primära biblioteket?** Aspose.Slides for Java  
- **Vilken Java-version krävs?** serier?** Ja – du kan lägga till valfritt antal serier i ett spridningsdiagram  
- **Hur ändrar jag markörfärger?** Använd `series.getMarker().getFillFormat().setFillColor(Color)`  
- **Behövs en licens för produktion?** Ja, en kommersiell licens tar bort utvärderingsbegränsningar  

## Förutsättningar

För att följa den här handledningen, se till att du har:
- **Aspose.Slides for Java** – version 25.4 eller senare.  
- **Java Development Kit (JDK)** – JDK 8 eller nyare.  
- Grundläggande kunskaper i Java och erfarenhet av Maven eller Gradle.  

## Så installerar du Aspose.Slides för Java

Integrera Aspose.Slides i ditt projekt med någon av följande metoder.

### Maven
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Eller ladda ner det senaste paketet från [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Licensanskaffning
- **Free Trial** – 30‑dagars utvärdering.  
- **Temporary License** – Utökad testning.  
- **Commercial License** – Fullt produktionsbruk.

Nu låt oss dyka ner i koden.

## Implementeringsguide

### Steg 1: Kataloginställning
Först, se till att output‑mappen finns så att presentationen kan sparas utan fel.

```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```

### Steg 2: Presentationinitialisering
Skapa en ny presentation och hämta den första bilden.

```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Steg 3: Lägg till ett spridningsdiagram
Infoga ett spridningsdiagram med mjuka linjer på bilden.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```

### Steg 4: Hantera diagramdata (Rensa & Lägg till serier)
Rensa eventuella standardserier och lägg till våra egna serier för **multiple series scatter chart**.

```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Adding new series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```

### Steg 5: Lägg till datapunkter spridning
Fyll varje serie med X‑Y‑värden med hjälp av **add data points scatter**.

```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```

### Steg 6: Anpassa serietyper & markörer
Justera den visuella stilen — byt till raka linjer med markörer och ange distinkta markörsymboler.

```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Modifying second series
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```

### Steg 7: Spara presentationen
Spara filen på disk.

```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Praktiska tillämpningar
- **Financial Analysis** – Plotta aktiekursrörelser med flera serier i ett spridningsdiagram.  
- **Scientific Research** – Visualisera experimentella mätningar med **add data points scatter** för exakt datavisualisering.  
- **Project Management** – Visa trender för resursallokering över flera projekt i ett enda spridningsdiagram.  

## Prestandaöverväganden
- Avsluta `Presentation`‑objektet efter sparning för att frigöra minne.  
- För stora dataset, fyll arbetsboken i batcher istället för en‑och‑en.  
- Undvik överdriven styling i täta loopar; applicera stilar efter datainmatning.  

## Vanliga problem & lösningar

| Problem | Lösning |
|-------|----------|
| **Diagrammet visas tomt** | Verifiera att datapunkter har lagts till i rätt serie och att arbetsbokens index matchar. |
| **Markörer syns inte** | Se till att `series.getMarker().setSize()` är satt till ett värde större än 0 och att markörsymbolen är definierad. |
| **OutOfMemoryError vid stora diagram** | Använd `pres.dispose()` efter sparning och överväg att öka JVM:s heap‑storlek (`-Xmx`). |

## Vanliga frågor

### Hur ändrar jag färgen på markörerna?
Använd `series.getMarker().getFillFormat().setFillColor(Color)` där `Color` är en instans av `java.awt.Color`.

### Kan jag lägga till mer än två serier i ett spridningsdiagram?
Absolut. Upprepa blocket för seriekonstruktion (Steg 4) för varje ytterligare serie du behöver.

### Är det möjligt att exportera diagrammet som en bild?
Ja. Anropa `chart.exportChartImage("chart.png", ImageFormat.Png)` efter att all data har lagts till.

### Stöder Aspose.Slides interaktiva verktygstips på spridningspunkter?
Även om PowerPoint i sig inte erbjuder verktygstips vid körning, kan du bädda in datalabels med `series.getDataPoints().get_Item(i).getLabel().setText("Your text")`.

### Hur kan jag animera spridningsserierna?
Använd `chart.getChartData().getSeries().get_Item(i).getFormat().getEffectFormat().setPresetEffect(PresetEffectType.Appear)` för att lägga till en enkel framträde‑animation.

---

**Senast uppdaterad:** 2026-01-24  
**Testat med:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}