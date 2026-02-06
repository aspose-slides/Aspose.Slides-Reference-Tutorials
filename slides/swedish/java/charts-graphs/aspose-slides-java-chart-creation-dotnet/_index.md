---
date: '2026-02-06'
description: Lär dig hur du initierar en presentation med Aspose Slides och anpassar
  ett grupperat stapeldiagram i .NET med Aspose.Slides för Java. Följ den här steg‑för‑steg‑guiden
  för att förbättra datavisualisering.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: 'Initiera presentation med Aspose Slides: .NET-diagram'
url: /sv/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa diagram i .NET-presentationer med Aspose.Slides för Java

## Introduktion
I den här handledningen kommer du att **initialisera presentation Aspose Slides** och lära dig hur du bäddar in dynamiska, anpassningsbara diagram i dina .NET‑bilder. Visuell data—som staplade kolumndiagram—hjälper din publik att omedelbart förstå trender, och Aspose.Slides för Java ger dig full programmatisk kontroll även när du riktar dig mot en .NET‑miljö. Vi går igenom hur du installerar biblioteket, skapar en ny presentation, lägger till ett diagram, fyller i data och tillämpar formateringsknep såsom färgning av negativa värden.

**Vad du kommer att lära dig**
- Hur du installerar Aspose.Slides för Java i ett .NET‑projekt.  
- Hur du **initialiserar presentation Aspose Slides** och lägger till ett diagram.  
- Hur du **anpassar staplat kolumndiagram** serier och kategorier.  
- Hantera diagrammets dataarbetsbok och tillämpa villkorlig formatering.  

### Snabba svar
- **Vad är första steget?** Initiera ett `Presentation`‑objekt.  
- **Vilken diagramtyp används i exemplet?** `ClusteredColumn`.  
- **Kan jag formatera negativa värden annorlunda?** Ja, med villkorade fyllningsfärger.  
- **Behöver jag en licens för testning?** En gratis provlicens fungerar för utveckling.  
- **Vilken Maven‑artefakt krävs?** `com.aspose:aspose-slides:25.4` med `jdk16`‑klassificerare.

## Vad är “initialize presentation Aspose Slides”?
Att initiera en presentation skapar en PPTX‑fil i minnet som du kan manipulera innan du sparar. Aspose.Slides abstraherar filformatet, så att du kan lägga till bilder, former och diagram utan att behöva hantera lågnivå‑OPC‑strukturer.

## Varför anpassa ett staplat kolumndiagram?
Staplade kolumndiagram är idealiska för att jämföra flera dataserier över kategorier. Att anpassa färger, datapunkter och etiketter låter dig framhäva viktiga insikter—som att markera negativa värden i rött och positiva i grönt—vilket gör dina bilder mer övertygande.

## Förutsättningar
- **Aspose.Slides for Java** ≥ 25.4  
- .NET‑utvecklingsmiljö (Visual Studio, .NET 6+ rekommenderas)  
- Grundläggande Java‑kunskaper (du kommer att skriva Java‑kod som körs på JVM och anropas från .NET via JNI eller ett brygglager)  

### Nödvändiga bibliotek och versioner
- **Aspose.Slides for Java**: Version 25.4 eller senare.

### Krav för miljöinställning
- En .NET‑kompatibel Java‑runtime (t.ex. AdoptOpenJDK 16).  
- Maven eller Gradle för beroendehantering.

### Kunskapsförutsättningar
- Bekantskap med att skapa presentationer i en .NET‑kontext.  
- Förståelse för Java‑projektkonfiguration (Maven/Gradle).

## Installera Aspose.Slides för Java
Lägg till biblioteket i ditt projekt med ditt föredragna byggverktyg.

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

### Direktnedladdning
Du kan också ladda ner den senaste JAR‑filen från den officiella releasesidan: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Steg för att skaffa licens
- **Free Trial** – generera en tillfällig licensfil för utveckling.  
- **Purchase** – skaffa en full licens för produktionsdistribution.

#### Grundläggande initiering och inställning
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
`try/finally`‑blocket garanterar att inhemska resurser frigörs, vilket förhindrar minnesläckor.

## Hur man initialiserar presentation Aspose Slides
Nedan dyker vi ner i de konkreta stegen för att skapa en ny presentation och förbereda den för diagraminfogning.

### Initiering av presentation
**Översikt:**  
Att skapa ett presentations‑instans sätter scenen för alla efterföljande operationer.

#### Steg 1: Importera nödvändiga paket
```java
import com.aspose.slides.Presentation;
```

#### Steg 2: Skapa ett nytt Presentation‑objekt
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Detta säkerställer att presentations‑objektet korrekt frigörs efter användning, vilket förhindrar minnesläckor.*

## Hur man anpassar staplat kolumndiagram
Nu när presentationen är klar, låt oss lägga till och skräddarsy ett staplat kolumndiagram.

### Lägg till diagram på bild
**Översikt:**  
Att lägga till ett diagram ger data liv på bilden.

#### Steg 1: Importera nödvändiga paket
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Steg 2: Initiera presentation och lägg till diagram
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*Här lägger vi till ett staplat kolumndiagram på den första bilden med angivna koordinater och dimensioner.*

### Hantera diagrammets dataarbetsbok
**Översikt:**  
Effektiv hantering av diagrammets dataarbetsbok gör att du kan manipulera serier och kategorier sömlöst.

#### Steg 1: Importera nödvändiga paket
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Steg 2: Åtkomst och rensa dataarbetsbok
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*Att rensa arbetsboken är avgörande för att börja med en ren start när du lägger till nya serier och kategorier.*

### Lägg till serier och kategorier i diagrammet
**Översikt:**  
Detta steg visar hur du kan lägga till meningsfulla datapunkter genom att hantera serier och kategorier.

#### Steg 1: Lägg till serier och kategorier
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*Att lägga till serier och kategorier möjliggör en mer organiserad datapresentation.*

### Fyll i seriedata och formatering
**Översikt:**  
Fyll i ditt diagram med datapunkter och formatera utseendet för att förbättra läsbarheten, särskilt när du hanterar negativa värden.

#### Steg 1: Fyll i seriedata
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*Detta avsnitt visar hur du fyller i data och tillämpar färgformatering för bättre visualisering.*

## Vanliga problem och lösningar
- **Memory leaks** – Wrappa alltid `Presentation`‑objektet i ett `try/finally`‑block som visas för att garantera att det frigörs.  
- **Incorrect cell coordinates** – Kom ihåg att rader och kolumner är nollbaserade; felaktiga index orsakar `NullPointerException`.  
- **License not found** – Placera licensfilen i applikationens arbetskatalog eller ange sökvägen explicit via `License.setLicense("Aspose.Slides.Java.lic")`.

## Vanliga frågor

**Q: Kan jag använda detta tillvägagångssätt med .NET Core?**  
A: Ja. Aspose.Slides för Java kör på vilken JVM som helst, och du kan anropa Java‑koden från .NET Core med en brygga som IKVM eller JNI.

**Q: Behöver jag en betald licens för utveckling?**  
A: En gratis provlicens räcker för utveckling och testning. Produktionsdistributioner kräver en köpt licens.

**Q: Hur ändrar jag diagramtypen efter skapandet?**  
A: Du kan anropa `chart.getChartData().setChartType(ChartType.Pie)` för att byta till en annan diagramtyp.

**Q: Är det möjligt att lägga till datalabels programatiskt?**  
A: Ja. Använd `series.getDataPoints().get_Item(i).getLabel().setShowValue(true)` för att visa värden på diagrammet.

**Q: Vilka format kan jag spara presentationen i?**  
A: Aspose.Slides stöder PPTX, PPT, PDF, XPS och flera bildformat som PNG och JPEG.

---

**Last Updated:** 2026-02-06  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}