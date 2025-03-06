---
title: Applicera Outer Shadow i PowerPoint med Java
linktitle: Applicera Outer Shadow i PowerPoint med Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Lär dig hur du applicerar yttre skuggeffekt i PowerPoint med Java med Aspose.Slides. Förbättra dina presentationer med djup och visuell tilltalande.
weight: 13
url: /sv/java/java-powerpoint-animation-effects/apply-outer-shadow-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Introduktion
Att skapa visuellt tilltalande PowerPoint-presentationer innebär ofta att man lägger till olika effekter på former och text. En sådan effekt är den yttre skuggan, som kan få element att sticka ut och lägga till djup till dina bilder. I den här handledningen kommer du att lära dig hur du applicerar en yttre skuggeffekt på en form i PowerPoint med Java med Aspose.Slides.
## Förutsättningar

Innan du börjar den här handledningen, se till att du har följande förutsättningar:

1. Java Development Kit (JDK): Se till att du har Java installerat på ditt system. Du kan ladda ner och installera den senaste versionen av JDK från Oracles webbplats.

2.  Aspose.Slides för Java: Ladda ner och installera Aspose.Slides för Java från[nedladdningssida](https://releases.aspose.com/slides/java/).

3. Integrated Development Environment (IDE): Välj din föredragna Java IDE som Eclipse, IntelliJ IDEA eller NetBeans för kodning och körning av Java-applikationer.

4. Grundläggande Java-kunskaper: Bekantskap med Java-programmeringsspråkets grunder och objektorienterade koncept kommer att vara fördelaktigt för att förstå kodexemplen.

## Importera paket

Importera först de nödvändiga paketen för att arbeta med Aspose.Slides och relaterade funktioner i ditt Java-projekt:

```java
import com.aspose.slides.*;
```

Låt oss nu dela upp exempelkoden i flera steg för att tillämpa den yttre skuggeffekten på en form i PowerPoint med Java med Aspose.Slides:

## Steg 1: Konfigurera din projektmiljö

Skapa ett nytt Java-projekt i din föredragna IDE och lägg till Aspose.Slides för Java-biblioteket till ditt projekts byggväg.

## Steg 2: Initiera presentationsobjekt

 Skapa en instans av`Presentation` klass, som representerar en PowerPoint-presentationsfil.

```java
Presentation presentation = new Presentation();
```

## Steg 3: Lägg till en bild och form

Få en referens till bilden där du vill lägga till formen och lägg sedan till en AutoShape (t.ex. rektangel) till bilden.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IAutoShape shape = slide.getShapes().addAutoShape(ShapeType.Rectangle, 150, 75, 400, 300);
```

## Steg 4: Anpassa formen

Ställ in fyllningstypen för formen till "NoFill" och lägg till text i formen.

```java
shape.getFillFormat().setFillType(FillType.NoFill);
shape.addTextFrame("Aspose TextBox");
```

## Steg 5: Anpassa texten

Få åtkomst till formens textegenskaper och anpassa teckenstorleken.

```java
IPortion portion = shape.getTextFrame().getParagraphs().get_Item(0).getPortions().get_Item(0);
IPortionFormat portionFormat = portion.getPortionFormat();
portionFormat.setFontHeight(50);
```

## Steg 6: Aktivera Outer Shadow-effekten

Aktivera den yttre skuggeffekten för textdelen.

```java
IEffectFormat effectFormat = portionFormat.getEffectFormat();
effectFormat.enableOuterShadowEffect();
```

## Steg 7: Ställ in skuggparametrar

Definiera parametrarna för den yttre skuggeffekten, såsom oskärpa radie, riktning, avstånd och skuggfärg.

```java
effectFormat.getOuterShadowEffect().setBlurRadius(8.0);
effectFormat.getOuterShadowEffect().setDirection(90.0F);
effectFormat.getOuterShadowEffect().setDistance(6.0);
effectFormat.getOuterShadowEffect().getShadowColor().setB((byte) 189);
effectFormat.getOuterShadowEffect().getShadowColor().setColorType(ColorType.Scheme);
effectFormat.getOuterShadowEffect().getShadowColor().setSchemeColor(SchemeColor.Accent1);
```

## Steg 8: Spara presentationen

Spara den ändrade presentationen med den yttre skuggeffekten applicerad på formen.

```java
presentation.save("output.pptx", SaveFormat.Pptx);
```

## Slutsats

Grattis! Du har framgångsrikt tillämpat en yttre skuggeffekt på en form i PowerPoint med Java med Aspose.Slides. Experimentera med olika parametrar för att uppnå önskade visuella effekter i dina presentationer.

## FAQ's

### Kan jag tillämpa den yttre skuggeffekten på andra former än rektanglar?
Ja, du kan använda den yttre skuggeffekten på olika former som stöds av Aspose.Slides, som cirklar, trianglar och anpassade former.

### Är det möjligt att anpassa skuggans färg och intensitet?
Absolut! Du har full kontroll över skuggparametrarna, inklusive färg, oskärpa radie, riktning och avstånd.

### Kan jag använda flera effekter på samma form?
Ja, du kan kombinera flera effekter som yttre skugga, inre skugga, glöd och reflektion för att förstärka det visuella tilltalande av former och text i dina presentationer.

### Stöder Aspose.Slides att tillämpa effekter på textelement?
Ja, du kan applicera effekter inte bara på former utan även på enskilda textdelar inom former, vilket ger dig stor flexibilitet när du utformar dina bilder.

### Var kan jag hitta fler resurser och support för Aspose.Slides?
 Du kan hänvisa till[dokumentation](https://reference.aspose.com/slides/java/) för detaljerade API-referenser och utforska[Aspose.Slides forum](https://forum.aspose.com/c/slides/11) för samhällsstöd och diskussioner.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
