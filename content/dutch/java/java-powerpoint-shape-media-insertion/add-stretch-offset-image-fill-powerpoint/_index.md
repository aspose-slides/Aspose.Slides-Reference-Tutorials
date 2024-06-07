---
title: Voeg rekverschuiving toe voor afbeeldingsvulling in PowerPoint
linktitle: Voeg rekverschuiving toe voor afbeeldingsvulling in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u een rekverschuiving kunt toevoegen voor afbeeldingsinvulling in PowerPoint-presentaties met behulp van Aspose.Slides voor Java. Inclusief stap-voor-stap handleiding.
type: docs
weight: 16
url: /nl/java/java-powerpoint-shape-media-insertion/add-stretch-offset-image-fill-powerpoint/
---
## Invoering
In deze zelfstudie leert u hoe u Aspose.Slides voor Java kunt gebruiken om een uitrekbare offset toe te voegen voor het opvullen van afbeeldingen in PowerPoint-presentaties. Met deze functie kunt u afbeeldingen in uw dia's manipuleren, waardoor u meer controle krijgt over hun uiterlijk.
## Vereisten
Zorg ervoor dat u over het volgende beschikt voordat u begint:
1. Java Development Kit (JDK) op uw systeem geïnstalleerd.
2. Aspose.Slides voor Java-bibliotheek gedownload en ingesteld in uw Java-project.
## Pakketten importeren
Importeer om te beginnen de benodigde pakketten in uw Java-project:
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
## Stap 1: Stel uw documentenmap in
Definieer de map waarin uw PowerPoint-document zich bevindt:
```java
String dataDir = "Your Document Directory";
```
## Stap 2: Maak een presentatieobject
Instantieer de klasse Presentation om het PowerPoint-bestand weer te geven:
```java
Presentation pres = new Presentation();
```
## Stap 3: Afbeelding toevoegen aan dia
Haal de eerste dia op en voeg er een afbeelding aan toe:
```java
ISlide sld = pres.getSlides().get_Item(0);
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx = pres.getImages().addImage(img);
```
## Stap 4: Voeg een fotolijst toe
Maak een fotolijst met de afmetingen die overeenkomen met de afbeelding:
```java
sld.getShapes().addPictureFrame(ShapeType.Rectangle, 50, 150, imgx.getWidth(), imgx.getHeight(), imgx);
```
## Stap 5: Sla de presentatie op
Sla het gewijzigde PowerPoint-bestand op:
```java
pres.save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```

## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u een rekverschuiving kunt toevoegen voor het opvullen van afbeeldingen in PowerPoint met behulp van Aspose.Slides voor Java. Deze functie opent een wereld aan mogelijkheden om uw presentaties te verbeteren met aangepaste afbeeldingen.
## Veelgestelde vragen
### Kan ik deze methode gebruiken om afbeeldingen toe te voegen aan specifieke dia's in een presentatie?
Ja, u kunt de dia-index opgeven wanneer u het diaobject ophaalt om een specifieke dia te targeten.
### Ondersteunt Aspose.Slides voor Java naast JPEG ook andere afbeeldingsformaten?
Ja, Aspose.Slides voor Java ondersteunt verschillende afbeeldingsformaten, waaronder onder meer PNG, GIF en BMP.
### Is er een limiet aan de grootte van de afbeeldingen die ik met deze methode kan toevoegen?
Aspose.Slides voor Java kan afbeeldingen van verschillende formaten verwerken, maar het wordt aanbevolen om afbeeldingen te optimaliseren voor betere prestaties in presentaties.
### Kan ik extra effecten of transformaties op de afbeeldingen toepassen nadat ik ze aan de dia's heb toegevoegd?
Ja, u kunt een breed scala aan effecten en transformaties op afbeeldingen toepassen met behulp van de uitgebreide API van Aspose.Slides voor Java.
### Waar kan ik meer bronnen en ondersteuning vinden voor Aspose.Slides voor Java?
 U kunt een bezoek brengen aan de[Aspose.Slides voor Java-documentatie](https://reference.aspose.com/slides/java/) voor gedetailleerde gidsen en verken de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11) voor gemeenschapssteun.