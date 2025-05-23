---
"description": "Leer hoe je een rechthoek in PowerPoint maakt met Aspose.Slides voor Java met deze gedetailleerde, stapsgewijze tutorial. Perfect voor Java-ontwikkelaars."
"linktitle": "Rechthoekgedeelte in PowerPoint verkrijgen met Java"
"second_title": "Aspose.Slides Java PowerPoint-verwerkings-API"
"title": "Rechthoekgedeelte in PowerPoint verkrijgen met Java"
"url": "/nl/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Rechthoekgedeelte in PowerPoint verkrijgen met Java

## Invoering
Dynamische presentaties maken in Java is een fluitje van een cent met Aspose.Slides voor Java. In deze tutorial duiken we in de details van het maken van een rechthoek in PowerPoint met Aspose.Slides. We behandelen alles, van het instellen van je omgeving tot het stapsgewijs analyseren van de code. Laten we beginnen!
## Vereisten
Voordat we met de code aan de slag gaan, willen we ervoor zorgen dat je alles bij de hand hebt om alles soepel te kunnen volgen:
1. Java Development Kit (JDK): Zorg ervoor dat JDK 8 of hoger op uw computer is geïnstalleerd.
2. Aspose.Slides voor Java: Download de nieuwste versie van [hier](https://releases.aspose.com/slides/java/).
3. Integrated Development Environment (IDE): Eclipse, IntelliJ IDEA of een andere Java IDE naar keuze.
4. Basiskennis van Java: Kennis van Java-programmering is essentieel.
## Pakketten importeren
Laten we eerst de benodigde pakketten importeren. Dit omvat Aspose.Slides en een paar andere pakketten om onze taak efficiënt uit te voeren.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## Stap 1: De presentatie instellen
De eerste stap is het maken van een nieuwe presentatie. Dit wordt ons canvas om op te werken.
```java
Presentation pres = new Presentation();
```
## Stap 2: Een tabel maken
Laten we nu een tabel toevoegen aan de eerste dia van onze presentatie. Deze tabel bevat de cellen waar we onze tekst gaan toevoegen.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## Stap 3: Alinea's toevoegen aan cellen
Vervolgens maken we alinea's en voegen deze toe aan een specifieke cel in de tabel. Dit houdt in dat we bestaande tekst wissen en vervolgens nieuwe alinea's toevoegen.
```java
// Alinea's maken
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Tekst toevoegen aan de tabelcel
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
We hebben de coördinaten van de linkerbovenhoek van de tabelcel nodig. Dit helpt ons de vormen nauwkeurig te plaatsen.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## Stap 6: Kaders toevoegen aan alinea's en gedeelten
Met behulp van de `IParagraph.getRect()` En `IPortion.getRect()` Met behulp van methoden kunnen we kaders toevoegen aan onze alinea's en gedeelten. Dit houdt in dat we door de alinea's en gedeelten heen itereren, er vormen omheen creëren en hun uiterlijk aanpassen.
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
## Stap 7: Kaders toevoegen aan AutoVorm-alinea's
Op vergelijkbare wijze voegen we kaders toe aan de alinea's in onze AutoVorm, waardoor de visuele aantrekkingskracht van de presentatie wordt vergroot.
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
Ten slotte slaan we onze presentatie op in een bepaald pad.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## Stap 9: Opruimen
Het is een goed idee om het presentatieobject te verwijderen om bronnen vrij te maken.
```java
if (pres != null) pres.dispose();
```
## Conclusie
Gefeliciteerd! Je hebt succesvol geleerd hoe je de deelrechthoek in PowerPoint kunt maken met Aspose.Slides voor Java. Deze krachtige bibliotheek opent een wereld aan mogelijkheden voor het programmatisch maken van dynamische en visueel aantrekkelijke presentaties. Duik dieper in Aspose.Slides en ontdek meer functies om je presentaties verder te verbeteren.
## Veelgestelde vragen
### Wat is Aspose.Slides voor Java?
Aspose.Slides voor Java is een krachtige bibliotheek waarmee ontwikkelaars programmatisch PowerPoint-presentaties kunnen maken, wijzigen en manipuleren.
### Kan ik Aspose.Slides voor Java gebruiken in commerciële projecten?
Ja, Aspose.Slides voor Java kan worden gebruikt in commerciële projecten. U kunt een licentie aanschaffen bij [hier](https://purchase.aspose.com/buy).
### Is er een gratis proefversie beschikbaar voor Aspose.Slides voor Java?
Ja, u kunt een gratis proefversie downloaden van [hier](https://releases.aspose.com/).
### Waar kan ik de documentatie voor Aspose.Slides voor Java vinden?
De documentatie is beschikbaar [hier](https://reference.aspose.com/slides/java/).
### Hoe kan ik ondersteuning krijgen voor Aspose.Slides voor Java?
U kunt ondersteuning krijgen via het Aspose-forum [hier](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}