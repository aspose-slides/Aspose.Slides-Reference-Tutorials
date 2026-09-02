---
date: '2026-09-02'
description: Leer hoe u een trechterdiagram in PowerPoint maakt met behulp van Aspose.Slides
  for Java. Deze stapsgewijze handleiding behandelt het instellen van grafiekgegevens,
  het aanpassen van kleuren en het exporteren van de presentatie.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Leer hoe u een trechterdiagram in PowerPoint maakt met Aspose.Slides
  for Java. Deze handleiding leidt u door het configureren van gegevens, het aanpassen
  van kleuren en het exporteren van de uiteindelijke presentatie.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Maak een trechterdiagram in PowerPoint met Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Maak een trechterdiagram in PowerPoint met Aspose.Slides for Java
url: /nl/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Beheersen van het maken van trechterdiagrammen in PowerPoint met Aspose.Slides voor Java

## Inleiding
Het creëren van overtuigende presentaties is een kunst die datavisualisatie, design en storytelling combineert. Eén krachtig visueel element dat een meerfasenproces direct verduidelijkt, is de trechterdiagram (funnel chart). Of je nu een sales‑pipeline, een conversiestroom of een productie‑knelpunt moet illustreren, een goed ontworpen trechterdiagram zet ruwe cijfers om in een intuïtief verhaal. In deze tutorial leer je hoe je **funnel chart maken** in PowerPoint programmeermatig met Aspose.Slides voor Java, de gegevens configureert, elke segmentkleur aanpast en de voltooide presentatie exporteert.

**Wat je zult leren**
- Hoe Aspose.Slides for Java toe te voegen aan een Maven‑ of Gradle‑project  
- Hoe een `Presentation`‑object te instantieren en toegang te krijgen tot de dia's  
- Hoe een funnel chart in te voegen, categorieën te definiëren en seriedata te vullen  
- Hoe elk segment van de funnel te stylen met effen vullingen of merkspecifieke kleuren  
- Hoe de presentatie op te slaan als een PPTX‑bestand of een dia te exporteren als afbeelding  

## Snelle antwoorden
- **Wat is de primaire bibliotheek voor java‑datavisualisatie?** Aspose.Slides for Java.  
- **Hoe maak je een funnel chart in PowerPoint?** Roep `slide.addChart(ChartType.Funnel, …)` aan op de doel‑dia.  
- **Welke API stelt de gegevensbron van het diagram in?** Gebruik `IChartDataWorkbook` samen met `chart.getChartData()`.  
- **Kun je kleuren aanpassen voor elk funnel‑segment?** Ja—stel `FillFormat.setFillType(FillType.Solid)` in en wijs een `java.awt.Color` toe.  
- **Heb je een licentie nodig voor productiegebruik?** Een aangeschafte Aspose.Slides‑licentie is vereist voor commerciële implementaties.

## Wat is Java‑datavisualisatie?
Java‑datavisualisatie is de praktijk van het omzetten van ruwe data in diagrammen, grafieken of interactieve graphics rechtstreeks vanuit Java‑applicaties. Aspose.Slides for Java is een toonaangevende bibliotheek die ontwikkelaars in staat stelt meer dan 100 diagramtypen te genereren — inclusief trechterdiagrammen — zonder PowerPoint handmatig te starten, en ondersteunt presentaties met tot 500 dia's terwijl het geheugenverbruik laag blijft.

## Waarom funnel‑diagrammen gebruiken in PowerPoint?
Trechterdiagrammen onthullen direct uitvalpercentages over opeenvolgende fasen, waardoor ze ideaal zijn voor sales‑pipelines, conversie‑analyse of proces‑efficiëntie‑reviews. Aspose.Slides geeft je pixel‑perfecte controle over lay‑out, segmentkleuren en gegevenslabels, zodat je merkconsistentie kunt behouden en handmatige bewerking van diagrammen in de PowerPoint‑UI kunt vermijden.

## Voorvereisten

### Vereiste bibliotheken, versies en afhankelijkheden
Om Aspose.Slides for Java in je project te implementeren, voeg je de juiste Maven‑ of Gradle‑coördinaten toe. De bibliotheek werkt met Java 8‑21 en vereist geen externe native afhankelijkheden.

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

Je kunt de JAR ook direct downloaden van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Omgevingsvereisten
Zorg ervoor dat je JDK 8 of hoger geïnstalleerd hebt en dat je `JAVA_HOME` naar de juiste JDK‑directory wijst. Aspose.Slides draait op elk OS dat de JDK ondersteunt, inclusief Windows, macOS en Linux.

### Kennisvoorvereisten
Basiskennis van Java‑syntaxis, object‑georiënteerd programmeren en het concept van een presentatie‑bestand helpt, maar de code‑fragmenten worden volledig uitgelegd voor ontwikkelaars van elk ervaringsniveau.

## Instellen van Aspose.Slides voor Java

1. **Voeg de afhankelijkheid toe** – Gebruik de Maven‑ of Gradle‑snippet hierboven.  
2. **Verkrijg een licentie** –  
   - **Gratis proefversie** – Download een tijdelijke licentie van [Aspose's website](https://purchase.aspose.com/temporary-license/) voor evaluatie.  
   - **Volledige licentie** – Koop een productielicentie via de [purchase page](https://purchase.aspose.com/buy).  
3. **Basisinitialisatie** –  

`Presentation` is de kernklasse van Aspose.Slides die een PowerPoint‑bestand in het geheugen representeert. Het biedt toegang tot dia's, vormen en diagramobjecten.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

De bovenstaande code maakt een nieuw `Presentation`‑instance, klaar voor dia‑manipulatie, en zorgt ervoor dat bronnen worden vrijgegeven met `dispose()`.

## Implementatie‑gids

We lopen elke functie door die nodig is om een volledig trechterdiagram te bouwen, met korte verklarende tekst vóór elke code‑placeholder.

### Functie 1: een presentatie maken

#### Overzicht
Begin met het maken van een instantie van de `Presentation`‑klasse. Dit object is het startpunt voor alle volgende bewerkingen.

`Presentation` is het top‑level object van Aspose.Slides dat de dia‑collectie en globale documentinstellingen bevat.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

Het fragment opent een lege presentatie, die je later kunt opslaan als een `.pptx`‑bestand.

### Functie 2: een funnel chart toevoegen aan een dia

#### Overzicht
Voeg een trechterdiagram toe op de eerste dia, definieer de grootte en stel het diagramtype in.

`ChartType.Funnel` vertelt Aspose.Slides om een trechter‑stijl visualisatie te renderen in plaats van een balk‑ of lijndiagram.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

De `addChart`‑aanroep maakt de diagramvorm, positioneert deze op `(50, 50)` punten en geeft een breedte van `500` en hoogte van `400`.

### Functie 3: diagramgegevens wissen

#### Overzicht
Voordat je het diagram vult, wis je eventuele placeholder‑categorieën of -reeksen die de sjabloon bevat.

`chart.getChartData().getCategories().clear()` verwijdert alle bestaande categorie‑items, terwijl `chart.getChartData().getSeries().clear()` eventuele vooraf ingevulde reeksen verwijdert.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Dit zorgt voor een schone lei zodat jouw aangepaste gegevens precies verschijnen zoals bedoeld.

### Functie 4: werkmap voor diagramgegevens instellen

#### Overzicht
Het `IChartDataWorkbook`‑object slaat de ruwe waarden op die het diagram aandrijven. Initialisatie maakt het mogelijk om direct gegevens in cellen te schrijven.

`IChartDataWorkbook` is een lichte in‑memory spreadsheet die Aspose.Slides gebruikt om diagramreeksen en -categorieën te voeden.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

De code wist eventuele bestaande cellen en bereidt de werkmap voor op nieuwe invoer.

### Functie 5: categorieën toevoegen aan een diagram

#### Overzicht
Definieer de tekstlabels die aan de linkerkant van de trechter verschijnen — deze vertegenwoordigen elke fase van je proces.

`chart.getChartData().getCategories().add()` maakt een nieuw categorie‑object aan dat gekoppeld is aan een specifieke werkmapcel.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Hier voegen we drie fasen toe: “Prospects”, “Qualified Leads” en “Closed Deals”.

### Functie 6: gegevensreeksen toevoegen aan een diagram

#### Overzicht
Vul de trechter met numerieke waarden en wijs eventueel een unieke kleur toe aan elk segment.

`IDataPoint` representeert een enkel gegevenspunt binnen een diagramreeks.  

`chart.getChartData().getSeries().add()` maakt een reeks aan die de numerieke gegevenspunten bevat; elke `IDataPoint` kan een eigen vulkleur krijgen.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

De lus toont hoe je een effen vulkleur instelt voor elk punt, met behulp van merkspecifieke `java.awt.Color`‑constanten of willekeurig gegenereerde kleuren voor visuele variatie.

## Veelvoorkomende use‑cases & tips

- **Rapportage van sales‑pipeline** – Toon hoeveel leads van prospect naar gesloten‑gewonnen gaan in elke fase.  
- **Analyse van procesefficiëntie** – Visualiseer materiaalverlies of tijdvertragingen over productiestappen.  
- **Marketing‑funnel review** – Vergelijk conversieratio's over campagnes of verkeersbronnen.  

**Pro tip:** Gebruik in plaats van willekeurige kleuren het merkschema van je bedrijf (bijv. `new Color(0, 112, 192)`) om de presentatie consistent te houden met andere marketing‑assets.

## Veelgestelde vragen

**V: Hoe wijzig ik de oriëntatie van de funnel chart?**  
A: Stel de `ChartOrientation`‑eigenschap in op het `IChart`‑object op `ChartOrientation.Vertical` of `ChartOrientation.Horizontal`.

**V: Kan ik de dia exporteren als afbeelding na het toevoegen van het diagram?**  
A: Ja—roep `pres.getSlides().get_Item(0).getThumbnail(1, 1)` aan en schrijf de resulterende `java.awt.image.BufferedImage` naar een PNG‑ of JPEG‑bestand.

**V: Wat als ik meer dan drie categorieën nodig heb?**  
A: Voeg eenvoudig extra categorieën toe met `chart.getChartData().getCategories().add(...)` en lever bijpassende gegevenspunten voor elke nieuwe categorie.

**V: Is er een manier om de legenda te verbergen?**  
A: Gebruik `chart.getChartTitle().setVisible(false)` en `chart.getLegend().setVisible(false)` om zowel de titel als de legenda uit de visualisatie te verwijderen.

**V: Heb ik een licentie nodig voor ontwikkel‑builds?**  
A: Een tijdelijke licentie is voldoende voor evaluatie; een volledige commerciële licentie is vereist voor productie‑implementaties.

---

**Last updated:** 2026-09-02  
**Getest met:** Aspose.Slides for Java 25.4 (jdk16)  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe een diagram toe te voegen aan PowerPoint met Aspose.Slides voor Java: Een stapsgewijze gids](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hoe PowerPoint‑diagramgegevens te bewerken met Aspose.Slides voor Java: Een uitgebreide gids](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Animatie toevoegen aan PowerPoint‑diagram met Aspose.Slides voor Java – Een stapsgewijze gids](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}