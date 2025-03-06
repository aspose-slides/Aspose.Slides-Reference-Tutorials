---
title: Gebruik ShapeUtil voor geometrische vorm in PowerPoint
linktitle: Gebruik ShapeUtil voor geometrische vorm in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Maak aangepaste vormen in PowerPoint met Aspose.Slides voor Java. Volg deze stapsgewijze handleiding om uw presentaties te verbeteren.
weight: 23
url: /nl/java/java-powerpoint-shape-formatting-geometry/use-shapeutil-geometry-shape-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Invoering
Voor het maken van visueel aantrekkelijke PowerPoint-presentaties is vaak meer nodig dan alleen het gebruik van standaardvormen en tekst. Stelt u zich eens voor dat u aangepaste vormen en tekstpaden rechtstreeks aan uw dia's kunt toevoegen, waardoor de visuele impact van uw presentatie wordt vergroot. Met Aspose.Slides voor Java kunt u dit eenvoudig bereiken. Deze tutorial begeleidt u bij het gebruik van de`ShapeUtil` klasse om geometrische vormen te maken in PowerPoint-presentaties. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze stapsgewijze handleiding helpt u de kracht van Aspose.Slides voor Java te benutten om verbluffende, op maat gemaakte inhoud te creëren.
## Vereisten
Voordat we in de tutorial duiken, zijn er een paar dingen die je nodig hebt:
1. Java Development Kit (JDK): Zorg ervoor dat JDK 8 of hoger op uw computer is geïnstalleerd.
2.  Aspose.Slides voor Java: Download de nieuwste versie van de[downloadpagina](https://releases.aspose.com/slides/java/).
3. Ontwikkelomgeving: Gebruik elke Java IDE zoals IntelliJ IDEA, Eclipse of NetBeans.
4.  Tijdelijke licentie: verkrijg een gratis tijdelijke licentie van[De tijdelijke licentiepagina van Aspose](https://purchase.aspose.com/temporary-license/) om de volledige functionaliteit van Aspose.Slides voor Java te ontgrendelen.
## Pakketten importeren
Om aan de slag te gaan, moet u de benodigde pakketten importeren om met Aspose.Slides en Java AWT (Abstract Window Toolkit) te werken:
```java
import com.aspose.slides.*;

import java.awt.*;
import java.awt.Shape;
import java.awt.font.GlyphVector;
import java.awt.image.BufferedImage;
```
## Stap 1: Uw project opzetten
Stel eerst uw Java-project in en voeg Aspose.Slides voor Java toe aan de afhankelijkheden van uw project. U kunt dit doen door de JAR-bestanden rechtstreeks toe te voegen of door een buildtool zoals Maven of Gradle te gebruiken.
## Stap 2: Maak een nieuwe presentatie
Begin met het maken van een nieuw PowerPoint-presentatieobject. Dit object is het canvas waarop u uw aangepaste vormen toevoegt.
```java
Presentation pres = new Presentation();
```
## Stap 3: voeg een rechthoekige vorm toe
Voeg vervolgens een rechthoekige basisvorm toe aan de eerste dia van de presentatie. Deze vorm zal later worden aangepast om een aangepast geometriepad op te nemen.
```java
GeometryShape shape = (GeometryShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 300, 100);
```
## Stap 4: Haal het geometriepad op en wijzig het
 Haal het geometrische pad van de rechthoekige vorm op en wijzig de vulmodus in`None`. Deze stap is cruciaal omdat u dit pad hiermee kunt combineren met een ander aangepast geometriepad.
```java
IGeometryPath originalPath = shape.getGeometryPaths()[0];
originalPath.setFillMode(PathFillModeType.None);
```
## Stap 5: Maak een aangepast geometriepad op basis van tekst
Maak nu een aangepast geometriepad op basis van tekst. Dit omvat het converteren van een tekstreeks naar een grafisch pad en het vervolgens converteren van dat pad naar een geometrisch pad.
```java
Shape graphicsPath = generateShapeFromText(new java.awt.Font("Arial", Font.PLAIN, 40), "Text in shape");
IGeometryPath textPath = ShapeUtil.graphicsPathToGeometryPath(graphicsPath);
textPath.setFillMode(PathFillModeType.Normal);
```
## Stap 6: Combineer de geometrische paden
Combineer het originele geometriepad met het nieuwe op tekst gebaseerde geometriepad en stel deze combinatie in op de vorm.
```java
shape.setGeometryPaths(new IGeometryPath[]{originalPath, textPath});
```
## Stap 7: Sla de presentatie op
Sla ten slotte de gewijzigde presentatie op in een bestand. Er wordt een PowerPoint-bestand met uw aangepaste vormen uitgevoerd.
```java
String resultPath = "GeometryShapeUsingShapeUtil.pptx";
pres.save(resultPath, SaveFormat.Pptx);
pres.dispose();
```
## Conclusie
Gefeliciteerd! U hebt zojuist een aangepaste geometrische vorm gemaakt in een PowerPoint-presentatie met Aspose.Slides voor Java. Deze tutorial begeleidt u bij elke stap, van het opzetten van uw project tot het genereren en combineren van geometriepaden. Door deze technieken onder de knie te krijgen, kunt u unieke en opvallende elementen aan uw presentaties toevoegen, waardoor deze opvallen.
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige API voor het werken met PowerPoint-bestanden in Java. Hiermee kunt u programmatisch presentaties maken, wijzigen en converteren.
### Hoe installeer ik Aspose.Slides voor Java?
 U kunt de nieuwste versie downloaden van de[downloadpagina](https://releases.aspose.com/slides/java/) en voeg de JAR-bestanden toe aan uw project.
### Kan ik Aspose.Slides gratis gebruiken?
Aspose.Slides biedt een gratis proefversie, die u kunt downloaden[hier](https://releases.aspose.com/)Voor volledige functionaliteit moet u een licentie aanschaffen.
### Wat is het gebruik van de ShapeUtil-klasse?
 De`ShapeUtil` klasse in Aspose.Slides biedt hulpprogramma's voor het werken met vormen, zoals het converteren van grafische paden naar geometrische paden.
### Waar kan ik ondersteuning krijgen voor Aspose.Slides?
 U kunt ondersteuning krijgen van de[Aspose.Slides-forum](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
