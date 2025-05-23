---
"date": "2025-04-17"
"description": "Leer hoe je cirkeldiagrammen maakt en aanpast met Aspose.Slides voor Java. Deze tutorial behandelt alles van installatie tot geavanceerde aanpassing."
"title": "Cirkeldiagrammen maken in Java met Aspose.Slides&#58; een uitgebreide handleiding"
"url": "/nl/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cirkeldiagrammen maken met Aspose.Slides voor Java: een complete tutorial

## Invoering
Het creëren van dynamische en visueel aantrekkelijke presentaties is cruciaal voor het overbrengen van impactvolle informatie. Met Aspose.Slides voor Java kunt u complexe grafieken, zoals cirkeldiagrammen, naadloos integreren in uw dia's, waardoor uw datavisualisatie moeiteloos wordt verbeterd. Deze uitgebreide handleiding begeleidt u bij het maken en aanpassen van een cirkeldiagram met Aspose.Slides Java, waarmee u veelvoorkomende presentatieproblemen eenvoudig kunt oplossen.

**Wat je leert:**
- Een presentatie initialiseren en dia's toevoegen.
- Een cirkeldiagram op uw dia maken en configureren.
- Grafiektitels, gegevenslabels en kleuren instellen.
- Prestaties optimaliseren en middelen effectief beheren.
- Aspose.Slides integreren in Java-projecten met Maven of Gradle.

Laten we beginnen door ervoor te zorgen dat je over alle benodigde hulpmiddelen en kennis beschikt om de cursus te kunnen volgen!

## Vereisten
Voordat u met deze tutorial aan de slag gaat, moet u ervoor zorgen dat u de volgende instellingen gereed hebt:

### Vereiste bibliotheken, versies en afhankelijkheden
- **Aspose.Slides voor Java**: Zorg ervoor dat u versie 25.4 of hoger hebt.
- **Java-ontwikkelingskit (JDK)**: Versie 16 of hoger is vereist.

### Vereisten voor omgevingsinstellingen
- Een ontwikkelomgeving met Java geïnstalleerd en geconfigureerd.
- Een Integrated Development Environment (IDE) zoals IntelliJ IDEA, Eclipse of NetBeans.

### Kennisvereisten
- Basiskennis van Java-programmering.
- Kennis van Maven of Gradle voor afhankelijkheidsbeheer.

## Aspose.Slides instellen voor Java
Om Aspose.Slides in je Java-projecten te gebruiken, moet je de bibliotheek als afhankelijkheid toevoegen. Zo doe je dat met verschillende buildtools:

**Maven**
Voeg dit fragment toe aan uw `pom.xml` bestand:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
Neem het volgende op in uw `build.gradle` bestand:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct downloaden**
Als u liever geen buildtool gebruikt, download dan de nieuwste versie van [Aspose.Slides voor Java-releases](https://releases.aspose.com/slides/java/).

### Stappen voor het verkrijgen van een licentie
- **Gratis proefperiode**: Start met een gratis proefperiode om de functies van Aspose.Slides te ontdekken.
- **Tijdelijke licentie**:Verkrijg een tijdelijke licentie voor langdurig gebruik zonder beperkingen.
- **Aankoop**: Overweeg een aankoop als u langdurig toegang nodig hebt.

**Basisinitialisatie en -installatie**
Om Aspose.Slides te kunnen gebruiken, moet u uw project initialiseren door een nieuw presentatieobject te maken:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementatiegids
Laten we het proces voor het toevoegen en aanpassen van een cirkeldiagram opsplitsen in beheersbare stappen.

### Presentatie en dia initialiseren
Begin met het opzetten van een nieuwe presentatie en open de eerste dia. Dit is je canvas voor het maken van grafieken:
```java
import com.aspose.slides.*;

// Een nieuw presentatie-exemplaar maken.
Presentation presentation = new Presentation();
// Ga naar de eerste dia van de presentatie.
islide slides = presentation.getSlides().get_Item(0);
```

### Cirkeldiagram toevoegen aan dia
Plaats een cirkeldiagram op de opgegeven positie met een standaardgegevensset:
```java
import com.aspose.slides.*;

// Voeg een cirkeldiagram toe op positie (100, 100) met grootte (400, 400).
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Grafiektitel instellen
Pas uw grafiek aan door de titel in te stellen en te centreren:
```java
import com.aspose.slides.*;

// Voeg een titel toe aan het cirkeldiagram.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Gegevenslabels voor reeksen configureren
Zorg ervoor dat de gegevenslabels waarden weergeven voor meer duidelijkheid:
```java
import com.aspose.slides.*;

// Gegevenswaarden weergeven in de eerste reeks.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Werkblad voor het voorbereiden van grafiekgegevens
Stel het gegevensblad van uw grafiek in door bestaande reeksen en categorieën te wissen:
```java
import com.aspose.slides.*;

// Bereid de werkmap met grafiekgegevens voor.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Categorieën toevoegen aan grafiek
Definieer categorieën voor uw cirkeldiagram:
```java
import com.aspose.slides.*;

// Nieuwe categorieën toevoegen.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Reeksen toevoegen en datapunten vullen
Maak een reeks en vul deze met datapunten:
```java
import com.aspose.slides.*;

// Voeg een nieuwe serie toe en geef de serie een naam.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Pas seriekleuren en randen aan
Vergroot de visuele aantrekkingskracht door kleuren in te stellen en randen aan te passen:
```java
import com.aspose.slides.*;

// Stel verschillende kleuren in voor de sectoren van de serie.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Herhaal dit voor andere datapunten met verschillende kleuren en stijlen.
```

### Aangepaste gegevenslabels configureren
Pas de labels voor elk gegevenspunt nauwkeurig aan:
```java
import com.aspose.slides.*;

// Aangepaste labels configureren.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Schakel aanhaallijnen voor labels in.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Rotatiehoek instellen en presentatie opslaan
Maak uw cirkeldiagram af door een rotatiehoek in te stellen en de presentatie op te slaan:
```java
import com.aspose.slides.*;

// Rotatiehoek instellen.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Sla de presentatie op in een bestand.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Conclusie
In deze tutorial heb je geleerd hoe je cirkeldiagrammen maakt en aanpast met Aspose.Slides voor Java. Door deze stappen te volgen, kun je je presentaties verbeteren met visueel aantrekkelijke datavisualisaties. Neem gerust contact met ons op als je vragen hebt of meer hulp nodig hebt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}