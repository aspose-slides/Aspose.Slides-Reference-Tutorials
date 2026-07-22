---
date: '2026-07-22'
description: Leer de Aspose Slides Maven Dependency om een stacked column chart in
  Java te maken, add data labels, change vertical axis number format, en exporteer
  het resultaat als een PPTX‑bestand.
keywords:
- aspose slides maven dependency
- add data labels to chart
- change vertical axis number format
- how to add percentage stacked chart
lastmod: '2026-07-22'
og_description: Aspose Slides Maven Dependency laat je een stacked column chart in
  Java bouwen, customize data labels, adjust vertical axis format, en opslaan als
  PPTX – allemaal met beknopte, production‑ready code.
og_image_alt: 'Developer guide: Build a stacked column chart in Java using Aspose.Slides
  Maven dependency'
og_title: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
schemas:
- author: Aspose
  dateModified: '2026-07-22'
  description: Learn the Aspose Slides Maven Dependency to create a stacked column
    chart in Java, add data labels, change vertical axis number format, and export
    the result as a PPTX file.
  headline: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
  type: TechArticle
- questions:
  - answer: Yes. The library supports JDK 8+; just use the appropriate classifier
      (e.g., `jdk16` for JDK 16 or later).
    question: Can I use this code with Java 11 or newer?
  - answer: Use `chart.getImage().save("chart.png", ImageFormat.Png);` after adding
      the chart to the slide.
    question: How do I export the chart as an image instead of a PPTX?
  - answer: Absolutely. Call `chart.getChartTitle().addTextFrameForOverriding("My
      Chart");` and configure `chart.getLegend()` as needed.
    question: Is it possible to add a legend to the stacked column chart?
  - answer: You can modify the `ChartDataWorkbook` cells and then call `chart.refresh();`
      to reflect changes.
    question: What if I need to update data after the presentation is generated?
  - answer: Yes. The library is pure Java and runs on any OS with a compatible JRE.
    question: Does Aspose.Slides work on Linux servers?
  type: FAQPage
tags:
- stacked column chart
- Aspose.Slides
- Java charting
- Maven dependency
- presentation generation
title: 'Aspose Slides Maven Dependency: Stacked Column Chart in Java'
url: /nl/java/charts-graphs/aspose-slides-java-stacked-column-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Aspose Slides Maven-afhankelijkheid: Gestapelde kolomgrafiek in Java

## Introductie

Verhoog uw presentaties door inzichtelijke datavisualisaties toe te voegen met de kracht van **Aspose.Slides for Java**. In deze gids maakt u **een gestapelde kolomgrafiek** die er professioneel uitziet, of u nu zakelijke rapporten voorbereidt of projectstatistieken presenteert. Aan het einde van deze tutorial kunt u:

- Uw omgeving instellen met de **Aspose Slides Maven-afhankelijkheid**
- Een presentatie vanaf nul maken
- **Een percentage‑gestapelde grafiek toevoegen** en het uiterlijk aanpassen
- **Grafiekdataplabels opmaken** en **het getalformaat van de verticale as wijzigen**
- **De presentatie opslaan als PPTX** met één regel code

## Snelle antwoorden
- **Welke bibliotheek heb ik nodig?** Voeg de `aspose-slides` Maven/Gradle‑afhankelijkheid toe (zie “Aspose Slides Maven Dependency” hieronder).  
- **Welk grafiektype maakt een gestapelde weergave?** Gebruik `ChartType.PercentsStackedColumn` voor een percentage‑gestapelde kolomgrafiek.  
- **Hoe kan ik het getalformaat van de as wijzigen?** Roep `IAxis.setNumberFormat()` aan en stel `setNumberFormatLinkedToSource(false)` in.  
- **Kan ik dataplabels aanpassen?** Ja – iterate door elke `IChartDataPoint` en wijs een aangepast `ITextFrame` toe.  
- **Hoe sla ik het bestand op?** Roep `presentation.save("output.pptx", SaveFormat.Pptx)` aan.

## Wat is een gestapelde kolomgrafiek?
Een gestapelde kolomgrafiek visualiseert meerdere gegevensreeksen die verticaal gestapeld zijn in elke categoriekolom, waarbij de **percentage‑gestapelde** variant elke kolom normaliseert tot 100 % voor eenvoudige proportievergelijking. Dit formaat stelt kijkers in staat snel te beoordelen hoe elk component bijdraagt aan het geheel over verschillende categorieën, waardoor trends en relatieve groottes meteen duidelijk worden.

## Waarom Aspose.Slides voor Java gebruiken?
Aspose.Slides voor Java stelt u in staat PowerPoint‑bestanden te genereren, bewerken en converteren **zonder Microsoft Office te hoeven** en ondersteunt **meer dan 50 uitvoerformaten** op Windows, Linux en macOS. De bibliotheek draait volledig op een JRE, waardoor server‑side automatisering en high‑throughput rapportage mogelijk zijn. Het biedt ook fijnmazige controle over grafiekobjecten, dia‑lay-outs en documenteigenschappen, waardoor het ideaal is voor enterprise‑niveau presentaties.

## Vereisten
- **Java Development Kit (JDK):** 8 of hoger  
- **IDE:** IntelliJ IDEA, Eclipse, of een andere Java‑compatibele editor  
- **Build‑tool:** Maven of Gradle (optioneel maar aanbevolen)  
- **Basiskennis van Java** – u moet vertrouwd zijn met klassen en methoden  

## Aspose.Slides voor Java instellen
Om te beginnen, voeg de Aspose.Slides‑bibliotheek toe aan uw project.

### Aspose Slides Maven-afhankelijkheid
Voeg het volgende toe aan uw `pom.xml` (dit is de **aspose slides maven-afhankelijkheid** die u nodig heeft):

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑alternatief
Als u de voorkeur geeft aan Gradle, voeg dan deze regel toe in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Directe download
U kunt ook de nieuwste JAR downloaden van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licentie‑acquisitie
U kunt beginnen met een gratis proefversie om de functies van Aspose.Slides te verkennen. Om evaluatiebeperkingen te verwijderen, overweeg een tijdelijke of aangeschafte licentie.

- **Gratis proefversie:** Toegang tot beperkte functies zonder directe kosten.  
- **Tijdelijke licentie:** Aanvragen via [Aspose’s site](https://purchase.aspose.com/temporary-license/).  
- **Aankoop:** Bezoek de aankooppagina voor volledige toegang.

### Basisinitialisatie
`Presentation` is de kernklasse van Aspose.Slides die een PowerPoint‑bestand in het geheugen vertegenwoordigt. Het volgende minimale fragment toont hoe u een `Presentation`‑object maakt:

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
Eerst maken we een lege presentatie en verifiëren we dat er een dia bestaat.

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

### Percentage‑gestapelde kolomgrafiek toevoegen aan een dia
**Overzicht:**  
Nu plaatsen we een **percentage‑gestapelde grafiek** op de eerste dia.

`ChartType.PercentsStackedColumn` geeft een percentage‑gestapelde kolomgrafiek op.

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

### Grafiekas‑getalformaat aanpassen
**Overzicht:**  
Voor betere leesbaarheid zullen we **het verticale as‑formaat wijzigen** zodat percentages worden weergegeven.

`IAxis` is de interface die een grafiekas vertegenwoordigt, waardoor format‑ en schaalaanpassingen mogelijk zijn.

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

### Reeksen en gegevenspunten aan grafiek toevoegen
**Overzicht:**  
We vullen de grafiek met voorbeeldgegevensreeksen.

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

#### Stap 2: Gegevensreeks toevoegen
```java
// Clear existing series and add new ones
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Add more data points as needed
```

### Kleur van reeksen opvullen opmaken
**Overzicht:**  
Geef elke reeks een onderscheidende kleur om de grafiek beter leesbaar te maken.

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

#### Stap 2: Opvulkleur instellen
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Repeat for other series with different colors
```

### Dataplabels opmaken
**Overzicht:**  
Nu **vormen we grafiekdataplabels** zodat ze aangepaste tekst weergeven.

`IChartDataPoint` vertegenwoordigt een individueel gegevenspunt binnen een grafiekreeks, en `ITextFrame` bevat de labeltekst.

#### Stap 1: Grafiekreeksen en gegevenspunten benaderen
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
- **Grafiek verschijnt leeg:** Zorg ervoor dat u ten minste één gegevensreeks en gegevenspunt heeft toegevoegd vóór het opslaan.  
- **As‑nummers tonen geen percentages:** Vergeet niet `verticalAxis.setNumberFormatLinkedToSource(false)` in te stellen; anders wordt het aangepaste formaat genegeerd.  
- **Licentie‑evaluatiebericht:** Pas een geldig licentiebestand toe vóór het maken van het `Presentation`‑object om de evaluatiebanner te onderdrukken.

## Veelgestelde vragen

**Q: Kan ik deze code gebruiken met Java 11 of nieuwer?**  
A: Ja. De bibliotheek ondersteunt JDK 8+; gebruik gewoon de juiste classifier (bijv. `jdk16` voor JDK 16 of later).

**Q: Hoe exporteer ik de grafiek als afbeelding in plaats van een PPTX?**  
A: Gebruik `chart.getImage().save("chart.png", ImageFormat.Png);` nadat u de grafiek aan de dia hebt toegevoegd.

**Q: Is het mogelijk om een legenda toe te voegen aan de gestapelde kolomgrafiek?**  
A: Zeker. Roep `chart.getChartTitle().addTextFrameForOverriding("My Chart");` aan en configureer `chart.getLegend()` naar behoefte.

**Q: Wat als ik gegevens moet bijwerken nadat de presentatie is gegenereerd?**  
A: U kunt de cellen van `ChartDataWorkbook` wijzigen en vervolgens `chart.refresh();` aanroepen om de wijzigingen weer te geven.

**Q: Werkt Aspose.Slides op Linux‑servers?**  
A: Ja. De bibliotheek is pure Java en draait op elk OS met een compatibele JRE.

## Conclusie
Door deze gids te volgen heeft u geleerd hoe u een **gestapelde kolomgrafiek** in Java kunt **maken met de Aspose Slides Maven‑afhankelijkheid**, van het opzetten van de omgeving tot fijn afgestemde visuele styling. Experimenteer met verschillende datasets, kleuren en label‑formaten om uw rapporten echt te laten opvallen.

---

**Last Updated:** 2026-07-22  
**Tested With:** Aspose.Slides 25.4 (jdk16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe een gegroepeerde kolomgrafiek maken in Java met Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-clustered-column-charts/)
- [Hoe getalformaten instellen in grafiekdatapunten met Aspose.Slides voor Java](/slides/java/charts-graphs/set-number-format-chart-data-points-aspose-slides-java/)
- [Hoe grafieken toevoegen en configureren in presentaties met Aspose.Slides voor Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}