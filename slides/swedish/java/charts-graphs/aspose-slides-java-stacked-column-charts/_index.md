---
date: '2026-01-24'
description: Lär dig hur du skapar diagram med Aspose.Slides för Java, inklusive inställning
  av procentuell staplad kolumn, axelformatering och anpassning av datamärkning.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: 'Hur man skapar diagram: Staplad kolumn med Aspose.Slides Java'
url: /sv/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Mästra staplade stapeldiagram i Java med Aspose.Slides: En omfattande guide

## Introduktion

Höj dina presentationer genom att integrera insiktsfulla datavisualiseringar med kraften i Aspose.Slides för Java. I den här handledningen lär du dig **hur du skapar diagram‑drivna bilder** som förvandlar råa siffror till tydliga berättelser – oavsett om du förbereder affärsrapporter, projekt‑dashboards eller marknadsföringspresentationer.  

Vi går igenom hur du ställer in din miljö, lägger till ett **procentuellt staplat stapeldiagram**, och anpassar axlar, serier och datamärkningar så att den färdiga presentationen ser polerad och professionell ut.

Låt oss dyka ner i att skapa presentationer som fängslar din publik.

## Snabba svar
- **Vad är huvudbiblioteket?** Aspose.Slides för Java
- **Vilken Maven‑artefakt lägger till biblioteket?** `com.aspose:aspose-slides` (se avsnittet *aspose slides maven*)
- **Hur lägger man till ett procentuellt staplat stapeldiagram?** Använd `ChartType.PercentsStackedColumn` när du anropar `addChart`
- **Kan jag formatera diagramaxelns siffror?** Ja – sätt `verticalAxis.setNumberFormat("0.00%")`
- **Hur anpassar jag texten i datamärkningarna?** Åsidosätt varje punkts `ITextFrame` via `point.getLabel().getTextFrameForOverriding()`

## Vad är ett staplat stapeldiagram?
Ett staplat stapeldiagram grupperar flera dataserier i en enda stapel, vilket låter dig jämföra den totala storleken samtidigt som du ser varje komponents bidrag. Varianten **procentuellt staplat stapeldiagram** normaliserar varje stapel till 100 %, vilket gör den idealisk för att visa proportionella data över kategorier.

## Varför använda Aspose.Slides för Java?
- **Ingen Office‑installation krävs** – generera PPTX‑filer på vilken server som helst.
- **Fullt utrustat diagram‑API** – stödjer alla diagramtyper, inklusive procentuellt staplat stapeldiagram.
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS.
- **Enkel Maven/Gradle‑integration** – se kodsnutten *aspose slides maven* nedan.

## Förutsättningar
- **Java Development Kit (JDK):** 8 eller högre.
- **IDE:** IntelliJ IDEA, Eclipse eller någon annan Java‑kompatibel editor.
- **Byggverktyg (valfritt):** Maven eller Gradle för beroendehantering.
- **Grundläggande Java‑kunskaper** – du bör vara bekväm med klasser, metoder och samlingar.

## Installera Aspose.Slides för Java
För att komma igång måste du inkludera Aspose.Slides‑biblioteket i ditt projekt.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkt nedladdning:**  
Alternativt kan du ladda ner den senaste JAR‑filen från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licensanskaffning
Du kan börja med en gratis provversion för att utforska Aspose.Slides‑funktionerna. För att ta bort utvärderingsbegränsningar, överväg att skaffa en temporär eller köpt licens.

- **Gratis prov:** Tillgång till begränsade funktioner utan omedelbara kostnader.  
- **Temporär licens:** Begär via [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Köp:** Besök köpsidan för full åtkomst.

### Grundläggande initiering
Så här initierar du Aspose.Slides i din Java‑applikation:
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

## Så skapar du ett diagram: Steg‑för‑steg‑guide

### Skapa en presentation och lägg till en bild
**Översikt:** Börja med att skapa en enkel presentation med en initial bild. Detta blir din grund för vidare förbättringar.

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
```java
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Lägg till procentuellt staplat stapeldiagram på en bild
**Översikt:** Förbättra din bild genom att lägga till ett **procentuellt staplat stapeldiagram**, vilket underlättar datakomparering.

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

### Anpassa diagramaxelns talformat
**Översikt:** Anpassa talformatet för diagrammets vertikala axel för bättre läsbarhet.

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

#### Steg 2: Ställ in eget talformat
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Lägg till serier och datapunkter i diagrammet
**Översikt:** Fyll ditt diagram med **lägg till seriedata** så att det blir informativt och visuellt tilltalande.

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
**Översikt:** Förbättra diagrammets estetik genom att formatera fyllningsfärgen för varje serie.

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
**Översikt:** Gör datamärkningarna mer läsbara genom att **formatera diagramdatamärkningar** för att visa anpassad text.

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

#### Steg 2: Anpassa datamärkningarna
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

## Vanliga användningsområden
- **Kvartalsvisa försäljnings‑dashboards** – visualisera produktlinjers bidrag som procent av total omsättning.  
- **Projektresursallokering** – visa hur teammedlemmar fördelas över uppgifter i en enda stapel.  
- **Undersökningsresultat** – jämför svarsfördelningar över flera frågor.

## Vanliga frågor

**Q: Behöver jag en betald licens för att generera staplade stapeldiagram?**  
A: En gratis provversion låter dig skapa diagram, men en permanent licens tar bort vattenmärken och låser upp full funktionalitet.

**Q: Kan jag ändra diagramtypen efter att den skapats?**  
A: Ja, du kan ersätta diagrammet genom att ta bort den befintliga formen och lägga till en ny med en annan `ChartType`.

**Q: Hur exporterar jag presentationen till PDF?**  
A: Använd `presentation.save("output.pdf", SaveFormat.Pdf);` efter att du har slutfört redigeringen av bilderna.

**Q: Är API‑et kompatibelt med Java 11 och nyare?**  
A: Absolut. Biblioteket fungerar med JDK 8 upp till JDK 21; välj bara rätt classifier (t.ex. `jdk16`).

**Q: Vad händer om jag behöver lägga till fler än tre serier?**  
A: Upprepa helt enkelt blocket för att lägga till serier och justera kalkylbladsreferenserna för varje ny serie.

## Slutsats
Genom att följa den här guiden vet du nu **hur du skapar diagram**‑visualiseringar med Aspose.Slides för Java, från att sätta upp Maven/Gradle‑beroendet till att anpassa ett procentuellt staplat stapeldiagrams axlar, seriefärger och datamärkningar. Experimentera med olika datamängder, applicera dina egna varumärkesfärger och integrera dessa bilder i automatiserade rapporterings‑pipelines.

---

**Senast uppdaterad:** 2026-01-24  
**Testat med:** Aspose.Slides 25.4 (jdk16 classifier)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}