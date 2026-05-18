---
date: '2026-02-22'
description: Lär dig hur du skapar ett staplat kolumndiagram i Java med Aspose.Slides.
  Denna handledning täcker Aspose Slides Maven‑beroendet, att lägga till ett procentuellt
  staplat diagram, formatera diagrammets dataetiketter och spara presentationen som
  PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Hur man skapar staplat kolumndiagram i Java med Aspose.Slides – En omfattande
  guide
url: /sv/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

 spaces.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man skapar staplat stapeldiagram i Java med Aspose.Slides – En omfattande guide

## Introduktion

Förbättra dina presentationer genom att integrera insiktsfulla datavisualiseringar med kraften i Aspose.Slides för Java. I den här guiden kommer du att **skapa staplade stapeldiagram**-bilder som ser professionella ut, oavsett om du förbereder affärsrapporter eller visar projektstatistik. I slutet av denna handledning kommer du att kunna:

- Ställ in din miljö med Aspose Slides Maven‑beroendet
- Skapa en presentation från grunden
- **Lägg till procentuellt staplat diagram** och anpassa dess utseende
- **Formatera diagrammets datamärkningar** och **ändra vertikalaxelns format**
- **Spara presentationen som PPTX** med en enda kodrad

Låt oss gå igenom varje steg så att du kan börja skapa övertygande presentationer omedelbart.

## Snabba svar
- **Vilket bibliotek behöver jag?** `aspose-slides` Maven/Gradle‑beroende (se “aspose slides maven dependency” nedan)  
- **Vilken diagramtyp används?** `ChartType.PercentsStackedColumn` för ett procentuellt staplat stapeldiagram  
- **Hur ändrar jag axelns talformat?** Använd `IAxis.setNumberFormat()` och inaktivera länkning till källa  
- **Kan jag anpassa datamärkningar?** Ja – iterera genom `IChartDataPoint`‑objekt och sätt en anpassad `ITextFrame`  
- **Hur sparar jag filen?** Anropa `presentation.save("output.pptx", SaveFormat.Pptx)`

## Vad är ett staplat stapeldiagram?
Ett staplat stapeldiagram visualiserar flera dataserier staplade ovanpå varandra i vertikala kolumner. När du använder den **procentuellt staplade** varianten summeras varje kolumn alltid till 100 %, vilket gör det enkelt att jämföra proportionella bidrag över kategorier.

## Varför använda Aspose.Slides för Java?
Aspose.Slides erbjuder ett rent Java‑API som fungerar på alla plattformar utan att Microsoft Office är installerat. Det ger fin‑granulerad kontroll över diagramobjekt, stöder ett brett spektrum av format och låter dig generera presentationer programmässigt – perfekt för automatiserad rapportering eller server‑sidig dokumentgenerering.

## Förutsättningar
- **Java Development Kit (JDK):** 8 eller högre  
- **IDE:** IntelliJ IDEA, Eclipse eller någon Java‑kompatibel editor  
- **Byggverktyg:** Maven eller Gradle (valfritt men rekommenderat)  
- **Grundläggande Java‑kunskaper** – du bör vara bekväm med klasser och metoder  

## Installera Aspose.Slides för Java
För att börja, lägg till Aspose.Slides‑biblioteket i ditt projekt.

### Aspose Slides Maven‑beroende
Lägg till följande i din `pom.xml` (detta är **aspose slides maven dependency** du behöver):

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
Alternativt, ladda ner den senaste JAR‑filen från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licensanskaffning
Du kan börja med en gratis provperiod för att utforska Aspose.Slides‑funktioner. För att ta bort utvärderingsbegränsningar, överväg att skaffa en tillfällig eller köpt licens.

- **Gratis provperiod:** Tillgång till begränsade funktioner utan omedelbara kostnader.  
- **Tillfällig licens:** Begär via [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Köp:** Besök köpsidan för full åtkomst.

### Grundläggande initiering
Här är ett minimalt kodexempel som visar hur man skapar ett `Presentation`‑objekt:

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
**Översikt:** Först skapar vi en tom presentation och verifierar att en bild finns.

#### Steg 1: Initiera Presentation‑objekt
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

### Lägga till procentuellt staplat stapeldiagram på en bild
**Översikt:** Nu placerar vi ett **procentuellt staplat diagram** på den första bilden.

#### Steg 1: Initiera och få åtkomst till bild
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
**Översikt:** För bättre läsbarhet kommer vi att **ändra vertikalaxelns format** för att visa procent.

#### Steg 1: Lägg till och få åtkomst till diagram
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
**Översikt:** Vi kommer att fylla diagrammet med exempeldata serier.

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

### Formatera seriers fyllningsfärg
**Översikt:** Ge varje serie en distinkt färg för att göra diagrammet lättare att läsa.

#### Steg 1: Initiera och få åtkomst till diagram
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
**Översikt:** Nu kommer vi att **formatera diagrammets datamärkningar** så att de visar anpassad text.

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
A: Ja. Biblioteket stöder JDK 8+; använd bara rätt klassificerare (t.ex. `jdk16` för JDK 16 eller senare).

**Q: Hur exporterar jag diagrammet som en bild istället för en PPTX?**  
A: Använd `chart.getImage().save("chart.png", ImageFormat.Png);` efter att ha lagt till diagrammet på bilden.

**Q: Är det möjligt att lägga till en legend i det staplade stapeldiagrammet?**  
A: Absolut. Anropa `chart.getChartTitle().addTextFrameForOverriding("My Chart");` och konfigurera `chart.getLegend()` efter behov.

**Q: Vad händer om jag behöver uppdatera data efter att presentationen har genererats?**  
A: Du kan ändra cellerna i `ChartDataWorkbook` och sedan anropa `chart.refresh();` för att reflektera förändringarna.

**Q: Fungerar Aspose.Slides på Linux‑servrar?**  
A: Ja. Biblioteket är rent Java och körs på alla OS med en kompatibel JRE.

## Slutsats
Genom att följa den här guiden har du lärt dig hur man **skapar staplade stapeldiagram**‑presentationer med Aspose.Slides för Java, från miljöinställning till finjusterad visuell stil. Experimentera med olika datamängder, färger och etikettformat för att få dina rapporter att verkligen sticka ut.

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}