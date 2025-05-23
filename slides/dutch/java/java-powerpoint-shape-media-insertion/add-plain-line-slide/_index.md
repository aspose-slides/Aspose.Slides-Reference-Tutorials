---
"description": "Leer hoe je programmatisch een rechte lijn aan een PowerPoint-dia toevoegt met Aspose.Slides voor Java. Verhoog je productiviteit met deze stapsgewijze handleiding."
"linktitle": "Voeg een gewone lijn toe aan de dia"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Voeg een gewone lijn toe aan de dia"
"url": "/nl/java/java-powerpoint-shape-media-insertion/add-plain-line-slide/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Voeg een gewone lijn toe aan de dia

## Invoering
Aspose.Slides voor Java is een krachtige bibliotheek waarmee Java-ontwikkelaars programmatisch met PowerPoint-presentaties kunnen werken. Met Aspose.Slides kunt u eenvoudig PowerPoint-bestanden maken, wijzigen en converteren, waardoor u tijd en moeite bespaart. In deze tutorial laten we u zien hoe u een standaardlijn aan een dia in een PowerPoint-presentatie kunt toevoegen met Aspose.Slides voor Java.
## Vereisten
Voordat we beginnen, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
- Java Development Kit (JDK) op uw systeem geïnstalleerd
- Aspose.Slides voor Java-bibliotheek gedownload en toegevoegd aan uw Java-project
- Basiskennis van de programmeertaal Java

## Pakketten importeren
Om te beginnen moet je de benodigde pakketten in je Java-code importeren. Zo doe je dat:
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
import com.aspose.slides.ShapeType;

import java.io.File;
```
## Stap 1: De omgeving instellen
Maak eerst een nieuw Java-project aan en voeg de Aspose.Slides voor Java-bibliotheek toe aan het classpath van je project. Je kunt de bibliotheek downloaden van [hier](https://releases.aspose.com/slides/java/).
## Stap 2: Een nieuwe presentatie maken
Instantieer vervolgens de `Presentation` klas om een nieuwe PowerPoint-presentatie te maken.
```java
Presentation pres = new Presentation();
```
## Stap 3: Een dia toevoegen
Haal de eerste dia van de presentatie op en sla deze op in een variabele.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## Stap 4: Een lijnvorm toevoegen
Voeg nu een autovorm van tekstregel toe aan de dia.
```java
slide.getShapes().addAutoShape(ShapeType.Line, 50, 150, 300, 0);
```
## Stap 5: Sla de presentatie op
Sla ten slotte de presentatie op schijf op.
```java
pres.save("Your Document Directory/LineShape1_out.pptx", SaveFormat.Pptx);
```

## Conclusie
Gefeliciteerd! U hebt met succes een gewone lijn toegevoegd aan een dia in een PowerPoint-presentatie met Aspose.Slides voor Java. Met Aspose.Slides kunt u PowerPoint-bestanden eenvoudig programmatisch bewerken, wat een wereld aan mogelijkheden voor uw Java-toepassingen opent.

## Veelgestelde vragen
### Kan ik de eigenschappen van de lijnvorm aanpassen?
Ja, u kunt verschillende eigenschappen, zoals lijnkleur, breedte, stijl en meer, aanpassen met behulp van de Aspose.Slides API.
### Is Aspose.Slides compatibel met verschillende versies van PowerPoint?
Ja, Aspose.Slides ondersteunt verschillende PowerPoint-formaten, waaronder PPT, PPTX en andere, waardoor compatibiliteit tussen verschillende versies gegarandeerd is.
### Biedt Aspose.Slides ondersteuning voor het toevoegen van andere vormen dan lijnen?
Absoluut! Aspose.Slides biedt een breed scala aan vormen, waaronder rechthoeken, cirkels, pijlen en meer.
### Kan ik naast de lijnvorm ook tekst aan de dia toevoegen?
Ja, u kunt tekst, afbeeldingen en andere inhoud aan de dia toevoegen met behulp van de Aspose.Slides API.
### Is er een gratis proefversie beschikbaar voor Aspose.Slides?
Ja, u kunt een gratis proefversie van Aspose.Slides downloaden van [hier](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}