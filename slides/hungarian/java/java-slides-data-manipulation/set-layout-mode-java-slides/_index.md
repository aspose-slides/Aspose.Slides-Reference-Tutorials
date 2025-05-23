---
"description": "Tanuld meg, hogyan állíthatsz be elrendezési módokat Java diákhoz az Aspose.Slides segítségével. Testreszabhatod a diagramok elhelyezését és méretezését ebben a lépésről lépésre szóló útmutatóban forráskóddal."
"linktitle": "Elrendezési mód beállítása Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Elrendezési mód beállítása Java diákban"
"url": "/hu/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Elrendezési mód beállítása Java diákban


## Bevezetés a Java diák elrendezési módjának beállításába

Ebben az oktatóanyagban megtanuljuk, hogyan állíthatjuk be a diagram elrendezési módját Java diákon az Aspose.Slides for Java használatával. Az elrendezési mód határozza meg a diagram elhelyezkedését és méretét a dián belül.

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg róla, hogy az Aspose.Slides for Java könyvtár telepítve és beállítva van a Java projektedben. A könyvtárat innen töltheted le: [itt](https://releases.aspose.com/slides/java/).

## 1. lépés: Prezentáció létrehozása

Először is létre kell hoznunk egy új prezentációt.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## 2. lépés: Dia és diagram hozzáadása

Következőként hozzáadunk egy diát és egy diagramot. Ebben a példában egy csoportos oszlopdiagramot fogunk létrehozni.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## 3. lépés: Diagram elrendezésének beállítása

Most állítsuk be a diagram elrendezését. A diagram pozícióját és méretét a dián belül a következővel fogjuk beállítani: `setX`, `setY`, `setWidth`, `setHeight` metódusok. Ezenkívül beállítjuk a `LayoutTargetType` az elrendezési mód meghatározásához.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

Ebben a példában a diagram elrendezési céltípusa „Belső” lett, ami azt jelenti, hogy a dia belső területéhez képest lesz elhelyezve és méretezve.

## 4. lépés: Mentse el a prezentációt

Végül mentsük el a prezentációt a diagram elrendezési beállításaival.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a Java Slides elrendezési módjának beállításához

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

Ebben az oktatóanyagban megtanultuk, hogyan állíthatjuk be a diagram elrendezési módját Java diákon az Aspose.Slides for Java használatával. A diagram pozícióját és méretét testreszabhatja az Ön igényei szerint a `setX`, `setY`, `setWidth`, `setHeight`, és `setLayoutTargetType` metódusok. Ezáltal szabályozhatod a diagramok elhelyezését a diákon belül.

## GYIK

### Hogyan változtathatom meg egy diagram elrendezési módját az Aspose.Slides for Java programban?

Az Aspose.Slides Java-ban egy diagram elrendezési módjának megváltoztatásához használhatja a `setLayoutTargetType` metódus a diagram ábrázolási területén. Beállíthatja a következőre: `LayoutTargetType.Inner` vagy `LayoutTargetType.Outer` kívánt elrendezéstől függően.

### Testreszabhatom a diagram pozícióját és méretét a dián belül?

Igen, a dián belüli diagram pozícióját és méretét testreszabhatja a `setX`, `setY`, `setWidth`, és `setHeight` metódusok a diagram ábrázolási területén. Módosítsa ezeket az értékeket a diagram igényeinek megfelelő elhelyezéséhez és méretéhez.

### Hol találok további információt az Aspose.Slides for Java-ról?

További információkat az Aspose.Slides Java-hoz való használatáról itt talál: [dokumentáció](https://reference.aspose.com/slides/java/)Részletes API-hivatkozásokat és példákat tartalmaz, amelyek segítenek a diákkal és diagramokkal való hatékony munkában Java nyelven.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}