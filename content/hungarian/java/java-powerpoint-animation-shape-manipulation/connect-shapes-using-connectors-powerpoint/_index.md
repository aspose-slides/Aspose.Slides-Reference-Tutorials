---
title: Csatlakoztassa az alakzatokat a PowerPoint csatlakozóival
linktitle: Csatlakoztassa az alakzatokat a PowerPoint csatlakozóival
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan kapcsolhat össze alakzatokat csatlakozókkal a PowerPoint-prezentációkban az Aspose.Slides for Java segítségével. Lépésről lépésre bemutató kezdőknek.
type: docs
weight: 18
url: /hu/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/
---
## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan kapcsolhatunk össze alakzatokat csatlakozókkal a PowerPoint-prezentációkban az Aspose.Slides for Java segítségével. Kövesse ezeket a lépésenkénti utasításokat az alakzatok hatékony összekapcsolásához és látványos diák létrehozásához.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következő előfeltételekkel:
- Java programozási nyelv alapismerete.
- Java Development Kit (JDK) telepítve a rendszerére.
-  Letöltötte és beállította az Aspose.Slides for Java-t. Ha még nem telepítette, letöltheti innen[itt](https://releases.aspose.com/slides/java/).
- Kódszerkesztő, például Eclipse vagy IntelliJ IDEA.

## Csomagok importálása
Először is importálja a szükséges csomagokat az Aspose.Slides használatához a Java projektben.
```java
import com.aspose.slides.*;

```
## 1. lépés: Példányos bemutató osztály
 Példányosítsa a`Presentation`osztály, amely azt a PPTX fájlt jelöli, amelyen éppen dolgozik.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## 2. lépés: Hozzáférés az alakzatgyűjteményhez
Hozzáférés a kiválasztott diához tartozó alakzatgyűjteményhez, amelyhez alakzatokat és csatlakozókat szeretne hozzáadni.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## 3. lépés: Adjon hozzá alakzatokat
Adja hozzá a kívánt formákat a diához. Ebben a példában egy ellipszist és egy téglalapot adunk hozzá.
```java
// Adjon hozzá automatikus ellipszis alakzatot
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Automatikus téglalap hozzáadása
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. lépés: Csatlakozó hozzáadása
Adjon hozzá csatlakozó alakzatot a diaformagyűjteményhez.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. lépés: Csatlakoztassa az alakzatokat a csatlakozókhoz
Csatlakoztassa az alakzatokat a csatlakozóhoz.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## 6. lépés: A csatlakozó átirányítása
Hívja a reroute-t az alakzatok közötti automatikus legrövidebb út beállításához.
```java
connector.reroute();
```
## 7. lépés: Mentse a bemutatót
Mentse el a bemutatót, miután az alakzatokat összekötőkkel csatlakoztatta.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Végül ne felejtse el kidobni a Prezentáció objektumot.
```java
if (input != null) input.dispose();
```
Sikeresen összekapcsolta az alakzatokat a PowerPoint csatlakozóival az Aspose.Slides for Java segítségével.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kapcsolhatunk össze alakzatokat csatlakozókkal a PowerPoint-prezentációkban az Aspose.Slides for Java programmal. Ezen egyszerű lépések követésével tetszetős diagramokkal és folyamatábrákkal bővítheti prezentációit.
## GYIK
### Testreszabhatom az Aspose.Slides for Java csatlakozóinak megjelenését?
Igen, testreszabhatja a csatlakozók különféle tulajdonságait, például színét, vonalstílusát és vastagságát a prezentációs igényeinek megfelelően.
### Az Aspose.Slides for Java kompatibilis a PowerPoint összes verziójával?
Az Aspose.Slides for Java különféle PowerPoint formátumokat támogat, beleértve a PPTX, PPT és ODP-t.
### Összeköthetek kettőnél több alakzatot egyetlen csatlakozóval?
Igen, több alakzatot is csatlakoztathat az Aspose.Slides for Java által biztosított összetett csatlakozókkal.
### Az Aspose.Slides for Java támogatja a szöveg alakzatokhoz való hozzáadását?
Az Aspose.Slides for Java segítségével természetesen egyszerűen hozzáadhat szöveget az alakzatokhoz és a csatlakozókhoz programozottan.
### Elérhető közösségi fórum vagy támogatási csatorna az Aspose.Slides for Java felhasználók számára?
 Igen, az Aspose.Slides fórumon hasznos forrásokat találhat, kérdéseket tehet fel, és kapcsolatba léphet más felhasználókkal[itt](https://forum.aspose.com/c/slides/11).