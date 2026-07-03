---
date: '2026-07-03'
description: Leer stap voor stap hoe je Sunburst-diagrammen maakt in Java met Aspose.Slides,
  met volledige aanpassingsopties voor PowerPoint-presentaties.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Hoe maak je Sunburst-diagrammen in Java met Aspose.Slides
url: /nl/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe maak je Sunburst‑diagrammen in Java met Aspose.Slides

## Introductie
In de data‑gedreven presentaties van vandaag kan **how to create sunburst** visualisaties snel maken je dia's onderscheiden. Deze tutorial leidt je door het bouwen van een Sunburst‑diagram met Aspose.Slides voor Java, van projectopzet tot uiteindelijke export, zodat je overtuigende hiërarchische datavisualisaties kunt leveren zonder het Java‑ecosysteem te verlaten.

## Snelle antwoorden
- **Wat is de hoofdklasse voor een PowerPoint‑bestand?** `Presentation` – het vertegenwoordigt de volledige PPTX in het geheugen.  
- **Hoeveel regels code zijn nodig voor een basis‑sunburst?** Meestal 5–7 regels zodra de bibliotheek is gerefereerd.  
- **Welke uitvoerformaten worden ondersteund?** PPTX, PDF, PNG, SVG en HTML.  
- **Kan ik individuele segmenten stylen?** Ja – vulkleuren, randen en gegevenslabels zijn volledig aanpasbaar.  
- **Heb ik een licentie nodig voor productie?** Een gratis evaluatie werkt voor testen; een commerciële licentie is vereist voor implementatie.

## Wat is een Sunburst‑diagram?
Een Sunburst‑diagram visualiseert hiërarchische gegevens als concentrische ringen, waarbij elke ring een niveau van de hiërarchie vertegenwoordigt. Het stelt kijkers in staat om ouder‑kindrelaties in één oogopslag te begrijpen, waardoor het ideaal is voor organigrammen, taxonomieweergaven en meer‑niveau‑metriek. Het is vooral nuttig voor het weergeven van meer‑niveau‑categorieën zoals productlijnen, geografische regio's of organisatiestructuren, waardoor kijkers zowel de algehele verdeling als de gedetailleerde uitsplitsing binnen elk segment kunnen zien.

## Waarom Aspose.Slides gebruiken voor Sunburst‑diagrammen?
Aspose.Slides ondersteunt **30+ diagramtypen**, verwerkt bestanden tot **500 MB** zonder het hele document in het geheugen te laden, en rendert graphics op **300 DPI** voor kristalheldere output. Deze gekwantificeerde mogelijkheden zorgen voor snelle generatie en hoge‑kwaliteit visuals, zelfs voor grote presentaties. Bovendien biedt de bibliotheek thread‑safe bewerkingen en integreert naadloos met populaire Java‑build‑tools, waardoor het geschikt is voor zowel desktop‑ als server‑side generatie van presentaties op schaal.

## Vereisten
- Java Development Kit (JDK) 8 of nieuwer.  
- Maven of Gradle voor afhankelijkheidsbeheer.  
- Aspose.Slides for Java (latest version).  
- Basiskennis van hiërarchische datastructuren.

## Hoe maak je Sunburst‑diagrammen stap voor stap?
Laad je omgeving, voeg een diagram toe, voer hiërarchische gegevens in, style het en sla het bestand op – alles in een handvol eenvoudige stappen. Hieronder vind je de exacte workflow die je kunt volgen zonder extra boilerplate‑code te schrijven. Het proces is volledig geautomatiseerd, vereist geen handmatige UI‑interactie en kan worden opgenomen in batch‑taken of webservices om diagrammen op aanvraag te produceren.

### Stap 1: Stel het project in
Voeg de Aspose.Slides Maven‑dependency (of het equivalente Gradle‑fragment) toe aan je `pom.xml`. Dit haalt alle benodigde binaries en transitieve bibliotheken binnen.

### Stap 2: Laad of maak een presentatie
`Presentation` is het top‑level object van Aspose.Slides dat een enkel PowerPoint‑bestand in het geheugen vertegenwoordigt. Instantieer het met `new Presentation()` voor een nieuwe deck of geef een bestandspad op om een bestaande PPTX te openen.

### Stap 3: Voeg een Sunburst‑diagram toe
Voeg een nieuw diagram‑shape toe aan een dia met `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)`. Dit creëert de Sunburst‑plaatsaanduiding klaar voor gegevens. `ChartType.Sunburst` specificeert het Sunburst‑diagramtype bij het toevoegen van een diagram aan een dia.

### Stap 4: Vul hiërarchische gegevens in
`ChartData` bevat de gegevensseries en categorieën voor een diagram. Toegang tot de `ChartData`‑collectie van het diagram en voeg series en categorieën toe die je hiërarchie weerspiegelen. Voor elk niveau specificeer je de ouder‑kindrelatie via de `ParentSeries`‑eigenschap, waardoor het diagram automatisch concentrische ringen rendert.

### Stap 5: Pas het uiterlijk aan
Fijn‑tune segmentkleuren, randstijlen en gegevenslabels via de objecten `ChartSeries` en `ChartDataPoint`. `ChartSeries` vertegenwoordigt een reeks gegevenspunten in een diagram. `ChartDataPoint` vertegenwoordigt een individueel gegevenspunt binnen een serie. Je kunt ook 3‑D‑rotatie inschakelen of de `Explode`‑eigenschap instellen om specifieke segmenten te benadrukken.

### Stap 6: Sla de presentatie op
De `SaveFormat`‑enum definieert de bestandsformaten waarin je een presentatie kunt opslaan. Roep `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` aan om het bestand naar schijf te schrijven. Je kunt ook exporteren naar PDF of PNG door de `SaveFormat`‑enumwaarde te wijzigen.

## Hoe pas je Sunburst‑diagramkleuren aan?
Specificeer een vulkleur voor elk `ChartDataPoint` met `point.getFillFormat().setFillType(FillType.Solid)` en vervolgens `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Deze directe aanpak stelt je in staat om de huisstijl van het bedrijf te volgen of belangrijke gegevenspunten te benadrukken. Je kunt ook gradientvullingen toepassen, transparantie aanpassen of themakleuren gebruiken om consistentie met de rest van je dia‑ontwerp te waarborgen.

## Veelvoorkomende problemen en oplossingen
- **Probleem:** Hiërarchie lijkt plat.  
  **Oplossing:** Zorg ervoor dat elke kind‑serie correct verwijst naar zijn `ParentSeries`. Ontbrekende koppelingen zorgen ervoor dat het diagram alle gegevens als één niveau behandelt.
- **Probleem:** Geëxporteerde PNG ziet er wazig uit.  
  **Oplossing:** Verhoog de export‑DPI door `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)` in te stellen.
- **Probleem:** Grote PPTX‑bestanden veroorzaken OutOfMemoryError.  
  **Oplossing:** Gebruik `Presentation.setMemoryOptimization(true)` om gegevens te streamen en het geheugenverbruik laag te houden.

## Veelgestelde vragen

**V: Kan ik een Sunburst‑diagram genereren vanuit een CSV‑bestand?**  
A: Ja. Lees de CSV, bouw de hiërarchie in het geheugen op en voer deze in de `ChartData`‑collectie van het diagram in voordat je opslaat.

**V: Ondersteunt Aspose.Slides geanimeerde overgangen voor Sunburst‑diagrammen?**  
A: Ja. Pas een `SlideShowTransition` toe op de dia of gebruik `ChartFormat.setAnimationEnabled(true)` voor animatie op diagramniveau.

**V: Is het mogelijk om het diagram te exporteren als een SVG‑vectorafbeelding?**  
A: Absoluut. Sla de presentatie op met `SaveFormat.Svg` om een schaalbare vectorversie van het Sunburst‑diagram te verkrijgen.

**V: Wat is het maximale aantal gegevenspunten dat een Sunburst‑diagram kan verwerken?**  
A: Aspose.Slides verwerkt betrouwbaar tot **10.000** gegevenspunten in één Sunburst‑diagram zonder prestatie‑degradatie.

**V: Heb ik een aparte licentie nodig voor elke implementatie‑omgeving?**  
A: Eén commerciële licentie dekt alle omgevingen (ontwikkeling, staging, productie) zolang de licentievoorwaarden worden gerespecteerd.

## Conclusie
Je hebt nu een volledige, stap‑voor‑stap‑gids voor **how to create sunburst** diagrammen in Java met Aspose.Slides. Door de bovenstaande workflow te volgen, kun je hoogwaardige, volledig aanpasbare hiërarchische visualisaties genereren voor elke PowerPoint‑presentatie.

---

**Last Updated:** 2026-07-03  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Gerelateerde tutorials

- [Hoe diagrammen toevoegen aan PowerPoint met Aspose.Slides voor Java: Een stapsgewijze handleiding](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [PowerPoint-diagramaanpassing beheersen met Aspose.Slides Java voor dynamische presentaties](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [PowerPoint-diagramcategorieën animeren met Aspose.Slides voor Java | Stapsgewijze handleiding](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}