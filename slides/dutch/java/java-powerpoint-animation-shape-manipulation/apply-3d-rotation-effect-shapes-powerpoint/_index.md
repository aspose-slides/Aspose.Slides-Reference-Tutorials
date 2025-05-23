---
"description": "Leer hoe u 3D-rotatie-effecten op vormen in PowerPoint toepast met Aspose.Slides voor Java met deze uitgebreide, stapsgewijze zelfstudie."
"linktitle": "3D-rotatie-effect toepassen op vormen in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "3D-rotatie-effect toepassen op vormen in PowerPoint"
"url": "/nl/java/java-powerpoint-animation-shape-manipulation/apply-3d-rotation-effect-shapes-powerpoint/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# 3D-rotatie-effect toepassen op vormen in PowerPoint

## Invoering
Ben je klaar om je PowerPoint-presentaties naar een hoger niveau te tillen? Door 3D-rotatie-effecten toe te voegen, worden je dia's dynamischer en aantrekkelijker. Of je nu een ervaren ontwikkelaar bent of net begint, deze stapsgewijze tutorial laat je zien hoe je 3D-rotatie-effecten toepast op vormen in PowerPoint met Aspose.Slides voor Java. Laten we er meteen mee aan de slag gaan!
## Vereisten
Voordat we beginnen, zorg ervoor dat u het volgende heeft geregeld:
1. Java Development Kit (JDK): Zorg ervoor dat de JDK op uw systeem is geïnstalleerd. U kunt deze downloaden van de [Oracle-website](https://www.oracle.com/java/technologies/javase-downloads.html).
2. Aspose.Slides voor Java: Download de nieuwste versie van Aspose.Slides voor Java van de [downloadlink](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Gebruik een IDE zoals IntelliJ IDEA of Eclipse voor het coderen.
4. Een geldig rijbewijs: Als u geen rijbewijs heeft, kunt u een [tijdelijke licentie](https://purchase.aspose.com/temporary-license/) om de functies uit te proberen.
## Pakketten importeren
Laten we eerst de benodigde pakketten in je Java-project importeren. Deze imports helpen je bij het verwerken van presentaties en vormen met Aspose.Slides.
```java
import com.aspose.slides.*;

```
## Stap 1: Stel uw project in
Voordat je de code induikt, moet je je projectomgeving instellen. Zorg ervoor dat je Aspose.Slides voor Java aan de afhankelijkheden van je project hebt toegevoegd.
Voeg Aspose.Slides toe aan uw project:
1. Download de Aspose.Slides JAR-bestanden van de [downloadpagina](https://releases.aspose.com/slides/java/).
2. Voeg deze JAR-bestanden toe aan het buildpad van uw project.
## Stap 2: Een nieuwe PowerPoint-presentatie maken
In deze stap maken we een nieuwe PowerPoint-presentatie.
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Een exemplaar van de presentatieklasse maken
Presentation pres = new Presentation();
```
Dit codefragment initialiseert een nieuw presentatieobject waaraan we onze vormen gaan toevoegen.
## Stap 3: Voeg een rechthoekige vorm toe
Laten we nu een rechthoekige vorm aan de eerste dia toevoegen.
```java
IShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 30, 30, 200, 200);
```
Met deze code wordt op de eerste dia een rechthoekige vorm op de opgegeven positie en grootte toegevoegd.
## Stap 4: 3D-rotatie toepassen op de rechthoek
Laten we nu een 3D-rotatie-effect toepassen op de rechthoekige vorm.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(40, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Hier stellen we de diepte, de rotatiehoek van de camera, het cameratype en het belichtingstype in om onze rechthoek een 3D-uitstraling te geven.
## Stap 5: Een lijnvorm toevoegen
Laten we nog een vorm aan de dia toevoegen, dit keer een lijn.
```java
autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Line, 30, 300, 200, 200);
```
Deze code plaatst een lijnvorm op de dia.
## Stap 6: 3D-rotatie toepassen op de lijn
Ten slotte passen we een 3D-rotatie-effect toe op de lijnvorm.
```java
autoShape.getThreeDFormat().setDepth((short) 6);
autoShape.getThreeDFormat().getCamera().setRotation(0, 35, 20);
autoShape.getThreeDFormat().getCamera().setCameraType(CameraPresetType.IsometricLeftUp);
autoShape.getThreeDFormat().getLightRig().setLightType(LightRigPresetType.Balanced);
```
Vergelijkbaar met de rechthoek stellen we de 3D-eigenschappen voor de lijnvorm in.
## Stap 7: Sla de presentatie op
Nadat u de vormen hebt toegevoegd en geconfigureerd, slaat u de presentatie op.
```java
pres.save(dataDir + "Rotation_out.pptx", SaveFormat.Pptx);
```
Met deze code wordt uw presentatie opgeslagen met de opgegeven bestandsnaam en in het gewenste formaat.
## Conclusie
Gefeliciteerd! Je hebt met succes 3D-rotatie-effecten toegepast op vormen in een PowerPoint-presentatie met Aspose.Slides voor Java. Door deze stappen te volgen, kun je visueel aantrekkelijke en dynamische presentaties maken. Raadpleeg de [Aspose.Slides-documentatie](https://reference.aspose.com/slides/java/).
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige API waarmee u PowerPoint-presentaties programmatisch kunt maken, wijzigen en manipuleren.
### Kan ik Aspose.Slides voor Java gratis uitproberen?
Ja, je kunt een [gratis proefperiode](https://releases.aspose.com/) of een [tijdelijke licentie](https://purchase.aspose.com/temporary-license/) om de functies te testen.
### Aan welke soorten vormen kan ik 3D-effecten toevoegen in Aspose.Slides?
U kunt 3D-effecten toevoegen aan verschillende vormen, zoals rechthoeken, lijnen, ellipsen en aangepaste vormen.
### Hoe krijg ik ondersteuning voor Aspose.Slides voor Java?
kunt de [ondersteuningsforum](https://forum.aspose.com/c/slides/11) voor hulp en om eventuele problemen te bespreken.
### Kan ik Aspose.Slides voor Java gebruiken in commerciële projecten?
Ja, maar je moet een licentie aanschaffen. Je kunt er een kopen bij de [aankooppagina](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}