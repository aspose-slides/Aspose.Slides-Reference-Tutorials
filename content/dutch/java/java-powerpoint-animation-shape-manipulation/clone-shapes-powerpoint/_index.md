---
title: Vormen klonen in PowerPoint
linktitle: Vormen klonen in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u vormen in PowerPoint-presentaties kunt klonen met Aspose.Slides voor Java. Stroomlijn uw workflow met deze eenvoudig te volgen tutorial.
type: docs
weight: 16
url: /nl/java/java-powerpoint-animation-shape-manipulation/clone-shapes-powerpoint/
---
## Invoering
In deze zelfstudie onderzoeken we hoe u vormen in PowerPoint-presentaties kunt klonen met Aspose.Slides voor Java. Door vormen te klonen kunt u bestaande vormen binnen een presentatie dupliceren, wat vooral handig kan zijn voor het maken van consistente lay-outs of het herhalen van elementen op dia's.
## Vereisten
Voordat we aan de slag gaan, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1.  Java Development Kit (JDK): Zorg ervoor dat Java Development Kit op uw systeem is geïnstalleerd. U kunt de nieuwste versie downloaden en installeren vanaf de[website](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides voor Java-bibliotheek: Download de Aspose.Slides voor Java-bibliotheek en neem deze op in uw Java-project. Je kunt de downloadlink vinden[hier](https://releases.aspose.com/slides/java/).

## Pakketten importeren
Om te beginnen moet u de benodigde pakketten in uw Java-project importeren. Deze pakketten bieden de functionaliteiten die nodig zijn om met PowerPoint-presentaties te werken met Aspose.Slides voor Java.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
```
## Stap 1: Laad de presentatie
 Eerst moet u de PowerPoint-presentatie laden met de vormen die u wilt klonen. Gebruik de`Presentation` class om de bronpresentatie te laden.
```java
String dataDir = "Your Document Directory";
Presentation srcPres = new Presentation(dataDir + "SourceFrame.pptx");
```
## Stap 2: Kloon de vormen
Vervolgens kloont u de vormen uit de bronpresentatie en voegt u ze toe aan een nieuwe dia in dezelfde presentatie. Dit houdt in dat u toegang krijgt tot de bronvormen, een nieuwe dia maakt en vervolgens de gekloonde vormen aan de nieuwe dia toevoegt.
```java
IShapeCollection sourceShapes = srcPres.getSlides().get_Item(0).getShapes();
ILayoutSlide blankLayout = srcPres.getMasters().get_Item(0).getLayoutSlides().getByType(SlideLayoutType.Blank);
ISlide destSlide = srcPres.getSlides().addEmptySlide(blankLayout);
IShapeCollection destShapes = destSlide.getShapes();
destShapes.addClone(sourceShapes.get_Item(1), 50, 150 + sourceShapes.get_Item(0).getHeight());
destShapes.addClone(sourceShapes.get_Item(2));
destShapes.insertClone(0, sourceShapes.get_Item(0), 50, 150);
```
## Stap 3: Sla de presentatie op
Sla ten slotte de gewijzigde presentatie met de gekloonde vormen op in een nieuw bestand.
```java
srcPres.save(dataDir + "CloneShape_out.pptx", SaveFormat.Pptx);
```

## Conclusie
Het klonen van vormen in PowerPoint-presentaties met Aspose.Slides voor Java is een eenvoudig proces dat u kan helpen de workflow voor het maken van uw presentaties te stroomlijnen. Door de stappen in deze zelfstudie te volgen, kunt u eenvoudig bestaande vormen dupliceren en deze indien nodig aanpassen.

## Veelgestelde vragen
### Kan ik vormen over verschillende dia's klonen?
Ja, u kunt vormen uit elke dia in de presentatie klonen en deze aan een andere dia toevoegen met Aspose.Slides voor Java.
### Zijn er beperkingen voor het klonen van vormen?
Hoewel Aspose.Slides voor Java robuuste kloonmogelijkheden biedt, worden complexe vormen of animaties mogelijk niet perfect gerepliceerd.
### Kan ik de gekloonde vormen wijzigen nadat ik ze aan een dia heb toegevoegd?
Absoluut, zodra de vormen zijn gekloond en aan een dia zijn toegevoegd, kunt u hun eigenschappen, stijl en inhoud naar wens aanpassen.
### Ondersteunt Aspose.Slides voor Java het klonen van andere elementen naast vormen?
Ja, u kunt dia's, tekst, afbeeldingen en andere elementen binnen een PowerPoint-presentatie klonen met Aspose.Slides voor Java.
### Is er een proefversie beschikbaar voor Aspose.Slides voor Java?
 Ja, u kunt een gratis proefversie van Aspose.Slides voor Java downloaden van de[website](https://releases.aspose.com/slides/java/).