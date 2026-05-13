---
date: '2026-02-19'
description: Leer hoe je een cirkeldiagram maakt in Java met Aspose.Slides en de kleuren
  van het cirkeldiagram aanpast, diagramreeksen toevoegt, werkt met het gegevenswerkblad
  van het diagram en de rotatiehoek instelt.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Hoe je taartdiagramkleuren aanpast in Java met Aspose.Slides – Een volledige
  gids
url: /nl/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

 "**Getest met:**"

"**Author:**" => "**Auteur:**"

Then closing shortcodes.

Also ensure we keep any bold formatting.

Now produce final content with all translations.

Let's construct final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maak taartdiagrammen met Aspose.Slides voor Java: Een volledige tutorial

## Introductie
Het creëren van dynamische en visueel aantrekkelijke presentaties is cruciaal voor het overbrengen van impactvolle informatie. Met Aspose.Slides voor Java kun je naadloos complexe diagrammen zoals taartdiagrammen in je dia's integreren, **customize pie chart colors**, en moeiteloos de datavisualisatie verbeteren. Deze uitgebreide gids leidt je stap voor stap door het proces van het maken en aanpassen van een taartdiagram met Aspose.Slides Java, en lost veelvoorkomende presentatiewaardenproblemen eenvoudig op.

Laten we beginnen door ervoor te zorgen dat je alle benodigde tools en kennis hebt om mee te doen!

## Snelle antwoorden
- **Wat is de primaire klasse om een presentatie te starten?** `Presentation` van `com.aspose.slides`.
- **Welke methode voegt een taartdiagram toe aan een dia?** `addChart(ChartType.Pie, …)`.
- **Hoe schakel je gevarieerde kleuren in voor elke segment?** Stel `setColorVaried(true)` in op de seriesgroep.
- **Kun je het taartdiagram roteren?** Ja, gebruik `setRotationAngle(double)` op het chart‑object.
- **Heb ik een licentie nodig voor productiegebruik?** Een Aspose.Slides‑licentie is vereist voor commerciële implementaties.

## Wat betekent “customize pie chart colors”?
Customizing pie chart colors betekent het toewijzen van verschillende vulkleuren aan elk segment van de taart, waardoor de leesbaarheid en visuele impact verbeteren. In Aspose.Slides bereik je dit door gevarieerde kleuren in te schakelen en vervolgens solide vulkleuren in te stellen voor individuele gegevenspunten.

## Waarom Aspose.Slides voor Java gebruiken om taartdiagrammen te maken?
- **Volledige controle** over het uiterlijk van het diagram zonder Microsoft Office.
- **Cross‑platform** compatibiliteit – werkt op Windows, Linux en macOS.
- **Rijke API** voor databinding, styling en exporteren naar PPTX, PDF of afbeeldingen.
- **Licentie‑flexibiliteit** – begin met een gratis proefversie en upgrade wanneer je de volledige functionaliteit nodig hebt.

## Voorvereisten
Voordat je aan deze tutorial begint, zorg dat je de volgende setup klaar hebt staan:

### Vereiste bibliotheken, versies en afhankelijkheden
- **Aspose.Slides for Java**: versie 25.4 of later.
- **Java Development Kit (JDK)**: versie 16 of hoger.

### Vereisten voor omgeving configuratie
- Een ontwikkelomgeving met Java geïnstalleerd en geconfigureerd.
- Een Integrated Development Environment (IDE) zoals IntelliJ IDEA, Eclipse of NetBeans.

### Kennisvereisten
- Basiskennis van Java‑programmeren.
- Bekendheid met Maven of Gradle voor afhankelijkheidsbeheer.

## Aspose.Slides voor Java instellen
Om Aspose.Slides in je Java‑projecten te gebruiken, moet je de bibliotheek als afhankelijkheid toevoegen. Hieronder zie je hoe je dit doet met verschillende build‑tools:

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

**Direct downloaden**  
Als je liever geen build‑tool gebruikt, download dan de nieuwste release van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Stappen voor het verkrijgen van een licentie
- **Gratis proefversie**: Begin met een gratis proefversie om de functies van Aspose.Slides te verkennen.  
- **Tijdelijke licentie**: Verkrijg een tijdelijke licentie voor uitgebreid gebruik zonder beperkingen.  
- **Aankoop**: Overweeg een aankoop als je langdurige toegang nodig hebt.

**Basisinitialisatie en -instelling**  
Om Aspose.Slides te gebruiken, initialiseert u uw project door een nieuw presentatie‑object te maken:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Implementatie‑gids
Nu splitsen we het proces van het toevoegen en aanpassen van een taartdiagram op in beheersbare stappen.

### Presentatie en dia initialiseren
Begin met het opzetten van een nieuwe presentatie en het openen van de eerste dia. Dit is je canvas voor het maken van diagrammen:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Taartdiagram aan dia toevoegen
Voeg een taartdiagram toe op de opgegeven positie met een standaard dataset:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Diagramtitel instellen
Pas je diagram aan door de titel in te stellen en te centreren:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Gegevenslabels voor serie configureren
Zorg ervoor dat gegevenslabels waarden weergeven voor duidelijkheid:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Werkblad voor diagramgegevens voorbereiden
Stel het gegevenswerkblad van je diagram in door bestaande series en categorieën te wissen:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Categorieën aan diagram toevoegen
Definieer categorieën voor je taartdiagram:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Serie toevoegen en gegevenspunten vullen
Maak een serie aan en vul deze met gegevenspunten – dit is waar we **add chart series**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Kleuren en randen van serie aanpassen
Verbeter de visuele aantrekkingskracht door kleuren in te stellen en randen aan te passen – dit **customizes pie chart colors** direct:
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
Fijn‑afstemmen van de labels voor elk gegevenspunt:
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
Rond je taartdiagram af door **set rotation angle** te gebruiken en het bestand op te slaan:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Veelvoorkomende problemen en oplossingen
| Probleem | Oorzaak | Oplossing |
|----------|---------|-----------|
| **Alle segmenten hebben dezelfde kleur** | `setColorVaried(true)` niet aangeroepen | Zorg ervoor dat je gevarieerde kleuren inschakelt op de seriesgroep. |
| **Gegevenslabels worden niet weergegeven** | `showValue`‑vlag uitgeschakeld | Roep `setShowValue(true)` aan op het juiste label‑formaat. |
| **Rotatie heeft geen effect** | Gebruik van een oudere Aspose.Slides‑versie | Upgrade naar versie 25.4 of later. |
| **Licentie‑exception tijdens uitvoering** | Ontbrekend of ongeldig licentiebestand | Laad uw licentie met `License license = new License(); license.setLicense("Aspose.Slides.lic");` vóór het aanmaken van de `Presentation`. |

## Veelgestelde vragen

**Q: Hoe verkrijg ik een Aspose.Slides‑licentie voor Java?**  
A: Je kunt een gratis proefversie aanvragen via de Aspose‑website en vervolgens een permanente licentie aanschaffen. Laad deze tijdens runtime zoals weergegeven in de tabel met veelvoorkomende problemen.

**Q: Kan ik deze code gebruiken met oudere JDK‑versies?**  
A: De API vereist JDK 16 of hoger; oudere versies worden niet ondersteund.

**Q: Is het mogelijk om het diagram als afbeelding te exporteren in plaats van PPTX?**  
A: Ja, roep `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` aan na het renderen.

**Q: Wat als ik meer dan één serie aan een taartdiagram moet toevoegen?**  
A: Taartdiagrammen tonen doorgaans één enkele serie; voor meerdere series kun je beter een donut‑diagram gebruiken.

**Q: Werkt de bibliotheek op Linux‑servers?**  
A: Absoluut – Aspose.Slides voor Java is platform‑onafhankelijk en draait op elk OS met een compatibele JDK.

**Laatst bijgewerkt:** 2026-02-19  
**Getest met:** Aspose.Slides for Java 25.4 (jdk16)  
**Auteur:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}