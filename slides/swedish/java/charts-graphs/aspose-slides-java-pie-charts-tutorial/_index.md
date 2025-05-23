---
"date": "2025-04-17"
"description": "Lär dig hur du skapar och anpassar cirkeldiagram med Aspose.Slides för Java. Den här handledningen täcker allt från installation till avancerad anpassning."
"title": "Skapa cirkeldiagram i Java med Aspose.Slides – En omfattande guide"
"url": "/sv/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Skapa cirkeldiagram med Aspose.Slides för Java: En komplett handledning

## Introduktion
Att skapa dynamiska och visuellt tilltalande presentationer är avgörande för att leverera effektfull information. Med Aspose.Slides för Java kan du sömlöst integrera komplexa diagram som cirkeldiagram i dina bilder, vilket förbättrar datavisualiseringen utan ansträngning. Den här omfattande guiden guidar dig genom processen att skapa och anpassa ett cirkeldiagram med Aspose.Slides Java, och löser vanliga presentationsutmaningar med lätthet.

**Vad du kommer att lära dig:**
- Initiera en presentation och lägga till bilder.
- Skapa och konfigurera ett cirkeldiagram på din bild.
- Ställa in diagramtitlar, dataetiketter och färger.
- Optimera prestanda och effektivt hantera resurser.
- Integrera Aspose.Slides i Java-projekt med hjälp av Maven eller Gradle.

Låt oss börja med att se till att du har alla nödvändiga verktyg och kunskaper för att följa med!

## Förkunskapskrav
Innan du dyker in i den här handledningen, se till att du har följande inställningar redo:

### Obligatoriska bibliotek, versioner och beroenden
- **Aspose.Slides för Java**Se till att du har version 25.4 eller senare.
- **Java-utvecklingspaket (JDK)**Version 16 eller senare krävs.

### Krav för miljöinstallation
- En utvecklingsmiljö med Java installerat och konfigurerat.
- En integrerad utvecklingsmiljö (IDE) som IntelliJ IDEA, Eclipse eller NetBeans.

### Kunskapsförkunskaper
- Grundläggande förståelse för Java-programmering.
- Bekantskap med Maven eller Gradle för beroendehantering.

## Konfigurera Aspose.Slides för Java
För att börja använda Aspose.Slides i dina Java-projekt måste du lägga till biblioteket som ett beroende. Så här gör du med olika byggverktyg:

**Maven**
Lägg till det här utdraget i din `pom.xml` fil:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
Inkludera följande i din `build.gradle` fil:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direkt nedladdning**
Om du föredrar att inte använda ett byggverktyg, ladda ner den senaste versionen från [Aspose.Slides för Java-versioner](https://releases.aspose.com/slides/java/).

### Steg för att förvärva licens
- **Gratis provperiod**Börja med en gratis provperiod för att utforska Aspose.Slides funktioner.
- **Tillfällig licens**Erhåll en tillfällig licens för utökad användning utan begränsningar.
- **Köpa**Överväg att köpa om du behöver långsiktig åtkomst.

**Grundläggande initialisering och installation**
För att börja använda Aspose.Slides, initiera ditt projekt genom att skapa ett nytt presentationsobjekt:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementeringsguide
Nu ska vi dela upp processen att lägga till och anpassa ett cirkeldiagram i hanterbara steg.

### Initiera presentation och bild
Börja med att skapa en ny presentation och öppna den första bilden. Detta är din arbetsyta för att skapa diagram:
```java
import com.aspose.slides.*;

// Skapa en ny presentationsinstans.
Presentation presentation = new Presentation();
// Få åtkomst till den första bilden i presentationen.
islide slides = presentation.getSlides().get_Item(0);
```

### Lägg till cirkeldiagram till bild
Infoga ett cirkeldiagram på den angivna positionen med en standarddatauppsättning:
```java
import com.aspose.slides.*;

// Lägg till ett cirkeldiagram vid position (100, 100) med storleken (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Ange diagramtitel
Anpassa ditt diagram genom att ställa in och centrera titeln:
```java
import com.aspose.slides.*;

// Lägg till en rubrik till cirkeldiagrammet.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Konfigurera dataetiketter för serier
Se till att dataetiketterna visar värden för tydlighetens skull:
```java
import com.aspose.slides.*;

// Visa datavärden för den första serien.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Förbered arbetsblad med diagramdata
Konfigurera diagrammets datablad genom att rensa befintliga serier och kategorier:
```java
import com.aspose.slides.*;

// Förbered arbetsboken med diagramdata.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Lägg till kategorier i diagrammet
Definiera kategorier för ditt cirkeldiagram:
```java
import com.aspose.slides.*;

// Lägg till nya kategorier.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Lägg till serier och fyll i datapunkter
Skapa en serie och fyll den med datapunkter:
```java
import com.aspose.slides.*;

// Lägg till en ny serie och ange dess namn.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Anpassa seriefärger och ramar
Förbättra det visuella intrycket genom att ställa in färger och anpassa ramar:
```java
import com.aspose.slides.*;

// Ställ in olika färger för seriens sektorer.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Upprepa för andra datapunkter med andra färger och stilar.
```

### Konfigurera anpassade dataetiketter
Finjustera etiketterna för varje datapunkt:
```java
import com.aspose.slides.*;

// Konfigurera anpassade etiketter.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Aktivera riktlinjer för etiketter.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Ställ in rotationsvinkel och spara presentation
Slutför ditt cirkeldiagram genom att ange en rotationsvinkel och spara presentationen:
```java
import com.aspose.slides.*;

// Ställ in rotationsvinkeln.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Spara presentationen till en fil.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Slutsats
I den här handledningen har du lärt dig hur du skapar och anpassar cirkeldiagram med Aspose.Slides för Java. Genom att följa dessa steg kan du förbättra dina presentationer med visuellt tilltalande datavisualiseringar. Om du har några frågor eller behöver ytterligare hjälp är du välkommen att kontakta oss.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}