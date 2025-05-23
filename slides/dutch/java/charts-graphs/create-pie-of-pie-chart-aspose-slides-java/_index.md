---
"date": "2025-04-17"
"description": "Leer hoe je een cirkeldiagram maakt en aanpast met Aspose.Slides voor Java. Deze handleiding behandelt de installatie, implementatie en praktische toepassingen."
"title": "Maak een cirkeldiagram in Java met Aspose.Slides&#58; een uitgebreide handleiding"
"url": "/nl/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maak een cirkeldiagram in Java met Aspose.Slides: een uitgebreide handleiding

## Grafieken en diagrammen

### Invoering

Bij datavisualisatie zijn cirkeldiagrammen een intuïtieve manier om verhoudingen binnen een dataset weer te geven. Bij complexe datasets, waarbij sommige segmenten aanzienlijk kleiner zijn dan andere, kunnen traditionele cirkeldiagrammen echter rommelig en moeilijk te interpreteren worden. Cirkeldiagrammen lossen dit op door kleine segmenten op te splitsen in een tweede diagram, wat de leesbaarheid verbetert.

In deze tutorial leer je hoe je een cirkeldiagram maakt en bewerkt met Aspose.Slides voor Java. Je leert hoe je je omgeving instelt, de grafiek maakt, eigenschappen zoals gegevenslabels en splitsingsposities aanpast en je presentatie opslaat in PPTX-formaat. Aan het einde beheers je deze functies met praktische toepassingen en prestatietips.

**Wat je leert:**
- Aspose.Slides instellen voor Java
- Een cirkeldiagram maken
- Het aanpassen van grafiekeigenschappen zoals gegevenslabels en splitsingsconfiguraties
- Uw presentatie op schijf opslaan

Klaar om te beginnen? Laten we eerst eens kijken naar de vereisten!

## Vereisten

Voordat u uw cirkeldiagram maakt, moet u ervoor zorgen dat u het volgende heeft:

### Vereiste bibliotheken, versies en afhankelijkheden:
- **Aspose.Slides voor Java**: Essentieel voor het programmatisch beheren van PowerPoint-presentaties.

### Vereisten voor omgevingsinstelling:
- Een Java Development Kit (JDK) geïnstalleerd op uw machine. Wij raden JDK 16 of hoger aan.
- Een Integrated Development Environment (IDE) zoals IntelliJ IDEA, Eclipse of NetBeans.

### Kennisvereisten:
- Basiskennis van Java-programmering
- Kennis van Maven of Gradle voor afhankelijkheidsbeheer

## Aspose.Slides instellen voor Java

### Installatie-informatie:

**Kenner:**
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

**Direct downloaden**: U kunt de nieuwste versie downloaden van [Aspose.Slides voor Java-releases](https://releases.aspose.com/slides/java/).

### Stappen voor het verkrijgen van een licentie:
- **Gratis proefperiode**: Begin met een proefperiode van 30 dagen om alle functies te ontdekken.
- **Tijdelijke licentie**Vraag een tijdelijke licentie aan voor uitgebreide evaluatie.
- **Aankoop**: Overweeg de aanschaf van een licentie als Aspose.Slides aan uw behoeften voldoet.

### Basisinitialisatie en -installatie

Zodra u de bibliotheek in uw project hebt ingesteld, initialiseert u deze door een exemplaar van de `Presentation` klas:

```java
Presentation presentation = new Presentation();
```

Dit legt de basis voor het toevoegen van diverse grafieken aan je dia's. Laten we nu verdergaan met de implementatie van onze cirkeldiagram.

## Implementatiegids

### Een 'taart van taart'-diagram maken

#### Overzicht
We beginnen met het maken van een exemplaar van een `Presentation` Voeg een cirkeldiagram toe aan de eerste dia. Dit diagram visualiseert gegevens effectief door kleinere segmenten in een tweede cirkel te verdelen, wat de leesbaarheid verbetert.

#### Stap 1: Een instantie van de presentatieklasse maken
```java
// Een nieuwe presentatie maken
ePresentation presentation = new Presentation();
```
Deze code initialiseert uw presentatie, waar we onze grafieken gaan toevoegen.

#### Stap 2: Voeg een 'taartdiagram' toe aan de eerste dia
```java
// Voeg een cirkeldiagram toe aan de eerste dia op positie (50, 50) met de grootte (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Hier specificeren we het type grafiek (`PieOfPie`) en de positie en afmetingen ervan op de dia.

#### Stap 3: Stel gegevenslabels in om waarden voor de reeks weer te geven
```java
// Configureer gegevenslabels om waarden weer te geven
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Met deze stap zorgen we ervoor dat elk segment van ons cirkeldiagram de bijbehorende waarde weergeeft, waardoor we de gegevens snel kunnen interpreteren.

#### Stap 4: Configureer de tweede taartgrootte en splitsing op percentage
```java
// Stel de grootte van de secundaire taart in
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Verdeel de taart in procenten
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Stel de splitpositie in
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Met deze configuraties kunt u aanpassen hoe uw diagram wordt opgesplitst en kleinere segmenten worden weergegeven, wat de duidelijkheid voor kijkers verbetert.

#### Stap 5: Sla de presentatie op schijf op in PPTX-formaat
```java
// Definieer de uitvoermap
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Sla de presentatie op\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}