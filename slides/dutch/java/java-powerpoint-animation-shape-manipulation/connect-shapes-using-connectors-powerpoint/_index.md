---
"description": "Leer hoe je vormen verbindt met connectoren in PowerPoint-presentaties met Aspose.Slides voor Java. Stapsgewijze handleiding voor beginners."
"linktitle": "Vormen verbinden met behulp van connectoren in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Vormen verbinden met behulp van connectoren in PowerPoint"
"url": "/nl/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vormen verbinden met behulp van connectoren in PowerPoint

## Invoering
In deze tutorial laten we zien hoe je vormen met elkaar verbindt met behulp van connectoren in PowerPoint-presentaties met behulp van Aspose.Slides voor Java. Volg deze stapsgewijze instructies om vormen efficiënt te verbinden en visueel aantrekkelijke dia's te maken.
## Vereisten
Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Basiskennis van de programmeertaal Java.
- Java Development Kit (JDK) op uw systeem geïnstalleerd.
- Aspose.Slides voor Java gedownload en geïnstalleerd. Als je het nog niet hebt geïnstalleerd, kun je het hier downloaden. [hier](https://releases.aspose.com/slides/java/).
- Een code-editor zoals Eclipse of IntelliJ IDEA.

## Pakketten importeren
Importeer eerst de benodigde pakketten voor het werken met Aspose.Slides in uw Java-project.
```java
import com.aspose.slides.*;

```
## Stap 1: Instantieer presentatieklasse
Instantieer de `Presentation` klasse, die het PPTX-bestand vertegenwoordigt waaraan u werkt.
```java
// Het pad naar de documentenmap.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## Stap 2: Toegang tot de vormencollectie
Open de vormenverzameling voor de geselecteerde dia waaraan u vormen en verbindingsstukken wilt toevoegen.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## Stap 3: Vormen toevoegen
Voeg de gewenste vormen toe aan de dia. In dit voorbeeld voegen we een ellips en een rechthoek toe.
```java
// Autovorm Ellips toevoegen
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Autovorm Rechthoek toevoegen
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## Stap 4: Connector toevoegen
Voeg een connectorvorm toe aan de verzameling diavormen.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## Stap 5: Vormen verbinden met connectoren
Verbind de vormen met de connector.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## Stap 6: Connector omleiden
Roep reroute aan om automatisch het kortste pad tussen vormen in te stellen.
```java
connector.reroute();
```
## Stap 7: Presentatie opslaan
Sla de presentatie op nadat u de vormen met behulp van verbindingsstukken hebt verbonden.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Vergeet ten slotte niet om het Presentatie-object te verwijderen.
```java
if (input != null) input.dispose();
```
U hebt nu met succes vormen met elkaar verbonden met behulp van connectoren in PowerPoint met behulp van Aspose.Slides voor Java.

## Conclusie
In deze tutorial hebben we geleerd hoe je vormen met elkaar verbindt met behulp van connectoren in PowerPoint-presentaties met Aspose.Slides voor Java. Door deze eenvoudige stappen te volgen, kun je je presentaties verfraaien met visueel aantrekkelijke diagrammen en stroomdiagrammen.
## Veelgestelde vragen
### Kan ik het uiterlijk van connectoren in Aspose.Slides voor Java aanpassen?
Ja, u kunt diverse eigenschappen van aansluitingen, zoals kleur, lijnstijl en dikte, aanpassen aan uw presentatiebehoeften.
### Is Aspose.Slides voor Java compatibel met alle versies van PowerPoint?
Aspose.Slides voor Java ondersteunt verschillende PowerPoint-indelingen, waaronder PPTX, PPT en ODP.
### Kan ik meer dan twee vormen met één connector verbinden?
Ja, u kunt meerdere vormen met elkaar verbinden met behulp van de complexe connectoren van Aspose.Slides voor Java.
### Biedt Aspose.Slides voor Java ondersteuning voor het toevoegen van tekst aan vormen?
Jazeker, u kunt eenvoudig tekst toevoegen aan vormen en connectoren via een programma met Aspose.Slides voor Java.
### Is er een communityforum of ondersteuningskanaal beschikbaar voor Aspose.Slides voor Java-gebruikers?
Ja, u kunt nuttige bronnen vinden, vragen stellen en met andere gebruikers in contact komen op het Aspose.Slides-forum [hier](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}