---
date: '2026-07-17'
description: Leer hoe u een taartdiagram roteert, de kleuren van het taartdiagram
  aanpast en een dia exporteert naar PDF met Aspose.Slides for Java – een volledige
  gids voor datavisualisatie.
keywords:
- rotate pie chart
- customize pie chart colors
- export slide to pdf
- chart data worksheet
- java data visualization
lastmod: '2026-07-17'
og_description: Roteer een taartdiagram en pas de kleuren van het taartdiagram aan
  met Aspose.Slides for Java. Leer hoe u een dia exporteert naar PDF en werkt met
  het werkblad met grafiekgegevens.
og_image_alt: Guide showing how to rotate a pie chart and set custom colors in Java
  with Aspose.Slides
og_title: Taartdiagram roteren en kleuren aanpassen in Java – Aspose.Slides-gids
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to rotate pie chart, customize pie chart colors, and export
    slide to PDF using Aspose.Slides for Java – a full data visualization guide.
  headline: How to Rotate Pie Chart and Customize Colors in Java with Aspose.Slides
  type: TechArticle
- questions:
  - answer: Request a free trial from the Aspose website, then purchase a permanent
      license. Load it at runtime as shown in the Common Issues table.
    question: How do I obtain an Aspose.Slides license for Java?
  - answer: The API requires JDK 16 or higher; older versions are not supported.
    question: Can I use this code with older JDK versions?
  - answer: Yes—after rendering, call `chart.getChartData().getChartDataWorkbook().save("chart.png",
      ImageFormat.Png);`.
    question: Is it possible to export the chart as an image instead of PPTX?
  - answer: Pie charts are designed for a single data series; for multiple series,
      consider using a doughnut chart.
    question: What if I need more than one series in a pie chart?
  - answer: Absolutely—Aspose.Slides for Java is platform‑independent and works on
      any OS with a compatible JDK.
    question: Does Aspose.Slides run on Linux servers?
  type: FAQPage
tags:
- rotate pie chart
- Aspose.Slides
- Java charting
- data visualization
title: Hoe een taartdiagram te roteren en kleuren aan te passen in Java met Aspose.Slides
url: /nl/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Cirkeldiagrammen maken met Aspose.Slides voor Java: Een volledige tutorial

## Introductie
In deze gids leer je hoe je **cirkeldiagrammen** kunt roteren, elke partitie een eigen kleur kunt geven en de uiteindelijke dia naar PDF kunt exporteren — alles met Aspose.Slides voor Java. Of je nu een verkoopdashboard, een financieel rapport of een andere datagedreven presentatie maakt, met deze technieken lever je duidelijke, opvallende visuals zonder afhankelijk te zijn van Microsoft Office. Laten we de benodigde tools klaarzetten en aan de slag gaan.

## Snelle antwoorden
- **Welke klasse start een nieuwe presentatie?** `Presentation` uit `com.aspose.slides`.
- **Welke API‑aanroep voegt een cirkeldiagram toe?** `slide.addChart(ChartType.Pie, …)`.
- **Hoe kun je elke partitie een unieke kleur geven?** Roep `series.setColorVaried(true)` aan en stel solide vullingen in per datapunt.
- **Welke methode roteert het diagram?** `chart.setRotationAngle(double)` — gebruik graden van 0 tot 360.
- **Kan de dia geëxporteerd worden naar PDF?** Ja, roep `presentation.save("output.pdf", SaveFormat.Pdf)` aan.

## Wat betekent “cirkeldiagramkleuren aanpassen”?
Het aanpassen van cirkeldiagramkleuren houdt in dat je verschillende vulkleuren toewijst aan elke partitie van de cirkel, waardoor de leesbaarheid en visuele impact verbeteren. In Aspose.Slides bereik je dit door gevarieerde kleuren in te schakelen en vervolgens solide vulkleuren in te stellen voor individuele datapoints. Deze aanpak zorgt ervoor dat elk datasegment duidelijk opvalt in de presentatie.

## Waarom Aspose.Slides voor Java gebruiken om cirkeldiagrammen te maken?
Aspose.Slides ondersteunt **meer dan 150 diagramtypen** en kan een presentatie van 300 pagina’s renderen in minder dan **5 seconden** op een typische server, zonder dat Microsoft Office geïnstalleerd hoeft te zijn. De bibliotheek draait op Windows, Linux en macOS, waardoor je platform‑onafhankelijke flexibiliteit krijgt voor elk Java‑gebaseerd datavisualisatieproject.

## Vereisten
- **Aspose.Slides voor Java** ≥ 25.4
- **JDK** 16 of nieuwer
- IDE zoals IntelliJ IDEA, Eclipse of NetBeans
- Basiskennis van Java en vertrouwdheid met Maven of Gradle

## Aspose.Slides voor Java installeren
Voeg de bibliotheek toe aan je build‑configuratie.

**Maven**  
Voeg dit fragment toe aan je `pom.xml`‑bestand:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Neem het volgende op in je `build.gradle`‑bestand:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Directe download**  
Als je de handmatige aanpak verkiest, download dan de nieuwste JAR van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Stappen voor het verkrijgen van een licentie
- **Gratis proefversie** – verken alle functies zonder kosten.  
- **Tijdelijke licentie** – verleng de proeflimieten voor een korte periode.  
- **Aankoop** – verkrijg een permanente licentie voor productiegebruik.

**Basisinitialisatie en -instelling**  
De `Presentation`‑klasse vertegenwoordigt een PowerPoint‑bestand in het geheugen en biedt methoden om dia’s te manipuleren.  
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementatie‑gids
Hieronder vind je een stap‑voor‑stap walkthrough die alles behandelt, van het maken van een dia tot het roteren van het uiteindelijke cirkeldiagram.

### Presentatie en dia initialiseren
Maak een nieuw `Presentation`‑object aan en haal de eerste dia op om als canvas voor het diagram te dienen.  
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Cirkeldiagram aan dia toevoegen
`addChart` voegt een diagramvorm van het opgegeven type toe aan de dia op de gegeven coördinaten.  
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Diagramtitel instellen
`setTitle` kent een teksttitel toe aan het diagram en centreert deze.  
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Gegevenslabels voor serie configureren
`setShowValue(true)` schakelt numerieke waardelabels in voor elk datapunt van de serie.  
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Werkblad voor diagramgegevens voorbereiden
`ChartDataWorkbook` slaat de onderliggende datatabel op die de diagramseries en -categorieën voedt.  
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Categorieën aan diagram toevoegen
`addCategory` maakt een nieuw categorielabel aan voor de gegevensseries van het diagram.  
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Serie toevoegen en datapoints vullen
`addSeries` creëert een gegevensserie, en `addDataPointForBarSeries` voegt numerieke waarden toe voor elke categorie.  
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Kleuren en randen van serie aanpassen
`setColorVaried(true)` schakelt per‑partitie kleuren in, en `setFillFormat` wijst een solide vulling toe aan elk datapunt.  
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

### Aangepaste gegevenslabels configureren
`setDataLabelFormat` personaliseert het uiterlijk, de positie en het lettertype van labels voor duidelijkere diagramannotaties.  
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

### Rotatiehoek instellen en presentatie opslaan
`setRotationAngle` roteert het volledige cirkeldiagram, en `save` schrijft de presentatie naar een bestand.  
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Hoe roteer je een cirkeldiagram?
Laad het diagramobject, roep `chart.setRotationAngle(45.0)` (of een andere graadwaarde) aan en sla vervolgens de presentatie op. Het roteren van een cirkeldiagram verschuift de starthoek, waardoor je een bepaald segment kunt benadrukken zonder de gegevens te wijzigen. Deze enkele methode‑aanroep werkt voor elke `Chart`‑instantie in Aspose.Slides. Je kunt rotatie ook combineren met gevarieerde partitie‑kleuren om de belangrijkste datapunt extra onder de aandacht te brengen.

## Veelvoorkomende problemen en oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **Alle partities hebben dezelfde kleur** | `setColorVaried(true)` niet aangeroepen | Zorg ervoor dat je gevarieerde kleuren inschakelt op de serie‑groep. |
| **Gegevenslabels worden niet weergegeven** | `showValue`‑vlag uitgeschakeld | Roep `setShowValue(true)` aan op het label‑formaat. |
| **Rotatie heeft geen effect** | Een oudere versie van Aspose.Slides wordt gebruikt | Upgrade naar versie 25.4 of hoger. |
| **Licentie‑exception tijdens uitvoering** | Ontbrekend of ongeldig licentiebestand | Laad je licentie met `License license = new License(); license.setLicense("Aspose.Slides.lic");` vóór het aanmaken van de `Presentation`. |

## Veelgestelde vragen

**V: Hoe verkrijg ik een Aspose.Slides‑licentie voor Java?**  
A: Vraag een gratis proefversie aan via de Aspose‑website en koop vervolgens een permanente licentie. Laad deze tijdens runtime zoals weergegeven in de tabel “Veelvoorkomende problemen en oplossingen”.

**V: Kan ik deze code gebruiken met oudere JDK‑versies?**  
A: De API vereist JDK 16 of hoger; oudere versies worden niet ondersteund.

**V: Is het mogelijk om het diagram als afbeelding te exporteren in plaats van als PPTX?**  
A: Ja — na het renderen roep je `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` aan.

**V: Wat als ik meer dan één serie nodig heb in een cirkeldiagram?**  
A: Cirkeldiagrammen zijn bedoeld voor één enkele gegevensserie; voor meerdere series kun je beter een donut‑diagram gebruiken.

**V: Werkt Aspose.Slides op Linux‑servers?**  
A: Absoluut — Aspose.Slides voor Java is platform‑onafhankelijk en werkt op elk besturingssysteem met een compatibele JDK.

---

**Laatst bijgewerkt:** 2026-07-17  
**Getest met:** Aspose.Slides voor Java 25.4 (JDK 16)  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe cirkeldiagrammen te maken in Java‑presentaties met Aspose.Slides: Een uitgebreide gids](/slides/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/)
- [Beheers cirkeldiagrammen in Java met Aspose.Slides: Een uitgebreide gids](/slides/java/charts-graphs/master-pie-charts-aspose-slides-java/)
- [Diagramteksten roteren in Java met Aspose.Slides: Een uitgebreide gids](/slides/java/charts-graphs/rotate-chart-texts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}