---
title: Voeg een ingesloten videoframe toe in PowerPoint
linktitle: Voeg een ingesloten videoframe toe in PowerPoint
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u videoframes in PowerPoint kunt insluiten met Aspose.Slides voor Java met deze stapsgewijze zelfstudie. Verbeter uw presentaties eenvoudig.
weight: 21
url: /nl/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Voeg een ingesloten videoframe toe in PowerPoint

## Invoering
Door video's aan uw PowerPoint-presentaties toe te voegen, kunnen ze aantrekkelijker en informatiever worden. Met Aspose.Slides voor Java kunt u eenvoudig video's rechtstreeks in uw dia's insluiten. In deze zelfstudie leiden we u stap voor stap door het proces, zodat u elk onderdeel van de code begrijpt en begrijpt hoe deze werkt. Of u nu een doorgewinterde ontwikkelaar bent of net begint, deze handleiding helpt u uw presentaties te verbeteren met ingesloten video's.
## Vereisten
Voordat u in de code duikt, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:
1. Java Development Kit (JDK): Zorg ervoor dat JDK op uw computer is geïnstalleerd.
2. Aspose.Slides voor Java: Download en installeer de Aspose.Slides voor Java-bibliotheek.
3. Integrated Development Environment (IDE): Gebruik een IDE zoals IntelliJ IDEA of Eclipse voor een betere ontwikkelervaring.
4. Videobestand: zorg dat u een videobestand heeft dat u in uw PowerPoint-presentatie wilt insluiten.
## Pakketten importeren
Eerst moet u de benodigde pakketten importeren om met Aspose.Slides te kunnen werken. Met deze importbewerkingen kunt u dia's, video's en presentatiebestanden beheren.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Stap 1: Stel uw omgeving in
Voordat u begint met coderen, moet u ervoor zorgen dat uw omgeving correct is ingesteld. Dit omvat het aanmaken van de benodigde mappen en het voorbereiden van het videobestand.
```java
// Het pad naar de documentenmap.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Maak een directory aan als deze nog niet aanwezig is.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Stap 2: Instantie van de presentatieklas
 Maak een exemplaar van de`Presentation` klas. Deze klasse vertegenwoordigt uw PowerPoint-bestand.
```java
// Instantieer de Presentation-klasse die de PPTX vertegenwoordigt
Presentation pres = new Presentation();
```
## Stap 3: Verkrijg de eerste dia
Ga naar de eerste dia in de presentatie waar u de video gaat insluiten.
```java
// Haal de eerste dia
ISlide sld = pres.getSlides().get_Item(0);
```
## Stap 4: Voeg de video toe aan de presentatie
Sluit het videobestand in de presentatie in. Zorg ervoor dat het videopad correct is opgegeven.
```java
// Video insluiten in presentatie
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Stap 5: Voeg videoframe toe aan dia
Maak een videoframe op de dia en stel de afmetingen en positie in.
```java
// Videoframe toevoegen
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Stap 6: Configureer videoframe-eigenschappen
Stel de video in op het videoframe en configureer de afspeelinstellingen zoals afspeelmodus en volume.
```java
// Stel video in op Videoframe
vf.setEmbeddedVideo(vid);
// Stel de afspeelmodus en het volume van de video in
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Stap 7: Sla de presentatie op
Sla de presentatie met de ingesloten video op in de door u opgegeven map.
```java
// Schrijf het PPTX-bestand naar schijf
pres.save(resultPath, SaveFormat.Pptx);
```
## Stap 8: Bronnen opruimen
Gooi ten slotte het presentatieobject weg om bronnen vrij te maken.
```java
// Gooi het presentatieobject weg
if (pres != null) pres.dispose();
```
## Conclusie
Het insluiten van een video in uw PowerPoint-presentaties met Aspose.Slides voor Java is een eenvoudig proces. Door de stappen in deze handleiding te volgen, kunt u uw presentaties verbeteren met boeiende video-inhoud. Vergeet niet dat oefening kunst baart, dus probeer verschillende video's in te sluiten en hun eigenschappen aan te passen om te zien wat het beste werkt voor uw behoeften.
## Veelgestelde vragen
### Kan ik meerdere video's in één dia insluiten?
Ja, u kunt meerdere video's in één dia insluiten door meerdere videoframes toe te voegen.
### Hoe kan ik het afspelen van de video regelen?
 U kunt het afspelen regelen met behulp van de`setPlayMode` En`setVolume` methoden van de`IVideoFrame` klas.
### Welke videoformaten worden ondersteund door Aspose.Slides?
Aspose.Slides ondersteunt verschillende videoformaten, waaronder MP4, AVI en WMV.
### Heb ik een licentie nodig om Aspose.Slides te gebruiken?
Ja, je hebt een geldige licentie nodig om Aspose.Slides te gebruiken. U kunt een tijdelijke licentie verkrijgen voor evaluatie.
### Kan ik de grootte en positie van het videoframe aanpassen?
Ja, u kunt de grootte en positie aanpassen door de juiste parameters in te stellen bij het toevoegen van het videoframe.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
