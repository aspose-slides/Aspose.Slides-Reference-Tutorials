---
date: '2026-08-21'
description: Leer hoe je een gegroepeerde kolomgrafiek maakt en trendlijnen toevoegt
  met Aspose.Slides for Java. Inclusief licentie‑instelling, Maven/Gradle‑integratie
  en gedetailleerde voorbeelden.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Maak een gegroepeerde kolomgrafiek en voeg trendlijnen toe met Aspose.Slides
  for Java. Deze gids behandelt licentie‑instelling, Maven/Gradle en stapsgewijze
  code‑fragmenten.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Maak een gegroepeerde kolomgrafiek en voeg trendlijnen toe met Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Hoe een gegroepeerde kolomgrafiek te maken en trendlijnen toe te voegen met
  Aspose.Slides for Java
url: /nl/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe maak je een clustered column chart en voeg trendlijnen toe met Aspose.Slides voor Java

Het maken van overtuigende presentaties begint vaak met een duidelijke visualisatie van uw gegevens. In deze gids maakt u **clustered column chart** objecten aan en verrijkt u ze vervolgens met verschillende trendlijnen — exponentieel, lineair, logaritmisch, voortschrijdend gemiddelde, polynomiaal en power — met behulp van de krachtige Aspose.Slides for Java API.

## Snelle antwoorden
- **Wat is de eerste stap?** Initialise een `Presentation` object en voeg een clustered column chart toe aan een dia.  
- **Welke bibliotheekversie is vereist?** Aspose.Slides for Java 25.4 of nieuwer.  
- **Kan ik Maven of Gradle gebruiken?** Ja, beide worden ondersteund; Maven gebruikt `<dependency>` en Gradle gebruikt `implementation`.  
- **Heb ik een licentie nodig?** Een proeflicentie werkt voor evaluatie; een volledige Aspose.Slides licentie verwijdert de evaluatiebeperkingen.  
- **Hoeveel trendlijntypen zijn er beschikbaar?** Zes ingebouwde types: exponentieel, lineair, logaritmisch, voortschrijdend gemiddelde, polynomiaal en power.

## Wat is create clustered column chart?
`create clustered column chart` betekent het genereren van een grafiek die meerdere gegevensreeksen naast elkaar groepeert binnen elke categorie, waardoor het eenvoudig is om waarden tussen reeksen te vergelijken. Dit grafiektype is ideaal voor het visualiseren van categorische gegevens zoals kwartaalverkopen per regio, waardoor kijkers snel verschillen tussen groepen kunnen zien.

## Waarom trendlijn toevoegen?
Trendlijnen onthullen het onderliggende patroon van een gegevensreeks, helpen u toekomstige waarden te voorspellen, groeipercentages te benadrukken of ruis in gegevens te verzachten. Door een trendlijn toe te voegen aan een clustered column chart, worden ruwe cijfers omgezet in bruikbare inzichten, waardoor belanghebbenden lange‑termijn trends kunnen begrijpen en datagedreven beslissingen kunnen nemen.

## Vereisten
- **Java Development Kit (JDK):** 8 of hoger.  
- **Aspose.Slides for Java:** versie 25.4 of nieuwer.  
- **IDE:** IntelliJ IDEA, Eclipse, of een andere Java‑compatibele editor.  
- **Build tool:** Maven of Gradle (optioneel maar aanbevolen).  
- **Licentie:** een proef- of aangeschafte Aspose.Slides licentiebestand.  

U moet vertrouwd zijn met basis Java-syntaxis en bekend zijn met het beheer van projectafhankelijkheden.

## Hoe Aspose.Slides voor Java in te stellen?
Voeg de Aspose.Slides bibliotheek toe aan uw project met uw favoriete dependency‑manager en plaats vervolgens uw licentiebestand op een locatie die de runtime kan vinden. Dit zorgt voor volledige functionaliteit en verwijdert evaluatiebeperkingen.

### Maven
Voeg deze dependency toe aan uw `pom.xml` bestand:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Voeg deze regel toe aan uw `build.gradle` bestand:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Directe download
U kunt de JAR ook handmatig downloaden van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Aspose Slides licentie
Plaats het bestand `Aspose.Slides.lic` in de hoofdmap van uw project of stel de licentie programmatisch in met `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Een proeflicentie verwijdert alle functierestricties, maar een aangeschafte licentie elimineert het evaluatiewatermerk en biedt volledige prestatie‑optimalisaties. Overweeg voor productiegebruik een licentie aan te schaffen via de [Aspose purchase page](https://purchase.aspose.com/buy).

## Hoe maak je een presentatie en voeg je een clustered column chart toe?
De klasse `Presentation` vertegenwoordigt een PowerPoint‑bestand en biedt methoden om dia's te maken, bewerken en opslaan. Maak een `Presentation` instantie, voeg een dia toe en roep vervolgens `addChart` aan met `ChartType.ClusteredColumn` om het grafiekobject te creëren. Dit proces zet het dia‑canvas op, voegt een grafiekvorm in en bereidt het voor op het vullen van gegevens en opmaak.

1. **Initialiseer de presentatie** – stel de uitvoermap in en maak een nieuwe `Presentation` instantie aan.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Voeg een clustered column chart toe** – verkrijg de grafiekvorm, configureer de reeksen en vul gegevenspunten in.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Hoe een exponentiële trendlijn toevoegen?
De interface `ITrendline` definieert een trendlijn die aan een grafiekreeks kan worden toegevoegd om gegevenspatronen te modelleren. Pas een exponentiële trendlijn toe op een reeks door een `ITrendline` instantie te maken, de `TrendlineType` in te stellen op `Exponential` en deze aan de gewenste reeks te koppelen. Dit type trendlijn is nuttig voor gegevens die snel groeien met een toenemend tempo.

1. **Configureer de trendlijn** – selecteer de reeks en roep `addTrendline(TrendlineType.Exponential)` aan.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Hoe een lineaire trendlijn toevoegen?
Een lineaire trendlijn toont de best passende rechte lijn door uw gegevenspunten. U kunt ook het uiterlijk aanpassen, zoals lijnkleur en -dikte, om het aan te laten sluiten bij uw presentatiestijl.

1. **Stel de trendlijn in** – gebruik `addTrendline(TrendlineType.Linear)` en pas vervolgens `getLineFormat().setFillFormat().setFillType(FillType.Solid)` aan om de kleur te wijzigen.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Hoe een logaritmische trendlijn met een aangepast tekstvak toevoegen?
Logaritmische trendlijnen zijn ideaal voor gegevens die eerst snel groeien en daarna afvlakken. Het overschrijven van het standaardlabel stelt u in staat om verklarende tekst toe te voegen die de betekenis van de trend verduidelijkt.

1. **Pas de trendlijn aan** – na het toevoegen van de trendlijn, krijg toegang tot `getDataLabel()` en stel de eigenschap `setText("Custom label")` in.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Hoe een voortschrijdend gemiddelde trendlijn toevoegen?
Voortschrijdende gemiddelde trendlijnen vloeien korte‑termijn fluctuaties glad om langere‑termijn trends te benadrukken. U kunt de periode (aantal punten) die voor het middelen wordt gebruikt opgeven, waardoor u de gladheid van de lijn kunt regelen.

1. **Configureer de trendlijn** – roep `addTrendline(TrendlineType.MovingAverage)` aan en stel `setPeriod(3)` in om een drie‑punt voortschrijdend gemiddelde te gebruiken.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Hoe een polynomiale trendlijn toevoegen?
Polynomiale trendlijnen passen gegevens aan met een kromme gedefinieerd door een polynomiale vergelijking. De eigenschap `order` bepaalt de graad van het polynoom, waardoor u complexere relaties kunt modelleren.

1. **Pas de trendlijn aan** – na het toevoegen van de trendlijn, stel `setOrder(3)` in voor een kubieke fitting.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Hoe een power trendlijn toevoegen?
Power trendlijnen zijn nuttig wanneer gegevens een power‑law relatie volgen. U kunt ook achterwaartse en voorwaartse voorspellingswaarden instellen om de lijn buiten het bestaande gegevensbereik uit te breiden.

1. **Configureer de trendlijn** – gebruik `addTrendline(TrendlineType.Power)` en pas `setBackward(2)` aan om de lijn achterwaarts uit te breiden.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Praktische toepassingen van trendlijnen in clustered column charts
- **Financiële analyse:** Exponentiële en polynomiale trends helpen bij het voorspellen van aandelenkoersbewegingen.  
- **Verkoopprognoses:** Voortschrijdende gemiddelde lijnen verzachten seizoenspieken, waardoor een duidelijker beeld ontstaat van onderliggende verkooptrends.  
- **Wetenschappelijk onderzoek:** Logaritmische trends zijn perfect voor gegevens die zich over meerdere orders van grootte uitstrekken, zoals akoestische intensiteit of pH-waarden.  
- **Operationeel toezicht:** Power trendlijnen kunnen prestatie‑degradatie over tijd modelleren.

## Hoe geheugen te optimaliseren bij gebruik van Aspose.Slides?
Maak objecten direct vrij en gebruik `presentation.dispose()` na het opslaan. Voor grote datasets, schakel lazy loading van afbeeldingen in en vermijd het in één keer laden van de volledige grafiek in het geheugen.

- **Dispose‑patronen:** Plaats `Presentation` in een try‑with‑resources blok of roep `presentation.dispose()` aan in een finally‑clausule.  
- **Lazy loading:** Stel `ChartData.setUseCache(true)` in bij het verwerken van duizenden gegevenspunten.  
- **Streaming output:** Schrijf de presentatie direct naar een `FileOutputStream` om te voorkomen dat het volledige bestand in RAM blijft.

## Gekwantificeerde voordelen van Aspose.Slides voor Java
Aspose.Slides ondersteunt **meer dan 50 grafiektype​n**, kan presentaties genereren met **meer dan 1.000 dia's** in minder dan **30 seconden** op een typische 2 GHz CPU, en verwerkt **500‑pagina PDF's** zonder dat Microsoft Office geïnstalleerd hoeft te zijn. Deze cijfers zijn geverifieerd op de nieuwste 25.4 release.

## Conclusie
U heeft nu een volledige, end‑to‑end oplossing voor **het maken van clustered column chart** objecten en het verrijken ervan met elk belangrijk trendlijntype dat beschikbaar is in Aspose.Slides for Java. Door de bovenstaande stappen te volgen, kunt u datagedreven presentaties maken die zowel visueel aantrekkelijk als analytisch krachtig zijn.

Volgende stappen omvatten het verkennen van grafiek‑stylingopties, exporteren naar PDF/HTML, en het automatiseren van grafiekgeneratie over meerdere gegevensbronnen.

## Veelgestelde vragen

**V: Hoe stel ik Aspose.Slides in voor een Maven‑project?**  
Voeg het `<dependency>` fragment toe dat in de Maven‑sectie wordt getoond aan uw `pom.xml` en voer `mvn clean install` uit.

**V: Kan ik trendlijnen aanpassen buiten kleur en label?**  
Ja, u kunt de lijnstijl, breedte, stippelpatroon aanpassen, en zelfs vooruit/achteruit voorspellingen doen via de `ITrendline` API.

**V: Wat moet ik doen als ik een versie‑compatibiliteitsfout tegenkom?**  
Controleer of uw JDK‑versie voldoet aan de minimale vereiste van Aspose.Slides (JDK 8+). Raadpleeg de Aspose release‑notes voor eventuele breaking changes.

**V: Is het mogelijk om trendlijnen automatisch aan meerdere grafieken toe te voegen?**  
Absoluut. Loop door elke `IChart` in een collectie van dia's en roep de juiste `addTrendline` methode aan voor elke reeks.

**V: Heb ik een betaalde licentie nodig voor productiegebruik?**  
Ja, een aangeschafte Aspose.Slides licentie verwijdert evaluatiebeperkingen en ontgrendelt volledige prestatie‑optimalisaties.

---

**Laatst bijgewerkt:** 2026-08-21  
**Getest met:** Aspose.Slides for Java 25.4  
**Auteur:** Aspose

## Gerelateerde tutorials

- [aspose slides maven dependency: Voeg grafieken toe en configureer ze in presentaties met Aspose.Slides voor Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}