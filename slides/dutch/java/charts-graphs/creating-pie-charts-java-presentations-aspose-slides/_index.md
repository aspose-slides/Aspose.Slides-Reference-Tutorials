---
date: '2026-08-01'
description: Leer hoe u een Aspose Slides license gebruikt om Pie Charts te maken
  en aan te passen in Java-presentaties. Volg stap‑voor‑stap instructies om pie chart
  data te configureren en chart slides efficiënt toe te voegen.
keywords:
- aspose slides license
- configure pie chart data
- create pie chart java
- add pie chart slides
- add chart slide
lastmod: '2026-08-01'
og_description: Leer hoe u een Aspose Slides license gebruikt om Pie Charts te maken
  en aan te passen in Java-presentaties. Volg stap‑voor‑stap instructies om pie chart
  data te configureren en chart slides efficiënt toe te voegen.
og_image_alt: 'Guide: Create pie charts in Java using Aspose Slides license'
og_title: Maak Pie Charts in Java met een Aspose Slides license
schemas:
- author: Aspose
  dateModified: '2026-08-01'
  description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  headline: Create Pie Charts in Java with an Aspose Slides License
  type: TechArticle
- description: Learn how to use an Aspose Slides license to create and customize pie
    charts in Java presentations. Follow step‑by‑step instructions to configure pie
    chart data and add chart slides efficiently.
  name: Create Pie Charts in Java with an Aspose Slides License
  steps:
  - name: Initialize Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a PowerPoint
      file in memory. Creating an instance gives you a blank slide deck ready for
      modification. This line creates a new presentation where all subsequent changes
      will be applied.'
  - name: Add Pie Chart to Slide
    text: '`Chart` is the class that encapsulates chart objects, including pie charts.
      Adding a chart to a slide is a single method call that specifies position and
      size. - `xPosition` and `yPosition` set the chart’s top‑left corner. - `width`
      and `height` define the chart’s visual footprint on the slide.'
  - name: Configure Pie Chart Data
    text: '`ChartData` holds the data series for a chart. **How do I configure pie
      chart data?** Provide a concise answer first: Use the `ChartData` collection
      to add a series, then populate `ChartDataPoint` objects with numeric values
      and category names. This approach lets you display up to 10 000 slices whil'
  - name: Save the Presentation
    text: Finally, persist the presentation to a file format of your choice (PPTX,
      PDF, or PNG). The `save` method respects the active license, ensuring no trial
      watermarks appear.
  type: HowTo
- questions:
  - answer: Call `slide.getShapes().addChart()` for each chart, providing unique coordinates
      and dimensions for each instance.
    question: How do I add multiple charts to a single slide?
  - answer: Apache POI and JFreeChart are common alternatives, but they lack the comprehensive
      export options and licensing model of Aspose.
    question: What are some alternatives to Aspose.Slides for Java?
  - answer: Yes—export to PDF, XPS, HTML, PNG, JPEG, SVG, and more with a single `save`
      call.
    question: Can I convert my presentation into other formats using Aspose.Slides?
  - answer: Purchase an enterprise license that covers multiple developers and servers;
      contact Aspose sales for volume discounts.
    question: How do I handle licensing for a large development team?
  - answer: Integrate Aspose.Slides with a data source (e.g., a SQL query) and rebuild
      the chart at runtime; the API supports dynamic data binding.
    question: What if my chart data updates frequently?
  type: FAQPage
tags:
- aspose slides
- pie chart java
- java presentation library
- data visualization
title: Maak Pie Charts in Java met een Aspose Slides license
url: /nl/java/charts-graphs/creating-pie-charts-java-presentations-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe maak je taartdiagrammen in Java‑presentaties met Aspose.Slides

## Inleiding

Als je professionele presentaties wilt maken, **een Aspose Slides‑licentie** geeft je de mogelijkheid om grafieken programmatically te genereren en op te maken. In deze gids leer je hoe je een taartdiagram maakt, de gegevens configureert en het in een Java‑slide‑deck embedt — zonder Microsoft PowerPoint te gebruiken. We lopen de installatie, de code‑stroom en best‑practice‑tips door zodat je binnen enkele minuten gepolijste visuele rapporten kunt leveren.

**Wat je zult leren:**
- Aspose.Slides voor Java instellen met een geldige licentie
- Stappen om een taartdiagram te maken en aan te passen
- Hoe taartdiagramgegevens te configureren en diagram‑slides toe te voegen
- Veelvoorkomende valkuilen en prestatie‑trucs

Laten we beginnen met bevestigen dat je omgeving klaar is.

## Snelle antwoorden
- **Wat maakt de Aspose Slides‑licentie mogelijk?** Volledig uitgeruste grafiekcreatie, export naar PDF/HTML, en verwijdering van watermerken.
- **Welke Java‑versie is vereist?** JDK 16 of hoger.
- **Heb ik Maven of Gradle nodig?** Beide werken; de bibliotheek is via beide beschikbaar.
- **Hoeveel gegevenspunten kan een taartdiagram bevatten?** Tot 10 000 punten zonder geheugenproblemen.
- **Kan ik de slide exporteren als afbeelding?** Ja – PNG, JPEG, SVG en meer worden ondersteund.

## Voorwaarden

Controleer vóór je begint dat je het volgende hebt:
- **Vereiste bibliotheken:** Aspose.Slides for Java (versie 25.4 of later) – deze versie ondersteunt de nieuwste bestandsformaten en prestatie‑optimalisaties.
- **Omgevingsinstelling:** JDK 16+ geïnstalleerd en geconfigureerd in je IDE of buildsysteem.
- **Basiskennis:** Vertrouwdheid met Java, Maven of Gradle, en object‑georiënteerde programmeerconcepten.

## Aspose.Slides voor Java instellen

Om Aspose.Slides voor Java te gebruiken, voeg je het toe aan je project. Hieronder zie je hoe je de afhankelijkheid toevoegt met de meest gebruikte build‑tools:

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

**Directe download:** Je kunt ook de nieuwste JAR downloaden van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licentie‑acquisitie

Aspose biedt een gratis proefversie die alle functies ontgrendelt, maar een **geldige Aspose Slides‑licentie** is vereist voor productiegebruik om evaluatiewatermerken te verwijderen en prestatievoordelen te behalen. Aankoopopties staan op de [purchase page](https://purchase.aspose.com/buy). Na het verkrijgen van het licentiebestand, laad je het één keer bij het opstarten van de applicatie:

`License` laadt en past je Aspose.Slides‑licentie toe.  
```java
// Initialize a new Presentation instance
demo.Presentation pres = new demo.Presentation();
```  

## Implementatie‑gids

### Maak en voeg een taartdiagram toe aan de presentatie

#### Overzicht
Deze sectie legt uit hoe je een taartdiagram maakt, de gegevensreeks configureert en het diagram in een slide embedt. Je ziet de volledige stroom van het initialiseren van het presentatie‑object tot het opslaan van het uiteindelijke bestand.

#### Stap 1: Presentatie initialiseren  
`Presentation` is het top‑level object van Aspose.Slides dat een PowerPoint‑bestand in het geheugen vertegenwoordigt. Het maken van een instantie geeft je een lege slide‑deck klaar voor bewerking.

```java
demo.Presentation pres = new demo.Presentation();
```  
Deze regel maakt een nieuwe presentatie waarin alle volgende wijzigingen worden toegepast.

#### Stap 2: Taartdiagram toevoegen aan slide  
`Chart` is de klasse die diagramobjecten omvat, inclusief taartdiagrammen. Een diagram aan een slide toevoegen is een enkele methode‑aanroep die positie en grootte specificeert.

```java
// Define position and size for the pie chart
int xPosition = 50;
int yPosition = 50;
int width = 400;
int height = 600;

demo.IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    demo.ChartType.Pie, xPosition, yPosition, width, height, false);
```  
- `xPosition` en `yPosition` stellen de linkerbovenhoek van het diagram in.  
- `width` en `height` definiëren de visuele afmeting van het diagram op de slide.

#### Stap 3: Taartdiagramgegevens configureren  
`ChartData` bevat de gegevensreeks voor een diagram.  
**Hoe configureer ik taartdiagramgegevens?**  
Geef eerst een beknopt antwoord: Gebruik de `ChartData`‑collectie om een reeks toe te voegen, en vul vervolgens `ChartDataPoint`‑objecten met numerieke waarden en categorienamen. Deze aanpak stelt je in staat tot 10 000 segmenten weer te geven terwijl de labelopmaak behouden blijft. Na het instellen van de gegevens kun je kleuren, legenda’s en datalabels aanpassen aan de huisstijl van je organisatie.

Hier is de code die twee categorieën toevoegt en hun labels weergeeft:

```java
// Accessing the default data series for demonstration
demo.IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Add new series and populate with data
demo.IChartSeries series = chart.getChartData().getSeries().add(wb.getCell(0, "B1", "Category 1"), demo.ChartType.Pie);
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B2", 30));
series.getDataPoints().addDataPointForPieSeries(wb.getCell(0, "B3", 70));

// Customize series labels
for (demo.IDataPoint point : series.getDataPoints()) {
    demo.IChartDataLabel label = point.getLabel();
    label.getDataLabelFormat().setShowCategoryName(true);
}
```  
De snippet maakt een gegevensreeks, voegt twee punten in en schakelt categorielabels in op het diagram.

#### Stap 4: Presentatie opslaan  
Sla tenslotte de presentatie op in een bestandsformaat naar keuze (PPTX, PDF of PNG). De `save`‑methode houdt rekening met de actieve licentie, zodat er geen proef‑watermerken verschijnen.

```java
presentation.save("PieChartDemo.pptx", SaveFormat.Pptx);
```

### Veelvoorkomende problemen en oplossingen
- **Fout: ontbrekende licentie:** Zorg ervoor dat het pad naar het licentiebestand correct is en dat het `License`‑object wordt geïnstantieerd vóór enige Aspose.Slides‑aanroepen.
- **Leeg diagram:** Controleer of de `ChartData`‑reeks minstens één `ChartDataPoint` bevat. Een lege reeks resulteert in een blanco diagramgebied.
- **Prestatie‑vertraging bij grote datasets:** Gebruik `presentation.getSlides().removeAt(index)` om ongebruikte slides te verwijderen en roep `System.gc()` aan na intensieve verwerking.

## Praktische toepassingen
1. **Bedrijfsrapporten:** Visualiseer marktaandeel of omzetverdeling over regio's met één taartdiagram.
2. **Academische presentaties:** Toon enquête‑resultaten of experimentele uitkomsten in een duidelijk, verteerbaar formaat.
3. **Projectdashboards:** Geef taakvoltooiingspercentages of resource‑allocatie direct weer op een slide.

Je kunt Aspose.Slides ook combineren met JDBC om live gegevens uit een database te halen, waardoor up‑to‑date diagrammen voor wekelijkse management‑briefings worden gegenereerd.

## Prestatie‑overwegingen
Bij het omgaan met presentaties die veel high‑resolution afbeeldingen of grote datasets bevatten:
- Maak objecten direct vrij met `try‑with‑resources` of expliciete `dispose()`‑aanroepen.
- Schakel lazy loading van slide‑resources in om het geheugenverbruik laag te houden.
- Voor batchverwerking, hergebruik een enkele `Presentation`‑instantie waar mogelijk om JVM‑overhead te verminderen.

## Conclusie
Je hebt nu een volledige, productie‑klare workflow voor het maken van taartdiagrammen in Java met een **Aspose Slides‑licentie**. Experimenteer met extra diagramtypen — staaf, lijn of donut — om je slides verder te verrijken. Verken vervolgens de exportmogelijkheden van de API om automatisch PDF‑rapporten of PNG‑afbeeldingen te genereren.

## Veelgestelde vragen

**V: Hoe voeg ik meerdere diagrammen toe aan één slide?**  
A: Roep `slide.getShapes().addChart()` aan voor elk diagram, met unieke coördinaten en afmetingen voor elke instantie.

**V: Wat zijn enkele alternatieven voor Aspose.Slides voor Java?**  
A: Apache POI en JFreeChart zijn gangbare alternatieven, maar ze missen de uitgebreide exportopties en het licentiemodel van Aspose.

**V: Kan ik mijn presentatie omzetten naar andere formaten met Aspose.Slides?**  
A: Ja — exporteer naar PDF, XPS, HTML, PNG, JPEG, SVG en meer met één `save`‑aanroep.

**V: Hoe ga ik om met licenties voor een groot ontwikkelingsteam?**  
A: Schaf een enterprise‑licentie aan die meerdere ontwikkelaars en servers dekt; neem contact op met de verkoop van Aspose voor volumekortingen.

**V: Wat als mijn diagramgegevens vaak worden bijgewerkt?**  
A: Integreer Aspose.Slides met een gegevensbron (bijv. een SQL‑query) en bouw het diagram opnieuw op tijdens runtime; de API ondersteunt dynamische databinding.

## Bronnen
- **Documentatie:** [Aspose.Slides Java Reference](https://reference.aspose.com/slides/java/)
- **Download:** [Latest Releases](https://releases.aspose.com/slides/java/)
- **Aankoop:** [Buy a License](https://purchase.aspose.com/buy)
- **Gratis proefversie:** [Try Aspose.Slides Free](https://releases.aspose.com/slides/java/)
- **Tijdelijke licentie:** [Obtain Temporary License](https://purchase.aspose.com/temporary-license/)
- **Ondersteuning:** [Aspose Forum](https://forum.aspose.com/c/slides/11)

---

**Laatst bijgewerkt:** 2026-08-01  
**Getest met:** Aspose.Slides for Java 25.4  
**Auteur:** Aspose

## Gerelateerde tutorials

- [Hoe diagrammen toe te voegen en te configureren in presentaties met Aspose.Slides voor Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Diagrammen maken en aanpassen in Java‑presentaties met Aspose.Slides](/slides/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/)
- [Hoe presentaties te maken en configureren met Aspose.Slides Java: een stapsgewijze gids](/slides/java/getting-started/create-configure-presentation-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}