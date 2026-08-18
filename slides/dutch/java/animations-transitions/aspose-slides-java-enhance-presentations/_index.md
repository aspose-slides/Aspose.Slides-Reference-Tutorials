---
date: '2026-06-23'
description: Leer hoe je een table in PowerPoint maakt, tekst toevoegt aan table cells,
  frames rond tekst tekent, en de presentatie opslaat als pptx met Aspose.Slides for
  Java.
keywords:
- create table in powerpoint
- add text to table
- draw frame around text
- highlight table cells
- save presentation as pptx
schemas:
- author: Aspose
  dateModified: '2026-06-23'
  description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  headline: How to create table in PowerPoint and draw frames with Aspose.Slides for
    Java
  type: TechArticle
- description: Learn how to create table in PowerPoint, add text to table cells, draw
    frames around text, and save presentation as pptx using Aspose.Slides for Java.
  name: How to create table in PowerPoint and draw frames with Aspose.Slides for Java
  steps:
  - name: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
    text: '**Install the Library**: Use Maven or Gradle to manage dependencies, or
      download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).'
  - name: '**License Acquisition**:'
    text: '**License Acquisition**:'
  - name: '**Basic Initialization**:'
    text: '**Basic Initialization**:'
  type: HowTo
- questions:
  - answer: The library supports JDK 8 onward, but the `jdk16` classifier gives the
      best performance on newer runtimes.
    question: Can I use these APIs with older JDK versions?
  - answer: Modify the line format fill color, e.g., `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.
    question: How do I change the frame color?
  - answer: Yes—use `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)`
      and then save the byte array.
    question: Is it possible to export the final slide as an image?
  - answer: Iterate through `cell.getTextFrame().getParagraphs()`, locate the portion
      containing “Total”, and draw a rectangle around that portion’s bounding box.
    question: What if I need to highlight only the word “Total” inside a cell?
  - answer: The API streams data and releases resources when `pres.dispose()` is called,
      which helps with memory management for large files.
    question: Does Aspose.Slides handle large presentations efficiently?
  type: FAQPage
title: Hoe maak je een table in PowerPoint en teken je frames met Aspose.Slides for
  Java
url: /nl/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe een tabel te maken in PowerPoint en frames te tekenen met Aspose.Slides voor Java

## Inleiding

Het programmatic maken van een **create table in PowerPoint** kan je uren handmatig opmaken besparen, vooral wanneer je belangrijke cijfers wilt benadrukken of toelichtende notities wilt toevoegen. In deze tutorial ontdek je hoe je tekst aan tabelcellen toevoegt, frames rond specifieke alinea's tekent, precieze tekstuitlijning instelt en uiteindelijk **save presentation as pptx** – allemaal met de krachtige Aspose.Slides for Java API. Aan het einde heb je een dia die er gepolijst uitziet, gemakkelijk leesbaar is en onmiddellijk de aandacht van het publiek vestigt op de belangrijkste gegevens.

## Snelle antwoorden
- **Wat betekent “add text to table”?** Het betekent het invoegen of bijwerken van de tekstinhoud van individuele tabelcellen programmatisch.  
- **Welke methode slaat het bestand op?** `pres.save("output.pptx", SaveFormat.Pptx)` – deze **save presentation as pptx** stap voltooit uw wijzigingen.  
- **Hoe kan ik tekst binnen een vorm uitlijnen?** Gebruik `TextAlignment.Left` (of Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Kan ik een rechthoek rond een alinea tekenen?** Ja – loop door alinea's, haal hun begrenzende rechthoek op, en voeg een `IAutoShape` toe zonder vulling en met een zwarte lijn.  
- **Heb ik een licentie nodig?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productiegebruik.  

## Waarom frames rond tekst tekenen?

Het tekenen van een frame (of rechthoek) rond een alinea of een specifiek gedeelte—bijvoorbeeld elke tekst die het teken **'0'** bevat—trekt onmiddellijk de aandacht van het publiek naar die inhoud. Het biedt een duidelijke visuele aanwijzing zonder de onderliggende tekst te wijzigen, waardoor het ideaal is voor het benadrukken van belangrijke cijfers, waarschuwingen of het scheiden van secties binnen een dia.

## Voorvereisten

Voordat je in de code duikt, zorg ervoor dat je het volgende hebt:

### Vereiste bibliotheken
Je hebt Aspose.Slides for Java nodig. Hieronder staat hoe je het kunt opnemen met Maven of Gradle:

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```  

**Gradle:**  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```  

### Omgevingsconfiguratie
Zorg ervoor dat je een Java Development Kit (JDK) geïnstalleerd hebt, bij voorkeur JDK 16 of later, aangezien dit voorbeeld de `jdk16` classifier gebruikt.

### Kennisvoorvereisten
- Basiskennis van Java-programmeren.  
- Bekendheid met presentatiesoftware zoals PowerPoint.  
- Ervaring met een Integrated Development Environment (IDE) zoals IntelliJ IDEA of Eclipse.

## Instellen van Aspose.Slides voor Java

`Presentation` is de kernklasse van Aspose.Slides die een PowerPoint‑bestand in het geheugen vertegenwoordigt en toegang biedt tot dia's, vormen en tabellen. Volg deze stappen om Aspose.Slides te gebruiken:

1. **Installeer de bibliotheek**: Gebruik Maven of Gradle om afhankelijkheden te beheren, of download deze rechtstreeks van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **Licentie‑acquisitie**:
   - Begin met een gratis proefversie door een tijdelijke licentie te downloaden van [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Voor volledige toegang kun je een licentie aanschaffen via [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basisinitialisatie**:  
   Initialiseert je presentatiemilieu met de volgende code‑fragment:  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Hoe tekst toevoegen aan tabel in Aspose.Slides voor Java?

Laad een nieuwe `Presentation`, maak een tabel op de gewenste coördinaten, vul cellen met `TextFrame`‑objecten en roep uiteindelijk `pres.save("output.pptx", SaveFormat.Pptx)` aan. Deze volgorde maakt een **create table in PowerPoint**, injecteert aangepaste tekst in elke cel en schrijft het resultaat naar een PPTX‑bestand in één efficiënte workflow.

### Functie 1: Tabel maken en tekst aan cellen toevoegen

#### Overzicht
Deze functie toont hoe je een **create table** maakt, vervolgens **add text to table** cellen toevoegt en later **save presentation as pptx** uitvoert.

#### Stappen

**1. Create a Table**  
Eerst initialiseert u uw presentatie en voegt u een tabel toe op positie (50, 50) met opgegeven kolombreedtes en rijhoogtes.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Text to Cells**  
Maak alinea's met tekstgedeelten en voeg ze toe aan een specifieke cel.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Functie 2: TextFrame toevoegen aan AutoShape en uitlijning instellen

#### Overzicht
Leer hoe je een tekstframe met specifieke uitlijning toevoegt aan een autoshape—een voorbeeld van **set text alignment java**.

#### Stappen

Een AutoShape is een vorm die tekst en grafische elementen kan bevatten.

**1. Add an AutoShape**  
Voeg een rechthoek toe als AutoShape op positie (400, 100) met opgegeven afmetingen.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment`‑enum definieert horizontale uitlijningsopties voor tekst binnen een vorm.

**2. Set Text Alignment**  
Stel de tekst in op “Text in shape” en lijn deze links uit.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### Functie 3: Frames tekenen rond alinea's en gedeelten in tabelcellen

#### Overzicht
Deze functie richt zich op **draw frames around text** en zelfs **draw rectangle around paragraph** voor gedeelten die het teken ‘0’ bevatten.

#### Stappen

`IAutoShape` vertegenwoordigt een vormobject dat op een dia kan worden getekend, zoals rechthoeken die als frames worden gebruikt.

**1. Create a Table**  
Hergebruik de code van “Create Table and Add Text to Cells” voor de initiële opzet.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Add Paragraphs**  
Herbruik de alinea‑creatiecode van de vorige functie.  
```java
    IParagraph paragraph0 = new Paragraph();
    paragraph0.getPortions().add(new Portion("Text "));
    paragraph0.getPortions().add(new Portion("in0"));
    paragraph0.getPortions().add(new Portion(" Cell"));

    IParagraph paragraph1 = new Paragraph();
    paragraph1.setText("On0");

    IParagraph paragraph2 = new Paragraph();
    paragraph2.getPortions().add(new Portion("Hi there "));
    paragraph2.getPortions().add(new Portion("col0"));

    ICell cell = tbl.get_Item(1, 1);
    cell.getTextFrame().getParagraphs().clear();
    cell.getTextFrame().getParagraphs().addAll(Arrays.asList(paragraph0, paragraph1, paragraph2));
```  

**3. Draw Frames**  
Itereer over alinea's en gedeelten om frames eromheen te tekenen.  
```java
    double x = tbl.getX() + cell.getOffsetX();
    double y = tbl.getY() + cell.getOffsetY();

    for (IParagraph para : cell.getTextFrame().getParagraphs()) {
        if ("".equals(para.getText())) continue;

        Rectangle2D.Float rect = (Rectangle2D.Float) para.getRect().clone();
        IAutoShape shape = (IAutoShape) pres.getSlides().get_Item(0).getShapes().addAutoShape(
            ShapeType.Rectangle, rect.x, rect.y, rect.width, rect.height);

        shape.getTextFrame().setText(para.getText());
        shape.setFillFormat(FillFormat.createNoFill());
        shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLACK);
    }
```  

**4. Save the Presentation**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Veelvoorkomende valkuilen & tips

- **Null checks** – Omring altijd je `Presentation`‑gebruik met een try‑finally‑blok om ervoor te zorgen dat `pres.dispose()` wordt uitgevoerd en native resources worden vrijgegeven.  
- **Bounding rectangle accuracy** – De rechthoek die door `para.getRect()` wordt geretourneerd, weerspiegelt de huidige lay-out; wijzig je de lettergrootte of marges, bereken dan de rechthoek opnieuw voordat je het frame tekent.  
- **Performance** – Bij het werken met zeer grote tabellen, overweeg om vorm‑toevoegingen te batchen of een enkele `IAutoShape`‑instantie te hergebruiken met bijgewerkte geometrie om het geheugenverbruik te verminderen.  

## Veelgestelde vragen

**Q: Kan ik deze API's gebruiken met oudere JDK‑versies?**  
A: De bibliotheek ondersteunt JDK 8 en hoger, maar de `jdk16` classifier biedt de beste prestaties op nieuwere runtimes.

**Q: Hoe wijzig ik de frame‑kleur?**  
A: Pas de vulkleur van het lijnformaat aan, bijvoorbeeld `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is het mogelijk om de uiteindelijke dia als afbeelding te exporteren?**  
A: Ja—gebruik `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` en sla vervolgens de byte‑array op.

**Q: Wat als ik alleen het woord “Total” binnen een cel wil markeren?**  
A: Loop door `cell.getTextFrame().getParagraphs()`, zoek het gedeelte dat “Total” bevat, en teken een rechthoek rond de begrenzende box van dat gedeelte.

**Q: Handelt Aspose.Slides grote presentaties efficiënt af?**  
A: De API streamt gegevens en geeft resources vrij wanneer `pres.dispose()` wordt aangeroepen, wat helpt bij het geheugenbeheer voor grote bestanden.

---

**Last Updated:** 2026-06-23  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Gerelateerde tutorials

- [Aspose.Slides voor Java&#58; Master PPTX Tabel- & Tekstmanipulatie in PowerPoint-presentaties](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Hoe dynamische tekstframes te maken in PowerPoint met Aspose.Slides voor Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Kolommen toevoegen in Tekstframe met Aspose.Slides voor Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}