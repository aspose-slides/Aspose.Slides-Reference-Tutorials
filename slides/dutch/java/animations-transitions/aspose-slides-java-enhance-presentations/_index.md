---
date: '2026-02-09'
description: Leer hoe u kaders rond tekst tekent en tekst toevoegt aan tabelcellen
  in PowerPoint met Aspose.Slides voor Java. Deze tutorial behandelt het maken van
  tabellen, het instellen van tekstuitlijning en het opslaan van de presentatie als
  pptx.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Hoe frames te tekenen en tekst aan een tabel toe te voegen met Aspose.Slides
  voor Java
url: /nl/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hoe kaders te tekenen en tekst toe te voegen aan tabel in presentaties met Aspose.Slides for Java

## Introductie

Het duidelijk presenteren van gegevens in PowerPoint kan een echte uitdaging zijn, vooral wanneer je **add text to table** cellen moet toevoegen en belangrijke waarden wilt benadrukken met visuele aanwijzingen. In deze gids leer je **how to draw frames** rond specifieke alinea's, tekstuitlijning in vormen in te stellen, en uiteindelijk **save presentation as pptx** — allemaal met behulp van Aspose.Slides for Java. Aan het einde heb je een gepolijste slide‑deck die de aandacht van het publiek precies daar naartoe trekt waar jij wilt.

Klaar om je dia's te laten opvallen? Laten we stap voor stap door het proces lopen.

## Snelle antwoorden
- **What does “add text to table” mean?** Het betekent het invoegen of bijwerken van de tekstuele inhoud van individuele tabelcellen programmatisch.  
- **Which method saves the file?** `pres.save("output.pptx", SaveFormat.Pptx)` – deze **save presentation as pptx** stap voltooit je wijzigingen.  
- **How can I align text inside a shape?** Gebruik `TextAlignment.Left` (of Center/Right) via `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)`.  
- **Can I draw a rectangle around a paragraph?** Ja – loop door de alinea's, haal hun begrenzende rechthoek op en voeg een `IAutoShape` toe zonder vulling en met een zwarte lijn.  
- **Do I need a license?** Een tijdelijke licentie werkt voor evaluatie; een volledige licentie is vereist voor productiegebruik.  

## Waarom kaders rond tekst tekenen?

Het tekenen van een kader (of rechthoek) rond een alinea of een specifiek gedeelte (bijvoorbeeld elke tekst die het teken **'0'** bevat) trekt onmiddellijk de aandacht. Deze techniek is ideaal voor:
- Het benadrukken van belangrijke financiële cijfers in een tabel.  
- Het accentueren van waarschuwingen of belangrijke notities in een dia.  
- Het creëren van visuele scheidingen zonder handmatig extra vormen toe te voegen.

## Vereisten

Voordat je in de code duikt, zorg ervoor dat je het volgende hebt:

### Vereiste bibliotheken
Je hebt Aspose.Slides for Java nodig. Hier zie je hoe je het kunt opnemen met Maven of Gradle:

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
Zorg ervoor dat je een Java Development Kit (JDK) geïnstalleerd hebt, bij voorkeur JDK 16 of hoger, aangezien dit voorbeeld de `jdk16` classifier gebruikt.

### Kennisvereisten
- Basiskennis van Java-programmeren.  
- Vertrouwdheid met presentatiesoftware zoals PowerPoint.  
- Ervaring met het gebruik van een Integrated Development Environment (IDE) zoals IntelliJ IDEA of Eclipse.

## Aspose.Slides voor Java instellen

Om Aspose.Slides te gaan gebruiken, volg je deze stappen:

1. **Install the Library**: Gebruik Maven of Gradle om afhankelijkheden te beheren, of download het direct van [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Begin met een gratis proefversie door een tijdelijke licentie te downloaden van [Temporary License](https://purchase.aspose.com/temporary-license/).
   - Voor volledige toegang, overweeg een licentie aan te schaffen via [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:
Initialiseer je presentatie‑omgeving met de volgende code‑snippet:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## Hoe tekst toe te voegen aan tabel in Aspose.Slides for Java

### Functie 1: Tabel maken en tekst toevoegen aan cellen

#### Overzicht
Deze functie laat zien hoe je een **create table** maakt, vervolgens **add text to table** cellen toevoegt en later **save presentation as pptx**.

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
Leer hoe je een tekstframe met specifieke uitlijning toevoegt aan een auto‑shape — een voorbeeld van **set text alignment java**.

#### Stappen

**1. Add an AutoShape**  
Voeg een rechthoek toe als AutoShape op positie (400, 100) met opgegeven afmetingen.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Set Text Alignment**  
Stel de tekst in op “Text in shape” en uitlijn deze naar links.
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

### Functie 3: Kaders tekenen rond alinea's en gedeelten in tabelcellen

#### Overzicht
Deze functie richt zich op **draw frames around text** en zelfs **draw rectangle around paragraph** voor gedeelten die het teken ‘0’ bevatten.

#### Stappen

**1. Create a Table**  
Herbruik de code van “Create Table and Add Text to Cells” voor de initiële opzet.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Add Paragraphs**  
Herbruik de code voor het maken van alinea's uit de vorige functie.
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
Loop door alinea's en gedeelten om kaders eromheen te tekenen.
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

- **Null checks** – Omring altijd het gebruik van `Presentation` met een try‑finally‑blok om ervoor te zorgen dat `pres.dispose()` wordt uitgevoerd en native resources vrijgeeft.  
- **Bounding rectangle accuracy** – De rechthoek die wordt geretourneerd door `para.getRect()` weerspiegelt de huidige lay-out; als je de lettergrootte of marges wijzigt, bereken dan de rechthoek opnieuw voordat je het kader tekent.  
- **Performance** – Bij het werken met zeer grote tabellen, overweeg om shape‑toevoegingen te batchen of een enkele `IAutoShape`‑instantie te hergebruiken met bijgewerkte geometrie om het geheugenverbruik te verminderen.

## Veelgestelde vragen

**Q: Kan ik deze API's gebruiken met oudere JDK‑versies?**  
A: De bibliotheek ondersteunt JDK 8 en hoger, maar de `jdk16` classifier biedt de beste prestaties op nieuwere runtimes.

**Q: Hoe wijzig ik de kleur van het kader?**  
A: Pas de vulkleur van het lijnformaat aan, bijvoorbeeld `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Is het mogelijk om de uiteindelijke dia als afbeelding te exporteren?**  
A: Ja — gebruik `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` en sla vervolgens de byte‑array op.

**Q: Wat als ik alleen het woord “Total” in een cel wil markeren?**  
A: Loop door `cell.getTextFrame().getParagraphs()`, vind het gedeelte dat “Total” bevat, en teken een rechthoek rond de begrenzende box van dat gedeelte.

**Q: Handelt Aspose.Slides grote presentaties efficiënt af?**  
A: De API streamt gegevens en geeft resources vrij wanneer `pres.dispose()` wordt aangeroepen, wat helpt bij het geheugenbeheer voor grote bestanden.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}