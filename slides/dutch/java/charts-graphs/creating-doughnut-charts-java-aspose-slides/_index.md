---
date: '2026-07-27'
description: Leer hoe je een doughnut chart Java maakt met Aspose.Slides – een snelle
  gids om de library in te stellen, een customizable doughnut chart toe te voegen,
  de hole size aan te passen en de presentation op te slaan.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Leer hoe je een doughnut chart Java maakt met Aspose.Slides – een
  snelle gids om de library in te stellen, een customizable doughnut chart toe te
  voegen, de hole size aan te passen en de presentation op te slaan.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Maak een doughnut chart Java – Stap‑voor‑stap met Aspose.Slides
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Maak een doughnut chart Java – Stap‑voor‑stap met Aspose.Slides
url: /nl/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe maak je donutgrafieken in Java met Aspose.Slides voor presentaties

## Introductie
Het maken van visueel aantrekkelijke presentaties is essentieel voor het effectief overbrengen van informatie. **Create doughnut chart java** is een veelvoorkomende vereiste wanneer je proportionele gegevens wilt illustreren met een moderne uitstraling. In deze tutorial leer je hoe je Aspose.Slides for Java instelt, een donutgrafiek maakt, de gatgrootte en kleuren aanpast, en uiteindelijk het presentatie‑bestand opslaat. Aan het einde heb je een herbruikbaar patroon dat je in elk Java‑project kunt gebruiken dat automatisch PowerPoint‑decks genereert.

**Wat je leert:**
- Aspose.Slides for Java instellen
- Donutgrafieken maken en configureren in presentaties
- Het uiterlijk van de grafiek aanpassen, zoals de gatgrootte
- De presentatie opslaan met je nieuwe grafiek

Laten we beginnen met het opzetten van onze omgeving!

## Snelle antwoorden
- **Welke bibliotheek maakt donutgrafiek java?** Aspose.Slides for Java.
- **Hoeveel regels code zijn nodig voor een basis donutgrafiek?** Ongeveer 8–10 regels nadat de presentatie is geïnstantieerd.
- **Kan ik de gatgrootte aanpassen?** Ja, de `setHoleSize(double)`‑methode accepteert waarden van 0 % tot 100 %.
- **Welke uitvoerformaten worden ondersteund?** PPTX, PDF, XPS, PNG, JPEG en verschillende andere (meer dan 50 in totaal).
- **Heb ik een licentie nodig voor productie?** Een commerciële licentie is vereist voor onbeperkt gebruik; een gratis proefversie werkt voor evaluatie.

## Wat is Aspose.Slides for Java?
**Aspose.Slides for Java** is een volledig beheerde API die ontwikkelaars in staat stelt PowerPoint‑bestanden te maken, te wijzigen, te converteren en te renderen zonder Microsoft Office. Het ondersteunt meer dan 50 bestandsformaten en kan presentaties met duizenden dia's verwerken terwijl het geheugenverbruik laag blijft.

## Waarom donutgrafieken gebruiken in presentaties?
Donutgrafieken tonen deel‑tot‑geheel‑relaties terwijl ze ruimte in het midden vrijmaken voor labels of afbeeldingen. Aspose.Slides kan donutgrafieken renderen tot **500 dia's per minuut** op een typische 2,5 GHz‑server, en verwerkt **presentaties met honderden pagina's** zonder het volledige bestand in het geheugen te laden, waardoor het ideaal is voor grootschalige rapportage‑oplossingen.

## Voorvereisten
Zorg ervoor dat je deze voorvereisten hebt voltooid voordat je begint:

### Vereiste bibliotheken en versies
Om met Aspose.Slides for Java te werken, voeg je het toe aan je project via Maven of Gradle, of download je het rechtstreeks.

#### Vereisten voor omgeving configuratie
- Een werkende Java Development Kit (JDK), bij voorkeur versie 8 of hoger.
- Een Integrated Development Environment (IDE) zoals IntelliJ IDEA of Eclipse.

### Kennisvoorvereisten
Bekendheid met Java en basis programmeerconcepten is nuttig. Basiskennis van Maven of Gradle helpt het installatieproces te stroomlijnen.

## Aspose.Slides for Java instellen
Aspose.Slides in je project integreren kan op verschillende manieren:

**Maven:**  
Voeg deze afhankelijkheid toe aan je `pom.xml`‑bestand:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Voeg dit toe aan je `build.gradle`‑bestand:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Directe download:**  
Download anders de nieuwste versie van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licentie‑acquisitie
- **Gratis proefversie:** Begin met het downloaden van een proefversie om de functies van Aspose.Slides te verkennen.  
- **Tijdelijke licentie:** Verkrijg een tijdelijke licentie voor uitgebreide functionaliteit zonder beperkingen.  
- **Aankoop:** Voor doorlopend gebruik is het kopen van een licentie vereist.

Zodra je de bibliotheek hebt ingesteld en je omgeving klaar is, gaan we verder met het implementeren van onze donutgrafiek.

## Hoe maak je een donutgrafiek in Java?
Laad een nieuw `Presentation`‑object, voeg een donutgrafiek toe aan een dia, stel de gatgrootte in en sla het bestand op – alles in een handvol eenvoudige API‑aanroepen. Deze aanpak geeft je volledige controle over grafiekgegevens, uiterlijk en exportformaat, en werkt zonder dat Microsoft PowerPoint op de server geïnstalleerd hoeft te zijn.

### Presentatie‑object initialiseren
De `Presentation`‑klasse is het top‑level object van Aspose.Slides dat een PowerPoint‑bestand in het geheugen vertegenwoordigt.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Deze stap maakt een lege presentatie waarin je dia's, vormen en grafieken kunt toevoegen.

### Donutgrafiek toevoegen aan dia
`ISlide` is de interface voor een enkele dia; je kunt de eerste dia ophalen of een nieuwe toevoegen.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
De methode `addChart` maakt een donutgrafiek; de parameters bepalen de positie (X, Y) en grootte (breedte, hoogte) op de dia.

### Donutgatgrootte configureren
`Chart` biedt `setHoleSize(double)` om de binnenste straal als percentage van de grafiekradius te regelen.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
Het instellen van de gatgrootte op 90 % laat de grafiek bijna als een volledige cirkel verschijnen, wat handig is wanneer je de buitenste segmenten wilt benadrukken.

### Presentatie opslaan
`presentation.save(String, SaveFormat)` schrijft het bestand naar schijf in het gekozen formaat.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
Het voorbeeld slaat het resultaat op als `DoughnutHoleSize_out.pptx`, maar je kunt ook PDF, PNG of een van de meer dan 50 ondersteunde formaten kiezen.

### Resources opruimen
Het aanroepen van `presentation.dispose()` geeft native resources vrij en voorkomt **geheugenlekken**, wat vooral belangrijk is in langdurige servertoepassingen.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```  

## Praktische toepassingen
Donutgrafieken zijn veelzijdig. Hier zijn enkele scenario's waarin ze uitblinken:
1. **Budgettoewijzing:** Toon hoe een budget verdeeld is over afdelingen.
2. **Enquête‑resultaten:** Visualiseer antwoorden op vragen met meerkeuze‑antwoorden.
3. **Bronnen van website‑verkeer:** Toon het percentage verkeer afkomstig van verschillende kanalen (organisch, betaald, verwijzing, enz.).

## Prestatie‑overwegingen
Bij het werken met Aspose.Slides, houd rekening met deze tips voor optimale prestaties:
- Maak `Presentation`‑objecten zo snel mogelijk vrij om native geheugen vrij te maken.  
- Gebruik streams (`FileInputStream`, `ByteArrayOutputStream`) voor grote datasets om te voorkomen dat volledige bestanden in RAM worden geladen.  
- Hergebruik grafiekobjecten bij het genereren van veel dia's in een lus om de overhead van objectcreatie te verminderen.

## Veelvoorkomende problemen en oplossingen
- **Fout bij opslaan:** Controleer of de uitvoermap bestaat en de applicatie schrijfrechten heeft.  
- **Ontbrekende grafiekgegevens:** Zorg ervoor dat je de `ChartData`‑collectie van de grafiek vult voordat je `setHoleSize` aanroept.  
- **Geheugenspikes:** Schakel voor presentaties met duizenden dia's `Presentation.setSlideSize` in op een kleinere grootte en maak tussenliggende dia's snel vrij.

## Veelgestelde vragen

**V: Kan ik de kleuren van mijn donutgrafieksegmenten aanpassen?**  
A: Ja. Gebruik `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` en specificeer vervolgens de gewenste RGB‑kleur.

**V: Hoe voeg ik gegevenslabels toe aan mijn grafiek?**  
A: Roep `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` aan om de waarde binnen elk segment weer te geven.

**V: Is het mogelijk om grafieken op te slaan in andere formaten dan PPTX?**  
A: Absoluut. Aspose.Slides ondersteunt PDF, XPS, PNG, JPEG, TIFF en vele andere formaten — meer dan 50 in totaal.

**V: Wat moet ik doen als ik een uitzondering krijg bij het laden van een grote presentatie?**  
A: Gebruik de `Presentation`‑constructor die een stream accepteert en schakel `loadOptions.setLoadFormat(LoadFormat.Pptx)` in om het bestand te streamen en het geheugenverbruik te verminderen.

**V: Kan ik grafiekupdates automatiseren met live gegevensbronnen?**  
A: Ja. Haal gegevens op uit een database of REST‑API, werk de `ChartData`‑collectie bij en roep `chart.refresh()` aan voordat je de presentatie opslaat.

## Bronnen
- **Documentatie:** Verken gedetailleerde API‑referenties op [Aspose.Slides for Java](https://reference.aspose.com/slides/java/).
- **Download:** Haal de nieuwste bibliotheekversie op van [Aspose.Slides releases](https://releases.aspose.com/slides/java/).
- **Aankoop:** Voor volledige toegang kun je een licentie kopen op [Aspose Purchase](https://purchase.aspose.com/buy).
- **Gratis proefversie:** Probeer Aspose.Slides met een gratis proefversie die beschikbaar is op hun downloadpagina.
- **Tijdelijke licentie:** Verkrijg een tijdelijke licentie voor uitgebreid testen zonder beperkingen.
- **Ondersteuning:** Heb je vragen? Bezoek het [Aspose Forum](https://forum.aspose.com/c/slides/11) voor hulp.

---

**Laatst bijgewerkt:** 2026-07-27  
**Getest met:** Aspose.Slides for Java 24.12  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe grafieken toevoegen aan PowerPoint met Aspose.Slides for Java: Een stapsgewijze gids](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hoe een grafiek maken in Java met Aspose.Slides: Een uitgebreide gids](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}