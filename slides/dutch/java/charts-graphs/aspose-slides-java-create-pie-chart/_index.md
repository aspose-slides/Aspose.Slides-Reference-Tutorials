---
date: '2026-07-08'
description: Leer hoe u taartdiagrammen aan PowerPoint‑presentaties kunt toevoegen
  met Aspose.Slides for Java. Volg deze stapsgewijze handleiding om professionele
  taartdiagrammen te maken en aan te passen.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Voeg een taartdiagram toe aan PowerPoint met Aspose.Slides for Java.
  Deze tutorial laat zien hoe u taartdiagrammen programmeerbaar kunt genereren en
  aanpassen, perfect voor geautomatiseerde rapporten.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Taartdiagram PowerPoint toevoegen met Aspose.Slides for Java – Snelle gids
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Hoe een taartdiagram toe te voegen aan PowerPoint met Aspose.Slides for Java
url: /nl/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Voeg taartdiagram PowerPoint toe met Aspose.Slides voor Java

## Introductie

Als je **taartdiagram PowerPoint**‑dia's wilt toevoegen zonder PowerPoint handmatig te openen, ben je hier op de juiste plek. In deze gids lopen we door het instellen van Aspose.Slides voor Java, het maken van een taartdiagram en het aanpassen van elke slice — perfect voor geautomatiseerde rapportage, dashboards of gepersonaliseerde presentaties. Aan het einde heb je een herbruikbare Java‑snippet die in enkele seconden een gepolijste taartdiagram PowerPoint‑bestand genereert.

### Snelle antwoorden
- **Welke bibliotheek maakt het diagram?** Aspose.Slides voor Java (nieuwste release).  
- **Kan ik het head‑less uitvoeren?** Ja — geen Office‑installatie vereist.  
- **Welke Java‑versie is optimaal?** JDK 16+ voor beste prestaties en GC‑verbeteringen.  
- **Hoe explodeer ik een segment?** Roep `setExplosion` aan op de `IDataPoint` en stel een pixel‑offset in.  
- **Heb ik een licentie nodig voor productie?** Een proefversie werkt voor ontwikkeling; een permanente licentie verwijdert alle evaluatielimieten.

## Waarom taartdiagram PowerPoint toevoegen met Aspose.Slides voor Java?

Je kunt up‑to‑date visuele rapporten direct vanuit je back‑end services genereren, waardoor handmatige copy‑paste‑fouten worden geëlimineerd en een merk‑consistent uiterlijk wordt gegarandeerd. Aspose.Slides ondersteunt **70+ diagramtypen** en kan presentaties met **10.000+ dia's** verwerken zonder het volledige bestand in het geheugen te laden, waardoor het ideaal is voor grootschalige automatisering.

## Vereisten

- **Aspose.Slides voor Java** — de tutorial verwijst naar versie 25.4 (de nieuwste op het moment van schrijven).  
- **Java Development Kit** — JDK 16 of nieuwer wordt aanbevolen.  
- **Maven** of **Gradle** voor afhankelijkheidsbeheer.  

## Aspose.Slides voor Java instellen

### Maven
Voeg deze afhankelijkheid toe aan uw `pom.xml`‑bestand:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Voeg het volgende toe aan uw `build.gradle`‑bestand:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Download de nieuwste versie rechtstreeks van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licenties
Om Aspose.Slides zonder beperkingen te gebruiken:

- Begin met een **gratis proefversie** om de API te evalueren.  
- Vraag een **tijdelijke licentie** aan voor uitgebreid testen op de [Temporary License](https://purchase.aspose.com/temporary-license/) pagina.  
- Koop een volledige abonnement via de [Purchase page](https://purchase.aspose.com/buy).

## Hoe taartdiagram PowerPoint toe te voegen met Aspose.Slides voor Java

Laad een nieuwe presentatie, voeg een taartdiagram in en sla het bestand op — alles in drie beknopte stappen. Dit patroon werkt voor elke grootte dataset en kan in een lus worden gewikkeld om tientallen dia's automatisch te genereren. De aanpak is lichtgewicht, vereist slechts een paar regels code en geen externe bronnen, waardoor hij geschikt is voor zowel kleine hulpprogramma's als grote batch‑taken.

### Stap 1: Initialiseer de presentatie
De `Presentation`‑klasse vertegenwoordigt een enkel PowerPoint‑bestand in het geheugen. Een instantie maken geeft je een frisse, lege dia‑set om mee te werken.
```java
Presentation pres = new Presentation();
```

### Stap 2: Voeg het taartdiagram toe
Voeg een taartdiagram toe aan de eerste dia. De coördinaten (50, 50) en grootte (600 × 400) passen in een standaard 16:9‑lay‑out en laten ruimte voor titels.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### Stap 3: Sla de presentatie op
Schrijf de presentatie naar schijf. Vervang `YOUR_OUTPUT_DIRECTORY` door de map waarin je het bestand wilt opslaan.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### Stap 4: Ruim bronnen op
Dispose van het `Presentation`‑object om native bronnen vrij te geven en geheugenlekken te voorkomen.
```java
if (pres != null) pres.dispose();
```

## Hoe gegevenspuntexplosie en kleur aanpassen?

Laad het diagram, lokaliseer het doel‑gegevenspunt en pas vervolgens een explosie‑offset en een solide vulkleur toe. Dit laat de slice opvallen voor nadruk. Deze aanpassingen helpen de aandacht van het publiek te trekken naar kritieke waarden en verbeteren de algehele leesbaarheid van het diagram.

### Stap 1: Laad een bestaande presentatie (of hergebruik de zojuist gemaakte)
Het `Presentation`‑object laadt een bestaand PowerPoint‑bestand in het geheugen, zodat je de inhoud kunt wijzigen.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### Stap 2: Toegang tot het diagram en het doelgegevenspunt
De `IDataPoint`‑interface vertegenwoordigt een individueel gegevenspunt (slice) binnen een diagramreeks.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### Stap 3: Pas explosie en kleur toe
`setExplosion(int)` stelt de afstand in, in pixels, waarmee een slice van het diagramcentrum wordt verschoven. Scheid de slice visueel met `setExplosion(20)` en wijzig de vulkleur naar blauw met `setFillType(FillType.Solid)` en `setSolidFillColor(Color.BLUE)`.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### Stap 4: Opslaan en vrijgeven
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Praktische toepassingen
- **Verkooprapporten:** Markeer best verkopende producten met geëxplodeerde slices.  
- **Budgetanalyse:** Wijs verschillende kleuren toe aan afdelingen voor snelle visuele vergelijking.  
- **Educatieve dia's:** Deel complexe concepten op in verteerbare diagramsegmenten.  

## Prestaties overwegingen
- **Dispose‑objecten** direct om geheugenlekken te voorkomen, vooral bij het genereren van veel dia's in een lus.  
- **Monitor heap‑gebruik** voor grote presentaties; gebruik de `Save`‑overload die een `OutputStream` accepteert om data te streamen en de geheugenvoetafdruk laag te houden.  
- Houd je aan **JDK 16+** om te profiteren van de nieuwste garbage‑collection‑verbeteringen, die de verwerkingstijd tot 30 % kunnen verminderen voor 1.000‑dia‑decks.

## Conclusie
Je hebt nu een volledige, productie‑klare workflow om **taartdiagram PowerPoint**‑bestanden te maken met Aspose.Slides voor Java. Experimenteer met verschillende explosie‑afstanden, kleuren en datasets om je branding te matchen. Wanneer je klaar bent, verken dan andere diagramtypen — staaf, lijn of spreiding — om een volledige analytics‑dashboard in PowerPoint te bouwen.

## Veelgestelde vragen

**Q: Wat is het grootste voordeel van het gebruik van Aspose.Slides voor Java?**  
A: Het stelt je in staat om PowerPoint‑bestanden programmatisch te maken, bewerken en renderen zonder Microsoft Office geïnstalleerd te hebben, met ondersteuning voor meer dan 70 diagramtypen en 100 + bestandsformaten.

**Q: Kan ik een PowerPoint‑bestand vanaf nul genereren?**  
A: Ja, instantiateer een `Presentation`‑object, voeg dia's, diagrammen of vormen toe, en roep `save` aan — alles in pure Java‑code.

**Q: Hoe explodeer ik een specifiek taartsegment?**  
A: Haal de `IDataPoint` voor het segment op en roep `setExplosion(pixelOffset)` aan. De offset bepaalt hoe ver het segment naar buiten beweegt.

**Q: Is er een limiet aan het aantal dia's dat ik kan maken?**  
A: Aspose.Slides kan presentaties met tot **10.000 dia's** in één bestand verwerken, mits je de output streamt om te voorkomen dat alles in het geheugen wordt geladen.

**Q: Waar kan ik meer geavanceerde diagram‑aanpassingsvoorbeelden vinden?**  
A: Bekijk de officiële [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) voor gedetailleerde API‑referenties en voorbeeldprojecten.

## Bronnen
- **Documentatie:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Last Updated:** 2026-07-08  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create and Validate Chart Layouts in PowerPoint Using Aspose.Slides for Java | SEO-Optimized Guide](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}