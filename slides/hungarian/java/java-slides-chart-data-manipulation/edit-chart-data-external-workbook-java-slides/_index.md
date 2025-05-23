---
"description": "Ismerje meg, hogyan szerkesztheti a diagramadatokat egy külső munkafüzetben az Aspose.Slides for Java használatával. Lépésről lépésre útmutató forráskóddal."
"linktitle": "Diagramadatok szerkesztése külső munkafüzetben Java Slides-ben"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Diagramadatok szerkesztése külső munkafüzetben Java Slides-ben"
"url": "/hu/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagramadatok szerkesztése külső munkafüzetben Java Slides-ben


## Bevezetés a külső munkafüzetben lévő diagramadatok szerkesztésébe Java Slides-ben

Ebben az útmutatóban bemutatjuk, hogyan szerkeszthetők diagramadatok egy külső munkafüzetben az Aspose.Slides Java verziójával. Megtanulod, hogyan módosíthatod programozottan a diagramadatokat egy PowerPoint-bemutatóban. Győződj meg róla, hogy az Aspose.Slides Java verziójú könyvtár telepítve és konfigurálva van a projektedben.

## Előfeltételek

- Aspose.Slides Java-hoz
- Java fejlesztői környezet

## 1. lépés: Töltse be a prezentációt

Először is be kell töltenünk azt a PowerPoint bemutatót, amely a szerkeszteni kívánt diagramot tartalmazza. `"Your Document Directory"` a prezentációs fájl tényleges elérési útjával.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## 2. lépés: Hozzáférés a diagramhoz

Miután a prezentáció betöltődött, hozzá kell férnünk a diagramhoz a prezentáción belül. Ebben a példában feltételezzük, hogy a diagram az első dián található, és az első alakzat a dián.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## 3. lépés: Diagramadatok módosítása

Most módosítsuk a diagram adatait. A diagram egy adott adatpontjának módosítására fogunk összpontosítani. Ebben a példában az első sorozat első adatpontjának értékét 100-ra állítottuk be. Ezt az értéket szükség szerint módosíthatja.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## 4. lépés: Mentse el a prezentációt

Miután elvégezte a szükséges módosításokat a diagram adatain, mentse el a módosított prezentációt egy új fájlba. A kimeneti fájl elérési útját és formátumát az igényeinek megfelelően adhatja meg.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## 5. lépés: Tisztítás

Ne felejtsd el megszabadulni a presentation objektumtól az erőforrások felszabadításához.

```java
if (pres != null) pres.dispose();
```

Most sikeresen szerkesztetted a diagram adatait egy külső munkafüzetben a PowerPoint-bemutatódon belül az Aspose.Slides for Java segítségével. Testreszabhatod ezt a kódot az igényeidnek megfelelően, és integrálhatod a Java-alkalmazásaidba.

## Teljes forráskód

```java
        // Figyelj arra, hogy a külső munkafüzet elérési útja alig van elmentve a prezentációban.
        // Tehát kérjük, másolja át az externalWorkbook.xlsx fájlt a Data/Chart könyvtárból (D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\) a példa futtatása előtt.
        // A dokumentumok könyvtárának elérési útja.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Következtetés

Ebben az átfogó útmutatóban azt vizsgáltuk meg, hogyan szerkeszthetők a PowerPoint-bemutatókon belüli külső munkafüzetekben található diagramadatok az Aspose.Slides for Java segítségével. A lépésenkénti utasítások és forráskódpéldák követésével megszerezted a tudást és a készségeket a diagramadatok programozott, egyszerű módosításához.

## GYIK

### Hogyan adhatok meg egy másik diagramot vagy diát?

Egy másik diagram vagy dia eléréséhez módosítsa a megfelelő indexet a `getSlides().get_Item()` és `getShapes().get_Item()` metódusok. Ne feledd, hogy az indexelés 0-tól kezdődik.

### Szerkeszthetek adatokat több diagramban ugyanazon a prezentáción belül?

Igen, ugyanazon a prezentáción belül több diagram adatait is szerkesztheti a diagramadatok módosításának lépéseinek megismétlésével minden diagram esetében.

### Mi a teendő, ha egy külső munkafüzetben lévő adatokat szeretnék szerkeszteni más formátumban?

A kódot úgy alakíthatod, hogy különböző külső munkafüzet-formátumokat kezeljen, ha a megfelelő Aspose.Cells osztályokat és metódusokat használod az adott formátumú adatok olvasásához és írásához.

### Hogyan automatizálhatom ezt a folyamatot több prezentációhoz?

Létrehozhat egy ciklust több prezentáció feldolgozásához, mindegyik betöltéséhez, a kívánt módosítások elvégzéséhez, majd a módosított prezentációk egyenkénti mentéséhez.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}