---
title: Lägg till inbäddad videoram i PowerPoint
linktitle: Lägg till inbäddad videoram i PowerPoint
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du bäddar in videoramar i PowerPoint med Aspose.Slides för Java med denna steg-för-steg handledning. Förbättra dina presentationer enkelt.
weight: 21
url: /sv/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduktion
Om du lägger till videor i dina PowerPoint-presentationer kan du göra dem mer engagerande och informativa. Med Aspose.Slides för Java kan du enkelt bädda in videor direkt i dina bilder. I den här handledningen går vi igenom processen steg-för-steg, så att du förstår varje del av koden och hur den fungerar. Oavsett om du är en erfaren utvecklare eller precis har börjat, hjälper den här guiden dig att förbättra dina presentationer med inbäddade videor.
## Förutsättningar
Innan du dyker in i koden, se till att du har följande förutsättningar på plats:
1. Java Development Kit (JDK): Se till att du har JDK installerat på din maskin.
2. Aspose.Slides for Java: Ladda ner och installera Aspose.Slides for Java-biblioteket.
3. Integrated Development Environment (IDE): Använd en IDE som IntelliJ IDEA eller Eclipse för bättre utvecklingsupplevelse.
4. Videofil: Ha en videofil som du vill bädda in i din PowerPoint-presentation.
## Importera paket
Först måste du importera de nödvändiga paketen för att arbeta med Aspose.Slides. Dessa importer hjälper dig att hantera bilder, videor och presentationsfiler.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Steg 1: Ställ in din miljö
Innan du börjar koda, se till att din miljö är korrekt inställd. Detta innebär att skapa de nödvändiga katalogerna och förbereda videofilen.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Skapa katalog om den inte redan finns.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Steg 2: Instantera presentationsklass
 Skapa en instans av`Presentation` klass. Den här klassen representerar din PowerPoint-fil.
```java
// Instantiate Presentation-klass som representerar PPTX
Presentation pres = new Presentation();
```
## Steg 3: Skaffa den första bilden
Gå till den första bilden i presentationen där du kommer att bädda in videon.
```java
// Få den första bilden
ISlide sld = pres.getSlides().get_Item(0);
```
## Steg 4: Lägg till videon i presentationen
Bädda in videofilen i presentationen. Se till att videosökvägen är korrekt angiven.
```java
// Bädda in video i presentationen
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Steg 5: Lägg till videoram till bild
Skapa en videoram på bilden och ställ in dess mått och position.
```java
// Lägg till videoram
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Steg 6: Konfigurera egenskaper för videoram
Ställ in videon på videoramen och konfigurera dess uppspelningsinställningar som uppspelningsläge och volym.
```java
// Ställ in video till videoram
vf.setEmbeddedVideo(vid);
// Ställ in uppspelningsläge och volym för videon
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Steg 7: Spara presentationen
Spara presentationen med den inbäddade videon i din angivna katalog.
```java
// Skriv PPTX-filen till disken
pres.save(resultPath, SaveFormat.Pptx);
```
## Steg 8: Rensa upp resurser
Släng slutligen presentationsobjektet för att frigöra resurser.
```java
// Kassera presentationsobjektet
if (pres != null) pres.dispose();
```
## Slutsats
Att bädda in en video i dina PowerPoint-presentationer med Aspose.Slides för Java är en enkel process. Genom att följa stegen som beskrivs i den här guiden kan du förbättra dina presentationer med engagerande videoinnehåll. Kom ihåg att övning ger färdighet, så försök bädda in olika videor och justera deras egenskaper för att se vad som fungerar bäst för dina behov.
## FAQ's
### Kan jag bädda in flera videor i en enda bild?
Ja, du kan bädda in flera videor i en enda bild genom att lägga till flera videorutor.
### Hur kan jag styra uppspelningen av videon?
 Du kan styra uppspelningen med hjälp av`setPlayMode` och`setVolume` metoder för`IVideoFrame` klass.
### Vilka videoformat stöds av Aspose.Slides?
Aspose.Slides stöder olika videoformat inklusive MP4, AVI och WMV.
### Behöver jag en licens för att använda Aspose.Slides?
Ja, du behöver en giltig licens för att använda Aspose.Slides. Du kan få en tillfällig licens för utvärdering.
### Kan jag anpassa storleken och placeringen av videoramen?
Ja, du kan anpassa storleken och positionen genom att ställa in lämpliga parametrar när du lägger till videoramen.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
