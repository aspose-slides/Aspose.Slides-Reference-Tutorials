---
date: '2026-03-20'
description: Leer hoe je een grafiek kunt toevoegen aan Java‑presentaties met Aspose.Slides
  en snel presentatiediagrambestanden genereert.
keywords:
- Java Presentations with Aspose.Slides
- Create Charts in Java
- Configure Presentation Data
title: Hoe een grafiek toe te voegen aan Java‑presentaties met Aspose.Slides
url: /nl/java/charts-graphs/create-java-presentations-charts-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe een grafiek toe te voegen aan een presentatie met Aspose.Slides voor Java

## Introductie

Het maken van dynamische presentaties die data effectief overbrengen, is essentieel in de hedendaagse, snelle zakelijke omgeving. Of je nu een financieel rapport, een marketing‑deck of een projectstatus‑update voorbereidt, **weten hoe je een grafiek** aan je dia's kunt toevoegen, kan de betrokkenheid van het publiek aanzienlijk verbeteren. In deze tutorial leer je stap‑voor‑stap hoe je een 3D gestapelde kolomgrafiek toevoegt, de gegevens configureert en het uiteindelijke bestand opslaat — alles met Aspose.Slides voor Java.

### Snelle antwoorden
- **Wat is de primaire bibliotheek?** Aspose.Slides for Java  
- **Welk grafiektype wordt gedemonstreerd?** 3D gestapelde kolom  
- **Kan ik presentatie‑grafiekbestanden programmatisch genereren?** Ja, met de hieronder getoonde API‑methoden  
- **Welke Java‑versie wordt aanbevolen?** JDK 16 of later  
- **Heb ik een licentie nodig voor productie?** Een geldige Aspose.Slides‑licentie is vereist voor commercieel gebruik  

## Wat is “how to add chart” in Aspose.Slides?

Aspose.Slides for Java biedt een uitgebreide set objecten waarmee je PowerPoint‑bestanden kunt maken, bewerken en exporteren zonder Microsoft Office. Een grafiek toevoegen is zo simpel als het maken van een `Presentation`‑object, een grafiekvorm invoegen en de gegevens via de ingebouwde werkmap voeden.

## Waarom grafiek toevoegen aan Java‑presentaties?

- **Visuele impact:** Grafieken veranderen ruwe cijfers in direct begrijpelijke visuals.  
- **Automatisering:** Genereer rapporten on‑the‑fly — ideaal voor geplande e‑mail‑samenvattingen of dashboards.  
- **Consistentie:** Gebruik dezelfde styling en branding in alle gegenereerde decks.  
- **Portabiliteit:** Exporteer naar PPTX, PDF of afbeeldingen met één methode‑aanroep.

## Vereisten

- **Bibliotheken en afhankelijkheden:** Aspose.Slides for Java moet geïnstalleerd zijn.  
- **Omgevingsinstelling:** Werk in een Java‑omgeving (JDK 16 of later aanbevolen).  
- **Kennisbasis:** Basiskennis van Java‑programmeren is nuttig.

## Aspose.Slides voor Java instellen

### Installatie

Om Aspose.Slides in je project te integreren, volg je een van de onderstaande opties.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**: Download anders de nieuwste versie van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licentie‑acquisitie
- **Gratis proefversie:** Begin met een gratis proefversie om de functionaliteit te verkennen.  
- **Tijdelijke licentie:** Verkrijg een tijdelijke licentie voor uitgebreid testen.  
- **Aankoop:** Schaf een volledige licentie aan voor commercieel gebruik.

Zodra geïnstalleerd, kun je de `Presentation`‑klasse instantieren, die dient als toegangspunt voor alle grafiekgerelateerde bewerkingen.

## Implementatie‑gids

### Hoe een grafiek toe te voegen aan een presentatie met een 3D gestapelde kolom

#### Overzicht
Een presentatie vanaf nul maken is eenvoudig met Aspose.Slides. In deze sectie voegen we een 3D gestapelde kolomgrafiek toe aan de eerste dia van onze presentatie.

**Stappen:**

1. **Initialiseer Presentation‑object**

   ```java
   import com.aspose.slides.*;

   public class ChartPresentation {
       public static void main(String[] args) {
           // Initialize a new Presentation object
           Presentation presentation = new Presentation();
           
           // Access the first slide in the presentation
           ISlide slide = presentation.getSlides().get_Item(0);
           
           // Add a 3D stacked column chart to the slide at position (0,0)
           IChart chart = slide.getShapes().addChart(
               ChartType.StackedColumn3D, 0, 0, 500, 500
           );
           
           configureChartData(chart);
           setRotation3D(chart);
           populateSeriesData(chart);
           setSeriesOverlap(chart);
           savePresentation(presentation);
       }
   }
   ```

2. **Leg parameters uit**  
   - `ChartType.StackedColumn3D`: specificeert het grafiektype.  
   - Positie en grootte `(0, 0, 500, 500)`: bepaalt waar de grafiek op de dia verschijnt.

### Grafiekgegevens configureren

#### Overzicht
Om je grafiek betekenisvol te maken, configureer je de gegevensreeksen en categorieën. Deze sectie laat zien hoe je specifieke gegevenspunten aan je grafiek toevoegt.

**Stappen:**

1. **Toegang tot de gegevenswerkmap van de grafiek**

   ```java
   public static void configureChartData(IChart chart) {
       // Set the index of the worksheet that contains chart data
       int defaultWorksheetIndex = 0;
       
       // Access the chart's data workbook
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       // Add two series with names
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), 
           chart.getType()
       );
       chart.getChartData().getSeries().add(
           fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), 
           chart.getType()
       );
       
       // Add three categories
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
       chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));
   }
   ```

### Rotatie‑3D‑eigenschappen voor grafiek instellen

#### Overzicht
Verbeter de visuele aantrekkingskracht van je grafiek met 3D‑rotatie‑eigenschappen. Deze aanpassing stelt je in staat het perspectief en de diepte aan te passen.

**Stappen:**

1. **Configureer 3D‑rotaties**

   ```java
   public static void setRotation3D(IChart chart) {
       // Enable right angle axes and configure rotations in X, Y directions, and depth percent
       chart.getRotation3D().setRightAngleAxes(true);
       chart.getRotation3D().setRotationX((byte) 40);
       chart.getRotation3D().setRotationY(270);
       chart.getRotation3D().setDepthPercents(150);
   }
   ```

2. **Leg parameters uit**  
   - `setRightAngleAxes(true)`: Zorgt ervoor dat de assen loodrecht staan.  
   - Rotatiewaarden: Pas de hoek en diepte van de 3D‑weergave aan.

### Reeksgegevens in grafiek vullen

#### Overzicht
Het vullen van je grafiek met gegevenspunten is cruciaal voor analyse. Hier voegen we specifieke waarden toe aan een reeks binnen onze grafiek.

**Stappen:**

1. **Gegevenspunten toevoegen**

   ```java
   public static void populateSeriesData(IChart chart) {
       // Access the second chart series
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       // Add data points for bar series with specified values
       int defaultWorksheetIndex = 0;
       IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
       
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 2, 30));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 2, 10));
       series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 2, 60));
   }
   ```

### Reeks‑overlap in grafiek aanpassen

#### Overzicht
Fijn afstellen van het uiterlijk van je grafiek kan de leesbaarheid verbeteren. Deze sectie behandelt hoe je de overlap‑eigenschap aanpast voor betere datavisualisatie.

**Stappen:**

1. **Stel reeks‑overlap in**

   ```java
   public static void setSeriesOverlap(IChart chart) {
       // Get the second series from the chart and set its overlap to 100
       IChartSeries series = chart.getChartData().getSeries().get_Item(1);
       
       series.getParentSeriesGroup().setOverlap((byte) 100);
   }
   ```

### Presentatie opslaan

#### Overzicht
Zodra je presentatie is geconfigureerd, sla je deze op schijf op in het gewenste formaat. Deze stap zorgt ervoor dat alle wijzigingen worden bewaard.

**Stappen:**

1. **Sla de presentatie op**

   ```java
   public static void savePresentation(Presentation presentation) {
       // Save the modified presentation to a file
       String outputFilePath = "output_presentation.pptx";
       presentation.save(outputFilePath, SaveFormat.Pptx);
   }
   ```

## Veelvoorkomende problemen en oplossingen

| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **Grafiek verschijnt plat** | 3D‑rotatie niet ingesteld | Roep `setRotation3D` aan met geschikte X/Y‑waarden. |
| **Gegevens worden niet weergegeven** | Werkmapcellen niet gekoppeld | Zorg ervoor dat `fact.getCell` naar de juiste rij‑/kolom‑indices verwijst. |
| **Bestand niet opgeslagen** | Onjuist pad of ontbrekende rechten | Controleer of `outputFilePath` schrijfbaar is en de map bestaat. |

## Veelgestelde vragen

**Q: Kan ik presentatie‑grafiekbestanden genereren in andere formaten dan PPTX?**  
A: Ja, Aspose.Slides ondersteunt PDF, ODP en afbeeldingsformaten via de `SaveFormat`‑enum.

**Q: Heb ik een licentie nodig om de code in ontwikkeling uit te voeren?**  
A: Een tijdelijke of evaluatielicentie werkt voor ontwikkeling, maar een volledige licentie is vereist voor productie‑implementaties.

**Q: Is het mogelijk om meerdere grafieken aan dezelfde dia toe te voegen?**  
A: Absoluut. Roep `slide.getShapes().addChart` meerdere keren aan met verschillende posities of groottes.

**Q: Hoe wijzig ik het kleurenpalet van de grafiek?**  
A: Gebruik `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` en stel een `SolidFillColor` in.

**Q: Kan ik de grafiek koppelen aan een externe gegevensbron, zoals een database?**  
A: Ja. Haal data op met JDBC en vul vervolgens de werkmapcellen programmatisch voordat je opslaat.

## Conclusie

Je hebt nu geleerd **hoe je een grafiek** aan een Java‑presentatie toevoegt, de gegevens configureert, 3D‑rotatie aanpast, reeks‑overlap instelt en het uiteindelijke bestand opslaat. Deze kennis stelt je in staat rapportgeneratie te automatiseren, consistente branding te creëren en data‑gedreven presentaties te leveren zonder handmatig werk. Voor diepere aanpassingen — zoals het stylen van legenda’s, assen of het toepassen van thema’s — verken je de volledige mogelijkheden in de officiële documentatie.

Voor meer geavanceerde functies en aanpassingsopties, raadpleeg de [Aspose.Slides for Java documentation](https://docs.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Laatst bijgewerkt:** 2026-03-20  
**Getest met:** Aspose.Slides for Java 25.4 (JDK 16)  
**Auteur:** Aspose