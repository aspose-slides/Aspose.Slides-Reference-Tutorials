---
title: Formázza az összekapcsolási stílusokat a PowerPointban
linktitle: Formázza az összekapcsolási stílusokat a PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan javíthatja PowerPoint-prezentációit az Aspose.Slides for Java segítségével különböző vonalillesztési stílusok beállításával az alakzatokhoz. Kövesse lépésenkénti útmutatónkat.
weight: 15
url: /hu/java/java-powerpoint-shape-formatting-geometry/format-join-styles-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Formázza az összekapcsolási stílusokat a PowerPointban

## Bevezetés
látványos PowerPoint-prezentációk készítése ijesztő feladat lehet, különösen akkor, ha azt szeretné, hogy minden részlet tökéletes legyen. Itt jön jól az Aspose.Slides for Java. Ez egy hatékony API, amely lehetővé teszi prezentációk programozott létrehozását, kezelését és kezelését. Az egyik használható funkció a különböző vonalillesztési stílusok beállítása az alakzatokhoz, ami jelentősen javíthatja a diák esztétikáját. Ebben az oktatóanyagban azt mutatjuk be, hogyan használhatja az Aspose.Slides for Java-t az alakzatok összekapcsolási stílusainak beállítására a PowerPoint-prezentációkban. 
## Előfeltételek
Mielőtt elkezdené, meg kell felelnie néhány előfeltételnek:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a gépen. Letöltheti innen[Az Oracle webhelye](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java Library: Le kell töltenie az Aspose.Slides for Java programot, és bele kell foglalnia a projektbe. től lehet kapni[itt](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Használjon olyan IDE-t, mint az IntelliJ IDEA, az Eclipse vagy a NetBeans a Java kód írásához és végrehajtásához.
4. Alapvető Java ismerete: A Java programozás alapvető ismerete segít az oktatóanyag követésében.
## Csomagok importálása
Először is importálnia kell az Aspose.Slides-hez szükséges csomagokat. Ez elengedhetetlen ahhoz, hogy elérjük a prezentációs manipulációinkhoz szükséges osztályokat és metódusokat.
```java
import com.aspose.slides.*;

import java.awt.*;
import java.io.File;
```
## 1. lépés: A projektkönyvtár beállítása
Kezdjük azzal, hogy hozzunk létre egy könyvtárat a bemutató fájljaink tárolására. Ez biztosítja, hogy minden fájlunk rendezett és könnyen hozzáférhető.
```java
String dataDir = "Your Document Directory";
// Hozzon létre könyvtárat, ha még nincs jelen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
    new File(dataDir).mkdirs();
```
Ebben a lépésben meghatározunk egy könyvtár elérési utat, és ellenőrizzük, hogy létezik-e. Ha nem, akkor létrehozzuk a könyvtárat. Ez egy egyszerű, de hatékony módszer a fájlok rendszerezésére.
## 2. lépés: Inicializálja a prezentációt
 Ezután példányosítjuk a`Presentation` osztály, amely a PowerPoint fájlunkat képviseli. Ez az az alap, amelyre diáinkat és formáinkat építjük.
```java
Presentation pres = new Presentation();
```
Ez a kódsor új bemutatót hoz létre. Képzelje el úgy, mint egy üres PowerPoint-fájl megnyitását, amelybe hozzáadja az összes tartalmat.
## 3. lépés: Adjon hozzá alakzatokat a diához
### Szerezd meg az első diát
Mielőtt formákat adnánk hozzá, referenciát kell kapnunk bemutatónk első diájára. Alapértelmezés szerint egy új bemutató egy üres diát tartalmaz.
```java
ISlide sld = pres.getSlides().get_Item(0);
```
### Téglalap alakzatok hozzáadása
Most adjunk hozzá három téglalap alakú formát a diánkhoz. Ezek az alakzatok bemutatják a különböző vonalillesztési stílusokat.
```java
IShape shp1 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 100, 150, 75);
IShape shp2 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 300, 100, 150, 75);
IShape shp3 = sld.getShapes().addAutoShape(ShapeType.Rectangle, 50, 250, 150, 75);
```
Ebben a lépésben három téglalapot adunk hozzá a dia meghatározott helyeire. Az egyes téglalapok stílusa később eltérő lesz, hogy bemutassa a különböző összekapcsolási stílusokat.
## 4. lépés: alakítsa ki az alakzatokat
### Állítsa be a kitöltés színét
Azt akarjuk, hogy a téglalapjaink egyszínűek legyenek. Itt a feketét választjuk kitöltési színként.
```java
shp1.getFillFormat().setFillType(FillType.Solid);
shp1.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp2.getFillFormat().setFillType(FillType.Solid);
shp2.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
shp3.getFillFormat().setFillType(FillType.Solid);
shp3.getFillFormat().getSolidFillColor().setColor(Color.BLACK);
```
### Állítsa be a vonal szélességét és színét
Ezután minden téglalaphoz meghatározzuk a vonal szélességét és színét. Ez segít a csatlakozási stílusok vizuális megkülönböztetésében.
```java
shp1.getLineFormat().setWidth(15);
shp2.getLineFormat().setWidth(15);
shp3.getLineFormat().setWidth(15);
shp1.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp1.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp2.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp2.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
shp3.getLineFormat().getFillFormat().setFillType(FillType.Solid);
shp3.getLineFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
```
## 5. lépés: Alkalmazza a csatlakozási stílusokat
Ennek az oktatóanyagnak a csúcspontja a vonalillesztési stílusok beállítása. Három különböző stílust fogunk használni: gérvágó, ferde és kerek.
```java
shp1.getLineFormat().setJoinStyle(LineJoinStyle.Miter);
shp2.getLineFormat().setJoinStyle(LineJoinStyle.Bevel);
shp3.getLineFormat().setJoinStyle(LineJoinStyle.Round);
```
Minden vonalillesztési stílus egyedi megjelenést kölcsönöz az alakzatoknak a vonalak találkozási sarkainál. Ez különösen hasznos lehet vizuálisan megkülönböztethető diagramok vagy illusztrációk létrehozásához.
## 6. lépés: Szöveg hozzáadása az alakzatokhoz
Annak érdekében, hogy egyértelművé tegyük az egyes alakzatok jelentését, minden téglalaphoz szöveget adunk, amely leírja a használt összekapcsolási stílust.
```java
((IAutoShape) shp1).getTextFrame().setText("This is Miter Join Style");
((IAutoShape) shp2).getTextFrame().setText("This is Bevel Join Style");
((IAutoShape) shp3).getTextFrame().setText("This is Round Join Style");
```
A szöveg hozzáadása segít a különböző stílusok azonosításában, amikor bemutatja vagy megosztja a diát.
## 7. lépés: Mentse el a bemutatót
Végül elmentjük a prezentációnkat a megadott könyvtárba.
```java
pres.save(dataDir + "RectShpLnJoin_out.pptx", SaveFormat.Pptx);
```
Ez a parancs egy PPTX fájlba írja a prezentációt, amelyet megnyithat a Microsoft PowerPoint vagy bármely más kompatibilis szoftverrel.
## Következtetés
És megvan! Most hozott létre egy PowerPoint diát három téglalappal, amelyek mindegyike más-más vonalillesztési stílust mutat be az Aspose.Slides for Java segítségével. Ez az oktatóanyag nemcsak az Aspose.Slides alapjainak megértésében segít, hanem azt is bemutatja, hogyan javíthatja bemutatóit egyedi stílusokkal. Boldog bemutatást!
## GYIK
### Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy hatékony API PowerPoint-prezentációk programozott létrehozásához, kezeléséhez és kezeléséhez.
### Használhatom az Aspose.Slides for Java programot bármely IDE-ben?
Igen, az Aspose.Slides for Java bármely Java által támogatott IDE-ben, például az IntelliJ IDEA-ban, az Eclipse-ben vagy a NetBeans-ben használható.
### Létezik ingyenes próbaverzió az Aspose.Slides for Java számára?
 Igen, ingyenes próbaverziót kaphat a webhelyen[itt](https://releases.aspose.com/).
### Mik azok a vonalillesztési stílusok a PowerPointban?
A vonalillesztési stílusok a sarkok alakjára utalnak, ahol két vonal találkozik. A gyakori stílusok közé tartozik a gérvágó, a ferde és a kerek.
### Hol találok további dokumentációt az Aspose.Slides for Java-ról?
 Részletes dokumentációt találhat[itt](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
