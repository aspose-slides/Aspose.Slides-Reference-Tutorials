---
"description": "Lär dig hur du bäddar in videobildrutor i PowerPoint med hjälp av Aspose.Slides för Java med den här steg-för-steg-handledningen. Förbättra dina presentationer enkelt."
"linktitle": "Lägg till inbäddad videoram i PowerPoint"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Lägg till inbäddad videoram i PowerPoint"
"url": "/sv/java/java-powerpoint-animation-shape-manipulation/add-embedded-video-frame-powerpoint/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Lägg till inbäddad videoram i PowerPoint

## Introduktion
Att lägga till videor i dina PowerPoint-presentationer kan göra dem mer engagerande och informativa. Med Aspose.Slides för Java kan du enkelt bädda in videor direkt i dina bilder. I den här handledningen guidar vi dig genom processen steg för steg, så att du förstår varje del av koden och hur den fungerar. Oavsett om du är en erfaren utvecklare eller precis har börjat, hjälper den här guiden dig att förbättra dina presentationer med inbäddade videor.
## Förkunskapskrav
Innan du går in i koden, se till att du har följande förutsättningar på plats:
1. Java Development Kit (JDK): Se till att du har JDK installerat på din dator.
2. Aspose.Slides för Java: Ladda ner och installera Aspose.Slides för Java-biblioteket.
3. Integrerad utvecklingsmiljö (IDE): Använd en IDE som IntelliJ IDEA eller Eclipse för bättre utvecklingsupplevelse.
4. Videofil: Har du en videofil som du vill bädda in i din PowerPoint-presentation.
## Importera paket
Först måste du importera de paket som krävs för att fungera med Aspose.Slides. Dessa importer hjälper dig att hantera bilder, videor och presentationsfiler.
```java
import com.aspose.slides.*;

import java.io.File;
import java.io.FileInputStream;
import java.io.FileNotFoundException;
```
## Steg 1: Konfigurera din miljö
Innan du börjar koda, se till att din miljö är korrekt konfigurerad. Detta innebär att skapa nödvändiga kataloger och förbereda videofilen.
```java
// Sökvägen till dokumentkatalogen.
String dataDir = "Your Document Directory";
String videoDir = "Path to Your Video Directory";
String resultPath = "Path to Save Result" + "VideoFrame_out.pptx";
// Skapa katalog om den inte redan finns.
boolean isExists = new File(dataDir).exists();
if (!isExists) new File(dataDir).mkdirs();
```
## Steg 2: Instansiera presentationsklassen
Skapa en instans av `Presentation` klass. Den här klassen representerar din PowerPoint-fil.
```java
// Instansiera Presentation-klassen som representerar PPTX
Presentation pres = new Presentation();
```
## Steg 3: Hämta den första bilden
Gå till den första bilden i presentationen där du ska bädda in videon.
```java
// Hämta den första bilden
ISlide sld = pres.getSlides().get_Item(0);
```
## Steg 4: Lägg till videon i presentationen
Bädda in videofilen i presentationen. Se till att sökvägen till videon är korrekt angiven.
```java
// Bädda in video i presentationen
IVideo vid = pres.getVideos().addVideo(new FileInputStream(videoDir + "Wildlife.mp4"), LoadingStreamBehavior.ReadStreamAndRelease);
```
## Steg 5: Lägg till videobildruta till bild
Skapa en videobildruta på bilden och ange dess dimensioner och position.
```java
// Lägg till videobildruta
IVideoFrame vf = sld.getShapes().addVideoFrame(50, 150, 300, 350, vid);
```
## Steg 6: Konfigurera egenskaper för videobildruta
Ställ in videon på videobildrutan och konfigurera dess uppspelningsinställningar som uppspelningsläge och volym.
```java
// Ställ in video till videobildruta
vf.setEmbeddedVideo(vid);
// Ställ in uppspelningsläge och volym för videon
vf.setPlayMode(VideoPlayModePreset.Auto);
vf.setVolume(AudioVolumeMode.Loud);
```
## Steg 7: Spara presentationen
Spara presentationen med den inbäddade videon i den angivna katalogen.
```java
// Skriv PPTX-filen till disken
pres.save(resultPath, SaveFormat.Pptx);
```
## Steg 8: Rensa upp resurser
Slutligen, kassera presentationsobjektet för att frigöra resurser.
```java
// Kassera presentationsobjektet
if (pres != null) pres.dispose();
```
## Slutsats
Att bädda in en video i dina PowerPoint-presentationer med Aspose.Slides för Java är en enkel process. Genom att följa stegen som beskrivs i den här guiden kan du förbättra dina presentationer med engagerande videoinnehåll. Kom ihåg att övning ger färdighet, så prova att bädda in olika videor och justera deras egenskaper för att se vad som fungerar bäst för dina behov.
## Vanliga frågor
### Kan jag bädda in flera videor i en enda bild?
Ja, du kan bädda in flera videor i en enda bild genom att lägga till flera videobildrutor.
### Hur kan jag styra uppspelningen av videon?
Du kan styra uppspelningen med hjälp av `setPlayMode` och `setVolume` metoderna för `IVideoFrame` klass.
### Vilka videoformat stöds av Aspose.Slides?
Aspose.Slides stöder olika videoformat, inklusive MP4, AVI och WMV.
### Behöver jag en licens för att använda Aspose.Slides?
Ja, du behöver en giltig licens för att använda Aspose.Slides. Du kan få en tillfällig licens för utvärdering.
### Kan jag anpassa storleken och positionen för videobildrutan?
Ja, du kan anpassa storleken och positionen genom att ställa in lämpliga parametrar när du lägger till videobildrutan.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}