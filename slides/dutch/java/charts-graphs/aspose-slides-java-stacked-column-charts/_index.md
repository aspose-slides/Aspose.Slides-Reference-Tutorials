---
"date": "2025-04-17"
"description": "Leer professionele presentaties maken met Aspose.Slides voor Java. Deze handleiding behandelt het instellen van je omgeving, het toevoegen van gestapelde kolomdiagrammen en het aanpassen ervan voor meer duidelijkheid."
"title": "Leer gestapelde kolomdiagrammen in Java met Aspose.Slides&#58; een uitgebreide handleiding"
"url": "/nl/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Leer gestapelde kolomdiagrammen in Java met Aspose.Slides: een uitgebreide handleiding

## Invoering

Verbeter uw presentaties door inzichtelijke datavisualisaties te integreren met de kracht van Aspose.Slides voor Java. Het maken van professioneel ogende dia's met gestapelde kolomdiagrammen is eenvoudig, of u nu bedrijfsrapporten voorbereidt of projectstatistieken presenteert.

In deze tutorial onderzoeken we hoe je Aspose.Slides voor Java kunt gebruiken om dynamische presentaties te maken en visueel aantrekkelijke gestapelde kolomdiagrammen toe te voegen. Aan het einde van deze handleiding beschik je over de vaardigheden die nodig zijn om:
- Stel uw omgeving in om Aspose.Slides te gebruiken
- Een presentatie vanaf nul maken
- Percentagegestapelde kolomdiagrammen toevoegen en aanpassen
- Formaat grafiekassen en gegevenslabels voor duidelijkheid

Laten we eens kijken hoe u presentaties kunt maken die uw publiek boeien.

## Vereisten
Voordat we beginnen, zorg ervoor dat u het volgende heeft:
- **Java-ontwikkelingskit (JDK):** Versie 8 of hoger.
- **IDE:** Elke geïntegreerde ontwikkelomgeving zoals IntelliJ IDEA of Eclipse.
- **Maven/Gradle:** Voor het beheren van afhankelijkheden (optioneel, maar aanbevolen).
- **Basiskennis Java:** Kennis van Java-programmeerconcepten.

## Aspose.Slides instellen voor Java
Om te beginnen moet u de Aspose.Slides-bibliotheek aan uw project toevoegen. Zo doet u dat:

**Kenner:**
Voeg deze afhankelijkheid toe aan uw `pom.xml` bestand:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
Neem dit op in uw `build.gradle` bestand:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct downloaden:**
U kunt ook de nieuwste JAR downloaden van [Aspose.Slides voor Java-releases](https://releases.aspose.com/slides/java/).

### Licentieverwerving
U kunt beginnen met een gratis proefperiode om de functies van Aspose.Slides te verkennen. Om de beperkingen van de evaluatieperiode te omzeilen, kunt u overwegen een tijdelijke of gekochte licentie aan te schaffen.
- **Gratis proefperiode:** Krijg toegang tot beperkte functies zonder directe kosten.
- **Tijdelijke licentie:** Aanvraag via [Aspose's site](https://purchase.aspose.com/temporary-license/).
- **Aankoop:** Ga naar de aankooppagina voor volledige toegang.

### Basisinitialisatie
Zo initialiseert u Aspose.Slides in uw Java-toepassing:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Een exemplaar van de presentatieklasse maken
        Presentation presentation = new Presentation();
        
        // Bewerkingen uitvoeren op het presentatieobject
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Implementatiegids

### Een presentatie maken en een dia toevoegen
**Overzicht:**
Begin met het maken van een eenvoudige presentatie met een eerste dia. Dit vormt de basis voor verdere verbeteringen.

#### Stap 1: Presentatieobject initialiseren
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Een nieuw presentatie-exemplaar maken
        Presentation presentation = new Presentation();
        
        // Verwijzing naar de eerste dia (automatisch aangemaakt)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### Stap 2: Sla de presentatie op
```java
// Sla de presentatie op in een bestand
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Percentage gestapelde kolomgrafiek toevoegen aan een dia
**Overzicht:**
Verbeter uw dia door een kolomdiagram met percentages toe te voegen, zodat u de gegevens eenvoudig kunt vergelijken.

#### Stap 1: Dia initialiseren en openen
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Ga in de volgende stap verder met het toevoegen van een grafiek
    }
}
```

#### Stap 2: Grafiek toevoegen aan dia
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Het aanpassen van de getalnotatie van de grafiekas
**Overzicht:**
Pas de getalnotatie van de verticale as van uw diagram aan voor betere leesbaarheid.

#### Stap 1: Grafiek toevoegen en openen
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

#### Stap 2: Aangepaste getalnotatie instellen
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Reeksen en datapunten toevoegen aan de grafiek
**Overzicht:**
Vul uw grafiek met gegevensreeksen, waardoor deze informatief en visueel aantrekkelijk wordt.

#### Stap 1: Presentatie en grafiek initialiseren
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

#### Stap 2: Gegevensreeksen toevoegen
```java
// Bestaande series wissen en nieuwe toevoegen
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Voeg indien nodig meer datapunten toe
```

### Opmaakreeks Vulkleur
**Overzicht:**
Verbeter de esthetiek van uw grafiek door de opvulkleur van elke reeks aan te passen.

#### Stap 1: Initialiseren en openen van grafiek
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

#### Stap 2: Vulkleuren instellen
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Herhaal dit voor andere series met verschillende kleuren
```

### Gegevenslabels opmaken
**Overzicht:**
Maak uw gegevenslabels leesbaarder door de opmaak aan te passen.

#### Stap 1: Toegang tot grafiekreeksen en datapunten
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

#### Stap 2: Gegevenslabels aanpassen
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

## Conclusie
Door deze handleiding te volgen, hebt u geleerd hoe u Aspose.Slides voor Java instelt en dynamische presentaties maakt met op percentages gestapelde kolomdiagrammen. U kunt uw diagrammen verder aanpassen door kleuren en labels naar wens aan te passen.

Veel plezier met coderen!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}