---
title: Verbind vormen met verbindingssites in PowerPoint
linktitle: Verbind vormen met verbindingssites in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u vormen in PowerPoint verbindt met Aspose.Slides voor Java. Automatiseer uw presentaties moeiteloos.
type: docs
weight: 19
url: /nl/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u vormen kunt verbinden met behulp van verbindingssites in PowerPoint met behulp van Aspose.Slides voor Java. Met deze krachtige bibliotheek kunnen we PowerPoint-presentaties programmatisch manipuleren, waardoor taken zoals het verbinden van vormen naadloos en efficiënt worden.
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1.  Java Development Kit (JDK): Zorg ervoor dat Java op uw systeem is geïnstalleerd. Je kunt het downloaden en installeren vanaf de[website](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides voor Java: Download en installeer Aspose.Slides voor Java vanaf de[downloadpagina](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Kies een IDE voor Java-ontwikkeling, zoals IntelliJ IDEA, Eclipse of NetBeans.

## Pakketten importeren
Importeer om te beginnen de benodigde pakketten in uw Java-project:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## Stap 1: Toegang tot de Shapes-collectie
Toegang tot de vormencollectie voor de geselecteerde dia:
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Instantieer de presentatieklasse die het PPTX-bestand vertegenwoordigt
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## Stap 2: Connectorvorm toevoegen
Voeg een verbindingsvorm toe aan de verzameling diavormen:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## Stap 3: AutoVormen toevoegen
Automatische vormen toevoegen, zoals ellips en rechthoek:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## Stap 4: Shapes verbinden met connectoren
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
In deze zelfstudie hebben we geleerd hoe u vormen kunt verbinden met behulp van verbindingssites in PowerPoint met behulp van Aspose.Slides voor Java. Met deze kennis kunt u uw PowerPoint-presentaties nu eenvoudig automatiseren en aanpassen.
## Veelgestelde vragen
### Kan Aspose.Slides voor Java worden gebruikt voor andere PowerPoint-manipulatietaken?
Ja, Aspose.Slides voor Java biedt een breed scala aan functionaliteiten voor het maken, bewerken en converteren van PowerPoint-presentaties.
### Is Aspose.Slides voor Java gratis te gebruiken?
 Aspose.Slides voor Java is een commerciële bibliotheek, maar u kunt de functies ervan verkennen met een gratis proefperiode. Bezoek[hier](https://releases.aspose.com/) starten.
### Kan ik ondersteuning krijgen als ik problemen ondervind tijdens het gebruik van Aspose.Slides voor Java?
 Ja, u kunt ondersteuning krijgen van de Aspose-communityforums[hier](https://forum.aspose.com/c/slides/11).
### Zijn er tijdelijke licenties beschikbaar voor Aspose.Slides voor Java?
 Ja, er zijn tijdelijke licenties beschikbaar voor test- en evaluatiedoeleinden. Je kunt er een verkrijgen[hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik een licentie kopen voor Aspose.Slides voor Java?
 kunt een licentie kopen op de Aspose-website[hier](https://purchase.aspose.com/buy).