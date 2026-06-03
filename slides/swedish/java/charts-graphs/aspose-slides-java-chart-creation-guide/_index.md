---
date: '2026-06-03'
description: Lär dig hur du skapar ett klustrat stapeldiagram i Java med Aspose.Slides.
  Denna guide täcker Maven‑beroende, stegen för att skapa diagrammet och databehandling.
keywords:
- create clustered column chart
- how to create chart
- maven dependency aspose slides
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  headline: Create Clustered Column Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to create clustered column chart in Java using Aspose.Slides.
    This guide covers Maven dependency, chart creation steps, and data handling.
  name: Create Clustered Column Chart in Java with Aspose.Slides
  steps:
  - name: Create a Presentation and Add a Clustered Column Chart
    text: '`Presentation` class represents a PowerPoint document and allows creating
      slides.'
  - name: Manage Chart Series
    text: Now we’ll clear any default series, add a new one, and populate it with
      both positive and negative values.
  - name: Invert Negative Data Points Conditionally
    text: '`invertIfNegative` method enables inversion of negative values in a chart
      series.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library is used?
  - answer: Clustered column chart.
    question: Which chart type is demonstrated?
  - answer: Yes, using `invertIfNegative`.
    question: Can I invert negative values?
  - answer: JDK 16 or later.
    question: What Java version is required?
  - answer: Yes, a valid Aspose license.
    question: Is a license needed for production?
  type: FAQPage
title: Skapa klustrat stapeldiagram i Java med Aspose.Slides
url: /sv/java/charts-graphs/aspose-slides-java-chart-creation-guide/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa grupperat stapeldiagram i Java med Aspose.Slides

## Hur man skapar diagram i Java: Introduktion
Att skapa dynamiska presentationer innebär ofta att visualisera data med diagram. Med **Aspose.Slides for Java** kan du enkelt **skapa grupperade stapeldiagram** objekt, förbättra tydligheten och göra ett starkare intryck på din publik. Denna handledning guidar dig genom att konfigurera biblioteket, lägga till ett grupperat stapeldiagram, hantera serier och villkorsstyrt invertera negativa datapunkter.

**Vad du kommer att lära dig**
- Hur du installerar Aspose.Slides for Java.
- Steg för att **skapa grupperat stapeldiagram** i din presentation.
- Tekniker för att hantera diagramserier och datapunkter.
- Metoder för att villkorsstyrt invertera negativa datapunkter för bättre visualisering.
- Hur du sparar presentationen på ett säkert sätt.

## Snabba svar
- **Vilket bibliotek används?** Aspose.Slides for Java.  
- **Vilken diagramtyp demonstreras?** Grupperat stapeldiagram.  
- **Kan jag invertera negativa värden?** Ja, med `invertIfNegative`.  
- **Vilken Java-version krävs?** JDK 16 eller senare.  
- **Behövs en licens för produktion?** Ja, en giltig Aspose-licens.

## Vad är ett grupperat stapeldiagram?
Ett grupperat stapeldiagram är en visuell representation som placerar flera dataserier sida‑vid‑sida för varje kategori, vilket möjliggör snabb jämförelse mellan grupper. Det är perfekt för finansiella rapporter, försäljningsdashboards och alla situationer där du behöver jämföra flera mätvärden samtidigt.

## Varför använda Aspose.Slides för diagramskapande?
Aspose.Slides låter dig generera och fullt anpassa diagram programatiskt, vilket eliminerar behovet av manuell PowerPoint‑redigering. Det stödjer **70+ in- och utdataformat** och kan bearbeta presentationer med **upp till 10 000 bilder** utan att ladda hela filen i minnet, vilket säkerställer hög prestanda för storskalig rapportering.

## Förutsättningar
1. **Nödvändiga bibliotek**  
   - Aspose.Slides for Java (version 25.4 eller senare).  

2. **Miljö**  
   - JDK 16 eller nyare.  
   - Maven eller Gradle för beroendehantering.  

3. **Kunskap**  
   - Grundläggande Java-programmering.  
   - Bekantskap med byggverktyg (Maven/Gradle).  

## Konfigurera Aspose.Slides för Java
### Maven‑installation
Lägg till följande beroende i din `pom.xml`‑fil:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑installation
Lägg till följande rad i din `build.gradle`‑fil:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkt nedladdning
Alternativt, ladda ner den senaste versionen från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licensanskaffning
- **Free Trial:** Utforska funktioner utan licens.  
- **Temporary License:** Använd under utvärdering.  
- **Full License:** Köp för produktionsdistribution.

### Grundläggande initiering
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
// Your code here...
pres.dispose(); // Always dispose of the presentation object when done.
```

## Hur lägger jag till ett grupperat stapeldiagram på en bild?
`Presentation` är huvudklassen som representerar en PowerPoint‑fil. Ladda en ny `Presentation`, lägg till en bild och anropa `slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 400)`. Detta enkla anrop skapar ett fullt funktionellt grupperat stapeldiagram placerat på de angivna koordinaterna. Du kan sedan komma åt diagramobjektet för att ändra serier, datapunkter och visuella stilar.

## Steg‑för‑steg‑guide

### Steg 1: Skapa en presentation och lägg till ett grupperat stapeldiagram
`Presentation`‑klassen representerar ett PowerPoint‑dokument och möjliggör att skapa bilder.  
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

### Steg 2: Hantera diagramserier
Nu kommer vi att rensa eventuella standardserier, lägga till en ny och fylla den med både positiva och negativa värden.  
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

### Steg 3: Invertera negativa datapunkter villkorsstyrt
`invertIfNegative`‑metoden möjliggör inversion av negativa värden i en diagramserie.  
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

## Vanliga fallgropar & tips
- **Glömt att avyttra `Presentation`‑objektet?** Anropa alltid `dispose()` i ett `finally`‑block för att frigöra inhemska resurser.  
- **Negativa värden visas inte som inverterade?** Se till att du anropar `invertIfNegative(true)` **efter** att datapunkten har lagts till.  
- **Problem med diagramstorlek:** Koordinaterna (X, Y) och dimensionerna (bredd, höjd) är i punkter; justera dem för att passa din bildlayout.  

## Vanliga frågor

**Q:** Kan jag skapa andra diagramtyper med samma tillvägagångssätt?  
A: Ja, ersätt helt enkelt `ChartType.ClusteredColumn` med något annat `ChartType`‑enum‑värde (t.ex. `Line`, `Pie`).  

**Q:** Behöver jag en licens för utvecklingsbyggen?  
A: En tillfällig eller utvärderingslicens krävs för full åtkomst till funktioner; annars fungerar biblioteket i provläge med vattenstämpelbegränsningar.  

**Q:** Hur exporterar jag presentationen till PDF efter att ha lagt till diagram?  
`SaveFormat.Pdf` anger PDF som utdataformat för att spara en presentation. Använd `pres.save("output.pdf", SaveFormat.Pdf);` när du är klar med diagrammanipuleringen.  

**Q:** Är det möjligt att formatera enskilda kolumner (färg, kantlinje)?  
`IChartDataPoint` representerar en enskild datapunkt i ett diagram och möjliggör formatering. Varje `IChartDataPoint` erbjuder alternativ som `getFillFormat().setFillType(FillType.Solid)` och `getLineFormat()`.  

**Q:** Vad händer om jag behöver uppdatera diagramdata efter att presentationen har sparats?  
A: Ladda presentationen igen med `new Presentation("file.pptx")`, ändra diagramdata och spara igen.  

---

**Senast uppdaterad:** 2026-06-03  
**Testat med:** Aspose.Slides for Java 25.4 (JDK 16)  
**Författare:** Aspose

## Relaterade handledningar

- [Hur man skapar staplat stapeldiagram i Java med Aspose.Slides – En omfattande guide](/slides/java/charts-graphs/aspose-slides-java-stacked-column-charts/)
- [Hur man skapar diagram i Java med Aspose.Slides – Mästarens guide till diagramskapande och validering](/slides/java/charts-graphs/aspose-slides-chart-creation-validation-java/)
- [Skapa & formatera diagram i Java med Aspose.Slides: En omfattande guide](/slides/java/charts-graphs/create-format-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}