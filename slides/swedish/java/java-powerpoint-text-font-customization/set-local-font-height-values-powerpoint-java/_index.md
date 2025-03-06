---
title: Ställ in lokala teckensnittshöjdvärden i PowerPoint med Java
linktitle: Ställ in lokala teckensnittshöjdvärden i PowerPoint med Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du justerar teckensnittshöjder i PowerPoint-presentationer med Java med Aspose.Slides. Förbättra textformateringen i dina bilder utan ansträngning.
weight: 17
url: /sv/java/java-powerpoint-text-font-customization/set-local-font-height-values-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Introduktion
I den här handledningen kommer du att lära dig hur du manipulerar teckensnittshöjder på olika nivåer i PowerPoint-presentationer med Aspose.Slides för Java. Att kontrollera teckenstorlekar är avgörande för att skapa visuellt tilltalande och strukturerade presentationer. Vi kommer att gå igenom steg-för-steg-exempel för att illustrera hur du ställer in teckensnittshöjder för olika textelement.
## Förutsättningar
Innan du börjar, se till att du har följande:
- Java Development Kit (JDK) installerat på ditt system
-  Aspose.Slides för Java-bibliotek. Du kan ladda ner den[här](https://releases.aspose.com/slides/java/).
- En grundläggande förståelse för Java-programmering och PowerPoint-presentationer
## Importera paket
Se till att inkludera de nödvändiga Aspose.Slides-paketen i din Java-fil:
```java
import com.aspose.slides.*;
```
## Steg 1: Initiera ett presentationsobjekt
Skapa först ett nytt PowerPoint-presentationsobjekt:
```java
Presentation pres = new Presentation();
```
## Steg 2: Lägg till en form och textram
Lägg till en automatisk form med en textram till den första bilden:
```java
IAutoShape newShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 100, 100, 400, 75, false);
newShape.addTextFrame("");
```
## Steg 3: Skapa textdelar
Definiera textdelar med olika teckensnittshöjder:
```java
IPortion portion0 = new Portion("Sample text with first portion");
IPortion portion1 = new Portion(" and second portion.");
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion0);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().add(portion1);
```
## Steg 4: Ställ in teckensnittshöjder
Ställ in teckensnittshöjder på olika nivåer:
```java
pres.getDefaultTextStyle().getLevel(0).getDefaultPortionFormat().setFontHeight(24);
newShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().getDefaultPortionFormat().setFontHeight(40);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0).getPortionFormat().setFontHeight(55);
newShape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(1).getPortionFormat().setFontHeight(18);
```
## Steg 5: Spara presentationen
Spara den ändrade presentationen till en fil:
```java
pres.save("YourOutputDirectory/SetLocalFontHeightValues.pptx", SaveFormat.Pptx);
```

## Slutsats
Denna handledning demonstrerade hur man justerar teckensnittshöjder i PowerPoint-bilder programmatiskt med Aspose.Slides för Java. Genom att manipulera teckenstorlekar på olika nivåer (presentationsövergripande, stycke och del) kan du uppnå exakt kontroll över textformateringen i dina presentationer.
## FAQ's
### Vad är Aspose.Slides för Java?
Aspose.Slides för Java är ett kraftfullt API för att manipulera PowerPoint-presentationer programmatiskt.
### Var kan jag hitta dokumentation för Aspose.Slides för Java?
 Du hittar dokumentationen[här](https://reference.aspose.com/slides/java/).
### Kan jag prova Aspose.Slides för Java innan jag köper?
 Ja, du kan få en gratis provperiod[här](https://releases.aspose.com/).
### Hur kan jag få support för Aspose.Slides för Java?
 För support, besök[Aspose.Slides forum](https://forum.aspose.com/c/slides/11).
### Var kan jag köpa en licens för Aspose.Slides för Java?
 Du kan köpa en licens[här](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
