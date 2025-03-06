---
title: Diagramadatok szerkesztése a Java Slides külső munkafüzetében
linktitle: Diagramadatok szerkesztése a Java Slides külső munkafüzetében
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan szerkesztheti a diagramadatokat egy külső munkafüzetben az Aspose.Slides for Java segítségével. Lépésről lépésre útmutató forráskóddal.
weight: 17
url: /hu/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Bevezetés a diagramadatok szerkesztésébe a Java Slides külső munkafüzetében

Ebben az útmutatóban bemutatjuk, hogyan lehet szerkeszteni diagramadatokat egy külső munkafüzetben az Aspose.Slides for Java segítségével. Megtudhatja, hogyan lehet programozottan módosítani a diagramadatokat PowerPoint-prezentációkon belül. Győződjön meg arról, hogy a projektben telepítve és konfigurálva van az Aspose.Slides for Java könyvtár.

## Előfeltételek

- Aspose.Slides a Java számára
- Java fejlesztői környezet

## 1. lépés: Töltse be a prezentációt

 Először is be kell töltenünk a PowerPoint bemutatót, amely tartalmazza azt a diagramot, amelynek adatait szerkeszteni szeretnénk. Cserélje ki`"Your Document Directory"` a prezentációs fájl tényleges elérési útjával.

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## 2. lépés: Nyissa meg a diagramot

A prezentáció betöltése után el kell érnünk a prezentáción belüli diagramot. Ebben a példában feltételezzük, hogy a diagram az első dián van, és az első alakzat a dián.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## 3. lépés: Módosítsa a diagram adatait

Most módosítsuk a diagram adatait. A diagram egy adott adatpontjának módosítására összpontosítunk. Ebben a példában az első sorozat első adatpontjának értékét 100-ra állítjuk. Ezt az értéket szükség szerint módosíthatja.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## 4. lépés: Mentse el a bemutatót

A diagramadatok szükséges módosításainak elvégzése után mentse a módosított prezentációt egy új fájlba. Megadhatja a kimeneti fájl elérési útját és formátumát igényei szerint.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## 5. lépés: Tisztítás

Ne felejtse el megválni a prezentációs objektumtól az erőforrások felszabadításához.

```java
if (pres != null) pres.dispose();
```

Sikeresen szerkesztette a diagramadatokat egy külső munkafüzetben a PowerPoint-prezentációban az Aspose.Slides for Java segítségével. Ezt a kódot testreszabhatja saját igényeinek megfelelően, és integrálhatja Java-alkalmazásaiba.

## Teljes forráskód

```java
        // Ügyeljen arra, hogy a külső munkafüzet elérési útja alig van elmentve a bemutatóban
        // ezért a példa futtatása előtt másolja ki az externalWorkbook.xlsx fájlt a Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\ mappából.
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

Ebben az átfogó útmutatóban megvizsgáltuk, hogyan lehet szerkeszteni a diagramadatokat külső munkafüzetekben a PowerPoint-prezentációkban az Aspose.Slides for Java segítségével. A lépésenkénti utasítások és a forráskód-példák követésével olyan ismeretekre és készségekre tett szert, amelyek segítségével könnyedén, programozottan módosíthatja a diagramadatokat.

## GYIK

### Hogyan adhatok meg másik diagramot vagy diát?

 Egy másik diagram vagy dia eléréséhez módosítsa a megfelelő indexet a`getSlides().get_Item()` és`getShapes().get_Item()`mód. Ne feledje, hogy az indexelés 0-tól kezdődik.

### Szerkeszthetek adatokat több diagramon ugyanazon a prezentáción belül?

Igen, ugyanazon a prezentáción belül több diagramon is szerkesztheti az adatokat, ha megismétli a diagramadatok módosításának lépéseit az egyes diagramoknál.

### Mi a teendő, ha egy másik formátumú külső munkafüzet adatait szeretném szerkeszteni?

A kódot hozzáigazíthatja a különböző külső munkafüzet-formátumok kezelésére a megfelelő Aspose.Cells osztályok és metódusok használatával az adatok olvasására és írására ebben a formátumban.

### Hogyan automatizálhatom ezt a folyamatot több prezentációhoz?

Létrehozhat egy hurkot több prezentáció feldolgozásához, mindegyik betöltéséhez, a kívánt módosítások elvégzéséhez és a módosított prezentációk egyenkénti mentéséhez.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
