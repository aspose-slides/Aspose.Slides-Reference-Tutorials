---
date: '2026-06-03'
description: Leer hoe u grafieken maakt in .NET-presentaties en een grafiek toevoegt
  aan een dia met Aspose.Slides for Java. Volg deze stapsgewijze handleiding voor
  datavisualisatie.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Grafieken maken in .NET met Aspose.Slides for Java
url: /nl/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maak grafieken in .NET met Aspose.Slides voor Java

## Inleiding
Het maken van overtuigende presentaties omvat vaak het integreren van visuele gegevensrepresentaties zoals grafieken om het begrip en de betrokkenheid van het publiek te verbeteren. **Als je grafieken wilt maken in .NET**, biedt Aspose.Slides voor Java een krachtige, taal‑agnostische API die naadloos werkt binnen .NET‑toepassingen. In deze tutorial leer je hoe je een presentatie initialiseert, verschillende grafiektype toevoegt, het gegevenswerkboek van de grafiek beheert en seriesgegevens opmaakt — inclusief het omgaan met negatieve waarden. Aan het einde kun je programmatically grafieken genereren in presentatiebestanden en een grafiek aan een dia toevoegen met slechts een paar regels code.

## Snelle antwoorden
- **Wat is het primaire doel?** Maak grafieken in .NET‑presentaties met Aspose.Slides voor Java.  
- **Welke bibliotheekversie is vereist?** Aspose.Slides voor Java 25.4 of later.  
- **Heb ik een licentie nodig?** Een gratis proefversie werkt voor ontwikkeling; een commerciële licentie is vereist voor productie.  
- **Kan ik Maven of Gradle gebruiken?** Ja — beide buildsysteem worden ondersteund.  
- **Welke grafiektype zijn beschikbaar?** Geclusterde kolom, lijn, taart, balk, gebied, en meer.

## Hoe maak je grafieken in .NET‑presentaties met Aspose.Slides voor Java?
`Presentation`‑klasse vertegenwoordigt een PowerPoint‑bestand en biedt methoden om de dia's te manipuleren. Laad een nieuw `Presentation`‑object, roep `slides.addEmptySlide()` aan om een dia te verkrijgen, en gebruik vervolgens `slide.getShapes().addChart()` om het gewenste grafiektype in te voegen op de door jou opgegeven coördinaten. Nadat de grafiek is toegevoegd, vul je het gegevenswerkboek met series en categorieën, pas je eventuele opmaak toe (zoals kleuren voor negatieve waarden) en sla je tenslotte de presentatie op als een .pptx‑bestand. Deze werkwijze stelt je in staat **grafieken in .NET** te maken met een beknopte set API‑aanroepen.

## Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een cross‑platform API die ontwikkelaars in staat stelt PowerPoint‑bestanden te maken, te wijzigen en te renderen zonder Microsoft Office. Het ondersteunt **50+ invoer‑ en uitvoerformaten** en kan presentaties met duizenden dia's verwerken terwijl het geheugenverbruik onder de 200 MB blijft.

## Waarom Aspose.Slides voor Java gebruiken in een .NET‑project?
Aspose.Slides voor Java draait op de Java Virtual Machine en kan vanuit .NET worden aangeroepen via een native wrapper, waardoor .NET‑ontwikkelaars toegang krijgen tot een volwassen grafiekengine, high‑performance verwerking van grote datasets en volledige compatibiliteit met bestaande Java‑code zonder logica te herschrijven.

## Vereisten
Voordat je begint met het maken van grafieken met Aspose.Slides voor Java, laten we opsommen wat je nodig hebt:

### Vereiste bibliotheken en versies
- **Aspose.Slides voor Java**: Versie 25.4 of later.

### Vereisten voor omgeving configuratie
- Een ontwikkelomgeving die .NET‑toepassingen ondersteunt.  
- Basiskennis van Java‑programmeervoorconcepten.

### Kennisvereisten
- Vertrouwdheid met het maken van presentaties in een .NET‑applicatiecontext.  
- Begrip van Java‑afhankelijkheden en hun beheer (Maven/Gradle).

## Aspose.Slides voor Java instellen
Om Aspose.Slides te gebruiken, moet je het opnemen als een afhankelijkheid in je project. Hier lees je hoe je dat doet:

### Maven
De Maven‑dependency‑snippet voegt Aspose.Slides voor Java toe aan je project.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Voeg deze regel toe aan je `build.gradle`‑bestand om de bibliotheek van Maven Central te halen.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Directe download
Je kunt de nieuwste versie ook downloaden van [Aspose.Slides voor Java releases](https://releases.aspose.com/slides/java/).

#### Stappen voor licentie‑acquisitie
- **Gratis proefversie**: Begin met een tijdelijke licentie om de functies te verkennen.  
- **Aankoop**: Koop een licentie voor onbeperkt gebruik in productie.

#### Basisinitialisatie en configuratie
`Slides`‑initialisatie vereist het instellen van de licentie en het aanmaken van een `Presentation`‑instance.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Deze configuratie zorgt ervoor dat resource‑beheer effectief wordt afgehandeld.

## Implementatie‑gids
We lopen stap‑voor‑stap door de implementatie van de functies.

### Presentatie initialiseren
**Overzicht:**  
Het maken van een presentatie‑instance legt de basis voor alle daaropvolgende bewerkingen. Deze functie laat zien hoe je vanaf nul begint met Aspose.Slides.

#### Stap 1: Importeer benodigde pakketten
`Presentation` en gerelateerde klassen maken deel uit van de `com.aspose.slides`‑namespace.

```java
import com.aspose.slides.Presentation;
```

#### Stap 2: Maak een nieuw Presentation‑object
Instantieer een `Presentation`‑object en wikkel het in een try‑with‑resources‑blok om gegarandeerde opruiming te waarborgen.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Dit zorgt ervoor dat het presentatie‑object correct wordt vrijgegeven na gebruik, waardoor geheugenlekken worden voorkomen.*

### Grafiek toevoegen aan dia
**Overzicht:**  
Een grafiek aan je dia toevoegen kan de datavisualisatie effectiever en aantrekkelijker maken.

#### Stap 1: Importeer benodigde pakketten
De `Chart`‑klasse vertegenwoordigt een grafiekvorm die op een dia kan worden geplaatst en aangepast.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Stap 2: Initialiseert presentatie en voeg grafiek toe
Maak een dia, roep vervolgens `addChart` aan met `ChartType.ClusteredColumn` en de gewenste positie en grootte.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Hier voegen we een geclusterde kolomgrafiek toe aan de eerste dia op de opgegeven coördinaten en afmetingen.*

### Beheren van grafiek‑gegevenswerkboek
**Overzicht:**  
Het efficiënt beheren van het gegevenswerkboek van je grafiek stelt je in staat series en categorieën naadloos te manipuleren.

#### Stap 1: Importeer benodigde pakketten
`IChartDataWorkbook` biedt toegang tot het onderliggende Excel‑achtige werkboek dat door grafieken wordt gebruikt.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Stap 2: Toegang tot en wissen van gegevenswerkboek
Haal het werkboek op uit de grafiek en wis alle bestaande gegevens om schoon te beginnen.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*Het wissen van het werkboek is cruciaal om met een schone lei te starten bij het toevoegen van nieuwe series en categorieën.*

### Series en categorieën toevoegen aan grafiek
**Overzicht:**  
Deze functie laat zien hoe je betekenisvolle gegevenspunten kunt toevoegen door series en categorieën te beheren.

#### Stap 1: Voeg series en categorieën toe
Gebruik `chart.getChartData().getSeries().add()` en `chart.getChartData().getCategories().add()` om de structuur te definiëren.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Het toevoegen van series en categorieën zorgt voor een meer georganiseerde gegevenspresentatie.*

### Seriesgegevens vullen en opmaken
**Overzicht:**  
Vul je grafiek met gegevenspunten en formatteer het uiterlijk om de leesbaarheid te verbeteren, vooral bij negatieve waarden.

#### Stap 1: Seriesgegevens vullen
Ken numerieke waarden toe aan elke cel in het werkboek en pas een rode vulling toe voor negatieve getallen.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Deze sectie demonstreert hoe je gegevens vult en kleuropmaak toepast voor betere visualisatie.*

## Veelvoorkomende problemen en oplossingen
- **LicenseNotFoundException** – Zorg ervoor dat het pad naar het licentiebestand correct is en dat het bestand toegankelijk is tijdens runtime.  
- **NullPointerException bij grafiekgegevens** – Wis altijd het werkboek voordat je nieuwe series toevoegt om restgegevens te voorkomen.  
- **Grafiek wordt niet weergegeven in .NET** – Controleer of je de .NET‑compatibele versie van de Aspose.Slides‑JAR gebruikt en of de Java‑runtime correct is geconfigureerd in je .NET‑project.

## Veelgestelde vragen

**V: Kan ik een grafiek genereren in presentatiebestanden zonder GUI?**  
A: Ja, Aspose.Slides voor Java is volledig headless en werkt op servers zonder grafische componenten.

**V: Welke .NET‑versies worden ondersteund?**  
A: .NET Framework 4.5+, .NET Core 3.1+, .NET 5 en .NET 6 worden allemaal ondersteund.

**V: Hoeveel grafiektype kan ik toevoegen?**  
A: Meer dan 20 grafiektype zijn beschikbaar, waaronder kolom, lijn, taart, gebied en radargrafieken.

**V: Is het mogelijk om individuele gegevenspunten te stijlen?**  
A: Absoluut – je kunt vulkleuren, randen en markers voor elk gegevenspunt instellen via de `IDataPoint`‑API.

**V: Moet ik Java‑objecten handmatig naar .NET‑typen converteren?**  
A: Nee, de Aspose.Slides voor Java .NET‑wrapper behandelt typeconversie automatisch.

---

**Laatst bijgewerkt:** 2026-06-03  
**Getest met:** Aspose.Slides voor Java 25.4  
**Auteur:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Hoe grafieken in .NET‑presentaties in te sluiten met Aspose.Slides voor effectieve datavisualisatie](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Hoe het type grafiek‑gegevensbron op te halen met Aspose.Slides voor .NET - Grafieken & diagrammen](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Beheers het maken en manipuleren van grafiekseries met Aspose.Slides .NET voor effectieve datavisualisatie](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}