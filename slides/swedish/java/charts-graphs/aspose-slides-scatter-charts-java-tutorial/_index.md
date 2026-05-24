---
date: '2026-02-24'
description: Lär dig hur du anpassar spridningsdiagram med Aspose.Slides för Java.
  Denna guide visar dig hur du skapar, formger och sparar dynamiska spridningsdiagram
  i dina presentationer.
keywords:
- Aspose.Slides for Java
- create scatter charts in Java
- customize Java charts with Aspose
title: Anpassa spridningsdiagram Aspose i Java
url: /sv/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Anpassa spridningsdiagram Aspose i Java

I den här handledningen kommer du att lära dig hur du **customize scatter chart aspose** med det kraftfulla Aspose.Slides för Java-biblioteket. Vi går igenom hur du ställer in ditt projekt, skapar ett spridningsdiagram, justerar serietyper och markörer, och slutligen sparar presentationen. I slutet kommer du att kunna generera professionellt utseende spridningsdiagram programatiskt och anpassa varje visuellt detalj för att matcha ditt varumärke eller rapporteringsbehov.

## Snabba svar
- **Vilket bibliotek behöver jag?** Aspose.Slides for Java (v25.4+).  
- **Vilken Java-version stöds?** JDK 8 eller högre.  
- **Kan jag ändra markörformer?** Ja – använd `MarkerStyleType` för att välja stjärnor, cirklar osv.  
- **Hur sparar jag filen?** Anropa `pres.save("output.pptx", SaveFormat.Pptx)`.  
- **Krävs en licens?** En gratis provperiod fungerar för utveckling; en kommersiell licens behövs för produktion.

## Vad är “customize scatter chart aspose”?
Att anpassa ett spridningsdiagram med Aspose innebär att programatiskt definiera diagrammets data, utseende och beteende—allt från punktkoordinater till markörsymboler—utan att öppna PowerPoint manuellt. Detta tillvägagångssätt är idealiskt för automatiserad rapportering, datadrivna presentationer eller någon situation där du behöver återupprepbara, högkvalitativa visualiseringar.

## Varför anpassa spridningsdiagram med Aspose.Slides?
- **Full kontroll** – modifiera serietyper, markörstilar, färger och mer via Java-kod.  
- **Automation** – generera dussintals diagram i realtid för instrumentpaneler eller batchrapporter.  
- **Cross‑platform** – fungerar på alla OS som stödjer Java, ingen Office-installation krävs.  
- **Prestanda** – lättviktig API som hanterar stora datamängder effektivt.

## Förutsättningar
För att följa med, se till att du har:

- **Aspose.Slides for Java** (v25.4 eller senare).  
- **Java Development Kit (JDK)** 8 + installerat.  
- Maven eller Gradle för beroendehantering (eller så kan du ladda ner JAR-filen manuellt).  
- Grundläggande kunskap i Java och bekantskap med ditt valda byggverktyg.

## Installera Aspose.Slides för Java
Integrera biblioteket i ditt projekt med någon av metoderna nedan.

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

Eller hämta den senaste versionen från [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Licensanskaffning
- **Free Trial** – 30‑dagars utvärdering.  
- **Temporary License** – förlängd testperiod.  
- **Full License** – produktionsanvändning med premiumsupport.

## Steg‑för‑steg guide för att anpassa spridningsdiagram Aspose

### 1️⃣ Förbered en mapp för dina presentationsfiler
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Create the directory
    new File(dataDir).mkdirs();
}
```
*Varför detta är viktigt:* Att säkerställa att utdatamappen finns förhindrar `FileNotFoundException` när du senare sparar PPTX-filen.

### 2️⃣ Skapa en ny presentation och hämta den första bilden
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
En ny `Presentation` ger dig en ren arbetsyta; den första bilden är där vi placerar diagrammet.

### 3️⃣ Lägg till ett spridningsdiagram med mjuka linjer
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
`ChartType.ScatterWithSmoothLines` skapar ett spridningsdiagram med mjuka linjer, perfekt för trendvisualisering.

### 4️⃣ Rensa eventuella standardserier och lägg till din egen
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
Att ta bort standardserien ger dig full kontroll över de data du visar.

### 5️⃣ Fyll den första serien med datapunkter
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
`addDataPointForScatterSeries` tar en X‑värdescell och en Y‑värdescell, och bygger spridningsdiagrammet punkt för punkt.

### 6️⃣ Anpassa serietyp och markörutseende
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
Här **customize the scatter chart aspose** genom att byta till raka linjer, förstora markörer och välja distinkta symboler (stjärna vs. cirkel) för visuell tydlighet.

### 7️⃣ Spara presentationen
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Att spara som `Pptx` bevarar alla diagramanpassningar och gör filen klar för delning eller vidare redigering.

## Vanliga användningsområden för anpassade spridningsdiagram
- **Financial dashboards** – plotta aktiekurs mot volym.  
- **Scientific research** – visa experimentella mätningar med felmarkörer.  
- **Project management** – jämför planerad vs. faktisk insats över uppgifter.  

## Prestandatips
- Avsluta `Presentation`-objektet (`pres.dispose()`) efter sparning för att frigöra inhemska resurser.  
- För stora datamängder, fyll i arbetsboken först och bind sedan serierna för att undvika upprepade UI‑uppdateringar.  
- Återanvänd en enda `IChartDataWorkbook`-instans när du lägger till många serier.

## Vanliga frågor

### Hur ändrar jag färgen på markörerna?
Använd `series.getMarker().getFillFormat().setFillColor(Color)` där `Color` är en instans av `java.awt.Color` (t.ex. `Color.RED`).

### Kan jag lägga till fler än två serier i ett spridningsdiagram?
Absolut. Upprepa anropet `chart.getChartData().getSeries().add(...)` för varje ytterligare serie och fyll i dess datapunkter därefter.

### Är det möjligt att ange en anpassad legend för varje serie?
Ja. Efter att ha skapat en serie, anropa `series.getLegend().setText("Your Legend Text")` för att åsidosätta standardnamnet.

### Hur kan jag exportera diagrammet som en bild istället för en PPTX?
Anropa `chart.getImage().save("chart.png", ImageFormat.Png)` efter att diagrammet har konfigurerats. Detta ger dig en fristående PNG‑fil.

### Vad händer om jag behöver animera spridningspunkterna?
Aspose.Slides stödjer animationseffekter. Använd `chart.getTimeline().getMainSequence().addEffect(...)` för att lägga till inträdes‑ eller betoningseffekter på diagrammet eller enskilda serier.

---

**Senast uppdaterad:** 2026-02-24  
**Testat med:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}