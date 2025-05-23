---
"description": "Tanuld meg, hogyan köthetsz össze alakzatokat összekötőkkel PowerPoint-bemutatókban az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató kezdőknek."
"linktitle": "Alakzatok összekapcsolása összekötőkkel a PowerPointban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Alakzatok összekapcsolása összekötőkkel a PowerPointban"
"url": "/hu/java/java-powerpoint-animation-shape-manipulation/connect-shapes-using-connectors-powerpoint/"
"weight": 18
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Alakzatok összekapcsolása összekötőkkel a PowerPointban

## Bevezetés
Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan lehet alakzatokat összekötők segítségével összekapcsolni PowerPoint-bemutatókban az Aspose.Slides for Java segítségével. Kövesd ezeket a lépésről lépésre szóló utasításokat az alakzatok hatékony összekapcsolásához és vizuálisan vonzó diák létrehozásához.
## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg arról, hogy a következő előfeltételekkel rendelkezünk:
- Java programozási nyelv alapismerete.
- Telepítette a Java Development Kitet (JDK) a rendszerére.
- Letöltötted és beállítottad az Aspose.Slides for Java programot. Ha még nem telepítetted, letöltheted innen: [itt](https://releases.aspose.com/slides/java/).
- Egy kódszerkesztő, például az Eclipse vagy az IntelliJ IDEA.

## Csomagok importálása
Először importáld a szükséges csomagokat az Aspose.Slides használatához a Java projektedben.
```java
import com.aspose.slides.*;

```
## 1. lépés: Prezentációs osztály példányosítása
Példányosítsa a `Presentation` osztály, amely a PPTX fájlt jelöli, amelyen dolgozol.
```java
// A dokumentumok könyvtárának elérési útja.                    
String dataDir = "Your Document Directory";
Presentation input = new Presentation();
```
## 2. lépés: Hozzáférés az alakzatok gyűjteményéhez
Nyissa meg a kijelölt dia alakzatgyűjteményét, amelyhez alakzatokat és összekötőket szeretne hozzáadni.
```java
IShapeCollection shapes = input.getSlides().get_Item(0).getShapes();
```
## 3. lépés: Alakzatok hozzáadása
Adja hozzá a szükséges alakzatokat a diához. Ebben a példában egy ellipszist és egy téglalapot fogunk hozzáadni.
```java
// Automatikus alakzat hozzáadása Ellipszis
IAutoShape ellipse = shapes.addAutoShape(ShapeType.Ellipse, 0, 100, 100, 100);
// Automatikus alakzat hozzáadása Téglalap
IAutoShape rectangle = shapes.addAutoShape(ShapeType.Rectangle, 100, 300, 100, 100);
```
## 4. lépés: Összekötő hozzáadása
Adjon hozzá egy összekötő alakzatot a dia alakzatgyűjteményhez.
```java
IConnector connector = shapes.addConnector(ShapeType.BentConnector2, 0, 0, 10, 10);
```
## 5. lépés: Alakzatok összekapcsolása összekötőkkel
Csatlakoztassa az alakzatokat az összekötőhöz.
```java
connector.setStartShapeConnectedTo(ellipse);
connector.setEndShapeConnectedTo(rectangle);
```
## 6. lépés: Csatlakozó átirányítása
Hívja meg az átirányítás függvényt az alakzatok közötti automatikus legrövidebb útvonal beállításához.
```java
connector.reroute();
```
## 7. lépés: Prezentáció mentése
Mentse a bemutatót az alakzatok összekötőkkel való összekapcsolása után.
```java
input.save(dataDir + "Connecting shapes using connectors_out.pptx", SaveFormat.Pptx);
```
Végül ne felejtsük el megszabadulni a Presentation objektumtól.
```java
if (input != null) input.dispose();
```
Most sikeresen összekapcsolta az alakzatokat összekötőkkel a PowerPointban az Aspose.Slides for Java használatával.

## Következtetés
Ebben az oktatóanyagban megtanultuk, hogyan kapcsolhatunk össze alakzatokat összekötőkkel PowerPoint-bemutatókban az Aspose.Slides for Java segítségével. Ezeket az egyszerű lépéseket követve vizuálisan vonzó diagramokkal és folyamatábrákkal gazdagíthatod a bemutatóidat.
## GYIK
### Testreszabhatom a csatlakozók megjelenését az Aspose.Slides for Java programban?
Igen, testreszabhatja az összekötők különböző tulajdonságait, például a színt, a vonalstílust és a vastagságot a prezentációs igényeinek megfelelően.
### Az Aspose.Slides for Java kompatibilis a PowerPoint összes verziójával?
Az Aspose.Slides Java-hoz készült változata számos PowerPoint formátumot támogat, beleértve a PPTX, PPT és ODP formátumokat.
### Összekapcsolhatok kettőnél több alakzatot egyetlen összekötővel?
Igen, több alakzatot is összekapcsolhatsz az Aspose.Slides for Java által biztosított összetett összekötőkkel.
### Az Aspose.Slides Java-ban támogatja a szöveg alakzatokhoz való hozzáadását?
Természetesen könnyedén hozzáadhatsz szöveget alakzatokhoz és összekötőkhöz programozottan az Aspose.Slides for Java használatával.
### Van közösségi fórum vagy támogatási csatorna az Aspose.Slides számára Java felhasználók számára?
Igen, hasznos forrásokat találhatsz, kérdéseket tehetsz fel és kapcsolatba léphetsz más felhasználókkal az Aspose.Slides fórumon. [itt](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}