---
title: Bewerk grafiekgegevens in externe werkmap in Java-dia's
linktitle: Bewerk grafiekgegevens in externe werkmap in Java-dia's
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u diagramgegevens in een externe werkmap kunt bewerken met Aspose.Slides voor Java. Stap-voor-stap handleiding met broncode.
weight: 17
url: /nl/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bewerk grafiekgegevens in externe werkmap in Java-dia's


## Inleiding tot het bewerken van diagramgegevens in een externe werkmap in Java-dia's

In deze handleiding laten we zien hoe u diagramgegevens in een externe werkmap kunt bewerken met Aspose.Slides voor Java. U leert hoe u diagramgegevens binnen een PowerPoint-presentatie programmatisch kunt wijzigen. Zorg ervoor dat de Aspose.Slides-bibliotheek voor Java in uw project is geïnstalleerd en geconfigureerd.

## Vereisten

- Aspose.Slides voor Java
- Java-ontwikkelomgeving

## Stap 1: Laad de presentatie

 Eerst moeten we de PowerPoint-presentatie laden die het diagram bevat waarvan we de gegevens willen bewerken. Vervangen`"Your Document Directory"` met het daadwerkelijke pad naar uw presentatiebestand.

```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Stap 2: Open de grafiek

Zodra de presentatie is geladen, hebben we toegang nodig tot het diagram in de presentatie. In dit voorbeeld gaan we ervan uit dat het diagram zich op de eerste dia bevindt en de eerste vorm op die dia is.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Stap 3: Wijzig diagramgegevens

Laten we nu de diagramgegevens wijzigen. We concentreren ons op het wijzigen van een specifiek gegevenspunt in het diagram. In dit voorbeeld stellen we de waarde van het eerste gegevenspunt in de eerste reeks in op 100. U kunt deze waarde indien nodig aanpassen.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Stap 4: Sla de presentatie op

Nadat u de nodige wijzigingen in de diagramgegevens heeft aangebracht, slaat u de gewijzigde presentatie op in een nieuw bestand. U kunt het pad en de indeling van het uitvoerbestand opgeven volgens uw vereisten.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Stap 5: Opruimen

Vergeet niet het presentatieobject weg te gooien om eventuele bronnen vrij te maken.

```java
if (pres != null) pres.dispose();
```

Nu hebt u met succes de diagramgegevens in een externe werkmap binnen uw PowerPoint-presentatie bewerkt met Aspose.Slides voor Java. U kunt deze code aanpassen aan uw specifieke behoeften en deze integreren in uw Java-applicaties.

## Volledige broncode

```java
        // Let op: het pad naar de externe werkmap wordt nauwelijks opgeslagen in de presentatie
        // Kopieer dus het bestand externalWorkbook.xlsx uit de Data/Chart-directory D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ voordat u het voorbeeld uitvoert
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

In deze uitgebreide handleiding hebben we onderzocht hoe u diagramgegevens in externe werkmappen in PowerPoint-presentaties kunt bewerken met Aspose.Slides voor Java. Door de stapsgewijze instructies en broncodevoorbeelden te volgen, heeft u de kennis en vaardigheden verworven om diagramgegevens eenvoudig programmatisch aan te passen.

## Veelgestelde vragen

### Hoe geef ik een ander diagram of andere dia op?

 Om toegang te krijgen tot een ander diagram of een andere dia, wijzigt u de juiste index in het`getSlides().get_Item()` En`getShapes().get_Item()`methoden. Houd er rekening mee dat de indexering begint vanaf 0.

### Kan ik gegevens in meerdere diagrammen binnen dezelfde presentatie bewerken?

Ja, u kunt gegevens in meerdere diagrammen binnen dezelfde presentatie bewerken door de stappen voor het wijzigen van diagramgegevens voor elk diagram te herhalen.

### Wat moet ik doen als ik gegevens in een externe werkmap met een ander formaat wil bewerken?

U kunt de code aanpassen om verschillende externe werkmapindelingen te verwerken door de juiste Aspose.Cells-klassen en -methoden te gebruiken voor het lezen en schrijven van gegevens in die indeling.

### Hoe kan ik dit proces automatiseren voor meerdere presentaties?

U kunt een lus maken om meerdere presentaties te verwerken, elke presentatie te laden, de gewenste wijzigingen aan te brengen en de gewijzigde presentaties één voor één op te slaan.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
