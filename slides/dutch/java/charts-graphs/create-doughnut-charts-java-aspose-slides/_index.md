---
"date": "2025-04-17"
"description": "Leer hoe je verbluffende ringdiagrammen maakt in Java met Aspose.Slides. Deze uitgebreide handleiding behandelt initialisatie, gegevensconfiguratie en het opslaan van presentaties."
"title": "Maak donutdiagrammen in Java met Aspose.Slides&#58; een uitgebreide handleiding"
"url": "/nl/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maak donutdiagrammen in Java met Aspose.Slides: een stapsgewijze handleiding

## Invoering

In de huidige datagedreven omgeving is het effectief visualiseren van informatie essentieel om begrip en betrokkenheid te vergroten. Hoewel het maken van professionele diagrammen via een programma lastig kan lijken, vooral met Java, begeleidt deze handleiding je bij het gebruik van Aspose.Slides voor Java om moeiteloos donutdiagrammen te maken.

Door deze stappen te volgen, krijgen ontwikkelaars praktische ervaring met het bewerken van presentatieslides en het naadloos integreren van datavisualisatie.

**Belangrijkste punten:**
- Initialiseer een presentatieobject met Aspose.Slides Java.
- Configureer grafiekgegevens en beheer bestaande series of categorieën.
- Voeg series en categorieën toe aan uw diagrammen en pas ze aan.
- Datapunten effectief opmaken en weergeven.
- Sla uw presentatie eenvoudig op in verschillende formaten.

Voordat u met de implementatie begint, moet u ervoor zorgen dat u alles hebt wat u nodig hebt om te beginnen.

## Vereisten

Om deze tutorial te kunnen volgen, moet u het volgende hebben:

- **Vereiste bibliotheken:**
  - Aspose.Slides voor Java versie 25.4 of later.
  
- **Omgevingsinstellingen:**
  - JDK 16 of hoger geïnstalleerd op uw systeem.
  - Een IDE zoals IntelliJ IDEA, Eclipse of NetBeans.

- **Kennisvereisten:**
  - Basiskennis van Java-programmeerconcepten.
  - Kennis van het beheer van afhankelijkheden in Maven- of Gradle-projecten.

## Aspose.Slides instellen voor Java

Om Aspose.Slides in uw project te integreren, volgt u deze stappen, afhankelijk van uw buildtool:

**Maven-installatie:**
Voeg de volgende afhankelijkheid toe aan uw `pom.xml` bestand:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle-installatie:**
Neem het volgende op in uw `build.gradle` bestand:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct downloaden:**
U kunt de nieuwste versie ook rechtstreeks downloaden van [Aspose.Slides voor Java-releases](https://releases.aspose.com/slides/java/).

### Een licentie verkrijgen

Om Aspose.Slides te gebruiken zonder evaluatiebeperkingen:
- **Gratis proefperiode:** Begin met een tijdelijke licentie om alle functies te ontdekken.
- **Tijdelijke licentie:** Verkrijg er een via de [Aspose-website](https://purchase.aspose.com/temporary-license/).
- **Aankoop:** Overweeg de aanschaf voor doorlopend gebruik.

Pas uw licentie toe in uw Java-applicatie met behulp van:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Implementatiegids

### Presentatie en grafiek initialiseren

#### Overzicht
Begin met het initialiseren van een presentatieobject en voeg een ringdiagram toe aan de eerste dia.

**Stap 1: Presentatie initialiseren**
Laad een bestaand PPTX-bestand of maak een nieuw bestand:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**Stap 2: Voeg een donutdiagram toe**
Maak een grafiek op de eerste dia op de opgegeven coördinaten:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Werkmap met grafiekgegevens configureren en bestaande series/categorieën wissen

#### Overzicht
Configureer de grafiekgegevenswerkmap en verwijder alle bestaande reeksen of categorieën.

**Stap 1: Toegang tot grafiekgegevenswerkmap**
Haal de werkmap op die aan uw grafiek is gekoppeld:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**Stap 2: Bestaande series en categorieën wissen**
Zorg ervoor dat er geen resterende datapunten zijn:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Serie toevoegen aan grafiek

#### Overzicht
Vul uw diagram met meerdere reeksen, elk aangepast wat betreft uiterlijk en gedrag.

**Stap 1: Serie iteratief toevoegen**
Loop door de indices om reeksen toe te voegen:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // Pas de serie aan
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Categorieën en datapunten toevoegen aan een grafiek

#### Overzicht
Configureer categorieën en voeg datapunten toe met specifieke opmaak voor labels.

**Stap 1: Categorieën toevoegen**
Loop door de indexen voor elke categorie:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**Stap 2: Voeg datapunten toe aan elke reeks**
Loop door elke serie voor de huidige categorie:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Instellingen voor gegevenspuntindeling
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Labelopmaak voor de laatste serie
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Weergaveopties aanpassen
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Positie van het label aanpassen
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### De presentatie opslaan

#### Overzicht
Nadat u uw grafiek hebt geconfigureerd, slaat u de presentatie op in de opgegeven map.

**Stap 1: Sla de presentatie op**
Gebruik de `save` methode om wijzigingen te schrijven:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Conclusie

Je hebt nu geleerd hoe je ringdiagrammen in Java kunt maken en aanpassen met Aspose.Slides. Deze stappen vormen een basis voor het integreren van geavanceerde datavisualisaties in je presentaties.

**Volgende stappen:**
- Experimenteer met de verschillende grafiektypen die beschikbaar zijn in Aspose.Slides.
- Ontdek extra aanpassingsopties zoals kleuren, lettertypen en stijlen om aan uw merkbehoeften te voldoen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}