---
"date": "2025-04-17"
"description": "Tanuld meg, hogyan hozhatsz létre és szabhatsz testre kördiagramokat az Aspose.Slides for Java használatával. Ez az oktatóanyag mindent lefed a beállítástól a haladó testreszabásig."
"title": "Kördiagramok létrehozása Java nyelven az Aspose.Slides segítségével – Átfogó útmutató"
"url": "/hu/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Kördiagramok létrehozása az Aspose.Slides segítségével Java-ban: Teljes körű útmutató

## Bevezetés
dinamikus és vizuálisan vonzó prezentációk készítése kulcsfontosságú a hatásos információk közvetítéséhez. Az Aspose.Slides Java verziójával zökkenőmentesen integrálhat összetett diagramokat, például kördiagramokat a diáiba, könnyedén javítva az adatvizualizációt. Ez az átfogó útmutató végigvezeti Önt a kördiagramok Aspose.Slides Java használatával történő létrehozásának és testreszabásának folyamatán, könnyedén megoldva a prezentációkkal kapcsolatos gyakori kihívásokat.

**Amit tanulni fogsz:**
- Prezentáció inicializálása és diák hozzáadása.
- Kördiagram létrehozása és konfigurálása a dián.
- Diagramcímek, adatfeliratok és színek beállítása.
- A teljesítmény optimalizálása és az erőforrások hatékony kezelése.
- Aspose.Slides integrálása Java projektekbe Maven vagy Gradle használatával.

Kezdjük azzal, hogy minden szükséges eszközzel és tudással rendelkezel a folytatáshoz!

## Előfeltételek
Mielőtt belevágna ebbe az oktatóanyagba, győződjön meg arról, hogy a következő beállításokkal rendelkezik:

### Szükséges könyvtárak, verziók és függőségek
- **Aspose.Slides Java-hoz**Győződjön meg róla, hogy a 25.4-es vagy újabb verzióval rendelkezik.
- **Java fejlesztőkészlet (JDK)**: 16-os vagy újabb verzió szükséges.

### Környezeti beállítási követelmények
- Fejlesztői környezet telepített és konfigurált Java-val.
- Integrált fejlesztői környezet (IDE), mint például az IntelliJ IDEA, az Eclipse vagy a NetBeans.

### Előfeltételek a tudáshoz
- Java programozási alapismeretek.
- Maven vagy Gradle ismeretek függőségkezelés terén.

## Az Aspose.Slides beállítása Java-hoz
Az Aspose.Slides Java projektekben való használatának elkezdéséhez hozzá kell adni a könyvtárat függőségként. Így teheted meg ezt különböző build eszközökkel:

**Szakértő**
Add hozzá ezt a részletet a `pom.xml` fájl:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
A következőket is vedd bele a listádba `build.gradle` fájl:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Közvetlen letöltés**
Ha nem szeretnél építőeszközt használni, töltsd le a legújabb verziót innen: [Aspose.Slides Java kiadásokhoz](https://releases.aspose.com/slides/java/).

### Licencbeszerzés lépései
- **Ingyenes próbaverzió**: Kezdje el egy ingyenes próbaverzióval az Aspose.Slides funkcióinak felfedezését.
- **Ideiglenes engedély**: Szerezzen be egy ideiglenes engedélyt korlátozás nélküli, meghosszabbított használatra.
- **Vásárlás**: Fontolja meg a vásárlást, ha hosszú távú hozzáférésre van szüksége.

**Alapvető inicializálás és beállítás**
Az Aspose.Slides használatának megkezdéséhez inicializálja a projektet egy új prezentációs objektum létrehozásával:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Megvalósítási útmutató
Most bontsuk le a kördiagram hozzáadásának és testreszabásának folyamatát kezelhető lépésekre.

### Prezentáció és dia inicializálása
Kezdésként állítson be egy új prezentációt, és nyissa meg az első diát. Ez a vászon a diagramok létrehozásához:
```java
import com.aspose.slides.*;

// Hozzon létre egy új prezentációs példányt.
Presentation presentation = new Presentation();
// Nyissa meg a prezentáció első diáját.
islide slides = presentation.getSlides().get_Item(0);
```

### Kördiagram hozzáadása diához
Kördiagram beszúrása a megadott pozícióba alapértelmezett adathalmazzal:
```java
import com.aspose.slides.*;

// Adjon hozzá egy kördiagramot a (100, 100) pozícióban, (400, 400) méretben.
ischart chart = slides.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Diagram címének beállítása
Szabja testre a diagramot a cím beállításával és középre igazításával:
```java
import com.aspose.slides.*;

// Adj címet a kördiagramhoz.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Adatsorok adatcímkéinek konfigurálása
Az áttekinthetőség érdekében győződjön meg arról, hogy az adatcímkék értékeket jelenítenek meg:
```java
import com.aspose.slides.*;

// Adatértékek megjelenítése az első sorozaton.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Diagramadat-munkalap elkészítése
Állítsa be a diagram adatlapját a meglévő sorozatok és kategóriák törlésével:
```java
import com.aspose.slides.*;

// Készítse elő a diagramadatokkal foglalkozó munkafüzetet.
int defaultWorksheetIndex = 0;
isChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Kategóriák hozzáadása a diagramhoz
Definiálja a kördiagram kategóriáit:
```java
import com.aspose.slides.*;

// Új kategóriák hozzáadása.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Sorozatok hozzáadása és adatpontok feltöltése
Hozz létre egy sorozatot, és töltsd fel adatpontokkal:
```java
import com.aspose.slides.*;

// Adjon hozzá egy új sorozatot, és adja meg a nevét.
ischartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Sorozatszínek és szegélyek testreszabása
Növelje a vizuális vonzerőt színek beállításával és a szegélyek testreszabásával:
```java
import com.aspose.slides.*;

// Állítson be különböző színeket a sorozat szektoraihoz.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

isChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Ismételje meg a műveletet más, eltérő színekkel és stílusokkal rendelkező adatpontok esetében.
```

### Egyéni adatcímkék konfigurálása
Finomhangolja az egyes adatpontok címkéit:
```java
import com.aspose.slides.*;

// Egyéni címkék konfigurálása.
isDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

isDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

isDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Vezető vonalak engedélyezése a címkékhez.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Forgatási szög beállítása és a prezentáció mentése
kördiagram véglegesítéséhez állítson be egy forgatási szöget, és mentse el a prezentációt:
```java
import com.aspose.slides.*;

// Állítsa be a forgási szöget.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Mentse el a prezentációt egy fájlba.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Következtetés
Ebben az oktatóanyagban megtanultad, hogyan hozhatsz létre és szabhatsz testre kördiagramokat az Aspose.Slides for Java segítségével. Ezeket a lépéseket követve vizuálisan vonzó adatvizualizációkkal gazdagíthatod prezentációidat. Ha bármilyen kérdésed van, vagy további segítségre van szükséged, fordulj hozzánk bizalommal.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}