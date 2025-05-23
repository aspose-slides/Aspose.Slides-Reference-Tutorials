---
"description": "Leer hoe u een opgemaakte ellips in PowerPoint maakt met Aspose.Slides voor Java met onze gedetailleerde stapsgewijze handleiding."
"linktitle": "Maak een geformatteerde ellips in PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Maak een geformatteerde ellips in PowerPoint"
"url": "/nl/java/java-powerpoint-shape-formatting-geometry/create-formatted-ellipse-powerpoint/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Maak een geformatteerde ellips in PowerPoint

## Invoering
Welkom bij deze uitgebreide tutorial over het maken van een geformatteerde ellips in PowerPoint met Aspose.Slides voor Java. Aspose.Slides is een krachtige bibliotheek waarmee ontwikkelaars PowerPoint-bestanden programmatisch kunnen bewerken. Of u nu de diageneratie automatiseert of presentaties verrijkt met aangepaste vormen, deze handleiding begeleidt u bij elke stap, zodat u eenvoudig een perfect geformatteerde ellips aan uw dia's kunt toevoegen. Laten we eens kijken hoe we dit kunnen bereiken!
## Vereisten
Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK): Zorg ervoor dat u JDK 1.6 of hoger hebt geïnstalleerd.
2. Aspose.Slides voor Java: Download de nieuwste versie van [Aspose.Slides voor Java](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Gebruik een IDE zoals IntelliJ IDEA of Eclipse.
4. Basiskennis van Java: Kennis van Java-programmering is vereist.
## Pakketten importeren
Om Aspose.Slides te kunnen gebruiken, moet je de benodigde pakketten importeren. Zo doe je dat:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## Stap 1: Stel uw projectmap in
Eerst hebt u een map nodig om uw PowerPoint-bestanden in op te slaan.
### Directory aanmaken
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een map aan als deze nog niet bestaat.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
```
Zorg ervoor dat u vervangt `"Your Document Directory"` met het daadwerkelijke pad waar u uw bestanden wilt opslaan.
## Stap 2: Initialiseer de presentatie
Maak nu een exemplaar van de Presentation-klasse, die het PowerPoint-bestand vertegenwoordigt.
```java
// Instantieer de presentatieklasse die de PPTX vertegenwoordigt
Presentation pres = new Presentation();
```
## Stap 3: Ontvang de eerste dia
Selecteer vervolgens de eerste dia van de presentatie waaraan u de ellips wilt toevoegen.
```java
// Ontvang de eerste dia
ISlide sld = pres.getSlides().get_Item(0);
```
## Stap 4: Voeg een ellipsvorm toe
Voeg een automatische vorm van het ellipstype toe aan de dia.
```java
// Autovorm van ellipstype toevoegen
IShape shp = sld.getShapes().addAutoShape(ShapeType.Ellipse, 50, 150, 150, 50);
```
Hier, `50, 150, 150, 50` zijn de coördinaten en de grootte van de ellips (x-positie, y-positie, breedte, hoogte).
## Stap 5: Opmaak toepassen op de ellips
Pas nu wat opmaak toe op de ellips. We kiezen een effen opvulkleur en een lijnkleur.
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
Sla de presentatie ten slotte op in de door u opgegeven map.
```java
// Schrijf het PPTX-bestand naar schijf
pres.save(dataDir + "EllipseShp2_out.pptx", SaveFormat.Pptx);
```
## Stap 7: Het presentatieobject verwijderen
Verwijder het presentatieobject om bronnen vrij te maken.
```java
finally {
    if (pres != null) pres.dispose();
}
```
## Conclusie
Gefeliciteerd! Je hebt met succes een opgemaakte ellips gemaakt in een PowerPoint-presentatie met Aspose.Slides voor Java. Deze tutorial heeft je begeleid bij het opzetten van je project, het toevoegen van een ellips, het toepassen van opmaak en het opslaan van je presentatie. Met deze vaardigheden kun je nu je PowerPoint-dia's programmatisch verbeteren, waardoor je presentaties dynamischer en visueel aantrekkelijker worden.
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige bibliotheek waarmee ontwikkelaars programmatisch PowerPoint-presentaties kunnen maken, wijzigen en beheren.
### Kan ik Aspose.Slides voor Java met elke IDE gebruiken?
Ja, u kunt Aspose.Slides voor Java gebruiken met elke Java IDE zoals IntelliJ IDEA, Eclipse of NetBeans.
### Heb ik een licentie nodig voor Aspose.Slides?
Ja, Aspose.Slides is een commercieel product en je hebt een licentie nodig voor volledige functionaliteit. Je kunt een tijdelijke licentie krijgen. [hier](https://purchase.aspose.com/temporary-license/).
### Waar kan ik meer documentatie vinden over Aspose.Slides voor Java?
Gedetailleerde documentatie vindt u op Aspose.Slides voor Java [documentatiepagina](https://reference.aspose.com/slides/java/).
### Is er ondersteuning beschikbaar voor Aspose.Slides?
Ja, Aspose biedt ondersteuning via hun [forum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}