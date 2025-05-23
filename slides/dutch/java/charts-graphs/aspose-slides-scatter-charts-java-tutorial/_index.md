---
"date": "2025-04-17"
"description": "Leer hoe u dynamische spreidingsdiagrammen maakt met Aspose.Slides voor Java. Verbeter uw presentaties met aanpasbare grafiekfuncties."
"title": "Maak en pas spreidingsdiagrammen aan in Java met Aspose.Slides"
"url": "/nl/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Maak en pas spreidingsdiagrammen aan in Java met Aspose.Slides

Verbeter uw presentaties door dynamische spreidingsdiagrammen toe te voegen met behulp van Java en Aspose.Slides. Deze uitgebreide tutorial begeleidt u bij het instellen van mappen, het initialiseren van presentaties, het maken van spreidingsdiagrammen, het beheren van grafiekgegevens, het aanpassen van reekstypen en markeringen en het opslaan van uw werk – allemaal met gemak.

**Wat je leert:**
- Een map instellen voor het opslaan van presentatiebestanden
- Presentaties initialiseren en manipuleren met Aspose.Slides
- Spreidingsdiagrammen op dia's maken
- Gegevens beheren en toevoegen aan grafiekreeksen
- Aanpassen van grafiekreekstypen en markeringen
- Uw presentatie met wijzigingen opslaan

Laten we beginnen met ervoor te zorgen dat u aan de noodzakelijke vereisten voldoet.

## Vereisten

Om deze tutorial te kunnen volgen, moet u het volgende doen:
- **Aspose.Slides voor Java**: Versie 25.4 of hoger is vereist.
- **Java-ontwikkelingskit (JDK)**: JDK 8 of hoger is vereist.
- Basiskennis van Java-programmering en vertrouwdheid met Maven- of Gradle-buildtools.

## Aspose.Slides instellen voor Java

Voordat we beginnen met coderen, integreert u Aspose.Slides in uw project met behulp van een van de volgende methoden:

### Maven
Neem deze afhankelijkheid op in uw `pom.xml` bestand:
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

U kunt ook de nieuwste Aspose.Slides voor Java downloaden van [Aspose-releases](https://releases.aspose.com/slides/java/).

#### Licentieverwerving
- **Gratis proefperiode**: Begin met een gratis proefperiode van 30 dagen om de functies te ontdekken.
- **Tijdelijke licentie**:Verkrijg een tijdelijke licentie voor uitgebreide tests.
- **Aankoop**: Koop een licentie voor volledige toegang en ondersteuning.

Initialiseer nu Aspose.Slides in uw Java-toepassing door de benodigde imports toe te voegen, zoals hieronder weergegeven.

## Implementatiegids

### Directory-instellingen
Zorg er eerst voor dat onze map bestaat om presentatiebestanden op te slaan. Deze stap voorkomt fouten tijdens het opslaan van bestanden.

#### Maak de map aan als deze niet bestaat
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Maak de directory aan
    new File(dataDir).mkdirs();
}
```
Dit fragment controleert op een opgegeven map en maakt deze aan als deze niet bestaat. Het gebruikt `File.exists()` om aanwezigheid te verifiëren en `File.mkdirs()` om mappen te creëren.

### Presentatie-initialisatie

Initialiseer vervolgens uw presentatieobject waar u het spreidingsdiagram gaat toevoegen.

#### Initialiseer uw presentatie
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Hier, `new Presentation()` creëert een lege presentatie. We openen de eerste dia om er direct mee te werken.

### Grafiek maken
Hierna maken we een spreidingsdiagram op onze geïnitialiseerde dia.

#### Spreidingsdiagram toevoegen aan dia
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Dit codefragment voegt een spreidingsdiagram met vloeiende lijnen toe aan de eerste dia. De parameters bepalen de positie en grootte van het diagram.

### Grafiekgegevensbeheer
Laten we nu onze grafiekgegevens beheren door bestaande reeksen te wissen en nieuwe toe te voegen.

#### Grafiekreeks beheren
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Nieuwe series toevoegen aan de grafiek
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
In deze sectie worden bestaande gegevens gewist en worden twee nieuwe reeksen toegevoegd aan ons spreidingsdiagram.

### Toevoeging van gegevenspunten voor spreidingsreeksen
Om onze gegevens te visualiseren, voegen we punten toe aan elke reeks in het spreidingsdiagram.

#### Gegevenspunten toevoegen
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Wij gebruiken `addDataPointForScatterSeries()` Om datapunten aan onze eerste reeks toe te voegen. Parameters definiëren X- en Y-waarden.

### Serietype en markerwijziging
Pas het uiterlijk van uw grafiek aan door het type en de stijl van de markeringen in elke serie te wijzigen.

#### Pas serie aan
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Wijziging van de tweede serie
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Met deze wijzigingen wordt het serietype aangepast voor het gebruik van rechte lijnen en markeringen. We stellen ook de grootte en het symbool van de marker in voor visueel onderscheid.

### Presentatie opslaan
Sla ten slotte uw presentatie op met alle gemaakte wijzigingen.

#### Bewaar uw presentatie
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Gebruik `SaveFormat.Pptx` om de PowerPoint-indeling voor het opslaan van uw bestand op te geven. Deze stap is cruciaal om alle wijzigingen te behouden.

## Praktische toepassingen
Hier zijn enkele praktijkvoorbeelden:
1. **Financiële analyse**: Gebruik spreidingsdiagrammen om aandelentrends in de loop van de tijd weer te geven.
2. **Wetenschappelijk onderzoek**: Representeren experimentele datapunten voor analyse.
3. **Projectmanagement**:Visualiseer de toewijzing van middelen en voortgangsgegevens.

Door Aspose.Slides in uw systeem te integreren, kunt u automatisch rapporten genereren en zo de productiviteit en nauwkeurigheid verbeteren.

## Prestatieoverwegingen
Voor optimale prestaties:
- Beheer het geheugengebruik door presentaties na het opslaan te verwijderen.
- Gebruik efficiënte datastructuren voor grote datasets.
- Minimaliseer resource-intensieve bewerkingen binnen lussen.

Best practices zorgen voor een soepele uitvoering, zelfs bij complexe grafiekmanipulaties.

## Conclusie
In deze tutorial heb je geleerd hoe je mappen instelt, Aspose.Slides-presentaties initialiseert, spreidingsdiagrammen maakt en aanpast, reeksgegevens beheert, markeringen aanpast en je werk opslaat. Om de mogelijkheden van Aspose.Slides verder te verkennen, kun je je verdiepen in geavanceerdere functies zoals animatie en dia-overgangen.

**Volgende stappen**: Experimenteer met verschillende grafiektypen of integreer deze technieken in een groter Java-project.

## Veelgestelde vragen

### Hoe verander ik de kleur van de markeringen?
Om de markeerkleur te veranderen, gebruik je `series.getMarker().getFillFormat().setFillColor(ColorObject)`, waar `ColorObject` is uw gewenste kleur.

### Kan ik meer dan twee reeksen aan een spreidingsdiagram toevoegen?
Ja, u kunt zoveel reeksen toevoegen als nodig is, door het proces van het toevoegen van nieuwe reeksen en datapunten te herhalen.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}