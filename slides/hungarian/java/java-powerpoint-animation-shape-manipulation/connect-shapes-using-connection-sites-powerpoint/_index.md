---
"description": "Tanuld meg, hogyan kapcsolhatsz össze alakzatokat PowerPointban az Aspose.Slides for Java segítségével. Automatizáld prezentációidat könnyedén."
"linktitle": "Alakzatok összekapcsolása a PowerPointban található kapcsolati webhelyek használatával"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Alakzatok összekapcsolása a PowerPointban található kapcsolati webhelyek használatával"
"url": "/hu/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connection-sites-powerpoint/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Alakzatok összekapcsolása a PowerPointban található kapcsolati webhelyek használatával

## Bevezetés
Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan lehet alakzatokat összekapcsolni PowerPointban a csatlakozási oldalak segítségével az Aspose.Slides for Java használatával. Ez a hatékony könyvtár lehetővé teszi számunkra, hogy programozottan manipuláljuk a PowerPoint-bemutatókat, így az olyan feladatok, mint az alakzatok összekapcsolása, zökkenőmentesen és hatékonyan végezhetők el.
## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg arról, hogy a következőkkel rendelkezünk:
1. Java fejlesztőkészlet (JDK): Győződjön meg arról, hogy a Java telepítve van a rendszerén. Letöltheti és telepítheti innen: [weboldal](https://www.oracle.com/java/technologies/javase-jdk15-downloads.html).
2. Aspose.Slides Java-hoz: Töltse le és telepítse az Aspose.Slides Java-hoz programot a következő helyről: [letöltési oldal](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Válasszon egy IDE-t Java fejlesztéshez, például IntelliJ IDEA, Eclipse vagy NetBeans.

## Csomagok importálása
Első lépésként importáld a szükséges csomagokat a Java projektedbe:
```java
import com.aspose.slides.*;

```
## 1. lépés: Alakzatgyűjtemény elérése
A kijelölt dia alakzatgyűjteményének elérése:
```java
// A dokumentumok könyvtárának elérési útja.                    
String dataDir = "Your Document Directory";
// Példányosítsa a PPTX fájlt reprezentáló megjelenítési osztályt
Presentation presentation = new Presentation();
IShapeCollection shapes = presentation.getSlides().get_Item(0).getShapes();
```
## 2. lépés: Összekötő alakjának hozzáadása
Összekötő alakzat hozzáadása a dia alakzatgyűjteményhez:
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector3, 0, 0, 10, 10);
```
## 3. lépés: Automatikus alakzatok hozzáadása
Automatikus alakzatok, például ellipszis és téglalap hozzáadása:
```java
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 200, 100, 100);
```
## 4. lépés: Alakzatok összekapcsolása összekötőkkel
Csatlakoztassa az alakzatokat az összekötőhöz:
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## 5. lépés: Csatlakozási webhely indexének beállítása
Állítsa be az alakzatok kívánt csatlakozási helyindexét:
```java
long wantedIndex = 6;
if (ellipse.getConnectionSiteCount() > (wantedIndex & 0xFFFFFFFFL))
{
    connector.setStartShapeConnectionSiteIndex(wantedIndex);
}
```

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kapcsolhatunk össze alakzatokat PowerPointban a csatlakozási oldalak segítségével az Aspose.Slides for Java segítségével. Ezzel a tudással most könnyedén automatizálhatja és testreszabhatja PowerPoint-bemutatóit.
## GYIK
### Használható az Aspose.Slides Java-ban más PowerPoint-manipulációs feladatokhoz?
Igen, az Aspose.Slides for Java széleskörű funkciókat kínál PowerPoint prezentációk létrehozásához, szerkesztéséhez és konvertálásához.
### Ingyenesen használható az Aspose.Slides Java-hoz?
Az Aspose.Slides for Java egy kereskedelmi célú könyvtár, de ingyenes próbaverzióval felfedezheti a funkcióit. Látogasson el ide: [itt](https://releases.aspose.com/) hogy elkezdhessük.
### Kaphatok támogatást, ha bármilyen problémába ütközöm az Aspose.Slides Java-alapú használata során?
Igen, kaphatsz támogatást az Aspose közösségi fórumain. [itt](https://forum.aspose.com/c/slides/11).
### Vannak ideiglenes licencek az Aspose.Slides for Java-hoz?
Igen, ideiglenes licencek állnak rendelkezésre tesztelési és értékelési célokra. Szerezhet egyet. [itt](https://purchase.aspose.com/temporary-license/).
### Hol vásárolhatok Aspose.Slides licencet Java-hoz?
Licenc vásárlása az Aspose weboldalán lehetséges. [itt](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}