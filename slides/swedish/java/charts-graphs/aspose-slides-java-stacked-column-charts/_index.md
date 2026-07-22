---
date: '2026-07-22'
description: Lär dig Aspose Slides Maven Dependency för att skapa ett staplat stapeldiagram
  i Java, lägga till data labels, ändra vertical axis number format och exportera
  resultatet som en PPTX‑fil.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency låter dig bygga ett staplat stapeldiagram
  i Java, anpassa data labels, justera vertical axis format och spara som PPTX – allt
  med koncis, produktionsklar kod.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Staplat stapeldiagram i Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Staplat stapeldiagram i Java'
url: /sv/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven‑beroende: Staplad stapeldiagram i Java

## Introduktion

Lyft dina presentationer genom att integrera insiktsfulla datavisualiseringar med kraften i **Aspose.Slides for Java**. I den här guiden kommer du att **skapa ett staplat stapeldiagram** som ser professionellt ut, oavsett om du förbereder affärsrapporter eller visar projektstatistik. I slutet av denna handledning kommer du att kunna:

- Ställ in din miljö med **Aspose Slides Maven‑beroendet**
- Skapa en presentation från början
- **Lägg till ett procent‑staplat diagram** och anpassa dess utseende
- **Formatera diagrammets datamärkningar** och **ändra det vertikala axelns talformat**
- **Spara presentationen som en PPTX** med en enda kodrad

## Snabba svar
- **Vilket bibliotek behöver jag?** Lägg till `aspose-slides` Maven/Gradle‑beroendet (se “Aspose Slides Maven‑beroende” nedan).  
- **Vilken diagramtyp skapar en staplad vy?** Använd `ChartType.PercentsStackedColumn` för ett procent‑staplat stapeldiagram.  
- **Hur kan jag ändra axelns talformat?** Anropa `IAxis.setNumberFormat()` och sätt `setNumberFormatLinkedToSource(false)`.  
- **Kan jag anpassa datamärkningar?** Ja – iterera genom varje `IChartDataPoint` och tilldela en anpassad `ITextFrame`.  
- **Hur sparar jag filen?** Anropa `presentation.save("output.pptx", SaveFormat.Pptx)`.

## Vad är ett staplat stapeldiagram?
Ett staplat stapeldiagram visualiserar flera dataserier staplade vertikalt i varje kategorikolumn, där **procent‑staplad** variant normaliserar varje kolumn till 100 % för enkel jämförelse av proportioner. Detta format låter tittare snabbt bedöma hur varje komponent bidrar till helheten över olika kategorier, vilket gör trender och relativa storlekar omedelbart tydliga.

## Varför använda Aspose.Slides för Java?
Aspose.Slides för Java låter dig skapa, redigera och konvertera PowerPoint‑filer **utan att behöva Microsoft Office** och stödjer **50+ exportformat** på Windows, Linux och macOS. Biblioteket körs helt på en JRE, vilket möjliggör server‑sidig automatisering och högkapacitetsrapportering. Det ger också fin‑granulerad kontroll över diagramobjekt, bildlayouter och dokumentegenskaper, vilket gör det idealiskt för företagsnivåpresentationer.

## Förutsättningar
- **Java Development Kit (JDK):** 8 eller högre  
- **IDE:** IntelliJ IDEA, Eclipse eller någon Java‑kompatibel editor  
- **Byggverktyg:** Maven eller Gradle (valfritt men rekommenderat)  
- **Grundläggande Java‑kunskaper** – du bör vara bekväm med klasser och metoder  

## Komma igång med Aspose.Slides för Java
För att börja, lägg till Aspose.Slides‑biblioteket i ditt projekt.

### Aspose Slides Maven‑beroende
Lägg till följande i din `pom.xml` (detta är **aspose slides maven‑beroendet** du behöver):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑alternativ
Om du föredrar Gradle, inkludera denna rad i `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkt nedladdning
Alternativt, ladda ner den senaste JAR‑filen från [Aspose.Slides för Java‑utgåvor](https://releases.aspose.com/slides/java/).

### Licensanskaffning
Du kan börja med en gratis provperiod för att utforska Aspose.Slides‑funktionerna. För att ta bort utvärderingsbegränsningar, överväg att skaffa en tillfällig eller köpt licens.

- **Gratis provperiod:** Tillgång till begränsade funktioner utan omedelbara kostnader.  
- **Tillfällig licens:** Begär via [Aspose:s webbplats](https://purchase.aspose.com/temporary-license/).  
- **Köp:** Besök köpsidan för full åtkomst.

### Grundläggande initiering
`Presentation` är Aspose.Slides kärnklass som representerar en PowerPoint‑fil i minnet. Följande minimala kodsnutt visar hur man skapar ett `Presentation`‑objekt:

```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Create an instance of Presentation class
        Presentation presentation = new Presentation();
        
        // Perform operations on the presentation object
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Implementeringsguide

### Skapa en presentation och lägga till en bild
**Översikt:**  
Först skapar vi en tom presentation och verifierar att en bild finns.

#### Steg 1: Initiera presentationsobjekt
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Create a new presentation instance
        Presentation presentation = new Presentation();
        
        // Reference to the first slide (auto-created)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Steg 2: Spara presentationen
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Lägga till procent‑staplat stapeldiagram på en bild
**Översikt:**  
Nu placerar vi ett **procent‑staplat diagram** på den första bilden.

`ChartType.PercentsStackedColumn` specificerar en procent‑staplad stapeldiagramtyp.

#### Steg 1: Initiera och få åtkomst till bilden
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Proceed to add chart in the next step
    }
}
```

#### Steg 2: Lägg till diagram på bilden
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Anpassa diagrammets axelns talformat
**Översikt:**  
För bättre läsbarhet kommer vi att **ändra det vertikala axelns format** så att det visar procent.

`IAxis` är gränssnittet som representerar en diagramaxel och möjliggör format- och skalningsjusteringar.

#### Steg 1: Lägg till och få åtkomst till diagrammet
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### Steg 2: Ställ in anpassat talformat
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Lägga till serier och datapunkter i diagrammet
**Översikt:**  
Vi kommer att fylla diagrammet med exempeldata serier.

#### Steg 1: Initiera presentation och diagram
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Steg 2: Lägg till dataserier
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Formatera seriernas fyllningsfärg
**Översikt:**  
Ge varje serie en distinkt färg för att göra diagrammet lättare att läsa.

#### Steg 1: Initiera och få åtkomst till diagrammet
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### Steg 2: Ställ in fyllningsfärger
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Formatera datamärkningar
**Översikt:**  
Nu kommer vi att **formatera diagrammets datamärkningar** så att de visar anpassad text.

`IChartDataPoint` representerar en enskild datapunkt inom en diagramserie, och `ITextFrame` innehåller märkningstexten.

#### Steg 1: Få åtkomst till diagramserier och datapunkter
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### Steg 2: Anpassa datamärkningar
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Vanliga problem och lösningar
- **Diagrammet visas tomt:** Se till att du har lagt till minst en dataserie och datapunkt innan du sparar.  
- **Axelns tal visas inte som procent:** Kom ihåg att sätta `verticalAxis.setNumberFormatLinkedToSource(false)`; annars ignoreras det anpassade formatet.  
- **Licensutvärderingsmeddelande:** Använd en giltig licensfil innan du skapar `Presentation`‑objektet för att undertrycka utvärderingsbanner.

## Vanliga frågor

**Q: Kan jag använda den här koden med Java 11 eller nyare?**  
A: Ja. Biblioteket stödjer JDK 8+; använd bara rätt klassificerare (t.ex. `jdk16` för JDK 16 eller senare).

**Q: Hur exporterar jag diagrammet som en bild istället för en PPTX?**  
A: Använd `chart.getImage().save("chart.png", ImageFormat.Png);` efter att ha lagt till diagrammet på bilden.

**Q: Är det möjligt att lägga till en legend i det staplade stapeldiagrammet?**  
A: Absolut. Anropa `chart.getChartTitle().addTextFrameForOverriding("My Chart");` och konfigurera `chart.getLegend()` efter behov.

**Q: Vad händer om jag behöver uppdatera data efter att presentationen har genererats?**  
A: Du kan modifiera cellerna i `ChartDataWorkbook` och sedan anropa `chart.refresh();` för att reflektera förändringarna.

**Q: Fungerar Aspose.Slides på Linux‑servrar?**  
A: Ja. Biblioteket är ren Java och körs på alla OS med en kompatibel JRE.

## Slutsats
Genom att följa den här guiden har du lärt dig hur man **skapar ett staplat stapeldiagram** i Java med **Aspose Slides Maven‑beroendet**, från miljöinställning till finjusterad visuell stil. Experimentera med olika dataset, färger och märkningformat för att få dina rapporter att verkligen sticka ut.

---

**Senast uppdaterad:** 2026-07-22  
**Testat med:** Aspose.Slides 25.4 (jdk16 classifier)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Hur man skapar grupperat stapeldiagram i Java med Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Hur man ställer in talformat i diagramdatapunkter med Aspose.Slides för Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Hur man lägger till och konfigurerar diagram i presentationer med Aspose.Slides för Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}