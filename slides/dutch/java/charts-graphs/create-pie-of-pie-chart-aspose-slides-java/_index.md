---
date: '2026-07-17'
description: Leer hoe u een grafiek aan PowerPoint kunt toevoegen door een Pie of
  Pie chart te maken met Aspose.Slides voor Java. Inclusief installatie, code, aanpassing
  en opslaan als PPTX.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Grafiek toevoegen aan PowerPoint met Aspose.Slides voor Java. Deze
  gids laat zien hoe u een Pie of Pie chart maakt, aanpast en binnen enkele minuten
  opslaat als PPTX.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Grafiek toevoegen aan PowerPoint – Maak een Pie of Pie Chart in Java
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Grafiek toevoegen aan PowerPoint – Maak een Pie of Pie Chart in Java met Aspose.Slides
url: /nl/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagram toevoegen aan PowerPoint – Maak een Pie of Pie-diagram in Java met Aspose.Slides

## Grafieken & Diagrammen

### Inleiding

In moderne data‑gedreven presentaties is **het toevoegen van een diagram aan PowerPoint** vaak de snelste manier om ruwe cijfers om te zetten in visueel inzicht. Een gewone taartdiagram werkt goed voor een handvol categorieën, maar wanneer enkele segmenten heel klein zijn, worden ze onleesbaar. Een *Pie of Pie*-diagram lost dit probleem op door die kleine segmenten te extraheren naar een secundaire taart, waardoor het hoofd‑diagram overzichtelijk blijft en de details toegankelijk zijn.

In deze tutorial leer je hoe je **een diagram aan PowerPoint kunt toevoegen** door een Pie of Pie-diagram te maken met Aspose.Slides voor Java. We doorlopen de installatie van de omgeving, het maken van diagrammen, het aanpassen van labels, het afstemmen van de split‑positie en tenslotte het opslaan van de presentatie als een PPTX‑bestand. Aan het einde ben je klaar om geavanceerde diagrammen in elke slide‑deck te integreren.

## Snelle antwoorden

In Aspose.Slides vertegenwoordigt `Presentation` een PPTX‑bestand, `ChartType.PieOfPie` selecteert het Pie of Pie‑diagram, `setShowValue(true)` toont waarden op labels, en `save` schrijft het bestand.

- **Wat is de primaire klasse voor PowerPoint-manipulatie?** `Presentation` – het vertegenwoordigt een volledig PPTX‑bestand in het geheugen.  
- **Welke diagramtype maakt een secundaire taart voor kleine segmenten?** `ChartType.PieOfPie`.  
- **Hoe toon je waarden op elk segment?** Stel `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)` in.  
- **Kun je het bestand direct opslaan als PPTX?** Ja – roep `presentation.save("output.pptx", SaveFormat.Pptx)` aan.  
- **Heb je een licentie nodig voor ontwikkeling?** Een gratis proefperiode van 30 dagen werkt voor testen; een permanente licentie verwijdert evaluatiewatermerken.

## Wat is een Pie of Pie-diagram?

Een **Pie of Pie-diagram** is een tweelaagse taartvisualisatie die een of meer kleine segmenten isoleert in een aparte, gekoppelde taart, waardoor ze makkelijker leesbaar zijn. Aspose.Slides ondersteunt dit diagramtype direct, waardoor je de split‑grootte, positie en labelopmaak kunt regelen.

## Waarom een diagram toevoegen aan PowerPoint met Aspose.Slides?

Aspose.Slides kan PowerPoint‑bestanden genereren, bewerken en renderen zonder dat Microsoft Office geïnstalleerd is. Het ondersteunt **meer dan 50 invoer‑ en uitvoerformaten**, verwerkt presentaties met **tot 500 dia's** in minder dan een seconde op typische serverhardware, en biedt **volledige API‑controle** over diagramstyling, datalabels en lay‑out — perfect voor geautomatiseerde rapportage‑pijplijnen.

## Vereisten

- **Java Development Kit (JDK) 16+** geïnstalleerd.  
- Een IDE zoals **IntelliJ IDEA**, **Eclipse** of **NetBeans**.  
- Maven of Gradle voor afhankelijkheidsbeheer (zie de secties hieronder).  
- Basiskennis van Java en vertrouwdheid met het bouwen van projecten.

## Aspose.Slides voor Java instellen

### Installatie‑informatie

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

**Direct Download:** Je kunt de nieuwste versie downloaden van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Stappen voor het verkrijgen van een licentie

- **Gratis proefversie:** Begin met een proefperiode van 30 dagen om alle functies te verkennen.  
- **Tijdelijke licentie:** Vraag een tijdelijke sleutel aan voor uitgebreide evaluatie.  
- **Aankoop:** Verkrijg een permanente licentie voor productiegebruik om evaluatiewatermerken te verwijderen.

### Basisinitialisatie en -configuratie

`Presentation` is het hoofdobject voor het maken van PowerPoint‑bestanden, en `Chart` vertegenwoordigt een diagramvorm binnen een dia.

```java
Presentation presentation = new Presentation();
```  

Dit maakt een lege presentatie klaar voor dia's en diagrammen.

## Implementatie‑gids

### Hoe voeg je een diagram toe aan PowerPoint met Aspose.Slides voor Java?

Laad een nieuwe `Presentation`, voeg een dia toe en voeg een `Chart` van het type `PieOfPie` in. De API‑aanroepketen is beknopt: maak het diagram, vul de seriedata in, pas de label‑zichtbaarheid aan, configureer de grootte van de secundaire taart, en sla tenslotte op. Het volledige proces past meestal in minder dan 20 regels code, waardoor het ideaal is voor geautomatiseerde rapportgeneratie.

### Een 'Pie of Pie'-diagram maken

#### Overzicht
We zullen een Pie of Pie-diagram op de eerste dia bouwen, de kleinste segmenten splitsen en elk segment labelen met zijn waarde.

#### Stap 1: Maak een instantie van de Presentation‑klasse
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Dit initialiseert de container voor alle volgende dia's en diagrammen.

#### Stap 2: Voeg een 'Pie of Pie'-diagram toe op de eerste dia
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Hier geven we `ChartType.PieOfPie` op en definiëren we de positie (X, Y) en grootte (breedte, hoogte) van het diagram op het dia‑canvas.

#### Stap 3: Stel datalabels in om waarden voor de serie weer te geven
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
Het inschakelen van `showValue` zorgt ervoor dat elk segment zijn numerieke waarde weergeeft, wat essentieel is voor snelle gegevensinterpretatie.

#### Stap 4: Configureer de grootte van de tweede taart en splits op percentage
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Deze opties laten je bepalen hoeveel van het diagram wordt toegewezen aan de secundaire taart en welke segmenten worden verplaatst op basis van een percentage‑drempel.

#### Stap 5: Sla de presentatie op schijf op in PPTX‑formaat
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Pro tip:** Gebruik een absoluut pad of Java’s `Paths.get()` om platform‑specifieke scheidingstekens te vermijden.

## Veelvoorkomende problemen en oplossingen

`License`-klasse laadt een licentiebestand om evaluatiebeperkingen te verwijderen.

- **Ontbrekende licentie‑waarschuwing:** Als je “Evaluation Only” op het diagram ziet, zorg er dan voor dat je een geldig licentiebestand hebt toegepast via `License license = new License(); license.setLicense("Aspose.Slides.lic");`.  
- **Onjuiste segment‑splitsing:** Controleer of de `splitBy`‑eigenschap is ingesteld op `SplitBy.Percentage` en dat `secondPieSize` een waarde tussen 0 en 100 is.  
- **Gegevens worden niet weergegeven:** Bevestig dat de serie van het diagram minstens één gegevenspunt bevat; anders wordt het diagram leeg weergegeven.

## Veelgestelde vragen

`IChart` vertegenwoordigt een diagramobject dat aan een dia kan worden toegevoegd.

**Q: Kan ik meerdere diagrammen genereren in één presentatie?**  
A: Ja, maak een nieuwe `IChart` aan voor elke dia of locatie; de API staat onbeperkt aantal diagramobjecten per bestand toe.

`SaveFormat.Pdf` specificeert het PDF‑uitvoerformaat voor opslaan.

**Q: Ondersteunt Aspose.Slides ook opslaan als PDF?**  
A: Absoluut – roep `presentation.save("output.pdf", SaveFormat.Pdf)` aan om dezelfde slide‑deck naar PDF te exporteren.

`IPortion` vertegenwoordigt een individueel segment van een taartdiagram.

**Q: Wat is het maximale aantal gegevenspunten dat een Pie of Pie-diagram kan verwerken?**  
A: De bibliotheek ondersteunt tot **10.000** gegevenspunten per serie, alleen beperkt door het beschikbare geheugen.

**Q: Is het mogelijk om de kleuren van individuele segmenten aan te passen?**  
A: Ja, krijg elk `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()` en stel `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))` in.

**Q: Hoe embed ik de gegenereerde PPTX in een webapplicatie?**  
A: Na het opslaan van het bestand, stream je het direct naar de client met `HttpServletResponse` en `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.

## Conclusie

Je hebt nu een complete, productie‑klare handleiding voor **het toevoegen van een diagram aan PowerPoint** door een Pie of Pie-diagram te maken met Aspose.Slides voor Java. Experimenteer met verschillende split‑drempels, label‑formaten en kleurschema's om aan je merkrichtlijnen te voldoen. Verken vervolgens andere diagramtypen — zoals gestapelde staaf- of radardiagrammen — om je geautomatiseerde slide‑decks verder te verrijken.

---

**Laatst bijgewerkt:** 2026-07-17  
**Getest met:** Aspose.Slides for Java 24.12  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Dynamisch diagram maken Java – PowerPoint‑diagrammen tutorials voor Aspose.Slides](/slides/java/charts-graphs/)
- [Hoe een taartdiagram toevoegen aan PowerPoint met Aspose.Slides voor Java](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Hoe diagrammen toevoegen aan PowerPoint met Aspose.Slides voor Java: Een stapsgewijze gids](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}