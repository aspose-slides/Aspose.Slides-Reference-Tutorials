---
date: '2026-07-17'
description: Leer hoe u Sunburst charts kunt toevoegen in PowerPoint met behulp van
  Aspose Slides for Java. Step‑by‑step guide behandelt setup, chart creation, customization,
  en real‑world use cases.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Hoe Sunburst charts toe te voegen in PowerPoint met Aspose Slides
  for Java. Volg deze tutorial om de library in te stellen, een chart te maken, data
  points aan te passen en toe te passen in real projects.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Hoe Sunburst charts toe te voegen in PowerPoint met Aspose (Java)
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Hoe Sunburst charts toe te voegen in PowerPoint met Aspose (Java)
url: /nl/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe Sunburst-diagrammen toe te voegen aan PowerPoint met Aspose (Java)

## Inleiding

Het toevoegen van een sunburst-diagram aan een PowerPoint-presentatie kan een platte datatabel direct omvormen tot een boeiende visuele hiërarchie. In deze tutorial leer je **hoe je sunburst**-diagrammen toevoegt in PowerPoint met Aspose.Slides voor Java, van het opzetten van de omgeving tot het fijn afstellen van kleuren en labels. Of je nu een verkoopdashboard, een project‑taakstructuur of een educatieve slide‑deck bouwt, de onderstaande stappen bieden een productieklare oplossing.

**Wat je zult leren**
- Hoe Aspose.Slides te configureren in een Maven- of Gradle‑project  
- Hoe een nieuwe presentatie te maken en een sunburst‑diagram in te voegen  
- Hoe gegevenspunten, labels en vulkleuren aan te passen  
- Praktijkvoorbeelden waarin sunburst‑diagrammen uitblinken  

Laten we beginnen en zien hoe eenvoudig het is om ruwe hiërarchische gegevens om te zetten in een gepolijste PowerPoint‑visualisatie.

## Snelle antwoorden
- **Primaire bibliotheek?** Aspose.Slides for Java  
- **Ondersteund grafiektype?** Sunburst (radiale hiërarchische)  
- **Minimale Java‑versie?** JDK 16  
- **Typische implementatietijd?** 10‑15 minuten voor een basisdiagram  
- **Licentie nodig voor productie?** Ja, een geldige Aspose‑licentie  

## Wat is een Sunburst-diagram?
Een sunburst-diagram is een radiaal diagram dat hiërarchische gegevens visualiseert door ringen van een centraal punt naar buiten te nestelen. Het is perfect voor het tonen van meer‑lagige relaties zoals organisatiestructuren, productcategorieën of bestandssysteem‑bomen. Elke concentrische ring vertegenwoordigt een niveau van de hiërarchie, en de grootte van elk segment weerspiegelt de kwantitatieve waarde, waardoor kijkers snel zowel de structuur als de omvang begrijpen.

## Waarom Aspose.Slides voor Java gebruiken?
Aspose.Slides ondersteunt **50+ grafiektype** en kan presentaties manipuleren met **tot 10.000 dia's** zonder het volledige bestand in het geheugen te laden, wat hoge prestaties levert voor rapportage op ondernemingsniveau. Het werkt cross‑platform, biedt uitgebreide API‑dekking en bevat robuuste licentieopties die evaluatielimieten verwijderen, waardoor het ideaal is voor productieomgevingen.

## Vereisten
- **Java Development Kit (JDK)** 16 of hoger  
- **IDE** – IntelliJ IDEA, Eclipse, of een andere Java‑compatibele editor  
- Basiskennis van Java‑syntaxis en Maven/Gradle‑build‑tools  

## Aspose.Slides voor Java instellen

### Maven‑afhankelijkheid
Voeg het Aspose.Slides Maven‑artefact toe aan je `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑afhankelijkheid
Als je Gradle verkiest, voeg dan de volgende regel toe in `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Directe download
Je kunt de nieuwste JAR ook direct downloaden vanaf de officiële releases‑pagina: [Aspose.Slides voor Java releases](https://releases.aspose.com/slides/java/).

### Licentie‑verwerving
Om zonder evaluatielimieten te werken, verkrijg een licentie:
- **Gratis proefversie** – tijdelijke licentie voor snelle evaluatie.  
- **Tijdelijke licentie** – vraag er een aan via de [Aspose‑website](https://purchase.aspose.com/temporary-license).  
- **Volledige aankoop** – koop een abonnement voor onbeperkt productiegebruik.

### Basisinitialisatie
De `Presentation`‑klasse is het toegangspunt voor het maken of openen van PowerPoint‑bestanden.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Implementatie‑gids

### Hoe een sunburst-diagram toe te voegen aan een PowerPoint‑presentatie met Aspose.Slides voor Java?
Laad een nieuwe `Presentation`, voeg een dia toe, voeg een `IChart` van het type `ChartType.Sunburst` in, en roep `save` aan. Dit beknopte drie‑stappenpatroon creëert een volledig functioneel sunburst‑diagram dat klaar is voor verdere aanpassing.

#### Stap 1: De presentatie initialiseren
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### Stap 2: Sunburst‑diagram toevoegen
De `IChart`‑interface definieert een grafiekobject dat op elke dia kan worden geplaatst. Hier voegen we een sunburst‑diagram toe op coördinaten (100, 100) met een grootte van 450 × 400 punten.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### Stap 3: De presentatie opslaan
Bewaar altijd je wijzigingen door `save` aan te roepen. Je kunt kiezen voor PPTX, PDF of een van de 50+ ondersteunde uitvoerformaten.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Gegevenspunten in diagram aanpassen

#### Overzicht
Je kunt elke slice van de sunburst—labels, kleuren en zichtbaarheid—aanpassen via de gegevenspuntcollectie van het diagram.

#### Stap 1: Toegang tot gegevenspuntcollectie
De eerste serie van het diagram bevat een collectie van `IChartDataPoint`‑objecten die elke slice vertegenwoordigen.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### Stap 2: Waarde tonen voor een specifiek gegevenspunt
Stel `IsValueShown` in op `true` voor het gewenste gegevenspunt om de numerieke waarde direct op de slice weer te geven.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### Stap 3: Labelopmaak aanpassen
Pas de zichtbaarheid van labels, de letterkleur en de achtergrond aan om de leesbaarheid te verbeteren.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### Stap 4: Vulkleur instellen voor gegevenspunten
Pas de vulkleur van individuele slices aan om overeen te komen met je merkpalet of om belangrijke segmenten te benadrukken.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### Stap 5: De aangepaste presentatie opslaan
Sla het aangepaste diagram op door de presentatie opnieuw op te slaan.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Praktische toepassingen

1. **Business Analytics** – Visualiseer verkoop per regio → productlijn → SKU in één radiale weergave.  
2. **Project Management** – Toon werkonderverdelingsstructuren, van fasen naar taken naar subtaken.  
3. **Education** – Breng curricula‑hiërarchieën in kaart, zoals afdelingen → cursussen → modules.  

## Prestatie‑overwegingen

- **Geheugenefficiëntie:** Aspose.Slides streamt data, zodat zelfs een deck van 500 pagina’s met meerdere diagrammen onder de 200 MB RAM blijft.  
- **Garbage Collection:** Maak dia‑objecten (`slide.dispose()`) vrij wanneer ze niet meer nodig zijn om geheugenlekken te voorkomen.  

## Veelgestelde vragen

**Q: Wat is een sunburst-diagram?**  
A: Een sunburst-diagram visualiseert hiërarchische gegevens in concentrische ringen, waarbij elke ring een niveau van de hiërarchie vertegenwoordigt.

**Q: Hoe installeer ik Aspose.Slides voor Java met Maven?**  
A: Voeg de Maven‑afhankelijkheid toe die wordt getoond in de sectie “Maven Dependency” aan je `pom.xml` en voer `mvn clean install` uit.

**Q: Kan ik andere grafiektype aanpassen met Aspose.Slides?**  
A: Ja, de bibliotheek ondersteunt meer dan 50 grafiektype, waaronder kolom‑, lijn‑, taart‑ en radardiagrammen.

**Q: Mijn presentatie wordt niet opgeslagen—wat moet ik controleren?**  
A: Controleer of het bestandspad correct is, de map bestaat en je schrijfrechten hebt. Zorg er ook voor dat de `Presentation.save()`‑methode wordt aangeroepen.

**Q: Waar kan ik meer hulp of voorbeelden vinden?**  
A: Bezoek het [Aspose‑forum](https://forum.aspose.com/c/slides/11) of raadpleeg de officiële [Aspose.Slides‑referentie](https://reference.aspose.com/slides/java/).

## Bronnen
- **Documentatie:** [Aspose.Slides-referentie](https://reference.aspose.com/slides/java/)  
- **Referentie (kleine letters):** [Aspose.Slides referentie](https://reference.aspose.com/slides/java/)  
- **Community‑forum:** [Aspose‑forum](https://forum.aspose.com/c/slides)  
- **Downloads:** [Aspose.Slides‑downloads](https://releases.aspose.com/slides/java)  

---

**Laatst bijgewerkt:** 2026-07-17  
**Getest met:** Aspose.Slides for Java 24.12  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe diagrammen toe te voegen aan PowerPoint met Aspose.Slides voor Java: Een stapsgewijze handleiding](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Diagrammen animeren in PowerPoint met Aspose.Slides voor Java – Een stapsgewijze handleiding](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Diagram maken in Java met Aspose.Slides – Diagrammen toevoegen en valideren](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}