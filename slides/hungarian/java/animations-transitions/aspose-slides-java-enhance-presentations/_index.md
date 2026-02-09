---
date: '2026-02-09'
description: Tanulja meg, hogyan rajzoljon kereteket a szöveg köré, és hogyan adjon
  szöveget a táblázat celláihoz a PowerPointban az Aspose.Slides for Java használatával.
  Ez az útmutató bemutatja a táblázatok létrehozását, a szöveg igazításának beállítását,
  valamint a prezentáció pptx formátumban való mentését.
keywords:
- Aspose.Slides for Java
- table manipulation in presentations
- frame drawing in PowerPoint
title: Keretek rajzolása és szöveg hozzáadása a táblához az Aspose.Slides for Java
  segítségével
url: /hu/java/animations-transitions/aspose-slides-java-enhance-presentations/
weight: 1
---

.

Check for any remaining English text: The shortcodes remain unchanged. The code block placeholders remain unchanged. The URLs remain unchanged.

Make sure we kept the bullet list formatting.

Now produce final content.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan rajzolj kereteket és adj hozzá szöveget a táblázathoz a prezentációkban az Aspose.Slides for Java segítségével

## Introduction

Az adatok világos bemutatása a PowerPointban igazi kihívás lehet, különösen, ha **szöveget kell hozzáadni a táblázathoz** a cellákban, és vizuális jelzésekkel szeretnéd kiemelni a fontos értékeket. Ebben az útmutatóban megtanulod, hogyan **rajzolj kereteket** konkrét bekezdések köré, hogyan állítsd be a szöveg igazítását alakzatokon belül, és végül hogyan **mentsd a prezentációt pptx formátumban** – mindezt az Aspose.Slides for Java használatával. A végére egy kifinomult diakészletet kapsz, amely a közönség figyelmét pontosan arra irányítja, ahová szeretnéd.

Készen állsz, hogy diáid kitűnjenek? Lépésről lépésre végigvezetünk a folyamaton.

## Quick Answers
- **Mi jelent a „szöveg hozzáadása a táblázathoz”?** Ez azt jelenti, hogy programozottan beszúrod vagy frissíted az egyes táblázatcellák szöveges tartalmát.  
- **Melyik metódus menti a fájlt?** `pres.save("output.pptx", SaveFormat.Pptx)` – ez a **save presentation as pptx** lépés véglegesíti a módosításokat.  
- **Hogyan igazítható a szöveg egy alakzatban?** Használd a `TextAlignment.Left` (vagy Center/Right) értéket a `autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(...)` segítségével.  
- **Rajzolhatok téglalapot egy bekezdés köré?** Igen – iterálj a bekezdéseken, szerezd meg a határoló téglalapot, és adj hozzá egy `IAutoShape`-t kitöltés nélkül és fekete vonallal.  
- **Szükségem van licencre?** Egy ideiglenes licenc elegendő értékeléshez; a teljes licenc szükséges a termelésben való használathoz.  

## Why draw frames around text?

Miért rajzoljunk kereteket a szöveg köré?

A bekezdés vagy egy adott rész (például minden **'0'** karaktert tartalmazó szöveg) köré keret (vagy téglalap) rajzolása azonnal felhívja a figyelmet. Ez a technika ideális:

- A táblázat kulcsfontosságú pénzügyi adatok kiemelésére.  
- Figyelmeztetések vagy fontos megjegyzések hangsúlyozására egy dián.  
- Vizuális elválasztók létrehozására további alakzatok manuális hozzáadása nélkül.

## Prerequisites

Az alábbiak biztosítása szükséges a kód megkezdése előtt:

### Required Libraries
Az alábbi könyvtárakra lesz szükséged. Így adhatod hozzá Maven vagy Gradle segítségével:

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

### Environment Setup
Győződj meg róla, hogy telepítve van egy Java Development Kit (JDK), ajánlott a JDK 16 vagy újabb, mivel ez a példa a `jdk16` osztálycímkét használja.

### Knowledge Prerequisites
- Alapvető Java programozási ismeretek.  
- Ismeret a prezentációs szoftverekkel, például a PowerPointtal.  
- Tapasztalat egy integrált fejlesztőkörnyezet (IDE) használatában, mint az IntelliJ IDEA vagy az Eclipse.

## Setting Up Aspose.Slides for Java

Az Aspose.Slides használatának megkezdéséhez kövesd az alábbi lépéseket:

1. **Könyvtár telepítése**: Használd a Maven vagy Gradle rendszert a függőségek kezeléséhez, vagy töltsd le közvetlenül a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

2. **Licenc beszerzése**:
   - Kezdd egy ingyenes próbaverzióval, ideiglenes licenc letöltésével a [Temporary License](https://purchase.aspose.com/temporary-license/) oldalról.
   - Teljes hozzáféréshez vásárolj licencet a [Purchase Aspose.Slides](https://purchase.aspose.com/buy) oldalon.

3. **Alapvető inicializálás**:
Inicializáld a prezentációs környezetet az alábbi kódrészlettel:
```java
import com.aspose.slides.*;

Presentation pres = new Presentation();
try {
    // Your code here
} finally {
    if (pres != null) pres.dispose();
}
```

## How to Add Text to Table in Aspose.Slides for Java

### 1. funkció: Táblázat létrehozása és szöveg hozzáadása a cellákhoz

#### Áttekintés
Ez a funkció bemutatja, hogyan **hozzunk létre táblázatot**, majd **adjunk szöveget a táblázat celláihoz**, és végül **mentsük a prezentációt pptx formátumban**.

#### Lépések

**1. Táblázat létrehozása**  
Először inicializáld a prezentációt, és adj hozzá egy táblázatot a (50, 50) pozícióban a megadott oszlopszélességekkel és sormagasságokkal.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Szöveg hozzáadása a cellákhoz**  
Hozz létre bekezdéseket szövegrészekkel, és add hozzá őket egy adott cellához.
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

**3. Prezentáció mentése**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 2. funkció: TextFrame hozzáadása AutoShape-hez és igazítás beállítása

#### Áttekintés
Tudd meg, hogyan adj hozzá egy szövegkeretet meghatározott igazítással egy auto shape-hez – egy példa a **set text alignment java** használatára.

#### Lépések

**1. AutoShape hozzáadása**  
Adj hozzá egy téglalapot AutoShape-ként a (400, 100) pozícióban a megadott méretekkel.
```java
Presentation pres = new Presentation();
try {
    IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(
        ShapeType.Rectangle, 400, 100, 60, 120);
```

**2. Szöveg igazítás beállítása**  
Állítsd be a szöveget „Text in shape” értékre, és igazítsd balra.
```java
    autoShape.getTextFrame().setText("Text in shape");
    autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```

**3. Prezentáció mentése**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### 3. funkció: Keretek rajzolása bekezdések és szövegrészek köré a táblázat celláiban

#### Áttekintés
Ez a funkció a **draw frames around text** és akár a **draw rectangle around paragraph** megvalósítására összpontosít, a ‘0’ karaktert tartalmazó részek esetén.

#### Lépések

**1. Táblázat létrehozása**  
Használd újra a „Create Table and Add Text to Cells” kódrészletet a kezdeti beállításhoz.
```java
Presentation pres = new Presentation();
try {
    ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(
        50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```

**2. Bekezdések hozzáadása**  
Használd újra a bekezdés létrehozó kódot az előző funkcióból.
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
Iterálj a bekezdéseken és szövegrészeken, hogy kereteket rajzolj köréjük.
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

**4. Prezentáció mentése**  
```java
    pres.save("YOUR_OUTPUT_DIRECTORY/GetRect_Out.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Common Pitfalls & Tips

- **Null ellenőrzések** – Mindig tedd a `Presentation` használatát try‑finally blokkba, hogy a `pres.dispose()` lefusson és felszabadítsa a natív erőforrásokat.  
- **A határoló téglalap pontossága** – A `para.getRect()` által visszaadott téglalap a jelenlegi elrendezést tükrözi; ha betűméretet vagy margókat változtatsz, számold újra a téglalapot a keret rajzolása előtt.  
- **Teljesítmény** – Nagyon nagy táblázatok esetén fontold meg a shape-ek csoportos hozzáadását vagy egyetlen `IAutoShape` példány újrahasználatát frissített geometriával a memóriahasználat csökkentése érdekében.

## Frequently Asked Questions

**K: Használhatom ezeket az API-kat régebbi JDK verziókkal?**  
V: A könyvtár a JDK 8-tól támogatott, de a `jdk16` osztálycímke a legjobb teljesítményt nyújt az újabb futtatókörnyezetekben.

**K: Hogyan változtathatom meg a keret színét?**  
V: Módosítsd a vonalformátum kitöltő színét, például `shape.getLineFormat().getFillFormat().setSolidFillColor(Color.BLUE);`.

**K: Lehetőség van a végső diát képként exportálni?**  
V: Igen – használd a `pres.getSlides().get_Item(0).getImage(Export.ImageFormat.Png)` metódust, majd mentsd el a byte tömböt.

**K: Mi a teendő, ha csak a „Total” szót kell kiemelni egy cellában?**  
V: Iterálj a `cell.getTextFrame().getParagraphs()` elemein, keresd meg a “Total” szót tartalmazó részt, és rajzolj egy téglalapot annak határoló kerete köré.

**K: Kezeli-e az Aspose.Slides hatékonyan a nagy prezentációkat?**  
V: Az API adatfolyamot használ és felszabadítja az erőforrásokat a `pres.dispose()` hívásakor, ami segít a memória kezelésében nagy fájlok esetén.

---

{{< blocks/products/products-backtop-button >}}

**Last Updated:** 2026-02-09  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}