---
title: Kép hozzáadása a táblázat celláihoz a Java PowerPointban
linktitle: Kép hozzáadása a táblázat celláihoz a Java PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ebből a részletes, lépésenkénti útmutatóból megtudhatja, hogyan adhat hozzá képeket a Java PowerPoint prezentációk táblázatcelláihoz az Aspose.Slides for Java használatával.
weight: 10
url: /hu/java/java-powerpoint-table-manipulation/add-image-inside-table-cells-java-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Ha szeretné javítani Java PowerPoint prezentációit azáltal, hogy képeket ágyaz be táblázatcellákba, akkor jó helyen jár! Ma az Aspose.Slides for Java használatával részletes, lépésről-lépésre szóló útmutatót mutatunk be. Ez az oktatóanyag végigvezeti Önt a teljes folyamaton, így még egy kezdő is követni tudja, és lenyűgöző eredményeket érhet el.
## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg arról, hogy mindennel rendelkezik, amire szüksége van:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a gépen. Letöltheti innen[Az Oracle webhelye](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Töltse le az Aspose.Slides könyvtárat a[weboldal](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Java fejlesztéshez IntelliJ IDEA vagy Eclipse használatát javasoljuk.
4. Képfájl: Készítsen egy képfájlt, amelyet be szeretne ágyazni a PowerPoint táblázat celláiba.
Most, hogy minden előfeltétel megvan, térjünk át a szükséges csomagok importálására és a kód megírására.
## Csomagok importálása
Először importálja a szükséges csomagokat a Java projektbe. Ezek a csomagok lehetővé teszik az Aspose.Slides és a Java képkezelés által biztosított funkciók kihasználását.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Bontsuk a példát több lépésre, hogy könnyebb legyen követni.
## 1. lépés: Állítsa be a bemutatót
Kezdje a prezentációs objektum beállításával, és nyissa meg az első diát.
```java
// Határozza meg a dokumentumkönyvtár elérési útját
String dataDir = "Your Document Directory";
// Példányosítsa a Presentation osztály objektumot
Presentation presentation = new Presentation();
```
Ez a kódrészlet inicializál egy új PowerPoint-prezentációt, és előkészíti a további módosításokra.
## 2. lépés: Nyissa meg az első diát
Ezután nyissa meg a prezentáció első diáját. Ez a dia lesz a vászon, ahová a táblázatot hozzáadjuk.
```java
try {
    // Nyissa meg az első diát
    ISlide slide = presentation.getSlides().get_Item(0);
```
## 3. lépés: Határozza meg a táblázat méreteit
Határozza meg a táblázat oszlopainak szélességét és sorainak magasságát. Ez a lépés kulcsfontosságú annak biztosításához, hogy a táblázatcellák megfelelő méretűek legyenek.
```java
    // Határozzon meg oszlopokat szélességgel és sorokat magassággal
    double[] columns = {150, 150, 150, 150};
    double[] rows = {100, 100, 100, 100, 90};
```
## 4. lépés: Táblázat hozzáadása a diához
Adja hozzá a táblázat alakját a diához a megadott méretekkel.
```java
    // Táblázat alakzat hozzáadása a csúszáshoz
    ITable table = slide.getShapes().addTable(50, 50, columns, rows);
```
## 5. lépés: Töltse be a képet
Töltse be a táblázat cellájába beágyazni kívánt képet. Győződjön meg arról, hogy a képfájl elérhető a megadott könyvtárban.
```java
    // Hozzon létre egy BufferedImage objektumot a képfájl tárolására
    BufferedImage image = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
    // Hozzon létre egy IPPImage objektumot a bitkép objektum használatával
    IPPImage imgx = presentation.getImages().addImage(image);
```
## 6. lépés: Kép hozzáadása a táblázat cellájához
Ideje hozzáadni a képet a táblázat első cellájához. Konfigurálja a kitöltési formátumot és állítsa be a kép tulajdonságait.
```java
    // Kép hozzáadása a táblázat első cellájához
    table.get_Item(0, 0).getCellFormat().getFillFormat().setFillType(FillType.Picture);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setPictureFillMode(PictureFillMode.Stretch);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().getPicture().setImage(imgx);
```
## 7. lépés: Állítsa be a képkivágást
Szükség esetén állítsa be a képkivágást úgy, hogy tökéletesen illeszkedjen a cellába. Ez a lépés biztosítja, hogy a kép megfelelően néz ki.
```java
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropRight(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropLeft(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropTop(20);
    table.get_Item(0, 0).getCellFormat().getFillFormat().getPictureFillFormat().setCropBottom(20);
```
## 8. lépés: Mentse el a prezentációt
Végül mentse a módosított prezentációt a kívánt könyvtárba.
```java
    // Mentse a PPTX-t lemezre
    presentation.save(dataDir + "Image_In_TableCell_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (presentation != null) presentation.dispose();
}
```

## Következtetés
Tessék, itt van! Az alábbi lépések követésével az Aspose.Slides segítségével sikeresen hozzáadhat képeket a Java PowerPoint prezentáció táblázatcelláihoz. Ez az útmutató a környezet beállításától a végső prezentáció mentéséig mindenre kiterjedt. Remélem, hogy ez az oktatóanyag segít látványosabb prezentációk létrehozásában.
## GYIK
### Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy hatékony API PowerPoint prezentációk létrehozásához, módosításához és kezeléséhez Java alkalmazásokban.
### Létezik ingyenes próbaverzió az Aspose.Slides számára?
 Igen, kaphat a[ingyenes próbaverzió](https://releases.aspose.com/) hogy vásárlás előtt próbálja ki az Aspose.Slides-t.
### Használhatok bármilyen képformátumot az Aspose.Slides programban?
Az Aspose.Slides különféle képformátumokat támogat, beleértve a JPEG-et, PNG-t, BMP-t és még sok mást.
### Hol találok részletesebb dokumentációt?
 Hivatkozhat a[dokumentáció](https://reference.aspose.com/slides/java/) részletesebb információkért és példákért.
### Hogyan vásárolhatom meg az Aspose.Slides for Java programot?
 Megvásárolhatja a[Aspose honlapja](https://purchase.aspose.com/buy).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
