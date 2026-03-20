---
date: '2026-03-20'
description: Leer hoe u een gegroepeerde kolomgrafiek aan een PowerPoint‑presentatie
  kunt toevoegen, een PowerPoint‑grafiek kunt aanpassen en een gegevensreeksgrafiek
  kunt invoegen met Aspose.Slides voor Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Hoe een gegroepeerde kolomgrafiek toe te voegen in PowerPoint met Aspose.Slides
  voor Java
url: /nl/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe een gegroepeerde kolomgrafiek toe te voegen in PowerPoint met Aspose.Slides voor Java

## Inleiding

Wanneer je een **gegroepeerde kolomgrafiek** moet toevoegen aan een PowerPoint‑presentatie, kan een duidelijke visualisatie ruwe cijfers omzetten in een direct begrijpelijk verhaal. Dit handmatig doen in PowerPoint is tijdrovend, vooral wanneer je veel dia's programmatically moet genereren. **Aspose.Slides for Java** verwijdert die frictie – het stelt je in staat om PowerPoint‑grafieken te maken, aan te passen en een gegevensreeks‑grafiek in te voegen met slechts een paar regels code.

In deze tutorial leer je hoe je:
- Een nieuwe PowerPoint‑presentatie initialiseren met Aspose.Slides voor Java.
- **Grafiek aan dia toevoegen** en configureren als een gegroepeerde kolomgrafiek.
- **Een gegroepeerde kolomgrafiek maken** door groeperingsniveaus voor categorieën te definiëren.
- **Gegevensreeksgrafiek invoegen** zodat je data correct wordt weergegeven.
- De voltooide presentatie opslaan als een PPTX‑bestand.

Zorg ervoor dat je alles hebt wat je nodig hebt voordat we in de code duiken.

## Snelle antwoorden
- **Wat is de primaire klasse?** `Presentation` van `com.aspose.slides`.
- **Welke grafiektype wordt gebruikt?** `ChartType.ClusteredColumn`.
- **Heb ik een licentie nodig voor testen?** Een gratis proefversie werkt, maar een licentie verwijdert evaluatielimieten.
- **Welke Java‑versie wordt ondersteund?** JDK 16 of nieuwer (het voorbeeld gebruikt JDK 16).
- **Hoe voer ik het voorbeeld uit?** Voeg de Maven/Gradle‑dependency toe, compileer en voer de `main`‑methode uit.

## Wat is “add clustered column chart”?

Een *gegroepeerde kolomgrafiek* (ook wel een grouped column chart genoemd) toont meerdere gegevensreeksen naast elkaar voor elke categorie, waardoor het eenvoudig is om waarden over groepen heen te vergelijken. In PowerPoint is dit grafiektype ideaal voor kwartaalomzet, enquête‑resultaten of elke situatie waarin je meerdere datasets binnen dezelfde categorie wilt contrasteren.

## Waarom Aspose.Slides gebruiken om een gegroepeerde kolomgrafiek toe te voegen?

- **Volledige automatisering** – genereer tientallen dia's zonder handmatige inspanning.
- **Fijne aanpassing** – beheer kleuren, labels, groeperingsniveaus en meer.
- **Cross‑platform** – werkt op elk OS dat Java ondersteunt.
- **Geen Office‑installatie vereist** – genereer PPTX‑bestanden op servers of CI‑pijplijnen.

## Vereisten

- **Aspose.Slides voor Java** bibliotheek (de nieuwste versie wordt aanbevolen).  
- JDK 16 of later.  
- Maven‑ of Gradle‑buildtool (of je kunt de JAR handmatig toevoegen).  
- Een IDE of teksteditor om Java‑code uit te voeren.

## Aspose.Slides voor Java instellen

Voeg de bibliotheek toe aan je project met een van de volgende build‑scripts.

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

Je kunt de nieuwste release ook direct downloaden van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licentie‑acquisitie

Voordat je naar productie gaat, verkrijg een licentie:
- **Gratis proefversie** – verken alle functies zonder aankoop.
- **Tijdelijke licentie** – evalueer uitgebreide mogelijkheden voor een korte periode.
- **Volledige licentie** – ontgrendel onbeperkt gebruik. Verkrijg deze via [Aspose's purchase page](https://purchase.aspose.com/buy).

## Implementatie‑gids

We lopen elke stap door en leggen **hoe je een grafiek toevoegt** en **PowerPoint‑grafiek aanpast** uit.

### Presentatie initialiseren

Maak eerst een nieuw `Presentation`‑object aan en haal de standaarddia op.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Grafiek aan dia toevoegen

Nu **voegen we een grafiek toe aan de dia** met het type `ClusteredColumn` en wissen we eventuele standaardgegevens.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Grafiek‑gegevenswerkmap voorbereiden

De grafiek slaat zijn gegevens op in een interne werkmap. We wissen deze om schoon te beginnen.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Categorieën toevoegen met groeperingsniveaus

Het groeperen van categorieën creëert het **gegroepeerde kolomgrafiek**‑effect. Elke categorie kan tot een logische groep behoren.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Gegevensreeks aan grafiek toevoegen

Hier **voegen we gegevensreeks‑grafiek**‑items toe die als afzonderlijke kolommen worden weergegeven.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Presentatie opslaan met grafiek

Schrijf tenslotte het PPTX‑bestand naar schijf.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Praktische toepassingen

- **Bedrijfsrapporten** – vergelijk kwartaalomzet per regio.  
- **Academisch onderzoek** – toon experimentele resultaten gegroepeerd per testconditie.  
- **Projectmanagement** – visualiseer taakvoltooiingspercentages voor meerdere teams op één dia.

## Prestatie‑overwegingen

- **Geheugenbeheer** – maak grote werkboeken vrij na gebruik.  
- **Batch‑bewerkingen** – vermijd het bijwerken van de grafiek binnen strakke lussen; verzamel eerst de data, pas ze daarna toe.  
- **Ingebouwde optimalisaties** – Aspose.Slides biedt methoden zoals `Presentation.optimize()` voor grote bestanden.

## Veelvoorkomende valkuilen & tips

- **Valkuil:** Het vergeten te wissen van bestaande series/categorieën kan leiden tot dubbele data.  
  **Tip:** Roep altijd `clear()` aan voordat je nieuwe data vult.  
- **Valkuil:** Het gebruiken van een verkeerd celadres (bijv. `"c2"` in plaats van `"C2"`).  
  **Tip:** Celreferenties zijn niet hoofdlettergevoelig, maar houd ze consistent voor leesbaarheid.  
- **Tip:** Gebruik `setGroupingItem` om betekenisvolle groepslabels te maken; deze verschijnen automatisch in de legenda van de grafiek.

## Veelgestelde vragen

**Q1: Hoe kan ik meerdere series aan mijn grafiek toevoegen?**  
A1: Roep herhaaldelijk `ch.getChartData().getSeries().add()` aan, waarbij je een unieke naam en gegevenspunten voor elke serie opgeeft.

**Q2: Wat zijn enkele veelvoorkomende problemen met Aspose.Slides‑grafieken?**  
A2: Problemen ontstaan vaak door niet‑overeenkomende gegevensbereiken of ontbrekende werkboekcellen. Controleer of elke categorie en elk gegevenspunt een corresponderende cel heeft.

**Q3: Kan ik Aspose.Slides met andere programmeertalen gebruiken?**  
A3: Ja, Aspose biedt equivalente bibliotheken voor .NET, C++, Python en meer.

**Q4: Hoe werk ik een bestaande grafiek in een presentatie bij?**  
A4: Laad de presentatie, locateer de grafiek via `slide.getShapes().get_Item(index)`, en wijzig vervolgens de series of opmaak naar behoefte.

**Q5: Zijn er beperkingen op grafiektype­s met Aspose.Slides?**  
A5: De bibliotheek ondersteunt een breed scala aan grafiektype­s, maar controleer altijd de nieuwste documentatie voor eventuele nieuw toegevoegde of verouderde typen.

## Bronnen

- **Documentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **Download**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **Free Trial**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **Temporary License**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **Support Forum**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Last Updated:** 2026-03-20  
**Tested With:** Aspose.Slides for Java 25.4 (JDK 16)  
**Author:** Aspose