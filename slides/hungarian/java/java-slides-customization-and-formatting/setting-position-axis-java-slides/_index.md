---
title: Pozíciótengely beállítása a Java Slides-ben
linktitle: Pozíciótengely beállítása a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Javítsa ki diagramjait az Aspose.Slides for Java segítségével. Tanulja meg, hogyan állíthatja be a pozíciótengelyt Java diákon, hogyan készíthet lenyűgöző prezentációkat, és hogyan testreszabhatja könnyedén a diagramelrendezéseket.
type: docs
weight: 16
url: /hu/java/customization-and-formatting/setting-position-axis-java-slides/
---

## Bevezetés a pozíciótengely beállításába az Aspose.Slides for Java programban

Ebben az oktatóanyagban megtanuljuk, hogyan állíthatja be a pozíciótengelyt egy diagramon az Aspose.Slides for Java segítségével. A tengely elhelyezése hasznos lehet, ha testre szeretné szabni a diagram megjelenését és elrendezését. Létrehozunk egy fürtözött oszlopdiagramot, és beállítjuk a vízszintes tengely helyzetét a kategóriák között.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a Java projektben. A könyvtárat innen töltheti le[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Prezentáció létrehozása

Először is hozzunk létre egy új bemutatót, amellyel dolgozni:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

 Mindenképpen cserélje ki`"Your Document Directory"` a dokumentumkönyvtár tényleges elérési útjával.

## 2. lépés: Diagram hozzáadása

Ezután hozzáadunk egy fürtözött oszlopdiagramot a diához. Megadjuk a diagram típusát, pozícióját (x, y koordináták) és méreteit (szélesség és magasság):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
```

Itt hozzáadtunk egy fürtözött oszlopdiagramot az (50., 50.) pozícióhoz, amelynek szélessége 450 és magassága 300. Ezeket az értékeket szükség szerint módosíthatja.

## 3. lépés: A pozíciótengely beállítása

kategóriák közötti pozíciótengely beállításához a következő kódot használhatja:

```java
chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
```

Ez a kód beállítja a vízszintes tengelyt a kategóriák közötti megjelenítésre, ami bizonyos diagramelrendezéseknél hasznos lehet.

## 4. lépés: A prezentáció mentése

Végül mentsük el a prezentációt a diagrammal:

```java
pres.save(dataDir + "AsposeClusteredColumnChart.pptx", SaveFormat.Pptx);
```

 Cserélje ki`"AsposeClusteredColumnChart.pptx"` a kívánt fájlnévvel.

Ez az! Sikeresen létrehozott egy fürtözött oszlopdiagramot, és beállította a pozíciótengelyt a kategóriák között az Aspose.Slides for Java segítségével.

## Teljes forráskód
```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 450, 300);
	chart.getAxes().getHorizontalAxis().setAxisBetweenCategories(true);
	pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megvizsgáltuk, hogyan állíthatjuk be a pozíciótengelyt egy diagramon az Aspose.Slides for Java segítségével. Az ebben az útmutatóban vázolt lépések követésével megtanulta, hogyan hozhat létre fürtözött oszlopdiagramot, és hogyan szabhatja testre megjelenését a vízszintes tengely kategóriák közötti elhelyezésével. Az Aspose.Slides for Java hatékony szolgáltatásokat nyújt a diagramokkal és prezentációkkal való munkavégzéshez, így értékes eszköz a Java-fejlesztők számára.

## GYIK

### Hogyan szabhatom tovább a diagramot?

Testreszabhatja a diagram különböző aspektusait, beleértve az adatsorokat, a diagram címét, a jelmagyarázatokat és egyebeket. Utal[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/) részletes utasításokért és példákért.

### Meg tudom változtatni a diagram típusát?

 Igen, módosíthatja a diagram típusát a`ChartType` paramétert a diagram hozzáadásakor. Az Aspose.Slides for Java különféle diagramtípusokat támogat, például oszlopdiagramokat, vonaldiagramokat és egyebeket.

### Hol találok további példákat és dokumentációt?

 Átfogó dokumentációt és további példákat találhat a webhelyen[Aspose.Slides for Java dokumentáció](https://reference.aspose.com/slides/java/) oldalon.

Ne felejtse el dobni a prezentációs objektumot, ha végzett vele a rendszererőforrások felszabadításához:

```java
if (pres != null) pres.dispose();
```

Ennyi az oktatóanyag. Megtanulta, hogyan állíthatja be a pozíciótengelyt egy diagramon az Aspose.Slides for Java segítségével.