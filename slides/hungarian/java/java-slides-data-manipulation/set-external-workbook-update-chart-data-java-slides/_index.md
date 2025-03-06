---
title: Állítsa be a külső munkafüzetet a diagramadatok frissítésével a Java Slides-ben
linktitle: Állítsa be a külső munkafüzetet a diagramadatok frissítésével a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be külső munkafüzeteket és frissítheti a diagramadatokat a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. Fejlessze PowerPoint automatizálási készségeit.
weight: 20
url: /hu/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Bevezetés a külső munkafüzet beállításához a diagramadatok frissítésével a Java Slides-ben

Ebben az átfogó útmutatóban végigvezetjük egy külső munkafüzet beállításának folyamatán, frissített diagramadatokkal a Java Slides alkalmazásban az Aspose.Slides for Java API használatával. Ez a nagy teljesítményű könyvtár lehetővé teszi a PowerPoint prezentációk programozott kezelését, megkönnyítve az olyan feladatok automatizálását, mint például a diagramadatok külső forrásból történő frissítése. Ennek az oktatóanyagnak a végére világosan megérti, hogyan lehet ezt a feladatot lépésről lépésre lépésről lépésre végrehajtani, és a kísérő Java-kódot tartalmazza.

## Előfeltételek

Mielőtt belevágnánk a megvalósításba, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1.  Aspose.Slides for Java: telepítenie kell az Aspose.Slides for Java könyvtárat. Letöltheti innen[itt](https://releases.aspose.com/slides/java/).

2. Java fejlesztői környezet: Győződjön meg arról, hogy a rendszeren be van állítva Java fejlesztői környezet.

## 1. lépés: Hozzon létre egy új prezentációt

A kezdéshez hozzunk létre egy új PowerPoint-prezentációt az Aspose.Slides for Java segítségével. Íme a Java kód ehhez:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Adjon hozzá egy diagramot

Most pedig adjunk hozzá egy diagramot bemutatónkhoz. Ebben a példában kördiagramot hozunk létre:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## 3. lépés: Állítsa be a külső munkafüzetet

Itt állítjuk be a külső munkafüzetet diagramunk adatforrásaként. Meg kell adnia a külső munkafüzet URL-címét, még akkor is, ha jelenleg nem létezik:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://útvonal/nincs/létezik", false);
```

## 4. lépés: Mentse el a bemutatót

Végül mentse el a prezentációt a frissített diagramadatokkal:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a külső munkafüzethez a Java Slides diagramadatok frissítésével

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://útvonal/nincs/létezik", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Gratulálunk! Megtanulta, hogyan állíthat be külső munkafüzetet frissített diagramadatokkal a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. Ez hihetetlenül hasznos lehet a PowerPoint-prezentációk külső adatforrásokból származó diagramjainak dinamikus frissítéséhez.

## GYIK

### Hogyan frissíthetem a diagram külső munkafüzet adatait?

A diagram külső munkafüzet-adatainak frissítéséhez egyszerűen módosítania kell a külső munkafüzet adatait a megadott URL-címen. A prezentáció következő megnyitásakor az Aspose.Slides for Java lekéri a frissített adatokat a külső munkafüzetből, és ennek megfelelően frissíti a diagramot.

### Használhatok helyi fájlt külső munkafüzetként?

Igen, használhat helyi fájlt külső munkafüzetként, ha URL helyett a fájl elérési útját adja meg. Csak győződjön meg arról, hogy a fájl elérési útja helyes, és elérhető-e a Java alkalmazásból.

### Vannak-e korlátozások a külső munkafüzetek Aspose.Slides for Java alkalmazással való használatára?

Bár a külső munkafüzetek használata hatékony szolgáltatás, ne feledje, hogy a külső munkafüzet adatainak elérhetősége attól függ, hogy a megadott URL-en vagy fájlútvonalon elérhető-e. Győződjön meg arról, hogy a külső adatforrás elérhető a bemutató megnyitásakor, hogy elkerülje az adatlekérési problémákat.

### Testreszabhatom a diagram megjelenését a külső munkafüzet beállítása után?

Igen, testreszabhatja a diagram megjelenését, beleértve a címét, a címkéket, a színeket és egyebeket, még a külső munkafüzet beállítása után is. Az Aspose.Slides for Java kiterjedt diagramformázási lehetőségeket kínál az Ön igényeinek megfelelően.

### Hol találok további dokumentációt és forrásokat az Aspose.Slides for Java-hoz?

 Részletes dokumentációért és további forrásokért keresse fel az Aspose.Slides for Java dokumentációt a címen[itt](https://reference.aspose.com/slides/java/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
