---
"description": "Leer hoe u grafiekgegevens in een externe werkmap bewerkt met Aspose.Slides voor Java. Stapsgewijze handleiding met broncode."
"linktitle": "Grafiekgegevens bewerken in een externe werkmap in Java Slides"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Grafiekgegevens bewerken in een externe werkmap in Java Slides"
"url": "/nl/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Grafiekgegevens bewerken in een externe werkmap in Java Slides


## Inleiding tot het bewerken van grafiekgegevens in een externe werkmap in Java Slides

In deze handleiding laten we zien hoe u grafiekgegevens in een externe werkmap kunt bewerken met Aspose.Slides voor Java. U leert hoe u grafiekgegevens in een PowerPoint-presentatie programmatisch kunt wijzigen. Zorg ervoor dat de Aspose.Slides-bibliotheek voor Java geïnstalleerd en geconfigureerd is in uw project.

## Vereisten

- Aspose.Slides voor Java
- Java-ontwikkelomgeving

## Stap 1: Laad de presentatie

Eerst moeten we de PowerPoint-presentatie laden die de grafiek bevat waarvan we de gegevens willen bewerken. Vervangen `"Your Document Directory"` met het daadwerkelijke pad naar uw presentatiebestand.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Stap 2: Toegang tot de grafiek

Zodra de presentatie is geladen, moeten we de grafiek in de presentatie openen. In dit voorbeeld gaan we ervan uit dat de grafiek op de eerste dia staat en de eerste vorm op die dia is.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Stap 3: Wijzig grafiekgegevens

Laten we nu de grafiekgegevens aanpassen. We richten ons op het wijzigen van een specifiek gegevenspunt in de grafiek. In dit voorbeeld stellen we de waarde van het eerste gegevenspunt in de eerste reeks in op 100. U kunt deze waarde naar wens aanpassen.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Stap 4: Sla de presentatie op

Nadat u de gewenste wijzigingen in de grafiekgegevens hebt aangebracht, slaat u de gewijzigde presentatie op in een nieuw bestand. U kunt het pad en de opmaak van het uitvoerbestand naar wens specificeren.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Stap 5: Opruimen

Vergeet niet om het presentatieobject te verwijderen om bronnen vrij te maken.

```java
if (pres != null) pres.dispose();
```

U hebt nu de grafiekgegevens in een externe werkmap in uw PowerPoint-presentatie succesvol bewerkt met Aspose.Slides voor Java. U kunt deze code aanpassen aan uw specifieke behoeften en integreren in uw Java-toepassingen.

## Volledige broncode

```java
        // Let op: het pad naar de externe werkmap wordt nauwelijks opgeslagen in de presentatie
        // Kopieer daarom het bestand externalWorkbook.xlsx uit de Data/Chart-map D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ voordat u het voorbeeld uitvoert
        // Het pad naar de documentenmap.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Conclusie

In deze uitgebreide handleiding hebben we besproken hoe je grafiekgegevens in externe werkmappen in PowerPoint-presentaties kunt bewerken met Aspose.Slides voor Java. Door de stapsgewijze instructies en broncodevoorbeelden te volgen, heb je de kennis en vaardigheden opgedaan om grafiekgegevens eenvoudig programmatisch aan te passen.

## Veelgestelde vragen

### Hoe geef ik een andere grafiek of dia op?

Om toegang te krijgen tot een andere grafiek of dia, wijzigt u de juiste index in de `getSlides().get_Item()` En `getShapes().get_Item()` methoden. Onthoud dat indexering vanaf 0 begint.

### Kan ik gegevens in meerdere grafieken binnen dezelfde presentatie bewerken?

Ja, u kunt gegevens in meerdere grafieken binnen dezelfde presentatie bewerken door de stappen voor het wijzigen van de grafiekgegevens voor elke grafiek te herhalen.

### Wat als ik gegevens in een externe werkmap met een andere opmaak wil bewerken?

U kunt de code aanpassen om verschillende externe werkmapindelingen te verwerken door de juiste Aspose.Cells-klassen en -methoden te gebruiken voor het lezen en schrijven van gegevens in die indeling.

### Hoe kan ik dit proces automatiseren voor meerdere presentaties?

U kunt een lus maken om meerdere presentaties te verwerken, waarbij u iedere presentatie laadt, de gewenste wijzigingen aanbrengt en de gewijzigde presentaties één voor één opslaat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}