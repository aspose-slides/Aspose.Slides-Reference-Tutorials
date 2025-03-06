---
title: Pas buitenste schaduweffecten toe in Java PowerPoint
linktitle: Pas buitenste schaduweffecten toe in Java PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u eenvoudig buitenste schaduweffecten kunt toepassen in Java PowerPoint-presentaties met behulp van Aspose.Slides met onze gedetailleerde, stapsgewijze handleiding.
weight: 11
url: /nl/java/java-powerpoint-animation-effects/apply-outer-shadow-effects-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Invoering
Om boeiende presentaties te maken, moet u vaak verschillende effecten toevoegen om de visuele aantrekkingskracht van uw dia's te vergroten. Eén zo'n effect is de buitenste schaduw, die ervoor kan zorgen dat uw elementen eruit springen en diepte aan uw inhoud toevoegt. In deze zelfstudie doorlopen we het proces van het toepassen van buitenste schaduweffecten op vormen in een PowerPoint-presentatie met behulp van Aspose.Slides voor Java.
## Vereisten
Voordat we in de stapsgewijze handleiding duiken, zorgen we ervoor dat u alles heeft wat u nodig heeft:
1.  Java Development Kit (JDK): Zorg ervoor dat JDK op uw computer is geïnstalleerd. Je kunt het downloaden van[De website van Oracle](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides voor Java Library: Download de nieuwste versie van[Aspose.Slides voor Java](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Gebruik een IDE zoals IntelliJ IDEA of Eclipse voor het schrijven en uitvoeren van uw Java-code.
4.  Een geldige Stel-licentie: u kunt een licentie kopen bij[Aspose](https://purchase.aspose.com/buy) of krijg een[tijdelijke licentie](https://purchase.aspose.com/temporary-license/) voor evaluatie.
## Pakketten importeren
Eerst moet u de benodigde pakketten voor Aspose.Slides importeren. Dit vormt de basis voor het gebruik van de krachtige functionaliteiten van de bibliotheek.
```java
import com.aspose.slides.*;
import java.awt.*;
import java.io.File;
```
Laten we het proces van het toepassen van buitenste schaduweffecten opsplitsen in beheersbare stappen:
## Stap 1: Stel de projectdirectory in
Voordat u begint met het schrijven van uw code, moet u de projectmap instellen waar uw PowerPoint-bestanden worden opgeslagen en geopend.
Zorg ervoor dat uw projectmap bestaat. Als dit niet het geval is, maakt u deze met de volgende code:
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
// Maak een directory aan als deze nog niet aanwezig is.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
## Stap 2: Initialiseer de presentatie
Nu moeten we de presentatie initialiseren waar we onze vormen en effecten toevoegen.

 Maak een nieuw exemplaar van de`Presentation` klas om met een nieuw PowerPoint-bestand te gaan werken.
```java
// Instantieer een PPTX-klasse
Presentation pres = new Presentation();
```
## Stap 3: Voeg een dia en vorm toe
Voeg vervolgens een dia toe aan uw presentatie en voeg vervolgens een vorm toe waarop u het schaduweffect gaat toepassen.
### Verwijzing naar de dia ophalen
Haal een verwijzing op naar de eerste dia in de presentatie.
```java
// Referentie van de dia opvragen
ISlide sld = pres.getSlides().get_Item(0);
```
### Voeg een AutoVorm toe
Voeg een rechthoekige AutoVorm toe aan de dia op opgegeven coördinaten.
```java
// Voeg een AutoVorm van het type Rechthoek toe
IAutoShape aShp = sld.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 150, 50);
```
## Stap 4: Pas de vorm aan
Voeg tekst toe aan uw vorm en pas de vulinstellingen aan om het schaduweffect beter zichtbaar te maken.
### Voeg TextFrame toe aan de vorm
Voeg tekst in de rechthoekige vorm in.
```java
// Voeg TextFrame toe aan de rechthoek
aShp.addTextFrame("Aspose TextBox");
```
### Vormvulling uitschakelen
Schakel de vulling van de vorm uit om de tekstschaduw te benadrukken.
```java
// Schakel vormvulling uit voor het geval we schaduw van tekst willen krijgen
aShp.getFillFormat().setFillType(FillType.NoFill);
```
## Stap 5: Pas het buitenste schaduweffect toe
Nu is het tijd om het buitenste schaduweffect op de vorm toe te passen.
### Schakel het buitenste schaduweffect in
Schakel het buitenste schaduweffect voor de vorm in.
```java
// Voeg buitenschaduw toe en stel alle noodzakelijke parameters in
aShp.getEffectFormat().enableOuterShadowEffect();
```
### Configureer schaduwparameters
Stel verschillende eigenschappen van de schaduw in, zoals vervagingsradius, richting, afstand, uitlijning en kleur.
```java
IOuterShadow shadow = aShp.getEffectFormat().getOuterShadowEffect();
shadow.setBlurRadius(4.0);
shadow.setDirection(45);
shadow.setDistance(3);
shadow.setRectangleAlign(RectangleAlignment.TopLeft);
shadow.getShadowColor().setColor(Color.BLACK);
```
## Stap 6: Sla de presentatie op
Sla ten slotte de presentatie op schijf op.
```java
//Schrijf de presentatie naar schijf
pres.save(dataDir + "pres_out.pptx", SaveFormat.Pptx);
```
## Stap 7: Gooi hulpbronnen weg
Zorg ervoor dat u bronnen vrijmaakt door het presentatieobject weg te gooien.
```java
// Hulpbronnen opruimen
if (pres != null) pres.dispose();
```
## Conclusie
En daar heb je het! U hebt met succes een buitenschaduweffect toegepast op een vorm in een PowerPoint-presentatie met Aspose.Slides voor Java. Dit effect kan de visuele aantrekkingskracht van uw dia's aanzienlijk vergroten, waardoor uw inhoud opvalt.
 Als u problemen ondervindt of verdere hulp nodig heeft, aarzel dan niet om de[Aspose.Slides-documentatie](https://reference.aspose.com/slides/java/) of bezoek de[Helpforum](https://forum.aspose.com/c/slides/11). Veel codeerplezier!
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige bibliotheek waarmee u PowerPoint-presentaties in Java-toepassingen kunt maken, manipuleren en converteren.
### Hoe kan ik een gratis proefversie van Aspose.Slides voor Java krijgen?
 U kunt een gratis proefversie downloaden van de[Aspose-website](https://releases.aspose.com/).
### Kan ik Aspose.Slides voor Java met elke IDE gebruiken?
Ja, u kunt Aspose.Slides voor Java gebruiken met elke Java-IDE zoals IntelliJ IDEA, Eclipse of NetBeans.
### Hoe krijg ik een tijdelijke licentie voor Aspose.Slides?
 U kunt een tijdelijke licentie verkrijgen bij de[Aspose-website](https://purchase.aspose.com/temporary-license/).
### Waar kan ik meer voorbeelden en documentatie voor Aspose.Slides vinden?
 Meer voorbeelden en gedetailleerde documentatie vindt u op de[Aspose.Slides documentatiepagina](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
