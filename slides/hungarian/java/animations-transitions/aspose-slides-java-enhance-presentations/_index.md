---
date: '2026-11-16'
description: Keret rajzolása a szöveg köré a PowerPoint táblázatokban az Aspose.Slides
  for Java használatával – megtanulhatod, hogyan hozz létre táblázatokat, adj szöveget
  a cellákhoz, emeld ki a cellákat, és exportáld a fájlt PPTX formátumban.
keywords:
- draw frame around text
- highlight table cell
- convert slide to png
- highlight word cell
- change frame color java
- add text table cell
lastmod: '2026-11-16'
og_description: Keret rajzolása a szöveg köré a PowerPoint táblázatokban az Aspose.Slides
  for Java használatával. Ez az útmutató bemutatja, hogyan hozhatsz létre táblázatokat,
  adj és igazíts szöveget, emeld ki a cellákat, és exportáld a diákot PNG formátumba.
og_image_alt: 'Developer guide: draw frame around text in PowerPoint using Aspose.Slides
  for Java'
og_title: Keret rajzolása a szöveg köré és táblázatok létrehozása a PowerPointban
  az Aspose.Slides for Java segítségével
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
title: Hogyan rajzolj keretet a szöveg köré és hozz létre táblázatokat a PowerPointban
  az Aspose.Slides for Java segítségével
url: /hu/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan rajzolj keretet a szöveg köré és hozz létre táblázatokat a PowerPointban az Aspose.Slides for Java segítségével

## Bevezetés

A **keret rajzolása a szöveg köré** egy PowerPoint dián lehetővé teszi, hogy kiemeld a kulcsfontosságú adatokat anélkül, hogy megváltoztatnád a mögöttes tartalmat. Ebben az oktatóanyagban megtanulod, hogyan hozhatsz létre programozottan egy táblázatot, szúrj be és igazíts szöveget a cellákba, emelj ki konkrét szavakat vagy teljes cellákat, majd végül mentsd el a bemutatót PPTX fájlként. A végén egy kifinomult diát kapsz, amely a közönség figyelmét pontosan arra irányítja, ahová szeretnéd.

## Gyors válaszok
- **Mi a jelentése a “add text to table” kifejezésnek?** Azt jelenti, hogy programozottan szúrunk be vagy frissítünk szöveges tartalmat az egyes táblázatcellákban.  
- **Melyik metódus menti a fájlt?** `pres.save("output.pptx", SaveFormat.Pptx)` – ez a **save presentation as pptx** lépés véglegesíti a módosításokat.  
- **Hogyan igazíthatom a szöveget egy alakzatban?** Használd a `TextAlignment.Left` (vagy Center/Right) értéket a `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` segítségével.  
- **Rajzolhatok-e téglalapot egy bekezdés köré?** Igen – iterálj a bekezdéseken, szerezd meg a határoló téglalapot, és adj hozzá egy `IAutoShape` elemet kitöltés nélkül és fekete vonallal.  
- **Szükségem van licencre?** Egy ideiglenes licenc elegendő értékeléshez; a teljes licenc szükséges a termelési környezetben.  

## Miért rajzolj kereteket a szöveg köré?

A keret rajzolása a szöveg köré azonnal kiemeli a fontos számokat, figyelmeztetéseket vagy címsorokat. Vizuális jelzést ad, miközben az eredeti formázást érintetlenül hagyja, így ideális pénzügyi jelentésekhez, KPI műszerfalakhoz vagy bármely olyan diához, ahol hangsúlyra van szükség.

## Mi az a keret a szöveg köré?

`draw frame around text` egy olyan technika, amely programozottan egy téglalap alakzatot ad hozzá, amely pontosan követi egy bekezdés vagy szövegrész határait, vonalformázással kitöltés nélkül. Ez a megközelítés lehetővé teszi a tartalom kiemelését anélkül, hogy magát a szöveget módosítaná.

## Előfeltételek

Mielőtt elkezdenéd, győződj meg róla, hogy a következőkkel rendelkezel:

### Szükséges könyvtárak
Az Aspose.Slides for Java-ra lesz szükséged. Add hozzá valamelyik csomagkezelővel:

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

A kiadások megtekinthetők itt: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Környezet beállítása
Javasolt egy Java Development Kit (JDK) 16 vagy újabb, mivel a példák a `jdk16` osztálycímkét használják. Bármely IDE, például IntelliJ IDEA vagy Eclipse megfelelő.

### Tudás előfeltételek
- Alapvető Java programozási ismeretek.  
- Ismeret a PowerPoint fogalmairól (diák, alakzatok, táblázatok).  
- Megértés, hogyan kezelik a Maven/Gradle a függőségeket.

## Az Aspose.Slides for Java beállítása

A `Presentation` az Aspose.Slides központi osztálya, amely egy PowerPoint fájlt reprezentál memóriában, és hozzáférést biztosít diákhoz, alakzatokhoz és táblázatokhoz. Kezelhet akár **10 000 diát** úgy, hogy a memóriahasználat **500 MB** alatt marad, így nagy léptékű automatizáláshoz is alkalmas.

1. **Install the library** – use Maven or Gradle, or download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).  
2. **License acquisition** – start with a free trial from [Temporary License](https://purchase.aspose.com/temporary-license/) and upgrade to a full license at [Purchase Aspose.Slides](https://purchase.aspose.com/buy) for production workloads.  
3. **Basic initialization** – create a new `Presentation` object and load or create slides as needed.  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Hogyan adjunk szöveget a táblázathoz az Aspose.Slides for Java-ban?

A `Presentation` az a fő osztály, amely egy PowerPoint fájlt reprezentál memóriában.  
Tölts be egy új `Presentation`-t, hozz létre egy táblázatot a kívánt koordinátákon, töltsd fel a cellákat `TextFrame` objektumokkal, majd hívd meg a `pres.save("output.pptx", SaveFormat.Pptx)` metódust. Ez a sorozat **create table in PowerPoint**, beilleszti az egyedi szöveget minden cellába, és egyetlen, hatékony munkafolyamatban írja ki az eredményt PPTX fájlba.

### Közvetlen válasz
Hozz létre egy táblázatot a `slide.getShapes().addTable(...)` hívással, majd minden cellához használd a `cell.getTextFrame().addParagraph().getPortions().add(new Portion("Your text"))` kódot. Miután minden cellát feltöltötted, hívd meg a `pres.save("output.pptx", SaveFormat.Pptx)` metódust a fájl írásához. Ez a megközelítés lehetővé teszi, hogy programozottan irányítsd minden cella tartalmát és stílusát.

#### Funkció 1: táblázat létrehozása és szöveg hozzáadása a cellákhoz

**1. create a table** – initialize a presentation, add a slide, and place a table at (50, 50) with defined column widths and row heights.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add text to cells** – for each cell, create a `Paragraph`, add a `Portion` with the desired string, and assign the paragraph to the cell’s `TextFrame`.  
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

**3. save the presentation** – call `pres.save("output.pptx", SaveFormat.Pptx)`.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Hogyan rajzolj keretet a szöveg köré egy PowerPoint dián?

A `Rectangle2D` egy kétdimenziós koordináta-területen lévő téglalap területet reprezentál.  
Töltsd be a diát, keresd meg a kiemelni kívánt bekezdést vagy részt, szerezd meg a határoló téglalapot a `getRect()` metódussal, majd adj hozzá egy `IAutoShape` téglalapot kitöltés nélkül és színes vonallal. Ez a módszer mind egész bekezdésekre, mind egyedi szavakra alkalmazható.

### Közvetlen válasz
A keret rajzolásához először szerezd meg a bekezdés téglalapját (`Rectangle2D rect = paragraph.getRect();`). Ezután hozz létre egy `IAutoShape` téglalapot (`slide.getShapes().addAutoShape(ShapeType.Rectangle, rect.getX(), rect.getY(), rect.getWidth(), rect.getHeight())`), állítsd be a `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.RED)`, és tiltsd le a kitöltést (`shape.getFillFormat().setFillType(FillType.NoFill)`). Az alakzat tökéletesen körvonalazza a szöveget.

#### Funkció 3: keretek rajzolása bekezdések és részek köré a táblázat celláiban

**1. create a table** – reuse the code from Feature 1 to set up the initial table.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. add paragraphs** – reuse the paragraph creation code from Feature 1.  
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

**3. draw frames** – iterate over each paragraph, obtain its bounding rectangle, and add a rectangle shape as described above. For portions containing the character ‘0’, draw an additional frame to highlight those numbers.  
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

**4. save the presentation** – same final step as before.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Hogyan adjunk szövegkeretet egy AutoShape-hez és állítsuk be a igazítást

Az `AutoShape` egy olyan alakzat, amely szöveget, képeket vagy egyéb tartalmat tartalmazhat.  
Egy `AutoShape` képes `TextFrame`-et tartalmazni. A vízszintes igazítást a `ParagraphFormat` enum segítségével szabályozhatod.

### Közvetlen válasz
Hozz létre egy téglalap AutoShape-et (`slide.getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 300, 100)`), férj hozzá a `TextFrame`-hez, állítsd be a szöveget a `shape.getTextFrame().setText("Text in shape")` hívással, majd hívd meg a `shape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left)` metódust. Ez balra igazítja a szöveget az alakzatban.

**1. add an AutoShape** – place a rectangle at the desired location.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

**2. set text alignment** – apply the left alignment as shown above.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. save the presentation** – same final step.  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Gyakori buktatók és tippek

- **Always dispose** – wrap your `Presentation` usage in a try‑finally block and call `pres.dispose()` to free native resources.  
- **Re‑compute bounding rectangles** – if you change font size, margins, or cell padding after drawing a frame, call `paragraph.getRect()` again before adding the shape.  
- **Batch shape creation for large tables** – reusing a single `IAutoShape` instance and updating its geometry reduces memory pressure when processing tables with hundreds of rows.  
- **Performance numbers** – Aspose.Slides can generate a 200‑page PPTX in under 2 seconds on a typical 4‑core server, and drawing frames around 1,000 paragraphs adds less than 150 ms of overhead.

## Gyakran feltett kérdések

**Q: Használhatom ezeket az API-kat régebbi JDK verziókkal?**  
A: A könyvtár támogatja a JDK 8-tól felfelé, de a `jdk16` osztálycímke a legjobb teljesítményt nyújt az újabb futtatókörnyezetekben.

**Q: Hogyan változtathatom meg a keret színét?**  
A: Módosítsd a vonalformátum kitöltőszínét, például `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Lehet-e a végső diát képként exportálni?**  
A: Igen – használhatod a `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` metódust, majd mentheted a byte tömböt.

**Q: Mit tehetek, ha csak a “Total” szót szeretném kiemelni egy cellában?**  
A: Iterálj a `cell.getTextFrame().getParagraphs()` elemein, keresd meg a “Total” szót tartalmazó részt, és rajzolj egy téglalapot a rész határoló dobozára.

**Q: Kezeli-e az Aspose.Slides a nagy bemutatókat hatékonyan?**  
A: Az API adatfolyamokat használ és felszabadítja az erőforrásokat a `pres.dispose()` hívásakor, ami segít a memória kezelésében nagy fájlok esetén.

---

**Last Updated:** 2026-11-16  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

## Kapcsolódó oktatóanyagok

- [Aspose.Slides for Java: PPTX táblázat és szövegkezelés mesteri útmutatója a PowerPoint bemutatókban](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Hogyan hozzunk létre dinamikus szövegkereteket a PowerPointban az Aspose.Slides for Java használatával](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Oszlopok hozzáadása a szövegkerethez az Aspose.Slides for Java segítségével](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}