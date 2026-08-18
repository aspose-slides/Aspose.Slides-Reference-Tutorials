---
date: '2026-06-23'
description: Ismerje meg, hogyan hozhat létre táblázatot PowerPointban, adhat szöveget
  a táblázat celláiba, rajzolhat kereteket a szöveg köré, és mentheti a prezentációt
  pptx formátumban az Aspose.Slides for Java használatával.
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
title: Hogyan hozzunk létre táblázatot PowerPointban, és rajzoljunk kereteket az Aspose.Slides
  for Java segítségével
url: /hu/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan hozzunk létre táblázatot PowerPointban, és rajzoljunk kereteket az Aspose.Slides for Java segítségével

## Bevezetés

A **create table in PowerPoint** programozott létrehozása órákat takaríthat meg a kézi formázásból, különösen akkor, ha ki kell emelni a kulcsfontosságú számokat vagy magyarázó megjegyzéseket kell hozzáadni. Ebben az útmutatóban megtudja, hogyan adhat szöveget a táblázat celláihoz, hogyan rajzolhat kereteket meghatározott bekezdések köré, hogyan állíthat be pontos szövegigazítást, és végül **save presentation as pptx** – mindezt az erőteljes Aspose.Slides for Java API-val. A végére egy olyan diát kap, amely kifinomult, könnyen olvasható, és azonnal felhívja a közönség figyelmét a legfontosabb adatokra.

## Gyors válaszok
- **Mi jelent a „add text to table”?** Ez azt jelenti, hogy programozottan szöveges tartalmat szúr be vagy frissít az egyes táblázatcellákban.  
- **Melyik metódus menti a fájlt?** `pres.save("output.pptx", SaveFormat.Pptx)` – ez a **save presentation as pptx** lépés véglegesíti a módosításokat.  
- **Hogyan igazíthatom a szöveget egy alakzatban?** Használja a `TextAlignment.Left` (vagy Center/Right) értéket a `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` híváson keresztül.  
- **Rajzolhatok-e téglalapot egy bekezdés köré?** Igen – iteráljon a bekezdéseken, szerezze meg a határoló téglalapot, és adjon hozzá egy `IAutoShape`-t kitöltés nélkül és fekete vonallal.  
- **Szükségem van licencre?** Egy ideiglenes licenc elegendő értékeléshez; a teljes licenc szükséges a termelési használathoz.  

## Miért rajzoljunk kereteket a szöveg köré?

Kerete (vagy téglalap) rajzolása egy bekezdés vagy egy meghatározott rész – például bármely **'0'** karaktert tartalmazó szöveg – köré azonnal felhívja a közönség figyelmét az adott tartalomra. Egyértelmű vizuális jelzést ad anélkül, hogy megváltoztatná az alapszöveget, így ideális a kulcsfontosságú számok, figyelmeztetések kiemelésére vagy a dián belüli szakaszok elválasztására.

## Előfeltételek

Mielőtt belemerülne a kódba, győződjön meg arról, hogy a következőkkel rendelkezik:

### Szükséges könyvtárak
Szüksége lesz az Aspose.Slides for Java-ra. Íme, hogyan lehet felvenni Maven vagy Gradle használatával:

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

### Környezet beállítása
Győződjön meg arról, hogy telepítve van egy Java Development Kit (JDK), lehetőleg JDK 16 vagy újabb, mivel ez a példa a `jdk16` osztályozót használja.

### Tudás előfeltételek
- Alapvető Java programozási ismeretek.  
- Ismeret a prezentációs szoftverekkel, mint a PowerPoint.  
- Tapasztalat integrált fejlesztőkörnyezet (IDE) használatában, például IntelliJ IDEA vagy Eclipse.

## Az Aspose.Slides for Java beállítása

A `Presentation` az Aspose.Slides központi osztálya, amely egy PowerPoint fájlt reprezentál a memóriában, és hozzáférést biztosít a diákhoz, alakzatokhoz és táblázatokhoz. Az Aspose.Slides használatához kövesse az alábbi lépéseket:

1. **Install the Library**: Use Maven or Gradle to manage dependencies, or download it directly from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

2. **License Acquisition**:
   - Start with a free trial by downloading a temporary license from [Temporary License](https://purchase.aspose.com/temporary-license/).
   - For full access, consider purchasing a license at [Purchase Aspose.Slides](https://purchase.aspose.com/buy).

3. **Basic Initialization**:  
   Initialize your presentation environment with the following code snippet:  
   ```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```  

## Hogyan adjon szöveget a táblázathoz az Aspose.Slides for Java-ban?

Töltsön be egy új `Presentation`-t, hozzon létre egy táblázatot a kívánt koordinátákon, töltse fel a cellákat `TextFrame` objektumokkal, majd végül hívja meg a `pres.save("output.pptx", SaveFormat.Pptx)` metódust. Ez a sorozat **create table in PowerPoint**-ot hoz létre, egyedi szöveget injektál minden cellába, és egyetlen, hatékony munkafolyamatban írja ki az eredményt egy PPTX fájlba.

### 1. funkció: Táblázat létrehozása és szöveg hozzáadása a cellákhoz

#### Áttekintés
Ez a funkció bemutatja, hogyan **create table**, majd **add text to table** cellákat, és végül **save presentation as pptx**.

#### Lépések

**1. Táblázat létrehozása**  
Először inicializálja a prezentációt, és adjon hozzá egy táblázatot a (50, 50) pozícióban a megadott oszlopszélességekkel és sormagasságokkal.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Szöveg hozzáadása a cellákhoz**  
Hozzon létre bekezdéseket szövegrészekkel, és adja hozzá őket egy adott cellához.  
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

**3. A prezentáció mentése**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### 2. funkció: TextFrame hozzáadása AutoShape-hez és igazítás beállítása

#### Áttekintés
Tanulja meg, hogyan adjon hozzá egy szövegkeretet meghatározott igazítással egy auto shape-hez – egy példa a **set text alignment java**-ra.

#### Lépések

Az AutoShape egy olyan alakzat, amely szöveget és grafikát is tartalmazhat.

**1. AutoShape hozzáadása**  
Adjon hozzá egy téglalapot AutoShape-ként a (400, 100) pozícióban a megadott méretekkel.  
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```  

`TextAlignment` enum definiálja a szöveg vízszintes igazítási lehetőségeit egy alakzatban.

**2. Szövegigazítás beállítása**  
Állítsa be a szöveget „Text in shape” értékre, és igazítsa balra.  
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```  

**3. A prezentáció mentése**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

### 3. funkció: Keretek rajzolása bekezdések és részek köré a táblázat celláiban

#### Áttekintés
Ez a funkció a **draw frames around text** és akár a **draw rectangle around paragraph** megvalósítására fókuszál, a ‘0’ karaktert tartalmazó részek esetén.

#### Lépések

`IAutoShape` egy olyan alakzatobjektum, amely a diára rajzolható, például keretekhez használt téglalapok.

**1. Táblázat létrehozása**  
Használja újra a „Create Table and Add Text to Cells” kódrészletet a kezdeti beállításhoz.  
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```  

**2. Bekezdések hozzáadása**  
Használja újra a bekezdéskészítő kódot az előző funkcióból.  
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

**3. Keretek rajzolása**  
Iteráljon a bekezdéseken és részeken, és rajzoljon köréjük kereteket.  
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

**4. A prezentáció mentése**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```  

## Gyakori buktatók és tippek

- **Null checks** – Mindig helyezze a `Presentation` használatát egy try‑finally blokkba, hogy a `pres.dispose()` lefusson és felszabadítsa a natív erőforrásokat.  
- **Bounding rectangle accuracy** – A `para.getRect()` által visszaadott téglalap a jelenlegi elrendezést tükrözi; ha betűméretet vagy margókat változtat, számolja újra a téglalapot a keret rajzolása előtt.  
- **Performance** – Nagyon nagy táblázatok esetén fontolja meg a shape‑ek csoportos hozzáadását vagy egyetlen `IAutoShape` példány újrahasználatát frissített geometriával a memóriahasználat csökkentése érdekében.  

## Gyakran feltett kérdések

**Q: Használhatom ezeket az API‑kat régebbi JDK verziókkal?**  
A: A könyvtár támogatja a JDK 8‑tól felfelé, de a `jdk16` osztályozó a legjobb teljesítményt nyújt az újabb futtatókörnyezetekben.

**Q: Hogyan változtathatom meg a keret színét?**  
A: Módosítsa a vonalformátum kitöltési színét, például `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**Q: Lehetőség van a végső dia képként exportálására?**  
A: Igen – használja a `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` metódust, majd mentse el a byte‑tömböt.

**Q: Mi a teendő, ha csak a „Total” szót kell kiemelnem egy cellán belül?**  
A: Iteráljon a `cell.getTextFrame().getParagraphs()` elemein, keresse meg a „Total” szót tartalmazó részt, és rajzoljon egy téglalapot a rész határoló doboza köré.

**Q: Az Aspose.Slides hatékonyan kezeli a nagy prezentációkat?**  
A: Az API adatfolyamot használ és felszabadítja az erőforrásokat a `pres.dispose()` hívásakor, ami segít a memória kezelésében nagy fájlok esetén.

---

**Last Updated:** 2026-06-23  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Aspose.Slides for Java: PPTX táblázat és szövegkezelés a PowerPoint prezentációkban](/slides/java/tables/aspose-slides-java-pptx-table-text-manipulation-guide/)
- [Dinamikus szövegkeretek létrehozása PowerPointban az Aspose.Slides for Java használatával](/slides/java/shapes-text-frames/dynamic-text-frames-powerpoint-aspose-slides-java/)
- [Oszlopok hozzáadása szövegkerethez az Aspose.Slides for Java segítségével](/slides/java/java-powerpoint-text-box-manipulation/add-columns-in-text-frame/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}