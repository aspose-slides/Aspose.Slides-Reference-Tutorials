---
title: Organisera diagramlayouttyp i SmartArt med Java
linktitle: Organisera diagramlayouttyp i SmartArt med Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Bemästra layouttyper för organiseringsdiagram i SmartArt med Java med Aspose.Slides, förbättra presentationsbilden utan ansträngning.
type: docs
weight: 13
url: /sv/java/java-powerpoint-smartart-manipulation/organize-chart-layout-type-smartart-java/
---
## Introduktion
den här handledningen går vi igenom processen att organisera diagramlayouttyp i SmartArt med hjälp av Java, speciellt med Aspose.Slides-biblioteket. SmartArt i presentationer kan avsevärt förbättra den visuella dragningskraften och klarheten i dina data, vilket gör det viktigt att behärska manipuleringen.
## Förutsättningar
Innan vi börjar, se till att du har följande:
1. Java Development Kit (JDK) installerat på ditt system.
2.  Aspose.Slides-biblioteket har laddats ner och ställts in. Om du inte redan har gjort det, ladda ner den från[här](https://releases.aspose.com/slides/java/).
3. Grundläggande förståelse för Java-programmering.

## Importera paket
Importera först de nödvändiga paketen:
```java
import com.aspose.slides.*;
```
Låt oss dela upp exemplet i flera steg:
## Steg 1: Initiera presentationsobjekt
```java
Presentation presentation = new Presentation();
```
Skapa ett nytt presentationsobjekt.
## Steg 2: Lägg till SmartArt till Slide
```java
ISmartArt smart = presentation.getSlides().get_Item(0).getShapes().addSmartArt(10, 10, 400, 300, SmartArtLayoutType.OrganizationChart);
```
Lägg till SmartArt till önskad bild med specificerade mått och layouttyp.
## Steg 3: Ställ in organisationsdiagramlayout
```java
smart.getNodes().get_Item(0).setOrganizationChartLayout(OrganizationChartLayoutType.LeftHanging);
```
Ställ in layouttyp för organisationsdiagram. I det här exemplet använder vi den Vänsterhängande layouten.
## Steg 4: Spara presentationen
```java
presentation.save(dataDir + "OrganizeChartLayoutType_out.pptx", SaveFormat.Pptx);
```
Spara presentationen med den organiserade diagramlayouten.

## Slutsats
Att bemästra organisationen av diagramlayouttyper i SmartArt med Java ger dig möjlighet att skapa visuellt engagerande presentationer med lätthet. Med Aspose.Slides blir processen strömlinjeformad och effektiv, så att du kan fokusera på att skapa effektfullt innehåll.
## FAQ's
### Är Aspose.Slides kompatibel med olika Java-utvecklingsmiljöer?
Ja, Aspose.Slides är kompatibel med olika Java-utvecklingsmiljöer, vilket säkerställer flexibilitet för utvecklare.
### Kan jag anpassa utseendet på SmartArt-element med Aspose.Slides?
Absolut, Aspose.Slides erbjuder omfattande anpassningsalternativ för SmartArt-element, vilket gör att du kan skräddarsy dem efter dina specifika krav.
### Erbjuder Aspose.Slides omfattande dokumentation för utvecklare?
Ja, utvecklare kan hänvisa till den detaljerade dokumentationen från Aspose.Slides för Java, som ger insikter om dess funktioner och användning.
### Finns det en testversion tillgänglig för Aspose.Slides?
Ja, du kan få tillgång till en gratis testversion av Aspose.Slides för att utforska dess funktioner innan du fattar ett köpbeslut.
### Var kan jag söka stöd för Aspose.Slides-relaterade frågor?
 För all hjälp eller frågor angående Aspose.Slides kan du besöka supportforumet[här](https://forum.aspose.com/c/slides/11).