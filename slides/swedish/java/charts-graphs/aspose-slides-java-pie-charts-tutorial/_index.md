---
date: '2026-02-19'
description: Lär dig hur du skapar ett cirkeldiagram i Java med Aspose.Slides och
  anpassar cirkeldiagrammets färger, lägger till diagramserier, arbetar med diagrammets
  datablad och ställer in rotationsvinkeln.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Hur du anpassar färger på cirkeldiagram i Java med Aspose.Slides – En komplett
  guide
url: /sv/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa pajdiagram med Aspose.Slides för Java: En komplett handledning

## Introduktion
Att skapa dynamiska och visuellt tilltalande presentationer är avgörande för att leverera kraftfull information. Med Aspose.Slides för Java kan du sömlöst integrera komplexa diagram som pajdiagram i dina bilder, **anpassa pajdiagramfärger**, och förbättra datavisualisering utan ansträngning. Denna omfattande guide går igenom processen för att skapa och anpassa ett pajdiagram med Aspose.Slides Java, och löser vanliga presentationsutmaningar med lätthet.

**Vad du kommer att lära dig:**
- Initiera en presentation och lägga till bilder.
- Skapa och konfigurera ett pajdiagram på din bild.
- Ställa in diagramrubriker, datalabels och **anpassa pajdiagramfärger**.
- Optimera prestanda och hantera resurser effektivt.
- Integrera Aspose.Slides i Java‑projekt med Maven eller Gradle.

Låt oss börja med att säkerställa att du har alla nödvändiga verktyg och kunskaper för att följa med!

## Snabba svar
- **Vilken är den primära klassen för att starta en presentation?** `Presentation` från `com.aspose.slides`.
- **Vilken metod lägger till ett pajdiagram på en bild?** `addChart(ChartType.Pie, …)`.
- **Hur aktiverar du varierade färger för varje segment?** Anropa `setColorVaried(true)` på series‑gruppen.
- **Kan du rotera pajdiagrammet?** Ja, använd `setRotationAngle(double)` på diagramobjektet.
- **Behöver jag en licens för produktionsanvändning?** En Aspose.Slides‑licens krävs för kommersiella distributioner.

## Vad betyder “customize pie chart colors”?
Att anpassa pajdiagramfärger innebär att tilldela olika fyllningsfärger till varje segment i pajen, vilket förbättrar läsbarhet och visuell påverkan. I Aspose.Slides uppnår du detta genom att aktivera varierade färger och sedan sätta solida fyllningsfärger för enskilda datapunkter.

## Varför använda Aspose.Slides för Java för att skapa pajdiagram?
- **Full kontroll** över diagrammets utseende utan att behöva Microsoft Office.
- **Plattformsoberoende** – fungerar på Windows, Linux och macOS.
- **Rik API** för databindning, styling och export till PPTX, PDF eller bilder.
- **Licensflexibilitet** – börja med en gratis provversion och uppgradera när du behöver hela funktionsuppsättningen.

## Förutsättningar
Innan du dyker ner i den här handledningen, se till att du har följande uppsättning klar:

### Nödvändiga bibliotek, versioner och beroenden
- **Aspose.Slides för Java**: version 25.4 eller senare.
- **Java Development Kit (JDK)**: version 16 eller högre.

### Miljöinställningar
- En utvecklingsmiljö med Java installerat och konfigurerat.
- En integrerad utvecklingsmiljö (IDE) som IntelliJ IDEA, Eclipse eller NetBeans.

### Kunskapsförutsättningar
- Grundläggande förståelse för Java‑programmering.
- Bekantskap med Maven eller Gradle för beroendehantering.

## Installera Aspose.Slides för Java
För att börja använda Aspose.Slides i dina Java‑projekt måste du lägga till biblioteket som ett beroende. Så här gör du med olika byggverktyg:

**Maven**  
Lägg till detta snippet i din `pom.xml`‑fil:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Inkludera följande i din `build.gradle`‑fil:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkt nedladdning**  
Om du föredrar att inte använda ett byggverktyg, ladda ner den senaste releasen från [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Steg för att skaffa licens
- **Gratis provversion**: Börja med en gratis provversion för att utforska Aspose.Slides‑funktionerna.  
- **Tillfällig licens**: Skaffa en tillfällig licens för förlängd användning utan begränsningar.  
- **Köp**: Överväg att köpa om du behöver långsiktig åtkomst.

**Grundläggande initiering och konfiguration**  
För att börja använda Aspose.Slides, initiera ditt projekt genom att skapa ett nytt presentation‑objekt:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementeringsguide
Nu bryter vi ner processen för att lägga till och anpassa ett pajdiagram i hanterbara steg.

### Initiera presentation och bild
Börja med att skapa en ny presentation och komma åt den första bilden. Detta är din duk för att skapa diagram:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Lägg till pajdiagram på bilden
Infoga ett pajdiagram på den angivna positionen med ett standarddatamängd:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Ställ in diagramrubrik
Anpassa ditt diagram genom att sätta och centrera rubriken:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Konfigurera datalabels för serie
Säkerställ att datalabels visar värden för tydlighet:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Förbered diagrammets dataarbetsblad
Ställ in diagrammets dataarbetsblad genom att rensa befintliga serier och kategorier:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Lägg till kategorier i diagrammet
Definiera kategorier för ditt pajdiagram:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Lägg till serie och fyll i datapunkter
Skapa en serie och fyll den med datapunkter – här **lägger vi till diagramserie**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Anpassa seriefärger och kanter
Förbättra det visuella genom att sätta färger och anpassa kanter – detta **anpassar pajdiagramfärger**:
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Konfigurera anpassade datalabels
Finjustera etiketterna för varje datapunkt:
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Ställ in rotationsvinkel och spara presentation
Slutför ditt pajdiagram genom att **ställa in rotationsvinkel** och spara filen:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Vanliga problem och lösningar
| Problem | Orsak | Lösning |
|-------|-------|-----|
| **Segmenten har alla samma färg** | `setColorVaried(true)` har inte anropats | Se till att du aktiverar varierade färger på series‑gruppen. |
| **Datalabels visas inte** | `showValue`‑flaggan är inaktiverad | Anropa `setShowValue(true)` på rätt label‑format. |
| **Rotation har ingen effekt** | Äldre version av Aspose.Slides används | Uppgradera till version 25.4 eller senare. |
| **Licensundantag vid körning** | Licensfil saknas eller är ogiltig | Ladda din licens med `License license = new License(); license.setLicense("Aspose.Slides.lic");` innan du skapar `Presentation`. |

## Vanliga frågor

**Q: Hur får jag en Aspose.Slides‑licens för Java?**  
A: Du kan begära en gratis provversion från Aspose‑webbplatsen och sedan köpa en permanent licens. Ladda den vid körning som visat i tabellen ovan.

**Q: Kan jag använda den här koden med äldre JDK‑versioner?**  
A: API‑et kräver JDK 16 eller högre; äldre versioner stöds inte.

**Q: Är det möjligt att exportera diagrammet som en bild istället för PPTX?**  
A: Ja, anropa `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` efter rendering.

**Q: Vad händer om jag behöver lägga till fler än en serie i ett pajdiagram?**  
A: Pajdiagram visar vanligtvis en enda serie; för flera serier överväg ett doughnut‑diagram istället.

**Q: Fungerar biblioteket på Linux‑servrar?**  
A: Absolut – Aspose.Slides för Java är plattformsoberoende och körs på alla OS med en kompatibel JDK.

---

**Senast uppdaterad:** 2026-02-19  
**Testat med:** Aspose.Slides för Java 25.4 (jdk16)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}