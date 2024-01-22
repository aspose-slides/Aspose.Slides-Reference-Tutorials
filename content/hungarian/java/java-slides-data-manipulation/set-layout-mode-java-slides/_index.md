---
title: Állítsa be az elrendezési módot a Java Slides alkalmazásban
linktitle: Állítsa be az elrendezési módot a Java Slides alkalmazásban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be Java diák elrendezési módokat az Aspose.Slides segítségével. Szabja testre a diagram pozícionálását és méretezését ebben a forráskóddal ellátott, lépésenkénti útmutatóban.
type: docs
weight: 23
url: /hu/java/data-manipulation/set-layout-mode-java-slides/
---

## Bevezetés az elrendezési mód beállításába a Java Slides programban

Ebben az oktatóanyagban megtudjuk, hogyan állíthatja be a diagram elrendezési módját Java diákon az Aspose.Slides for Java segítségével. Az elrendezési mód határozza meg a diagram elhelyezését és méretét a dián belül.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár telepítve van és be van állítva a Java projektben. A könyvtárat innen töltheti le[itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Hozzon létre egy prezentációt

Először is létre kell hoznunk egy új prezentációt.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 2. lépés: Adjon hozzá egy dia és egy diagramot

Ezután egy diát és egy diagramot adunk hozzá. Ebben a példában fürtözött oszlopdiagramot fogunk létrehozni.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## 3. lépés: Állítsa be a diagram elrendezését

 Most állítsuk be a diagram elrendezését. A dián belüli diagram helyzetét és méretét a gombbal állítjuk be`setX`, `setY`, `setWidth`, `setHeight` mód. Ezenkívül beállítjuk a`LayoutTargetType` az elrendezési mód meghatározásához.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Ebben a példában úgy állítottuk be a diagramot, hogy az elrendezési céltípus "Belső" legyen, ami azt jelenti, hogy a dia belső területéhez képest lesz elhelyezve és méretezve.

## 4. lépés: Mentse el a prezentációt

Végül mentsük el a bemutatót a diagram elrendezési beállításaival.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Teljes forráskód az elrendezési mód beállításához a Java Slides-ben

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

 Ebben az oktatóanyagban megtanultuk, hogyan állíthatjuk be a diagram elrendezési módját Java diákon az Aspose.Slides for Java segítségével. Testreszabhatja a diagram helyzetét és méretét saját igényei szerint, ha módosítja az értékeket a`setX`, `setY`, `setWidth`, `setHeight` , és`setLayoutTargetType`mód. Ezzel szabályozhatja a diagramok elhelyezését a diákon belül.

## GYIK

### Hogyan módosíthatom a diagram elrendezési módját az Aspose.Slides for Java alkalmazásban?

 A diagram elrendezési módjának megváltoztatásához az Aspose.Slides for Java programban használhatja a`setLayoutTargetType` metódus a diagram ábrázolási területén. Bármelyikre beállíthatja`LayoutTargetType.Inner` vagy`LayoutTargetType.Outer` a kívánt elrendezéstől függően.

### Testreszabhatom a diagram helyzetét és méretét a dián belül?

 Igen, testreszabhatja a diagram helyzetét és méretét a dián belül a gombbal`setX`, `setY`, `setWidth` , és`setHeight` módszereket a diagram plot területén. Állítsa be ezeket az értékeket a diagram elhelyezéséhez és méretéhez az igényeinek megfelelően.

### Hol találhatok további információt az Aspose.Slides for Java programról?

 További információt az Aspose.Slides for Java programról itt találhat[dokumentáció](https://reference.aspose.com/slides/java/). Részletes API-referenciákat és példákat tartalmaz, amelyek segítségével hatékonyan dolgozhat a diákkal és diagramokkal Java nyelven.