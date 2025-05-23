---
"description": "Verbeter uw grafieken met Aspose.Slides voor Java. Leer hoe u de positie-as in Java-dia's instelt, verbluffende presentaties maakt en eenvoudig grafieklay-outs aanpast."
"linktitle": "Positie-as instellen in Java-dia's"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Positie-as instellen in Java-dia's"
"url": "/nl/java/customization-and-formatting/setting-position-axis-java-slides/"
"weight": 16
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Positie-as instellen in Java-dia's


## Inleiding tot het instellen van de positie-as in Aspose.Slides voor Java

In deze tutorial leren we hoe je de positie-as in een grafiek instelt met Aspose.Slides voor Java. Het positioneren van de as kan handig zijn wanneer je het uiterlijk en de lay-out van je grafiek wilt aanpassen. We maken een geclusterde kolomgrafiek en passen de positie van de horizontale as tussen categorieën aan.

## Vereisten

Voordat we beginnen, zorg ervoor dat je de Aspose.Slides voor Java-bibliotheek hebt geïnstalleerd en ingesteld in je Java-project. Je kunt de bibliotheek downloaden van [hier](https://releases.aspose.com/slides/java/).

## Stap 1: Een presentatie maken

Laten we eerst een nieuwe presentatie maken om mee te werken:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Zorg ervoor dat u vervangt `"Your Document Directory"` met het werkelijke pad naar uw documentenmap.

## Stap 2: Een grafiek toevoegen

Vervolgens voegen we een geclusterde kolomgrafiek toe aan de dia. We specificeren het grafiektype, de positie (x, y-coördinaten) en de afmetingen (breedte en hoogte) van de grafiek:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Hier hebben we een geclusterde kolomgrafiek toegevoegd op positie (50, 50) met een breedte van 450 en een hoogte van 300. U kunt deze waarden naar wens aanpassen.

## Stap 3: Positie-as instellen

Om de positie-as tussen categorieën in te stellen, kunt u de volgende code gebruiken:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Met deze code wordt de horizontale as zo ingesteld dat deze tussen categorieën wordt weergegeven. Dit kan handig zijn voor bepaalde grafiekindelingen.

## Stap 4: De presentatie opslaan

Laten we ten slotte de presentatie met de grafiek opslaan:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

Vervangen `"AsposeClusteredColumnChart.pptx"` met de gewenste bestandsnaam.

Dat is alles! Je hebt met succes een geclusterde kolomgrafiek gemaakt en de positie-as tussen categorieën ingesteld met Aspose.Slides voor Java.

## Volledige broncode
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Conclusie

In deze tutorial hebben we onderzocht hoe je de positie-as in een grafiek instelt met Aspose.Slides voor Java. Door de stappen in deze handleiding te volgen, heb je geleerd hoe je een geclusterde kolomgrafiek maakt en de weergave ervan aanpast door de horizontale as tussen categorieën te positioneren. Aspose.Slides voor Java biedt krachtige functies voor het werken met grafieken en presentaties, waardoor het een waardevolle tool is voor Java-ontwikkelaars.

## Veelgestelde vragen

### Hoe kan ik de grafiek verder aanpassen?

U kunt verschillende aspecten van de grafiek aanpassen, waaronder gegevensreeksen, grafiektitels, legenda's en meer. Raadpleeg de [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/) voor gedetailleerde instructies en voorbeelden.

### Kan ik het grafiektype wijzigen?

Ja, u kunt het grafiektype wijzigen door de `ChartType` parameter bij het toevoegen van de grafiek. Aspose.Slides voor Java ondersteunt verschillende grafiektypen, zoals staafdiagrammen, lijndiagrammen en meer.

### Waar kan ik meer voorbeelden en documentatie vinden?

Uitgebreide documentatie en meer voorbeelden vindt u op de [Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/) pagina.

Vergeet niet om het presentatieobject te verwijderen wanneer u er klaar mee bent, om systeembronnen vrij te maken:

```java
if (pres != null) pres.dispose();
```

Dat was het voor deze tutorial. Je hebt geleerd hoe je de positie-as in een grafiek instelt met Aspose.Slides voor Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}