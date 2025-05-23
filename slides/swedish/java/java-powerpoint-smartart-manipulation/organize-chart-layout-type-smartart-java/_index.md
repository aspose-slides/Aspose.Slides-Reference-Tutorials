---
"description": "Bemästra layouttyper för organisering av scheman i SmartArt med Java och Aspose.Slides, och förbättra presentationers visuella effekter utan ansträngning."
"linktitle": "Organisera diagramlayout Skriv i SmartArt med Java"
"second_title": "Aspose.Slides Java PowerPoint-bearbetnings-API"
"title": "Organisera diagramlayout Skriv i SmartArt med Java"
"url": "/sv/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Organisera diagramlayout Skriv i SmartArt med Java

## Introduktion
I den här handledningen går vi igenom processen att organisera diagramlayouter i SmartArt med hjälp av Java, särskilt med hjälp av Aspose.Slides-biblioteket. SmartArt i presentationer kan avsevärt förbättra den visuella attraktionskraften och tydligheten hos dina data, vilket gör det viktigt att behärska dess hantering.
## Förkunskapskrav
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.
2. Aspose.Slides-biblioteket har laddats ner och konfigurerats. Om du inte redan har gjort det, ladda ner det från [här](https://releases.aspose.com/slides/java/).
3. Grundläggande förståelse för Java-programmering.

## Importera paket
Importera först de nödvändiga paketen:
```java
import com.aspose.slides.*;
```
Låt oss dela upp exemplet i flera steg:
## Steg 1: Initiera presentationsobjektet
```java
Presentation presentation = new Presentation();
```
Skapa ett nytt presentationsobjekt.
## Steg 2: Lägg till SmartArt till bilden
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Lägg till SmartArt på önskad bild med angivna dimensioner och layouttyp.
## Steg 3: Ställ in organisationsschemalayout
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Ange layouttypen för organisationsschemat. I det här exemplet använder vi vänsterhängande layout.
## Steg 4: Spara presentationen
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Spara presentationen med den organiserade diagramlayouten.

## Slutsats
Att bemästra organisationen av diagramlayouttyper i SmartArt med hjälp av Java ger dig möjlighet att enkelt skapa visuellt engagerande presentationer. Med Aspose.Slides blir processen strömlinjeformad och effektiv, så att du kan fokusera på att skapa effektfullt innehåll.
## Vanliga frågor
### Är Aspose.Slides kompatibelt med olika Java-utvecklingsmiljöer?
Ja, Aspose.Slides är kompatibel med olika Java-utvecklingsmiljöer, vilket garanterar flexibilitet för utvecklare.
### Kan jag anpassa utseendet på SmartArt-element med hjälp av Aspose.Slides?
Absolut, Aspose.Slides erbjuder omfattande anpassningsalternativ för SmartArt-element, så att du kan skräddarsy dem efter dina specifika behov.
### Erbjuder Aspose.Slides omfattande dokumentation för utvecklare?
Ja, utvecklare kan hänvisa till den detaljerade dokumentationen som tillhandahålls av Aspose.Slides för Java, som ger insikter i dess funktioner och användning.
### Finns det en testversion tillgänglig för Aspose.Slides?
Ja, du kan få tillgång till en gratis testversion av Aspose.Slides för att utforska dess funktioner innan du fattar ett köpbeslut.
### Var kan jag söka support för Aspose.Slides-relaterade frågor?
För hjälp eller frågor gällande Aspose.Slides kan du besöka supportforumet. [här](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}