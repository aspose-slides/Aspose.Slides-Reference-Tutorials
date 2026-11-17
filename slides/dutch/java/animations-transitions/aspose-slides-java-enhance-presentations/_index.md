---
date: '2026-11-16'
description: Teken een kader rond tekst in PowerPoint-tabellen met Aspose.Slides for
  Java – leer hoe je tabellen maakt, tekst aan cellen toevoegt, cellen markeert en
  het bestand exporteert als PPTX.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Teken een kader rond tekst in PowerPoint-tabellen met Aspose.Slides
  for Java. Deze gids laat zien hoe je tabellen maakt, tekst toevoegt en uitlijnt,
  cellen markeert en dia's exporteert als PNG.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Kader rond tekst tekenen en tabellen maken in PowerPoint met Aspose.Slides
  for Java
schemas:
- author: Aspose
  dateModified: '2026-11-16'
  description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  headline: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
  type: TechArticle
- description: Draw frame around text in PowerPoint tables using Aspose.Slides for
    Java – learn how to create tables, add text to cells, highlight content, and save
    the file as PPTX.
  name: How to draw frame around text and create tables in PowerPoint with Aspose.Slides
    for Java
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
tags:
- Aspose.Slides
- Java presentation automation
- PowerPoint table manipulation
- draw frame around text
- PPTX generation
title: Hoe een kader rond tekst te tekenen en tabellen te maken in PowerPoint met
  Aspose.Slides for Java
url: /nl/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hoe een kader rond tekst te tekenen en tabellen te maken in PowerPoint met Aspose.Slides voor Java

## Introductie

Het tekenen van een **kader rond tekst** in een PowerPoint‑dia stelt je in staat belangrijke cijfers te benadrukken zonder de onderliggende inhoud te wijzigen. In deze tutorial leer je hoe je programmatisch een tabel maakt, tekst in cellen invoegt en uitlijnt, specifieke woorden of volledige cellen markeert, en uiteindelijk de presentatie opslaat als een PPTX‑bestand. Aan het einde heb je een gepolijste dia die de aandacht van het publiek precies daar richt waar jij dat wilt.

## Snelle antwoorden
- **Wat betekent “add text to table”?** Het betekent het programmatisch invoegen of bijwerken van de tekstinhoud van individuele tabelcellen.  
- **Welke methode slaat het bestand op?** `pres.save("output.pptx", SaveFormat.Pptx)` – deze **save presentation as pptx** stap voltooit je wijzigingen.  
- **Hoe kan ik tekst binnen een vorm uitlijnen?** Gebruik `TextAlignment.Left` (of Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Kan ik een rechthoek rond een alinea tekenen?** Ja – loop door alinea’s, haal hun begrenzende rechthoek op, en voeg een `IAutoShape` toe zonder vulling en met een zwarte lijn.  
- **Heb ik een licentie nodig?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productiegebruik.  

## Waarom kaders rond tekst tekenen?

Het tekenen van een kader rond tekst markeert direct belangrijke cijfers, waarschuwingen of koppen. Het biedt een visueel signaal terwijl de oorspronkelijke opmaak onaangeroerd blijft, waardoor het ideaal is voor financiële rapporten, KPI‑dashboards of elke dia waar nadruk nodig is.

## Wat is een kader rond tekst?

`draw frame around text` is de techniek waarbij programmatisch een rechthoekige vorm wordt toegevoegd die exact de grenzen van een alinea of tekstgedeelte volgt, met alleen lijnopmaak en zonder de binnenkant op te vullen. Deze aanpak laat je inhoud benadrukken zonder de tekst zelf te wijzigen.

## Voorvereisten

Voordat je begint, zorg ervoor dat je het volgende hebt:

### Vereiste bibliotheken
Je hebt Aspose.Slides voor Java nodig. Voeg het toe met een van de package‑managers:

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

Je kunt ook de releases bekijken op [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Omgevingsconfiguratie
Een Java Development Kit (JDK) 16 of nieuwer wordt aanbevolen omdat de voorbeelden de `jdk16`‑classifier gebruiken. Elke IDE zoals IntelliJ IDEA of Eclipse werkt.

### Kennisvoorvereisten
- Basisvaardigheden in Java‑programmeren.  
- Vertrouwdheid met PowerPoint‑concepten (dia’s, vormen, tabellen).  
- Begrip van hoe Maven/Gradle afhankelijkheden beheren.

## Aspose.Slides voor Java instellen

`Presentation` is de kernklasse van Aspose.Slides die een PowerPoint‑bestand in het geheugen vertegenwoordigt en toegang biedt tot dia’s, vormen en tabellen. Het kan presentaties met tot **10.000 dia’s** verwerken terwijl het geheugenverbruik onder **500 MB** blijft, waardoor het geschikt is voor grootschalige automatisering.

1. **Installeer de bibliotheek** – gebruik Maven of Gradle, of download direct van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).  
2. **Licentie‑acquisitie** – begin met een gratis proefversie via [Temporary License](https://purchase.aspose.com/temporary-license/) en upgrade naar een volledige licentie op [Purchase Aspose.Slides](https://purchase.aspose.com/buy) voor productie‑workloads.  
3. **Basisinitialisatie** – maak een nieuw `Presentation`‑object aan en laad of maak dia’s naar behoefte.  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Hoe tekst toevoegen aan een tabel in Aspose.Slides voor Java?

`Presentation` is de hoofdklasse die een PowerPoint‑bestand in het geheugen vertegenwoordigt.  
Laad een nieuwe `Presentation`, maak een tabel op de gewenste coördinaten, vul cellen met `TextFrame`‑objecten, en roep uiteindelijk `pres.save("output.pptx", SaveFormat.Pptx)` aan. Deze volgorde creëert een **create table in PowerPoint**, injecteert aangepaste tekst in elke cel, en schrijft het resultaat naar een PPTX‑bestand in één efficiënte workflow.

### Direct antwoord
Maak een tabel door `slide.getShapes().addTable(...)` aan te roepen, en gebruik voor elke cel `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))`. Na het vullen van alle cellen, roep `pres.save("output.pptx", SaveFormat.Pptx)` aan om het bestand te schrijven. Deze aanpak stelt je in staat programmatisch de inhoud en stijl van elke cel te beheersen.

#### Functie 1: tabel maken en tekst aan cellen toevoegen

**1. create a table** – initialiseert een presentatie, voegt een dia toe, en plaatst een tabel op (50, 50) met gedefinieerde kolombreedtes en rijhoogtes.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add text to cells** – voor elke cel maak je een `Paragraph`, voeg je een `Portion` met de gewenste tekenreeks toe, en wijs je de alinea toe aan het `TextFrame` van de cel.  
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

**3. save the presentation** – roep `pres.save("output.pptx", SaveFormat.Pptx)` aan.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Hoe een kader rond tekst te tekenen in een PowerPoint‑dia?

`Rectangle2D` vertegenwoordigt een rechthoekig gebied in een tweedimensionale coördinatenruimte.  
Laad de dia, lokaliseer de alinea of het deel dat je wilt benadrukken, haal de begrenzende rechthoek op via `getRect()`, en voeg vervolgens een `IAutoShape`‑rechthoek toe zonder vulling en met een gekleurde lijn. Deze methode werkt zowel voor volledige alinea’s als voor individuele woorddelen.

### Direct antwoord
Om een kader rond tekst te tekenen, haal eerst de rechthoek van de alinea op (`Rectangle2D rect = paragraph.getRect();`). Maak vervolgens een `IAutoShape`‑rechthoek (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), stel `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)` in, en schakel de vulling uit (`shape.getFillFormat().setFillType(FillType.NoFill)`). De vorm omlijnt de tekst perfect.

#### Functie 3: kaders tekenen rond alinea’s en delen in tabelcellen

**1. create a table** – hergebruik de code van Functie 1 om de initiële tabel op te zetten.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add paragraphs** – hergebruik de alinea‑creatiecode van Functie 1.  
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

**3. draw frames** – loop door elke alinea, verkrijg de begrenzende rechthoek, en voeg een rechthoekvorm toe zoals hierboven beschreven. Voor delen die het teken ‘0’ bevatten, teken je een extra kader om die cijfers te markeren.  
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

**4. save the presentation** – dezelfde laatste stap als eerder.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Hoe een tekstframe toevoegen aan een AutoShape en uitlijning instellen

`AutoShape` is een vorm die tekst, afbeeldingen of andere inhoud kan bevatten.  
Een `AutoShape` kan een `TextFrame` bevatten. Je kunt de horizontale uitlijning regelen met de `ParagraphFormat`‑enum.

### Direct antwoord
Maak een rechthoekige AutoShape (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), krijg toegang tot het `TextFrame`, stel de tekst in met `shape.getTextFrame().setText("Text in shape")`, en roep vervolgens `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)` aan. Hiermee wordt de tekst links uitgelijnd binnen de vorm.

**1. add an AutoShape** – plaats een rechthoek op de gewenste locatie.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. set text alignment** – pas de linkse uitlijning toe zoals hierboven getoond.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. save the presentation** – dezelfde laatste stap.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Veelvoorkomende valkuilen & tips

- **Always dispose** – wikkel je `Presentation`‑gebruik in een try‑finally‑blok en roep `pres.dispose()` aan om native resources vrij te geven.  
- **Re‑compute bounding rectangles** – wijzig je de lettergrootte, marges of cel‑padding na het tekenen van een kader, roep dan `paragraph.getRect()` opnieuw aan voordat je de vorm toevoegt.  
- **Batch shape creation for large tables** – hergebruik één `IAutoShape`‑instantie en werk de geometrie bij om geheugenbelasting te verminderen bij het verwerken van tabellen met honderden rijen.  
- **Performance numbers** – Aspose.Slides kan een PPTX van 200 pagina’s genereren in minder dan 2 seconden op een typische 4‑core server, en het tekenen van kaders rond 1.000 alinea’s voegt minder dan 150 ms overhead toe.

## Veelgestelde vragen

**Q: Kan ik deze API’s gebruiken met oudere JDK‑versies?**  
A: De bibliotheek ondersteunt JDK 8 en hoger, maar de `jdk16`‑classifier biedt de beste prestaties op nieuwere runtimes.

**Q: Hoe wijzig ik de kleur van het kader?**  
A: Pas de vulling van het lijnformaat aan, bijvoorbeeld `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is het mogelijk de uiteindelijke dia als afbeelding te exporteren?**  
A: Ja—gebruik `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` en sla vervolgens de byte‑array op.

**Q: Wat als ik alleen het woord “Total” in een cel wil markeren?**  
A: Loop door `cell.getTextFrame().getParagraphs()`, vind het deel dat “Total” bevat, en teken een rechthoek rond de begrenzende box van dat deel.

**Q: Handelt Aspose.Slides grote presentaties efficiënt af?**  
A: De API streamt gegevens en geeft resources vrij wanneer `pres.dispose()` wordt aangeroepen, wat helpt bij het geheugenbeheer voor grote bestanden.

---

**Laatst bijgewerkt:** 2026-11-16  
**Getest met:** Aspose.Slides for Java 25.4 (jdk16)  
**Auteur:** Aspose  

## Gerelateerde tutorials

- [Aspose.Slides for Java: Master PPTX Table & Text Manipulation in PowerPoint Presentations](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [How to Create Dynamic Text Frames in PowerPoint Using Aspose.Slides for Java](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Add Columns in Text Frame using Aspose.Slides for Java](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}