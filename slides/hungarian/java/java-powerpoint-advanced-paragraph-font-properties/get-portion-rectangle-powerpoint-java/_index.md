---
title: Szerezze be a Portion Rectangle-t a PowerPointban Java segítségével
linktitle: Szerezze be a Portion Rectangle-t a PowerPointban Java segítségével
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ebből a részletes, lépésenkénti oktatóanyagból megtudhatja, hogyan állíthatja be a résztéglalapot a PowerPointban az Aspose.Slides for Java segítségével. Java fejlesztőknek tökéletes.
weight: 12
url: /hu/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Dinamikus prezentációk létrehozása Java nyelven gyerekjáték az Aspose.Slides for Java segítségével. Ebben az oktatóanyagban belevetjük magunkat az Aspose.Slides segítségével a rész-téglalap PowerPointban való lekérésének alapjaiba. A környezet beállításától a kód lépésről lépésre történő lebontásáig mindenre kiterjedünk. Szóval, kezdjük!
## Előfeltételek
Mielőtt belevágnánk a kódba, győződjünk meg arról, hogy minden megvan, ami a zökkenőmentes követéshez szükséges:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK 8 vagy újabb verziója van telepítve a gépére.
2.  Aspose.Slides for Java: Töltse le a legújabb verziót innen[itt](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Eclipse, IntelliJ IDEA vagy bármilyen más Java IDE, amelyet Ön választ.
4. Alapszintű Java ismerete: A Java programozás ismerete elengedhetetlen.
## Csomagok importálása
Először is importáljuk a szükséges csomagokat. Ez magában foglalja az Aspose.Slides-t és néhány másikat is a feladatunk hatékony kezeléséhez.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## 1. lépés: A prezentáció beállítása
Az első lépés egy új prezentáció létrehozása. Ez lesz a vásznunk, amin dolgozhatunk.
```java
Presentation pres = new Presentation();
```
## 2. lépés: Táblázat létrehozása
Most pedig adjunk hozzá egy táblázatot bemutatónk első diájához. Ez a táblázat tartalmazza azokat a cellákat, ahová a szövegünket hozzáadjuk.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## 3. lépés: Bekezdések hozzáadása a cellákhoz
Ezután bekezdéseket hozunk létre, és hozzáadjuk őket a táblázat egy adott cellájához. Ez magában foglalja a meglévő szöveg törlését, majd új bekezdések hozzáadását.
```java
// Hozzon létre bekezdéseket
IParagraph paragraph0 = new Paragraph();
paragraph0.getPortions().add(new Portion("Text "));
paragraph0.getPortions().add(new Portion("in0"));
paragraph0.getPortions().add(new Portion(" Cell"));
IParagraph paragraph1 = new Paragraph();
paragraph1.setText("On0");
IParagraph paragraph2 = new Paragraph();
paragraph2.getPortions().add(new Portion("Hi there "));
paragraph2.getPortions().add(new Portion("col0"));
// Szöveg hozzáadása a táblázat cellájához
ICell cell = tbl.get_Item(1, 1);
cell.getTextFrame().getParagraphs().clear();
cell.getTextFrame().getParagraphs().add(paragraph0);
cell.getTextFrame().getParagraphs().add(paragraph1);
cell.getTextFrame().getParagraphs().add(paragraph2);
```
## 4. lépés: Szövegkeret hozzáadása egy AutoShape-hoz
Prezentációnk dinamikusabbá tételéhez szövegkeretet adunk az AutoShape-hoz, és beállítjuk annak igazítását.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## 5. lépés: Koordináták kiszámítása
Meg kell kapnunk a táblázatcella bal felső sarkának koordinátáit. Ez segít a formák pontos elhelyezésében.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## 6. lépés: Keretek hozzáadása a bekezdésekhez és részekhez
 Használni a`IParagraph.getRect()` és`IPortion.getRect()`módszerekkel kereteket adhatunk a bekezdéseinkhez és részeinkhez. Ez magában foglalja a bekezdések és részek iterációját, alakzatok létrehozását körülöttük és a megjelenésük testreszabását.
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
## 7. lépés: Keretek hozzáadása az AutoShape bekezdésekhez
Hasonlóképpen kereteket adunk a bekezdésekhez az AutoShape-ban, javítva a prezentáció vizuális vonzerejét.
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
## 8. lépés: A prezentáció mentése
Végül elmentjük a prezentációnkat egy megadott útvonalra.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## 9. lépés: Tisztítás
Jó gyakorlat a prezentációs objektum megsemmisítése az erőforrások felszabadítása érdekében.
```java
if (pres != null) pres.dispose();
```
## Következtetés
Gratulálunk! Sikeresen megtanulta, hogyan szerezheti be a résztéglalapot a PowerPointban az Aspose.Slides for Java segítségével. Ez a hatékony könyvtár a lehetőségek világát nyitja meg a dinamikus és tetszetős prezentációk programozott létrehozásához. Merüljön el mélyebben az Aspose.Slides-ben, és fedezzen fel további funkciókat prezentációinak továbbfejlesztéséhez.
## GYIK
### Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára PowerPoint prezentációk programozott létrehozását, módosítását és kezelését.
### Használhatom az Aspose.Slides for Java programot kereskedelmi projektekben?
 Igen, az Aspose.Slides for Java használható kereskedelmi projektekben. Engedélyt vásárolhat innen[itt](https://purchase.aspose.com/buy).
### Létezik ingyenes próbaverzió az Aspose.Slides for Java számára?
 Igen, letölthet egy ingyenes próbaverziót a webhelyről[itt](https://releases.aspose.com/).
### Hol találom az Aspose.Slides for Java dokumentációját?
 A dokumentáció elérhető[itt](https://reference.aspose.com/slides/java/).
### Hogyan kaphatok támogatást az Aspose.Slides for Java számára?
 Támogatást kaphat az Aspose fórumtól[itt](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
