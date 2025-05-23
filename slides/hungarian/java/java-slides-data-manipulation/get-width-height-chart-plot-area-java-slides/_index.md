---
"description": "Tanuld meg, hogyan kérheted le a diagramterület méreteit Java Slidesben az Aspose.Slides for Java használatával. Fejleszd PowerPoint automatizálási készségeidet."
"linktitle": "Szélesség és magasság lekérése a diagramterületről Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Szélesség és magasság lekérése a diagramterületről Java diákban"
"url": "/hu/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Szélesség és magasság lekérése a diagramterületről Java diákban


## Bevezetés

diagramok hatékony eszközt jelentenek az adatok PowerPoint-bemutatókban történő vizualizációjához. Előfordulhat, hogy különféle okokból, például a diagram elemeinek átméretezéséhez vagy áthelyezéséhez szüksége lehet a diagram nyomtatási területének méreteire. Ez az útmutató bemutatja, hogyan lehet a nyomtatási terület szélességét és magasságát Java és az Aspose.Slides for Java használatával meghatározni.

## Előfeltételek

Mielőtt belemerülnénk a kódba, győződjünk meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és beállítva van a Java projektünkben. A könyvtárat letölthetjük az Aspose weboldaláról. [itt](https://releases.aspose.com/slides/java/).

## 1. lépés: A környezet beállítása

Győződjön meg róla, hogy az Aspose.Slides for Java könyvtár hozzá van adva a Java projekthez. Ezt megteheti úgy, hogy a könyvtárat a projekt függőségei közé veszi fel, vagy manuálisan hozzáadja a JAR fájlt.

## 2. lépés: PowerPoint-bemutató létrehozása

Kezdjük egy PowerPoint bemutató létrehozásával és egy diával. Ez fog szolgálni a diagramunk tárolójaként.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Csere `"Your Document Directory"` dokumentumkönyvtár elérési útjával.

## 3. lépés: Diagram hozzáadása

Most adjunk hozzá egy csoportos oszlopdiagramot a diához. Ezenkívül ellenőrizzük a diagram elrendezését.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Ez a kód egy fürtözött oszlopdiagramot hoz létre a (100, 100) pozícióban, (500, 350) dimenziókkal.

## 4. lépés: A telekterület méreteinek lekérdezése

A diagram nyomtatási területének szélességének és magasságának lekéréséhez a következő kódot használhatjuk:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Most a változók `x`, `y`, `w`, és `h` tartalmazza a nyomtatási terület X koordinátájának, Y koordinátájának, szélességének és magasságának megfelelő értékeit.

## 5. lépés: A prezentáció mentése

Végül mentse el a prezentációt a diagrammal együtt.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Mindenképpen cserélje ki `"Chart_out.pptx"` a kívánt kimeneti fájlnévvel.

## Teljes forráskód a szélesség és magasság lekéréséhez a diagramterületről Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Prezentáció mentése diagrammal
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben a cikkben azt tárgyaltuk, hogyan lehet lekérdezni egy diagram nyomtatási területének szélességét és magasságát Java Slides-ban az Aspose.Slides for Java API használatával. Ez az információ értékes lehet, ha dinamikusan kell módosítani a diagramok elrendezését a PowerPoint-bemutatókon belül.

## GYIK

### Hogyan módosíthatom a diagram típusát a fürtözött oszlopoktól eltérőre?

A diagram típusát a következő cseréjével módosíthatja: `ChartType.ClusteredColumn` a kívánt diagramtípus-felsorolással, például `ChartType.Line` vagy `ChartType.Pie`.

### Módosíthatom a diagram más tulajdonságait?

Igen, a diagram különböző tulajdonságait, például az adatokat, a címkéket és a formázást módosíthatja az Aspose.Slides for Java API használatával. További részletekért lásd a dokumentációt.

### Alkalmas az Aspose.Slides Java-hoz professzionális PowerPoint automatizáláshoz?

Igen, az Aspose.Slides for Java egy hatékony könyvtár PowerPoint-feladatok automatizálására Java-alkalmazásokban. Átfogó funkciókat biztosít prezentációkkal, diákkal, alakzatokkal, diagramokkal és egyebekkel való munkához.

### Hogyan tudhatok meg többet az Aspose.Slides Java-hoz készült verziójáról?

Bőséges dokumentációt és példákat találsz az Aspose.Slides for Java dokumentációs oldalán. [itt](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}