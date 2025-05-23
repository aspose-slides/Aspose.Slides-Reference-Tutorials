---
"date": "2025-04-17"
"description": "Lär dig hur du skapar fantastiska ringdiagram i Java med Aspose.Slides. Den här omfattande guiden täcker initialisering, datakonfiguration och hur man sparar presentationer."
"title": "Skapa ringdiagram i Java med hjälp av Aspose.Slides – En omfattande guide"
"url": "/sv/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa ringdiagram i Java med Aspose.Slides: En steg-för-steg-guide

## Introduktion

dagens datadrivna miljö är det viktigt att visualisera information effektivt för att öka förståelsen och engagemanget. Även om det kan verka utmanande att skapa professionella diagram programmatiskt, särskilt med Java, kommer den här guiden att guida dig genom att använda Aspose.Slides för Java för att enkelt skapa ringdiagram.

Genom att följa dessa steg får utvecklare praktisk erfarenhet av att manipulera presentationsbilder och integrera datavisualisering sömlöst.

**Viktiga slutsatser:**
- Initiera ett presentationsobjekt med hjälp av Aspose.Slides Java.
- Konfigurera diagramdata och hantera befintliga serier eller kategorier.
- Lägg till och anpassa serier och kategorier för dina diagram.
- Formatera och visa datapunkter effektivt.
- Spara enkelt din presentation i olika format.

Innan du börjar implementationen, se till att du har allt som behövs för att komma igång.

## Förkunskapskrav

För att följa den här handledningen, se till att du har:

- **Obligatoriska bibliotek:**
  - Aspose.Slides för Java version 25.4 eller senare.
  
- **Miljöinställningar:**
  - JDK 16 eller senare installerat på ditt system.
  - En IDE som IntelliJ IDEA, Eclipse eller NetBeans.

- **Kunskapsförkunskapskrav:**
  - Grundläggande förståelse för Java-programmeringskoncept.
  - Erfarenhet av att hantera beroenden i Maven- eller Gradle-projekt.

## Konfigurera Aspose.Slides för Java

För att integrera Aspose.Slides i ditt projekt, följ dessa steg baserat på ditt byggverktyg:

**Maven-inställningar:**
Lägg till följande beroende till din `pom.xml` fil:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle-inställningar:**
Inkludera följande i din `build.gradle` fil:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkt nedladdning:**
Alternativt kan du ladda ner den senaste versionen direkt från [Aspose.Slides för Java-versioner](https://releases.aspose.com/slides/java/).

### Att förvärva en licens

För att använda Aspose.Slides utan utvärderingsbegränsningar:
- **Gratis provperiod:** Börja med en tillfällig licens för att utforska alla funktioner.
- **Tillfällig licens:** Skaffa en via [Asposes webbplats](https://purchase.aspose.com/temporary-license/).
- **Köpa:** Överväg att köpa för kontinuerligt bruk.

Använd din licens i ditt Java-program med hjälp av:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementeringsguide

### Initierar presentation och diagram

#### Översikt
Börja med att initiera ett presentationsobjekt och lägga till ett ringdiagram på den första bilden.

**Steg 1: Initiera presentationen**
Ladda en befintlig PPTX-fil eller skapa en ny:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Steg 2: Lägg till ringdiagram**
Skapa ett diagram på den första bilden vid angivna koordinater:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Konfigurera arbetsboken för diagramdata och rensa befintliga serier/kategorier

#### Översikt
Konfigurera arbetsboken för diagramdata och ta bort alla befintliga serier eller kategorier.

**Steg 1: Åtkomst till arbetsboken för diagramdata**
Hämta arbetsboken som är länkad till ditt diagram:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Steg 2: Rensa befintliga serier och kategorier**
Se till att det inte finns några kvarvarande datapunkter:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Lägga till serier i diagrammet

#### Översikt
Fyll ditt diagram med flera serier, var och en anpassad för utseende och beteende.

**Steg 1: Lägg till serier iterativt**
Loopa igenom index för att lägga till serier:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Anpassa serien
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Lägga till kategorier och datapunkter i diagrammet

#### Översikt
Konfigurera kategorier och lägg till datapunkter med specifik formatering för etiketter.

**Steg 1: Lägg till kategorier**
Gå igenom index för varje kategori:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Steg 2: Lägg till datapunkter i varje serie**
Gå igenom varje serie för den aktuella kategorin:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Inställningar för datapunktsformat
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Etikettformatering för den senaste serien
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Justera visningsalternativ
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Justera etikettpositionen
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### Spara presentationen

#### Översikt
När du har konfigurerat ditt diagram sparar du presentationen i en angiven katalog.

**Steg 1: Spara presentationen**
Använd `save` metod för att skriva ändringar:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Slutsats

Du har nu lärt dig hur du skapar och anpassar ringdiagram i Java med hjälp av Aspose.Slides. Dessa steg ger en grund för att integrera sofistikerade datavisualiseringar i dina presentationer.

**Nästa steg:**
- Experimentera med olika diagramtyper som finns i Aspose.Slides.
- Utforska ytterligare anpassningsalternativ som färger, teckensnitt och stilar för att matcha dina varumärkesbehov.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}