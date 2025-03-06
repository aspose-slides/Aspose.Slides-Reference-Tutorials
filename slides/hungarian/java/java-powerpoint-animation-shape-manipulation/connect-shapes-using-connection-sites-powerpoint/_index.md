---
title: Kapcsolja össze az alakzatokat a PowerPoint kapcsolati webhelyeivel
linktitle: Kapcsolja össze az alakzatokat a PowerPoint kapcsolati webhelyeivel
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan kapcsolhat össze alakzatokat a PowerPointban az Aspose.Slides for Java segítségével. Automatizálja prezentációit könnyedén.
weight: 19
url: /hu/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

## Bevezetés
Ebben az oktatóanyagban megvizsgáljuk, hogyan kapcsolhat össze alakzatokat a PowerPoint kapcsolati webhelyeivel az Aspose.Slides for Java használatával. Ez a nagy teljesítményű könyvtár lehetővé teszi a PowerPoint-prezentációk programozott kezelését, zökkenőmentessé és hatékonysá téve az olyan feladatokat, mint az alakzatok összekapcsolása.
## Előfeltételek
Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik az alábbiakkal:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a Java telepítve van a rendszeren. Letöltheti és telepítheti a[weboldal](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2.  Aspose.Slides for Java: Töltse le és telepítse az Aspose.Slides for Java alkalmazást a[letöltési oldal](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Válasszon egy IDE-t Java fejlesztéshez, például IntelliJ IDEA, Eclipse vagy NetBeans.

## Csomagok importálása
A kezdéshez importálja a szükséges csomagokat a Java projektbe:
```java
import com.aspose.slides.*;

```
## 1. lépés: A Shapes Collection elérése
Hozzáférés a kiválasztott diához tartozó alakzatgyűjteményhez:
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Példányosítási osztály, amely a PPTX fájlt képviseli
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## 2. lépés: Csatlakozó alakjának hozzáadása
Csatlakozó alakzat hozzáadása a diaformagyűjteményhez:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## 3. lépés: AutoShapes hozzáadása
Automatikus alakzatok, például ellipszis és téglalap hozzáadása:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## 4. lépés: Az alakzatok összekapcsolása a csatlakozókkal
Csatlakoztassa az alakzatokat a csatlakozóhoz:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## 5. lépés: A csatlakozási webhely indexének beállítása
Állítsa be az alakzatokhoz a kívánt csatlakozási hely indexet:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kapcsolhatunk össze alakzatokat a PowerPoint kapcsolati webhelyeivel az Aspose.Slides for Java használatával. Ezzel a tudással most már könnyedén automatizálhatja és testreszabhatja PowerPoint-prezentációit.
## GYIK
### Használható az Aspose.Slides for Java más PowerPoint-kezelési feladatokhoz?
Igen, az Aspose.Slides for Java funkciók széles skáláját kínálja PowerPoint-prezentációk létrehozásához, szerkesztéséhez és konvertálásához.
### Ingyenesen használható az Aspose.Slides for Java?
 Az Aspose.Slides for Java egy kereskedelmi célú könyvtár, de szolgáltatásait ingyenes próbaverzióval fedezheti fel. Látogatás[itt](https://releases.aspose.com/) kezdeni.
### Kaphatok támogatást, ha bármilyen problémát tapasztalok az Aspose.Slides for Java használata során?
 Igen, támogatást kaphat az Aspose közösségi fórumokon[itt](https://forum.aspose.com/c/slides/11).
### Rendelkezésre állnak ideiglenes licencek az Aspose.Slides for Java számára?
 Igen, tesztelési és értékelési célokra rendelkezésre állnak ideiglenes licencek. Beszerezhetsz egyet[itt](https://purchase.aspose.com/temporary-license/).
### Hol vásárolhatok licencet az Aspose.Slides for Java-hoz?
Licenceket vásárolhat az Aspose webhelyéről[itt](https://purchase.aspose.com/buy).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
