---
date: '2026-01-14'
description: Lär dig hur du lägger till ett grupperat stapeldiagram och placerar diagrammet
  på en bild i .NET‑presentationer med Aspose.Slides för Java. Följ den här steg‑för‑steg‑guiden
  med kompletta kodexempel.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: Lägg till klustrat stapeldiagram i .NET-presentationer med Aspose.Slides Java
url: /sv/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa diagram i .NET-presentationer med Aspose.Slides för Java
## Introduktion
Att skapa engagerande presentationer innebär ofta att integrera visuella datavisualiseringar som diagram för att förbättra publikens förståelse och engagemang. Om du är en utvecklare som vill lägga till dynamiska, anpassningsbara diagram i dina .NET-presentationer med Aspose.Slides för Java, är den här handledningen skräddarsydd för dig. Vi kommer att gå igenom hur du kan initiera presentationer, lägga till olika diagramtyper, hantera diagramdata och formatera seriedata på ett effektivt sätt.

**Vad du kommer att lära dig:**
- Hur du installerar och använder Aspose.Slides för Java i din .NET-miljö.
- Initiera en ny presentation med Aspose.Slides.
- Lägga till och anpassa diagram i bilder.
- Hantera diagramdata‑arbetsböcker.
- Formatera seriedata, särskilt hantering av negativa värden.

Vi går sedan vidare till förutsättningsavsnittet för att säkerställa att du är redo att följa med utan problem.

## Snabba svar
- **Vad är huvudmålet?** Lägg till ett grupperat stapeldiagram i en .NET-bild.
- **Vilket bibliotek krävs?** Aspose.Slides för Java (v25.4+).
- **Kan jag använda det i ett .NET‑projekt?** Ja – Java‑biblioteket fungerar via Java‑till‑.NET‑bron.
- **Behöver jag en licens?** En gratis provversion fungerar för utveckling; en kommersiell licens krävs för produktion.
- **Hur lång tid tar implementeringen?** Cirka 10‑15 minuter för ett grundläggande diagram.

## Vad är ett grupperat stapeldiagram?
Ett grupperat stapeldiagram visar flera dataserier sida‑vid‑sida för varje kategori, vilket gör det enkelt att jämföra värden mellan grupper. Denna visualisering är perfekt för affärsdashboards, resultatrapporter och alla scenarier där du behöver kontrastera flera nyckeltal.

## Varför lägga till diagram i bild med Aspose.Slides för Java?
Genom att använda Aspose.Slides kan du generera, modifiera och spara presentationer utan att Microsoft PowerPoint är installerat. Det ger full kontroll över diagramtyper, data och stil, vilket innebär att du kan automatisera rapportgenerering direkt från dina .NET‑applikationer.

## Förutsättningar
Innan du dyker ner i att skapa diagram med Aspose.Slides för Java, låt oss gå igenom vad du behöver:

### Nödvändiga bibliotek och versioner
- **Aspose.Slides för Java**: Version 25.4 eller senare.

### Miljöuppsättningskrav
- En utvecklingsmiljö som stödjer .NET‑applikationer.
- Grundläggande förståelse för Java‑programmeringskoncept.

### Kunskapsförutsättningar
- Erfarenhet av att skapa presentationer i en .NET‑applikationskontext.
- Förståelse för Java‑beroenden och deras hantering (Maven/Gradle).

## Installera Aspose.Slides för Java
För att börja använda Aspose.Slides måste du lägga till det som en beroende i ditt projekt. Så här gör du:

### Maven
Lägg till följande beroende i din `pom.xml`‑fil:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Inkludera detta i din `build.gradle`‑fil:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkt nedladdning
Alternativt kan du ladda ner den senaste versionen från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Steg för att skaffa licens
- **Gratis provversion**: Börja med en tillfällig licens för att utforska funktionerna.
- **Köp**: Överväg att köpa en licens för omfattande användning.

#### Grundläggande initiering och konfiguration
Så här initierar du Aspose.Slides i din kod:
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
Denna konfiguration säkerställer att resurshanteringen sköts effektivt.

## Implementeringsguide
Vi går igenom implementeringen steg‑för‑steg.

### Initiera presentation
**Översikt:**  
Att skapa en presentationsinstans lägger grunden för alla efterföljande operationer. Denna funktion visar hur du startar från början med Aspose.Slides.

#### Steg 1: Importera nödvändiga paket
```java
import com.aspose.slides.Presentation;
```

#### Steg 2: Skapa ett nytt Presentation‑objekt
Så här gör du:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Detta säkerställer att presentationsobjektet korrekt frigörs efter användning, vilket förhindrar minnesläckor.*

### Lägga till diagram i bild
**Översikt:**  
Att lägga till ett diagram i din bild kan göra datavisualisering mer effektiv och engagerande.

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
*Här lägger vi till ett grupperat stapeldiagram på den första bilden på angivna koordinater och dimensioner.*

### Hantera diagramdata‑arbetsbok
**Översikt:**  
Effektiv hantering av ditt diagrams dataarbetsbok gör att du kan manipulera serier och kategorier sömlöst.

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
*Att rensa arbetsboken är avgörande för att börja med en ren grund när du lägger till nya serier och kategorier.*

### Lägga till serier och kategorier i diagram
**Översikt:**  
Denna funktion visar hur du kan lägga till meningsfulla datapunkter genom att hantera serier och kategorier.

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

### Fyll seriedata och formatera
**Översikt:**  
Fyll ditt diagram med datapunkter och formatera utseendet för att förbättra läsbarheten, särskilt när du hanterar negativa värden.

#### Steg 1: Fyll seriedata
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
*Detta avsnitt demonstrerar hur du fyller data och applicerar färgformat för bättre visualisering.*

## Vanliga problem och lösningar
- **Minnesläckor:** Anropa alltid `dispose()` på `Presentation`‑objektet i ett `finally`‑block.
- **Fel diagramtyp:** Säkerställ att du använder `ChartType.ClusteredColumn` när du vill ha ett grupperat stapeldiagram; andra typer ger olika visuella resultat.
- **Färger för negativa värden tillämpas inte:** Verifiera att `IDataPoint`‑värdet korrekt kastas till `Number` innan jämförelse.

## Vanliga frågor

**Q: Kan jag använda Aspose.Slides för Java i ett rent .NET‑projekt utan Java?**  
A: Ja. Biblioteket fungerar via Java‑till‑.NET‑bron, vilket låter dig anropa Java‑API:er från .NET‑språk.

**Q: Stöder gratisprovversionen skapande av diagram?**  
A: Proversionen inkluderar full diagramfunktionalitet, men genererade filer innehåller ett litet utvärderingsvattenstämpel.

**Q: Vilka .NET‑versioner är kompatibla?**  
A: Alla .NET‑versioner som kan interoperera med Java 16+, inklusive .NET Framework 4.6+, .NET Core 3.1+ samt .NET 5/6/7.

**Q: Hur hanterar jag stora presentationer med många diagram?**  
A: Återanvänd samma `IChartDataWorkbook`‑instans där det är möjligt och frigör varje `Presentation` omedelbart för att frigöra minne.

**Q: Är det möjligt att exportera diagrammet som en bild?**  
A: Ja. Använd `chart.getImage()` eller `chart.exportChartImage()`‑metoderna för att få PNG/JPEG‑representationer.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Senast uppdaterad:** 2026-01-14  
**Testat med:** Aspose.Slides för Java 25.4  
**Författare:** Aspose  

---