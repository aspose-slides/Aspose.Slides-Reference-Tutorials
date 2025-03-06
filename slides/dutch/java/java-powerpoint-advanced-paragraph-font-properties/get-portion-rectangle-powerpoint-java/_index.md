---
title: Krijg een gedeelterechthoek in PowerPoint met Java
linktitle: Krijg een gedeelterechthoek in PowerPoint met Java
second_title: Aspose.Slides Java PowerPoint-verwerkings-API
description: Leer hoe u de portierechthoek in PowerPoint kunt krijgen met Aspose.Slides voor Java met deze gedetailleerde, stapsgewijze zelfstudie. Ideaal voor Java-ontwikkelaars.
weight: 12
url: /nl/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Krijg een gedeelterechthoek in PowerPoint met Java

## Invoering
Het maken van dynamische presentaties in Java is een fluitje van een cent met Aspose.Slides voor Java. In deze zelfstudie duiken we in de kern van het verkrijgen van de gedeelterechthoek in PowerPoint met behulp van Aspose.Slides. We behandelen alles, van het instellen van uw omgeving tot het stapsgewijs afbreken van de code. Dus laten we beginnen!
## Vereisten
Voordat we ingaan op de code, moeten we ervoor zorgen dat je alles hebt wat je nodig hebt om de code soepel te kunnen volgen:
1. Java Development Kit (JDK): Zorg ervoor dat JDK 8 of hoger op uw computer is geïnstalleerd.
2.  Aspose.Slides voor Java: Download de nieuwste versie van[hier](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Eclipse, IntelliJ IDEA of een andere Java IDE naar keuze.
4. Basiskennis van Java: Inzicht in Java-programmeren is essentieel.
## Pakketten importeren
Laten we eerst de benodigde pakketten importeren. Dit omvat Aspose.Slides en een paar anderen voor het efficiënt uitvoeren van onze taak.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Stap 1: De presentatie opzetten
De eerste stap is het maken van een nieuwe presentatie. Dit wordt ons canvas om op te werken.
```java
Presentation pres = new Presentation();
```
## Stap 2: Een tabel maken
Laten we nu een tabel toevoegen aan de eerste dia van onze presentatie. Deze tabel bevat de cellen waarin we onze tekst zullen toevoegen.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Stap 3: Alinea's aan cellen toevoegen
Vervolgens maken we alinea's en voegen deze toe aan een specifieke cel in de tabel. Dit houdt in dat alle bestaande tekst wordt gewist en vervolgens nieuwe alinea's worden toegevoegd.
```java
// Maak alinea's
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Voeg tekst toe aan de tabelcel
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## Stap 4: Een tekstkader toevoegen aan een AutoVorm
Om onze presentatie dynamischer te maken, voegen we een tekstkader toe aan een AutoVorm en stellen we de uitlijning ervan in.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## Stap 5: Coördinaten berekenen
We hebben de coördinaten van de linkerbovenhoek van de tabelcel nodig. Dit zal ons helpen de vormen nauwkeurig te plaatsen.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Stap 6: Frames toevoegen aan alinea's en gedeelten
 De ... gebruiken`IParagraph.getRect()` En`IPortion.getRect()`methoden, kunnen we frames toevoegen aan onze paragrafen en gedeelten. Dit omvat het doorlopen van de alinea's en gedeelten, het creëren van vormen eromheen en het aanpassen van hun uiterlijk.
```java
for (IParagraph para : cell.getTextFrame().getParagraphs()) {
    if ("".equals(para.getText())) continue;
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + (float) x,
        (float) rect.getY() + (float) y,
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
    for (IPortion portion : para.getPortions()) {
        if (portion.getText().contains("0")) {
            rect = portion.getRect();
            shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
                ShapeType.Rectangle,
                (float) rect.getX() + (float) x,
                (float) rect.getY() + (float) y,
                (float) rect.getWidth(),
                (float) rect.getHeight()
            );
            shape.getFillFormat().setFillType(FillType.NoFill);
        }
    }
}
```
## Stap 7: Frames toevoegen aan AutoShape-paragrafen
Op dezelfde manier voegen we kaders toe aan de alinea's in onze AutoVorm, waardoor de visuele aantrekkingskracht van de presentatie wordt vergroot.
```java
for (IParagraph para : autoShape.getTextFrame().getParagraphs()) {
    Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
    IAutoShape shape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle,
        (float) rect.getX() + autoShape.getX(),
        (float) rect.getY() + autoShape.getY(),
        (float) rect.getWidth(),
        (float) rect.getHeight()
    );
    shape.getFillFormat().setFillType(FillType.NoFill);
    shape.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
    shape.getLineFormat().getFillFormat().setFillType(FillType.Solid);
}
```
## Stap 8: De presentatie opslaan
Ten slotte slaan we onze presentatie op een opgegeven pad op.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Stap 9: Opruimen
Het is een goede gewoonte om het presentatieobject weg te gooien om bronnen vrij te maken.
```java
if (pres != null) pres.dispose();
```
## Conclusie
Gefeliciteerd! U hebt met succes geleerd hoe u de gedeelterechthoek in PowerPoint kunt krijgen met behulp van Aspose.Slides voor Java. Deze krachtige bibliotheek opent een wereld aan mogelijkheden voor het programmatisch creëren van dynamische en visueel aantrekkelijke presentaties. Duik dieper in Aspose.Slides en ontdek meer functies om uw presentaties verder te verbeteren.
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige bibliotheek waarmee ontwikkelaars PowerPoint-presentaties programmatisch kunnen maken, wijzigen en manipuleren.
### Kan ik Aspose.Slides voor Java gebruiken in commerciële projecten?
 Ja, Aspose.Slides voor Java kan in commerciële projecten worden gebruikt. U kunt een licentie kopen bij[hier](https://purchase.aspose.com/buy).
### Is er een gratis proefversie beschikbaar voor Aspose.Slides voor Java?
 Ja, u kunt een gratis proefversie downloaden van[hier](https://releases.aspose.com/).
### Waar kan ik de documentatie voor Aspose.Slides voor Java vinden?
 De documentatie is beschikbaar[hier](https://reference.aspose.com/slides/java/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor Java?
 U kunt ondersteuning krijgen via het Aspose-forum[hier](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
