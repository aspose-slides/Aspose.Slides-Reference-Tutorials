---
"description": "Leer hoe je vormen in PowerPoint verbindt met Aspose.Slides voor Java. Automatiseer je presentaties moeiteloos."
"linktitle": "Vormen verbinden met behulp van verbindingspunten in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Vormen verbinden met behulp van verbindingspunten in PowerPoint"
"url": "/nl/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vormen verbinden met behulp van verbindingspunten in PowerPoint

## Invoering
In deze tutorial onderzoeken we hoe je vormen kunt verbinden met behulp van verbindingspunten in PowerPoint met Aspose.Slides voor Java. Deze krachtige bibliotheek stelt je in staat om PowerPoint-presentaties programmatisch te bewerken, waardoor taken zoals het verbinden van vormen naadloos en efficiënt verlopen.
## Vereisten
Voordat we beginnen, zorg ervoor dat u het volgende heeft:
1. Java Development Kit (JDK): Zorg ervoor dat Java op uw systeem is geïnstalleerd. U kunt het downloaden en installeren vanaf de [website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides voor Java: Download en installeer Aspose.Slides voor Java vanaf de [downloadpagina](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Kies een IDE voor Java-ontwikkeling, zoals IntelliJ IDEA, Eclipse of NetBeans.

## Pakketten importeren
Om te beginnen importeert u de benodigde pakketten in uw Java-project:
```java
import com.aspose.slides.*;

```
## Stap 1: Toegang tot de vormencollectie
Toegang tot de vormenverzameling voor de geselecteerde dia:
```java
// Het pad naar de documentenmap.                    
String dataDir = "Your Document Directory";
// Instantieer de presentatieklasse die het PPTX-bestand vertegenwoordigt
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Stap 2: Connectorvorm toevoegen
Voeg een connectorvorm toe aan de diavormverzameling:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Stap 3: AutoVormen toevoegen
Automatische vormen toevoegen, zoals ellips en rechthoek:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Stap 4: Vormen verbinden met connectoren
Verbind de vormen met de connector:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Stap 5: Verbindingssite-index instellen
Stel de gewenste verbindingssite-index voor de vormen in:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Conclusie
In deze tutorial hebben we geleerd hoe je vormen kunt verbinden met behulp van verbindingspunten in PowerPoint met Aspose.Slides voor Java. Met deze kennis kun je nu eenvoudig je PowerPoint-presentaties automatiseren en aanpassen.
## Veelgestelde vragen
### Kan Aspose.Slides voor Java gebruikt worden voor andere PowerPoint-manipulatietaken?
Ja, Aspose.Slides voor Java biedt een breed scala aan functionaliteiten voor het maken, bewerken en converteren van PowerPoint-presentaties.
### Is Aspose.Slides voor Java gratis te gebruiken?
Aspose.Slides voor Java is een commerciële bibliotheek, maar u kunt de functies ervan verkennen met een gratis proefperiode. Bezoek [hier](https://releases.aspose.com/) om te beginnen.
### Kan ik ondersteuning krijgen als ik problemen ondervind bij het gebruik van Aspose.Slides voor Java?
Ja, u kunt ondersteuning krijgen van de Aspose-communityforums [hier](https://forum.aspose.com/c/slides/11).
### Zijn er tijdelijke licenties beschikbaar voor Aspose.Slides voor Java?
Ja, tijdelijke licenties zijn beschikbaar voor test- en evaluatiedoeleinden. U kunt er een verkrijgen [hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik een licentie voor Aspose.Slides voor Java kopen?
U kunt een licentie aanschaffen via de Aspose-website [hier](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}