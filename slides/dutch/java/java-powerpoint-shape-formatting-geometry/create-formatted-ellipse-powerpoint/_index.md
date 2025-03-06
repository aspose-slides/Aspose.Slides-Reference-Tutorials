---
title: Maak een opgemaakte ellips in PowerPoint
linktitle: Maak een opgemaakte ellips in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u een opgemaakte ellips in PowerPoint maakt met Aspose.Slides voor Java met onze gedetailleerde stapsgewijze handleiding.
weight: 17
url: /nl/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Invoering
Welkom bij deze uitgebreide tutorial over het maken van een opgemaakte ellips in PowerPoint met behulp van Aspose.Slides voor Java. Aspose.Slides is een krachtige bibliotheek waarmee ontwikkelaars PowerPoint-bestanden programmatisch kunnen manipuleren. Of u nu het genereren van dia's automatiseert of presentaties verbetert met aangepaste vormen, deze gids begeleidt u bij elke stap, zodat u gemakkelijk een perfect opgemaakte ellips aan uw dia's kunt toevoegen. Laten we erin duiken en kijken hoe we dit kunnen bereiken!
## Vereisten
Voordat we beginnen, zorg ervoor dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK): Zorg ervoor dat JDK 1.6 of hoger is geïnstalleerd.
2.  Aspose.Slides voor Java: Download de nieuwste versie van[Aspose.Slides voor Java](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Gebruik een IDE zoals IntelliJ IDEA of Eclipse.
4. Basiskennis van Java: Bekendheid met programmeren in Java is vereist.
## Pakketten importeren
Om Aspose.Slides te gaan gebruiken, moet u de benodigde pakketten importeren. Hier ziet u hoe u het kunt doen:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Stap 1: Stel uw projectdirectory in
Ten eerste hebt u een map nodig om uw PowerPoint-bestanden op te slaan.
### Maak een map
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een directory aan als deze nog niet aanwezig is.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
 Zorg ervoor dat u vervangt`"Your Document Directory"` met het daadwerkelijke pad waar u uw bestanden wilt opslaan.
## Stap 2: Initialiseer de presentatie
Instantieer nu de klasse Presentation, die het PowerPoint-bestand vertegenwoordigt.
```java
// Instantieer de Presentation-klasse die de PPTX vertegenwoordigt
Presentation pres = new Presentation();
```
## Stap 3: Verkrijg de eerste dia
Haal vervolgens de eerste dia uit de presentatie waar u de ellips gaat toevoegen.
```java
// Haal de eerste dia
ISlide sld = pres.getSlides().get_Item(0);
```
## Stap 4: Voeg een ellipsvorm toe
Voeg een automatische vorm van het ellipstype toe aan de dia.
```java
// Voeg een autovorm van het ellipstype toe
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
 Hier,`50, 150, 150, 50` zijn de coördinaten en de grootte van de ellips (x-positie, y-positie, breedte, hoogte).
## Stap 5: Pas opmaak toe op de ellips
Pas nu wat opmaak toe op de ellips. We stellen een effen vulkleur en een lijnkleur in.
### Vulkleur instellen
```java
// Pas wat opmaak toe op de ellipsvorm
shp.getFillFormat().setFillType(FillType.Solid);
shp.getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Chocolate));
```
### Lijnkleur en -breedte instellen
```java
// Pas wat opmaak toe op de lijn van Ellipse
shp.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp.getLineFormat().setWidth(5);
```
## Stap 6: Sla de presentatie op
Sla ten slotte de presentatie op in de door u opgegeven map.
```java
// Schrijf het PPTX-bestand naar schijf
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Stap 7: Gooi het presentatieobject weg
Gooi het presentatieobject weg om bronnen vrij te maken.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Conclusie
Gefeliciteerd! U hebt met succes een opgemaakte ellips in een PowerPoint-presentatie gemaakt met Aspose.Slides voor Java. In deze zelfstudie leert u hoe u uw project instelt, een ellips toevoegt, opmaak toepast en uw presentatie opslaat. Met deze vaardigheden kunt u uw PowerPoint-dia's nu programmatisch verbeteren, waardoor uw presentaties dynamischer en visueel aantrekkelijker worden.
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige bibliotheek waarmee ontwikkelaars PowerPoint-presentaties programmatisch kunnen maken, wijzigen en beheren.
### Kan ik Aspose.Slides voor Java met elke IDE gebruiken?
Ja, u kunt Aspose.Slides voor Java gebruiken met elke Java-IDE zoals IntelliJ IDEA, Eclipse of NetBeans.
### Heb ik een licentie nodig voor Aspose.Slides?
Ja, Aspose.Slides is een commercieel product en je hebt een licentie nodig voor volledige functionaliteit. U kunt een tijdelijke licentie krijgen[hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik meer documentatie vinden over Aspose.Slides voor Java?
 Gedetailleerde documentatie vindt u op Aspose.Slides voor Java[documentatiepagina](https://reference.aspose.com/slides/java/).
### Is er ondersteuning beschikbaar voor Aspose.Slides?
 Ja, Aspose biedt ondersteuning via hun[forum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
