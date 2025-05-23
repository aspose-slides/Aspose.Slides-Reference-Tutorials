---
"description": "Tanuld meg, hogyan állíthatsz be külső munkafüzeteket és frissítheted a diagramadatokat Java Slides-ben az Aspose.Slides for Java használatával. Fejleszd PowerPoint automatizálási készségeidet."
"linktitle": "Külső munkafüzet beállítása a diagramadatok frissítésével Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Külső munkafüzet beállítása a diagramadatok frissítésével Java diákban"
"url": "/hu/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Külső munkafüzet beállítása a diagramadatok frissítésével Java diákban


## Bevezetés a külső munkafüzet beállításához a diagramadatok frissítésével Java Slides-ben

Ebben az átfogó útmutatóban végigvezetünk egy külső munkafüzet beállításának folyamatán, amely frissített diagramadatokat tartalmaz Java Slides-ban az Aspose.Slides for Java API használatával. Ez a hatékony könyvtár lehetővé teszi a PowerPoint-bemutatók programozott kezelését, megkönnyítve az olyan feladatok automatizálását, mint például a diagramadatok frissítése külső forrásból. A bemutató végére világosan megérted majd, hogyan valósíthatod meg ezt a feladatot lépésről lépésre bemutatott utasítások és a hozzá tartozó Java-kód segítségével.

## Előfeltételek

Mielőtt belevágnánk a megvalósításba, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:

1. Aspose.Slides Java-hoz: Telepíteni kell az Aspose.Slides Java-hoz könyvtárat. Letöltheti innen: [itt](https://releases.aspose.com/slides/java/).

2. Java fejlesztői környezet: Győződjön meg arról, hogy van Java fejlesztői környezet beállítva a rendszerén.

## 1. lépés: Új prezentáció létrehozása

Kezdésként hozzunk létre egy új PowerPoint bemutatót az Aspose.Slides for Java használatával. Íme a Java kód ehhez:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## 2. lépés: Diagram hozzáadása

Most adjunk hozzá egy diagramot a prezentációnkhoz. Ebben a példában egy kördiagramot fogunk létrehozni:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## 3. lépés: Külső munkafüzet beállítása

Itt állítjuk be a külső munkafüzetet a diagram adatforrásaként. Meg kell adnia a külső munkafüzet URL-címét, még akkor is, ha az jelenleg nem létezik:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://"path/does/létezik", "false");
```

## 4. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt a frissített diagramadatokkal:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a külső munkafüzet beállításához a diagramadatok frissítésével Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://"path/does/létezik", "false");
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Gratulálunk! Megtanultad, hogyan állíthatsz be egy külső munkafüzetet frissített diagramadatokkal Java Slidesben az Aspose.Slides for Java használatával. Ez hihetetlenül hasznos lehet a PowerPoint-bemutatóidban található diagramok külső adatforrásokból történő dinamikus frissítéséhez.

## GYIK

### Hogyan frissíthetem a diagram külső munkafüzet-adatait?

A diagram külső munkafüzet-adatainak frissítéséhez egyszerűen módosítania kell a megadott URL-címen található külső munkafüzet adatait. A prezentáció következő megnyitásakor az Aspose.Slides for Java lekéri a frissített adatokat a külső munkafüzetből, és ennek megfelelően frissíti a diagramot.

### Használhatok egy helyi fájlt külső munkafüzetként?

Igen, használhatsz helyi fájlt külső munkafüzetként, ha URL helyett a fájl elérési útját adod meg. Csak győződj meg róla, hogy a fájl elérési útja helyes és elérhető a Java-alkalmazásodból.

### Vannak-e korlátozások a külső munkafüzetek Aspose.Slides for Java használatával történő használatára vonatkozóan?

Bár a külső munkafüzetek használata hatékony funkció, ne feledje, hogy a külső munkafüzet adatainak elérhetősége a megadott URL-címen vagy fájlelérési úton való elérhetőségüktől függ. Az adatlekérési problémák elkerülése érdekében győződjön meg arról, hogy a külső adatforrás elérhető a bemutató megnyitásakor.

### Testreszabhatom a diagram megjelenését a külső munkafüzet beállítása után?

Igen, testreszabhatja a diagram megjelenését, beleértve a címét, címkéit, színeit és egyebeket, még a külső munkafüzet beállítása után is. Az Aspose.Slides for Java kiterjedt diagramformázási lehetőségeket kínál az Ön igényeinek kielégítésére.

### Hol találok további dokumentációt és forrásokat az Aspose.Slides for Java-hoz?

Részletes dokumentációért és további forrásokért látogassa meg az Aspose.Slides Java-hoz készült dokumentációját a következő címen: [itt](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}