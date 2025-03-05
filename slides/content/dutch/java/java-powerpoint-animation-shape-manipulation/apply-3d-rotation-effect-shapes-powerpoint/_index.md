---
title: Pas het 3D-rotatie-effect toe op vormen in PowerPoint
linktitle: Pas het 3D-rotatie-effect toe op vormen in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u 3D-rotatie-effecten kunt toepassen op vormen in PowerPoint met behulp van Aspose.Slides voor Java met deze uitgebreide, stapsgewijze zelfstudie.
type: docs
weight: 12
url: /nl/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/
---
## Invoering
Bent u klaar om uw PowerPoint-presentaties naar een hoger niveau te tillen? Door 3D-rotatie-effecten toe te voegen, kunnen uw dia's dynamischer en boeiender worden. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze stapsgewijze zelfstudie laat u zien hoe u 3D-rotatie-effecten kunt toepassen op vormen in PowerPoint met behulp van Aspose.Slides voor Java. Laten we er meteen in duiken!
## Vereisten
Voordat we beginnen, zorg ervoor dat u over het volgende beschikt:
1.  Java Development Kit (JDK): Zorg ervoor dat JDK op uw systeem is geïnstalleerd. Je kunt het downloaden van de[Oracle-website](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides voor Java: Download de nieuwste versie van Aspose.Slides voor Java van de[download link](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Gebruik een IDE zoals IntelliJ IDEA of Eclipse voor codering.
4.  Een geldige licentie: Als u geen licentie heeft, kunt u een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) om de functies uit te proberen.
## Pakketten importeren
Laten we eerst de benodigde pakketten in uw Java-project importeren. Met deze invoer kunt u presentaties en vormen verwerken met Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Stap 1: Stel uw project in
Voordat u in de code duikt, stelt u uw projectomgeving in. Zorg ervoor dat u Aspose.Slides voor Java hebt toegevoegd aan de afhankelijkheden van uw project.
Voeg Aspose.Slides toe aan uw project:
1.  Download de Aspose.Slides JAR-bestanden van de[downloadpagina](https://releases.aspose.com/slides/java/).
2. Voeg deze JAR-bestanden toe aan het buildpad van uw project.
## Stap 2: Maak een nieuwe PowerPoint-presentatie
In deze stap gaan we een nieuwe PowerPoint-presentatie maken.
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een exemplaar van de presentatieklasse
Presentation pres = new Presentation();
```
Dit codefragment initialiseert een nieuw presentatieobject waaraan we onze vormen zullen toevoegen.
## Stap 3: voeg een rechthoekige vorm toe
Laten we vervolgens een rechthoekige vorm aan de eerste dia toevoegen.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Deze code voegt een rechthoekige vorm toe op de opgegeven positie en grootte op de eerste dia.
## Stap 4: Pas 3D-rotatie toe op de rechthoek
Laten we nu een 3D-rotatie-effect toepassen op de rechthoekige vorm.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Hier stellen we de diepte, camerarotatiehoeken, cameratype en verlichtingstype in om onze rechthoek een 3D-look te geven.
## Stap 5: Voeg een lijnvorm toe
Laten we nog een vorm, dit keer een lijn, aan de dia toevoegen.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Deze code plaatst een lijnvorm op de dia.
## Stap 6: Pas 3D-rotatie toe op de lijn
Ten slotte passen we een 3D-rotatie-effect toe op de lijnvorm.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Net als bij de rechthoek stellen we de 3D-eigenschappen voor de lijnvorm in.
## Stap 7: Sla de presentatie op
Nadat u uw vormen hebt toegevoegd en geconfigureerd, slaat u de presentatie op.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Deze code slaat uw presentatie op met de opgegeven bestandsnaam in het gewenste formaat.
## Conclusie
 Gefeliciteerd! U hebt met succes 3D-rotatie-effecten toegepast op vormen in een PowerPoint-presentatie met Aspose.Slides voor Java. Door deze stappen te volgen, kunt u visueel aantrekkelijke en dynamische presentaties maken. Voor verdere aanpassingen en meer geavanceerde functies raadpleegt u de[Aspose.Slides-documentatie](https://reference.aspose.com/slides/java/).
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige API voor het programmatisch maken, wijzigen en manipuleren van PowerPoint-presentaties.
### Kan ik Aspose.Slides voor Java gratis uitproberen?
 Ja, je kunt een[gratis proefperiode](https://releases.aspose.com/) of een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) om de functies te testen.
### Aan welke soorten vormen kan ik 3D-effecten toevoegen in Aspose.Slides?
kunt 3D-effecten toevoegen aan verschillende vormen, zoals rechthoeken, lijnen, ellipsen en aangepaste vormen.
### Hoe krijg ik ondersteuning voor Aspose.Slides voor Java?
 U kunt een bezoek brengen aan de[Helpforum](https://forum.aspose.com/c/slides/11) voor hulp en om eventuele problemen te bespreken.
### Kan ik Aspose.Slides voor Java gebruiken in commerciële projecten?
 Ja, maar u moet een licentie aanschaffen. Je kunt er een kopen bij de[aankooppagina](https://purchase.aspose.com/buy).