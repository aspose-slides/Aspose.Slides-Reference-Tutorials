---
"description": "Tanuld meg, hogyan állíthatsz be egyéni jelmagyarázat-beállításokat Java Slides-ben az Aspose.Slides for Java használatával. Testreszabhatod a jelmagyarázat pozícióját és méretét a PowerPoint-diagramjaidban."
"linktitle": "Jelmagyarázat egyéni beállításainak megadása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Jelmagyarázat egyéni beállításainak megadása Java diákban"
"url": "/hu/java/customization-and-formatting/set-legend-custom-options-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Jelmagyarázat egyéni beállításainak megadása Java diákban


## Bevezetés a Java diák jelmagyarázat-egyéni beállításainak megadásához

Ebben az oktatóanyagban bemutatjuk, hogyan szabhatod testre egy PowerPoint-bemutató diagramjának jelmagyarázat-tulajdonságait az Aspose.Slides for Java segítségével. A jelmagyarázat pozícióját, méretét és egyéb attribútumait a prezentációs igényeidnek megfelelően módosíthatod.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következőkkel rendelkezik:

- Aspose.Slides Java API-hoz telepítve.
- Java fejlesztői környezet beállítása.

## 1. lépés: Importálja a szükséges osztályokat:

```java
// Aspose.Slides importálása Java osztályokhoz
import com.aspose.slides.*;
```

## 2. lépés: Adja meg a dokumentumkönyvtár elérési útját:

```java
String dataDir = "Your Document Directory";
```

## 3. lépés: Hozz létre egy példányt a következőből: `Presentation` osztály:

```java
Presentation presentation = new Presentation();
```

## 4. lépés: Dia hozzáadása a prezentációhoz:

```java
try {
    ISlide slide = presentation.getSlides().get_Item(0);
```

## 5. lépés: Csoportos oszlopdiagram hozzáadása a diához:

```java
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
```

## 6. lépés. Jelmagyarázat tulajdonságainak beállítása:

- A jelmagyarázat X pozíciójának beállítása (a diagram szélességéhez viszonyítva):

```java
chart.getLegend().setX(50 / chart.getWidth());
```

- A jelmagyarázat Y pozíciójának beállítása (a diagram magasságához képest):

```java
chart.getLegend().setY(50 / chart.getHeight());
```

- A jelmagyarázat szélességének beállítása (a diagram szélességéhez viszonyítva):

```java
chart.getLegend().setWidth(100 / chart.getWidth());
```

- jelmagyarázat magasságának beállítása (a diagram magasságához viszonyítva):

```java
chart.getLegend().setHeight(100 / chart.getHeight());
```

## 7. lépés: Mentse a prezentációt lemezre:

```java
    presentation.save(dataDir + "Legend_out.pptx", SaveFormat.Pptx);
} finally {
    if (presentation != null) presentation.dispose();
}
```

Ennyi! Sikeresen testre szabtad egy PowerPoint-bemutatóban lévő diagram jelmagyarázat-tulajdonságait az Aspose.Slides for Java használatával.

## Teljes forráskód a Java Slides jelmagyarázat egyéni beállításainak beállításához

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozz létre egy példányt a Presentation osztályból
Presentation presentation = new Presentation();
try
{
	// Dia hivatkozásának lekérése
	ISlide slide = presentation.getSlides().get_Item(0);
	// Csoportos oszlopdiagram hozzáadása a diához
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 500, 500);
	// Jelmagyarázat tulajdonságainak beállítása
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

Ebben az oktatóanyagban megtanultuk, hogyan szabhatjuk testre egy PowerPoint-bemutató diagramjának jelmagyarázat-tulajdonságait az Aspose.Slides Java verziójával. Módosíthatjuk a jelmagyarázat pozícióját, méretét és egyéb tulajdonságait, hogy vizuálisan vonzó és informatív bemutatókat hozzunk létre.

## GYIK

## Hogyan tudom megváltoztatni a jelmagyarázat pozícióját?

A jelmagyarázat pozíciójának módosításához használja a `setX` és `setY` legend objektum metódusai. Az értékek a diagram szélességéhez és magasságához viszonyítva vannak megadva.

## Hogyan tudom beállítani a jelmagyarázat méretét?

A jelmagyarázat méretét a következővel módosíthatja: `setWidth` és `setHeight` a legend objektum metódusai. Ezek az értékek a diagram szélességéhez és magasságához képest is relatívak.

## Testreszabhatom a jelmagyarázat egyéb attribútumait?

Igen, testreszabhatja a jelmagyarázat különböző attribútumait, például a betűstílust, a szegélyt, a háttérszínt és egyebeket. A jelmagyarázatok testreszabásával kapcsolatos részletes információkért tekintse meg az Aspose.Slides dokumentációját.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}