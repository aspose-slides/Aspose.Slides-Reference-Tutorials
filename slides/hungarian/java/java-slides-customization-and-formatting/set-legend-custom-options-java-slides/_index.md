---
title: Állítsa be a Jelmagyarázat egyéni beállításait a Java Slides alkalmazásban
linktitle: Állítsa be a Jelmagyarázat egyéni beállításait a Java Slides alkalmazásban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be egyéni jelmagyarázat-beállításokat a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. Szabja testre a jelmagyarázat pozícióját és méretét a PowerPoint diagramokon.
weight: 14
url: /hu/java/customization-and-formatting/set-legend-custom-options-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Állítsa be a Jelmagyarázat egyéni beállításait a Java Slides alkalmazásban


## Bevezetés a Java Slides jelmagyarázat egyéni beállításainak megadásához

Ebben az oktatóanyagban bemutatjuk, hogyan lehet testreszabni egy diagram jelmagyarázat tulajdonságait egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. Módosíthatja a jelmagyarázat helyzetét, méretét és egyéb attribútumait a prezentációs igényeinek megfelelően.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Aspose.Slides for Java API telepítve.
- Java fejlesztői környezet beállítása.

## 1. lépés: Importálja a szükséges osztályokat:

```java
// Importálja az Aspose.Slides-t a Java osztályokhoz
import com.aspose.slides.*;
```

## 2. lépés: Adja meg a dokumentumkönyvtár elérési útját:

```java
String dataDir = "Your Document Directory";
```

##  3. lépés: Hozzon létre egy példányt a`Presentation` class:

```java
Presentation presentation = new Presentation();
```

## 4. lépés: Adjon hozzá egy diát a prezentációhoz:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## 5. lépés: Adjon hozzá egy fürtözött oszlopdiagramot a diához:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## 6. lépés: Állítsa be a jelmagyarázat tulajdonságait:

- Állítsa be a jelmagyarázat X-pozícióját (a diagram szélességéhez képest):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- Állítsa be a jelmagyarázat Y-pozícióját (a diagram magasságához képest):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- Állítsa be a jelmagyarázat szélességét (a diagram szélességéhez képest):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- Állítsa be a jelmagyarázat magasságát (a diagram magasságához képest):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## 7. lépés: Mentse el a prezentációt lemezre:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Ez az! Sikeresen testreszabta egy PowerPoint-prezentáció diagramjának jelmagyarázat tulajdonságait az Aspose.Slides for Java segítségével.

## Teljes forráskód a Java Slides jelmagyarázat egyéni beállításaihoz

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation presentation = new Presentation();
try
{
	// Szerezzen hivatkozást a diára
	ISlide slide = presentation.getSlides().get_Item(0);
	// Adjon hozzá egy fürtözött oszlopdiagramot a diához
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Állítsa be a Jelmagyarázat tulajdonságait
	chart.getLegend().setX(50 / chart.getWidth());
	chart.getLegend().setY(50 / chart.getHeight());
	chart.getLegend().setWidth(100 / chart.getWidth());
	chart.getLegend().setHeight(100 / chart.getHeight());
	// Prezentáció írása lemezre
	presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```
## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan lehet testreszabni egy diagram jelmagyarázat tulajdonságait egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. Módosíthatja a jelmagyarázat helyzetét, méretét és egyéb attribútumait, hogy tetszetős és informatív bemutatókat hozzon létre.

## GYIK

## Hogyan változtathatom meg a legenda pozícióját?

 A jelmagyarázat pozíciójának megváltoztatásához használja a`setX` és`setY` a legenda objektum módszerei. Az értékek a diagram szélességéhez és magasságához viszonyítva vannak megadva.

## Hogyan állíthatom be a legenda méretét?

 A jelmagyarázat méretét a gombbal állíthatja be`setWidth` és`setHeight` a legenda objektum módszerei. Ezek az értékek a diagram szélességéhez és magasságához is vonatkoznak.

## Testreszabhatok más jelmagyarázat attribútumokat?

Igen, testreszabhatja a jelmagyarázat különféle attribútumait, például a betűstílust, a keretet, a háttérszínt és egyebeket. Fedezze fel az Aspose.Slides dokumentációját a legendák testreszabásával kapcsolatos részletes információkért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
