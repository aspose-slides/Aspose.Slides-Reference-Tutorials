---
"description": "Tanuld meg, hogyan készítheted el a PowerPointban a szakasztéglalapot az Aspose.Slides for Java segítségével ezzel a részletes, lépésről lépésre szóló útmutatóval. Tökéletes Java-fejlesztők számára."
"linktitle": "Szerezd meg a Portion Rectangle-t PowerPointban Java-val"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Szerezd meg a Portion Rectangle-t PowerPointban Java-val"
"url": "/hu/java/java-powerpoint-advanced-paragraph-font-properties/get-portion-rectangle-powerpoint-java/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Szerezd meg a Portion Rectangle-t PowerPointban Java-val

## Bevezetés
A dinamikus prezentációk készítése Java nyelven gyerekjáték az Aspose.Slides segítségével. Ebben az oktatóanyagban részletesen bemutatjuk, hogyan készítsünk egy téglalapot PowerPointban az Aspose.Slides segítségével. Mindent áttekintünk, a környezet beállításától kezdve a kód lépésről lépésre történő lebontásáig. Akkor kezdjük is!
## Előfeltételek
Mielőtt belevágnánk a kódba, győződjünk meg róla, hogy minden megvan, amire szükséged van a zökkenőmentes követéshez:
1. Java fejlesztőkészlet (JDK): Győződjön meg arról, hogy a JDK 8-as vagy újabb verziója telepítve van a gépén.
2. Aspose.Slides Java-hoz: Töltse le a legújabb verziót innen: [itt](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Eclipse, IntelliJ IDEA, vagy bármely más választott Java IDE.
4. Java alapismeretek: A Java programozás ismerete elengedhetetlen.
## Csomagok importálása
Először is importáljuk a szükséges csomagokat. Ez magában foglalja az Aspose.Slides-t és néhány mást, amelyek hatékonyan kezelik a feladatunkat.
```java
import com.aspose.slides.*;
import com.aspose.slides.examples.RunExamples;
import java.awt.*;
import java.awt.geom.Rectangle2D;
```
## 1. lépés: A prezentáció beállítása
Az első lépés egy új prezentáció létrehozása. Ez lesz a vásznunk, amelyen dolgozhatunk.
```java
Presentation pres = new Presentation();
```
## 2. lépés: Táblázat létrehozása
Most adjunk hozzá egy táblázatot a prezentációnk első diájához. Ez a táblázat fogja tartalmazni azokat a cellákat, ahová a szöveget beillesztjük.
```java
ITable tbl = pres.getSlides().get_Item(0).getShapes().addTable(50, 50, new double[]{50, 70}, new double[]{50, 50, 50});
```
## 3. lépés: Bekezdések hozzáadása cellákhoz
Ezután bekezdéseket hozunk létre, és hozzáadjuk azokat a táblázat egy adott cellájához. Ez magában foglalja a meglévő szöveg törlését, majd új bekezdések hozzáadását.
```java
// Bekezdések létrehozása
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
## 4. lépés: Szövegkeret hozzáadása egy alakzathoz
A prezentációnk dinamikusabbá tétele érdekében szövegkeretet adunk hozzá egy alakzathoz, és beállítjuk az igazítását.
```java
IAutoShape autoShape = pres.getSlides().get_Item(0).getShapes().addAutoShape(ShapeType.Rectangle, 400, 100, 60, 120);
autoShape.getTextFrame().setText("Text in shape");
autoShape.getTextFrame().getParagraphs().get_Item(0).getParagraphFormat().setAlignment(TextAlignment.Left);
```
## 5. lépés: Koordináták kiszámítása
Meg kell kapnunk a táblázatcella bal felső sarkának koordinátáit. Ez segít majd pontosan elhelyezni az alakzatokat.
```java
double x = tbl.getX() + cell.getOffsetX();
double y = tbl.getY() + cell.getOffsetY();
```
## 6. lépés: Keretek hozzáadása bekezdésekhez és részekhez
A `IParagraph.getRect()` és `IPortion.getRect()` metódusok segítségével kereteket adhatunk a bekezdésekhez és a részekhez. Ez magában foglalja a bekezdések és részek közötti iterációt, alakzatok létrehozását körülöttük, és a megjelenésük testreszabását.
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
Hasonlóképpen, kereteket adunk a bekezdésekhez az alakzatunkban, ami fokozza a bemutató vizuális vonzerejét.
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
Végül a prezentációnkat egy megadott elérési útra mentjük.
```java
String outPath = "path_to_output_directory";
pres.save(outPath + "GetRect_Out.pptx", SaveFormat.Pptx);
```
## 9. lépés: Takarítás
Jó gyakorlat a prezentációs objektum eltávolítása az erőforrások felszabadítása érdekében.
```java
if (pres != null) pres.dispose();
```
## Következtetés
Gratulálunk! Sikeresen megtanultad, hogyan készíthetsz résztéglalapot PowerPointban az Aspose.Slides Java verziójával. Ez a hatékony könyvtár a lehetőségek tárházát nyitja meg előtted dinamikus és vizuálisan vonzó prezentációk programozott létrehozására. Merülj el mélyebben az Aspose.Slides világában, és fedezz fel további funkciókat a prezentációid további fejlesztéséhez.
## GYIK
### Mi az Aspose.Slides Java-hoz?
Az Aspose.Slides for Java egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan hozzanak létre, módosítsanak és manipuláljanak PowerPoint prezentációkat.
### Használhatom az Aspose.Slides-t Java-ban kereskedelmi projektekben?
Igen, az Aspose.Slides Java-hoz használható kereskedelmi projektekben. Licenc vásárolható innen: [itt](https://purchase.aspose.com/buy).
### Van ingyenes próbaverzió az Aspose.Slides for Java-hoz?
Igen, letölthetsz egy ingyenes próbaverziót innen [itt](https://releases.aspose.com/).
### Hol találom az Aspose.Slides Java-hoz készült dokumentációját?
A dokumentáció elérhető [itt](https://reference.aspose.com/slides/java/).
### Hogyan kaphatok támogatást az Aspose.Slides for Java-hoz?
Segítséget kaphatsz az Aspose fórumon [itt](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}