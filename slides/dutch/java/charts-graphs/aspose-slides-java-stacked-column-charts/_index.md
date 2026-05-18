---
date: '2026-02-22'
description: Leer hoe je een gestapelde kolomgrafiek maakt in Java met Aspose.Slides.
  Deze tutorial behandelt de Aspose Slides Maven‑afhankelijkheid, het toevoegen van
  een procentueel gestapelde grafiek, het opmaken van grafiekgegevenslabels en het
  opslaan van de presentatie als PPTX.
keywords:
- Aspose.Slides
- stacked column chart
- Java presentation
title: Hoe maak je een gestapelde kolomgrafiek in Java met Aspose.Slides – Een uitgebreide
  gids
url: /nl/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

 shortcodes.

Also ensure we keep the markdown formatting exactly.

Now produce final output with all sections.

Let's craft final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe een gestapelde kolomgrafiek te maken in Java met Aspose.Slides – Een uitgebreide gids

## Introductie

Verbeter uw presentaties door inzichtelijke datavisualisaties toe te voegen met de kracht van Aspose.Slides voor Java. In deze gids maakt u **gestapelde kolomgrafiek**‑dia's die er professioneel uitzien, of u nu zakelijke rapporten voorbereidt of projectstatistieken presenteert. Aan het einde van deze tutorial kunt u:

- Installeer uw omgeving met de Aspose Slides Maven‑dependency
- Maak een presentatie vanaf nul
- **Voeg een percentage‑gestapelde grafiek toe** en pas het uiterlijk aan
- **Formatteer grafiek‑dataplabels** en **wijzig het verticale as‑formaat**
- **Sla de presentatie op als PPTX** met één regel code

Laten we elke stap doorlopen zodat u direct overtuigende presentaties kunt maken.

## Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** `aspose-slides` Maven/Gradle‑dependency (zie “aspose slides maven dependency” hieronder)  
- **Welk grafiektype wordt gebruikt?** `ChartType.PercentsStackedColumn` voor een percentage‑gestapelde kolomgrafiek  
- **Hoe wijzig ik het getalformaat van de as?** Gebruik `IAxis.setNumberFormat()` en schakel koppeling aan bron uit  
- **Kan ik dataplabels aanpassen?** Ja – itereren door `IChartDataPoint`‑objecten en een aangepast `ITextFrame` instellen  
- **Hoe sla ik het bestand op?** Roep `presentation.save("output.pptx", SaveFormat.Pptx)` aan

## Wat is een gestapelde kolomgrafiek?
Een gestapelde kolomgrafiek visualiseert meerdere dataseries die bovenop elkaar worden gestapeld in verticale kolommen. Wanneer u de **percentage‑gestapelde** variant gebruikt, telt elke kolom altijd 100 %, waardoor het eenvoudig is om proportionele bijdragen over categorieën te vergelijken.

## Waarom Aspose.Slides voor Java gebruiken?
Aspose.Slides biedt een pure‑Java API die op elk platform werkt zonder dat Microsoft Office geïnstalleerd hoeft te zijn. Het biedt fijnmazige controle over grafiekobjecten, ondersteunt een breed scala aan formaten, en stelt u in staat presentaties programmatisch te genereren—perfect voor geautomatiseerde rapportage of server‑side documentgeneratie.

## Vereisten
- **Java Development Kit (JDK):** 8 of hoger  
- **IDE:** IntelliJ IDEA, Eclipse of een andere Java‑compatibele editor  
- **Build‑tool:** Maven of Gradle (optioneel maar aanbevolen)  
- **Basiskennis van Java** – u moet vertrouwd zijn met klassen en methoden  

## Aspose.Slides voor Java instellen
Om te beginnen voegt u de Aspose.Slides‑bibliotheek toe aan uw project.

### Aspose Slides Maven‑dependency
Voeg het volgende toe aan uw `pom.xml` (dit is de **aspose slides maven dependency** die u nodig heeft):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑alternatief
Als u Gradle verkiest, voeg deze regel toe in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Directe download
U kunt ook de nieuwste JAR downloaden van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licentie‑acquisitie
U kunt starten met een gratis proefversie om de functies van Aspose.Slides te verkennen. Om evaluatiebeperkingen te verwijderen, overweeg een tijdelijke of aangekochte licentie.

- **Gratis proefversie:** Toegang tot beperkte functionaliteit zonder directe kosten.  
- **Tijdelijke licentie:** Aanvragen via [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Aankoop:** Bezoek de aankooppagina voor volledige toegang.

### Basisinitialisatie
Hier is een minimale code‑fragment dat laat zien hoe u een `Presentation`‑object maakt:

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

## Implementatie‑gids

### Een presentatie maken en een dia toevoegen
**Overzicht:**  
Eerst maken we een lege presentatie en controleren we of er een dia bestaat.

#### Stap 1: Presentatie‑object initialiseren
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

#### Stap 2: De presentatie opslaan
```
// Save the presentation to a file
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Een percentage‑gestapelde kolomgrafiek aan een dia toevoegen
**Overzicht:**  
Nu plaatsen we een **percentage‑gestapelde grafiek** op de eerste dia.

#### Stap 1: Dia initialiseren en benaderen
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

#### Stap 2: Grafiek aan dia toevoegen
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Het getalformaat van de grafiekas aanpassen
**Overzicht:**  
Voor betere leesbaarheid zullen we het **verticale as‑formaat wijzigen** zodat percentages worden weergegeven.

#### Stap 1: Grafiek toevoegen en benaderen
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

#### Stap 2: Aangepast getalformaat instellen
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Series en datapoints aan grafiek toevoegen
**Overzicht:**  
We vullen de grafiek met voorbeeld‑dataseries.

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

#### Stap 2: Dataseries toevoegen
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Kleur van series vullen opmaken
**Overzicht:**  
Geef elke serie een eigen kleur zodat de grafiek beter leesbaar is.

#### Stap 1: Grafiek initialiseren en benaderen
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

// Repeat for other series with different colors
```

### Dataplabels opmaken
**Overzicht:**  
Nu **formatteren we de grafiek‑dataplabels** zodat ze aangepaste tekst tonen.

#### Stap 1: Grafiekseries en datapoints benaderen
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

#### Stap 2: Dataplabels aanpassen
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

## Veelvoorkomende problemen en oplossingen
- **Grafiek verschijnt leeg:** Zorg ervoor dat u minstens één dataserie en datapunt hebt toegevoegd vóór het opslaan.  
- **As‑nummers tonen geen percentages:** Vergeet niet `verticalAxis.setNumberFormatLinkedToSource(false)` in te stellen; anders wordt het aangepaste formaat genegeerd.  
- **Licentie‑evaluatie‑bericht:** Pas een geldig licentiebestand toe voordat u het `Presentation`‑object maakt om de evaluatie‑banner te onderdrukken.

## Veelgestelde vragen

**V: Kan ik deze code gebruiken met Java 11 of nieuwer?**  
A: Ja. De bibliotheek ondersteunt JDK 8+; gebruik gewoon de juiste classifier (bijv. `jdk16` voor JDK 16 of later).

**V: Hoe exporteer ik de grafiek als afbeelding in plaats van een PPTX?**  
A: Gebruik `chart.getImage().save("chart.png", ImageFormat.Png);` nadat u de grafiek aan de dia hebt toegevoegd.

**V: Is het mogelijk een legenda toe te voegen aan de gestapelde kolomgrafiek?**  
A: Absoluut. Roep `chart.getChartTitle().addTextFrameForOverriding("My Chart");` aan en configureer `chart.getLegend()` naar wens.

**V: Wat als ik data moet bijwerken nadat de presentatie is gegenereerd?**  
A: U kunt de cellen van `ChartDataWorkbook` aanpassen en vervolgens `chart.refresh();` aanroepen om de wijzigingen weer te geven.

**V: Werkt Aspose.Slides op Linux‑servers?**  
A: Ja. De bibliotheek is pure Java en draait op elk OS met een compatibele JRE.

## Conclusie
Door deze gids te volgen heeft u geleerd hoe u **gestapelde kolomgrafiek**‑presentaties maakt met Aspose.Slides voor Java, van het opzetten van de omgeving tot fijn afgestemde visuele styling. Experimenteer met verschillende datasets, kleuren en label‑formaten om uw rapporten echt te laten opvallen.

---

**Last Updated:** 2026-02-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}