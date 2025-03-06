---
title: Az OLE-objektumadatok módosítása a PowerPointban
linktitle: Az OLE-objektumadatok módosítása a PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan módosíthatja az OLE objektumadatokat a PowerPointban az Aspose.Slides for Java segítségével. Lépésről lépésre szóló útmutató a hatékony és egyszerű frissítésekhez.
weight: 14
url: /hu/java/java-powerpoint-animation-shape-manipulation/change-ole-object-data-powerpoint/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Az OLE-objektumadatok módosítása a PowerPoint-prezentációkban kulcsfontosságú feladat lehet, amikor a diák manuális szerkesztése nélkül kell frissítenie a beágyazott tartalmat. Ez az átfogó útmutató végigvezeti a folyamaton az Aspose.Slides for Java használatával, amely egy PowerPoint-prezentációk kezelésére tervezett hatékony könyvtár. Akár tapasztalt fejlesztő, akár csak most kezdi, ezt az oktatóanyagot hasznosnak és könnyen követhetőnek találja.
## Előfeltételek
Mielőtt belemerülnénk a kódba, győződjünk meg arról, hogy mindennel rendelkezünk, ami az induláshoz szükséges.
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren. Letöltheti innen[Az Oracle webhelye](https://www.oracle.com/java/technologies/javase-downloads.html).
2.  Aspose.Slides for Java: Töltse le a legújabb verziót a[Aspose.Slides letöltési oldal](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Bármilyen Java IDE-t használhat, például az IntelliJ IDEA-t, az Eclipse-t vagy a NetBeans-t.
4.  Aspose.Cells for Java: Ez szükséges az OLE objektumon belüli beágyazott adatok módosításához. Töltse le innen[Aspose.Cells letöltési oldal](https://releases.aspose.com/cells/java/).
5.  Prezentációs fájl: Készítsen PowerPoint fájlt egy beágyazott OLE objektummal. Adjunk nevet ennek az oktatóanyagnak`ChangeOLEObjectData.pptx`.
## Csomagok importálása
Először is importáljuk a szükséges csomagokat a Java projektbe.
```java
import com.aspose.cells.OoxmlSaveOptions;
import com.aspose.cells.Workbook;
import com.aspose.slides.*;

import java.io.ByteArrayInputStream;
import java.io.ByteArrayOutputStream;
```

Most bontsuk le a folyamatot egyszerű, kezelhető lépésekre.
## 1. lépés: Töltse be a PowerPoint-prezentációt
A kezdéshez be kell töltenie az OLE objektumot tartalmazó PowerPoint bemutatót.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx");
```
## 2. lépés: Nyissa meg az OLE objektumot tartalmazó diát
Ezután szerezze be azt a diát, amelybe az OLE objektum be van ágyazva.
```java
ISlide slide = pres.getSlides().get_Item(0);
```
## 3. lépés: Keresse meg az OLE objektumot a dián
Ismételje meg a dián lévő alakzatokat az OLE objektum megkereséséhez.
```java
OleObjectFrame ole = null;
// Minden alakzat bejárása az Ole kerethez
for (IShape shape : slide.getShapes()) {
    if (shape instanceof OleObjectFrame) {
        ole = (OleObjectFrame) shape;
        break;
    }
}
```
## 4. lépés: Bontsa ki a beágyazott adatokat az OLE objektumból
Ha az OLE objektumot megtalálja, bontsa ki a beágyazott adatait.
```java
if (ole != null) {
    ByteArrayInputStream msln = new ByteArrayInputStream(ole.getEmbeddedData().getEmbeddedFileData());
```
## 5. lépés: Módosítsa a beágyazott adatokat az Aspose.Cells használatával
Most az Aspose.Cells segítségével olvassa el és módosítsa a beágyazott adatokat, amelyek ebben az esetben valószínűleg egy Excel-munkafüzet.
```java
    Workbook wb = new Workbook(msln);
    // Módosítsa a munkafüzet adatait
    wb.getWorksheets().get(0).getCells().get(0, 4).putValue("E");
    wb.getWorksheets().get(0).getCells().get(1, 4).putValue(12);
    wb.getWorksheets().get(0).getCells().get(2, 4).putValue(14);
    wb.getWorksheets().get(0).getCells().get(3, 4).putValue(15);
```
## 6. lépés: Mentse vissza a módosított adatokat az OLE objektumba
A szükséges módosítások elvégzése után mentse vissza a módosított munkafüzetet az OLE objektumba.
```java
    ByteArrayOutputStream msout = new ByteArrayOutputStream();
    OoxmlSaveOptions so1 = new OoxmlSaveOptions(SaveFormat.XLSX);
    wb.save(msout, so1);
    IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.toByteArray(), ole.getEmbeddedData().getEmbeddedFileExtension());
    ole.setEmbeddedData(newData);
```
## 7. lépés: Mentse el a frissített prezentációt
Végül mentse a frissített PowerPoint-prezentációt.
```java
    pres.save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## Következtetés
Az OLE-objektumadatok frissítése a PowerPoint-prezentációkban az Aspose.Slides for Java használatával egyszerű folyamat, miután egyszerű lépésekre bontja. Ez az útmutató végigvezeti Önt a prezentáció betöltésén, a beágyazott OLE adatok elérésén és módosításán, valamint a frissített prezentáció mentésén. Ezekkel a lépésekkel hatékonyan kezelheti és programozottan frissítheti a PowerPoint-diák beágyazott tartalmát.
## GYIK
### Mi az az OLE-objektum a PowerPointban?
Az OLE (Object Linking and Embedding) objektumok lehetővé teszik más alkalmazásokból, például Excel-táblázatokból származó tartalom beágyazását PowerPoint diákba.
### Használhatom az Aspose.Slides-t más programozási nyelvekkel?
Igen, az Aspose.Slides számos nyelvet támogat, beleértve a .NET-et, a Python-t és a C-t++.
### Szükségem van az Aspose.Cells fájlra az OLE objektumok PowerPointban történő módosításához?
Igen, ha az OLE objektum egy Excel-táblázat, akkor az Aspose.Cells fájlra lesz szüksége a módosításához.
### Létezik az Aspose.Slides próbaverziója?
 Igen, kaphat a[ingyenes próbaverzió](https://releases.aspose.com/) hogy tesztelje az Aspose.Slides funkcióit.
### Hol találom az Aspose.Slides dokumentációját?
 A részletes dokumentációt megtalálja a[Az Aspose.Slides dokumentációs oldala](https://reference.aspose.com/slides/java/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
