---
"date": "2025-04-17"
"description": "Tanuld meg, hogyan hozhatsz létre dinamikus szóródási diagramokat az Aspose.Slides for Java segítségével. Dobd fel prezentációidat testreszabható diagramfunkciókkal."
"title": "Hozzon létre és szabjon testre szóródási diagramokat Java nyelven az Aspose.Slides segítségével"
"url": "/hu/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hozzon létre és szabjon testre szóródási diagramokat Java nyelven az Aspose.Slides segítségével

Dobd fel prezentációidat dinamikus szóródási diagramok hozzáadásával Java használatával az Aspose.Slides segítségével. Ez az átfogó oktatóanyag végigvezet a könyvtárak beállításán, a prezentációk inicializálásán, a szóródási diagramok létrehozásán, a diagramadatok kezelésén, a sorozattípusok és jelölők testreszabásán, valamint a munkád mentésén – mindezt könnyedén.

**Amit tanulni fogsz:**
- Könyvtár beállítása prezentációs fájlok tárolására
- Prezentációk inicializálása és kezelése az Aspose.Slides használatával
- Pontdiagramok létrehozása diákon
- Adatok kezelése és hozzáadása diagramsorozatokhoz
- Diagramsorozat-típusok és -jelölők testreszabása
- A prezentáció mentése módosításokkal

Kezdjük azzal, hogy megbizonyosodunk arról, hogy rendelkezel a szükséges előfeltételekkel.

## Előfeltételek

A bemutató követéséhez győződjön meg arról, hogy rendelkezik a következőkkel:
- **Aspose.Slides Java-hoz**: 25.4-es vagy újabb verzió szükséges.
- **Java fejlesztőkészlet (JDK)**JDK 8 vagy újabb verzió szükséges.
- Alapvető Java programozási ismeretek és jártasság a Maven vagy Gradle build eszközök használatában.

## Az Aspose.Slides beállítása Java-hoz

Mielőtt elkezdenénk a kódolást, integráljuk az Aspose.Slides-t a projektbe az alábbi módszerek egyikével:

### Szakértő
Vegye fel ezt a függőséget a `pom.xml` fájl:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Add hozzá ezt a sort a `build.gradle` fájl:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Vagy töltse le a legújabb Aspose.Slides for Java verziót innen: [Aspose kiadások](https://releases.aspose.com/slides/java/).

#### Licencszerzés
- **Ingyenes próbaverzió**: Kezdje egy 30 napos ingyenes próbaidőszakkal, hogy felfedezhesse a funkciókat.
- **Ideiglenes engedély**: Szerezzen be ideiglenes engedélyt meghosszabbított tesztelésre.
- **Vásárlás**: Vásároljon licencet a teljes hozzáférésért és támogatásért.

Most inicializáld az Aspose.Slides-t a Java alkalmazásodban a szükséges importálások hozzáadásával, az alábbiak szerint.

## Megvalósítási útmutató

### Könyvtár beállítása
Először is győződjön meg arról, hogy létezik a könyvtárunk a prezentációs fájlok tárolására. Ez a lépés megakadályozza a fájlok mentése során fellépő hibákat.

#### Hozza létre a könyvtárat, ha nem létezik
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Hozza létre a könyvtárat
    new File(dataDir).mkdirs();
}
```
Ez a kódrészlet egy megadott könyvtárat keres, és létrehozza, ha az nem létezik. A következőt használja: `File.exists()` jelenlétének ellenőrzésére és `File.mkdirs()` könyvtárak létrehozásához.

### Prezentáció inicializálása

Ezután inicializáld a prezentációs objektumot, ahová a szóródási diagramot szeretnéd hozzáadni.

#### Inicializálja a prezentációját
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Itt, `new Presentation()` üres prezentációt hoz létre. Az első diához férünk hozzá, hogy közvetlenül azzal dolgozhassunk.

### Diagram létrehozása
A következő lépés egy pontdiagram létrehozása az inicializált dián.

#### Pontdiagram hozzáadása a diához
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Ez a kódrészlet egy simított vonalakkal rendelkező pontdiagramot ad hozzá az első diához. A paraméterek határozzák meg a diagram pozícióját és méretét.

### Diagramadat-kezelés
Most pedig kezeljük a diagram adatait a meglévő sorozatok törlésével és újak hozzáadásával.

#### Diagramsorozat kezelése
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Új sorozatok hozzáadása a diagramhoz
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Ez a szakasz törli a meglévő adatokat, és két új adatsort ad hozzá a szóródási diagramhoz.

### Adatpontok összeadása szóródási sorozatokhoz
Az adataink vizualizálásához pontokat adunk hozzá a szóródási diagram minden sorozatához.

#### Adatpontok hozzáadása
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Használjuk `addDataPointForScatterSeries()` hogy adatpontokat fűzzünk az első sorozatunkhoz. A paraméterek határozzák meg az X és Y értékeket.

### Sorozattípus és jelölő módosítása
Szabja testre diagramja megjelenését az egyes sorozatokban található jelölők típusának és stílusának módosításával.

#### Sorozat testreszabása
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// A második sorozat módosítása
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Ezek a változtatások a sorozat típusát úgy módosítják, hogy egyenes vonalakat és jelölőket használjon. A vizuális megkülönböztetés érdekében beállítottuk a jelölő méretét és szimbólumát is.

### Prezentáció mentése
Végül mentsd el a prezentációt az összes módosítással együtt.

#### Mentse el a prezentációját
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Használat `SaveFormat.Pptx` a fájl mentésének PowerPoint-formátumának megadásához. Ez a lépés elengedhetetlen az összes módosítás megőrzéséhez.

## Gyakorlati alkalmazások
Íme néhány valós felhasználási eset:
1. **Pénzügyi elemzés**: Használjon szóródási diagramokat a részvények trendjeinek időbeli megjelenítéséhez.
2. **Tudományos kutatás**: Kísérleti adatpontokat jelölnek elemzés céljából.
3. **Projektmenedzsment**: Erőforrás-elosztás és haladásmérőszámok vizualizálása.

Az Aspose.Slides integrálása a rendszerébe lehetővé teszi a jelentéskészítés automatizálását, növelve a termelékenységet és a pontosságot.

## Teljesítménybeli szempontok
Az optimális teljesítmény érdekében:
- A memóriahasználat kezelése a prezentációk mentés utáni törlésével.
- Használjon hatékony adatszerkezeteket nagy adathalmazok esetén.
- Minimalizálja az erőforrás-igényes műveleteket a ciklusokon belül.

A legjobb gyakorlatok biztosítják a zökkenőmentes végrehajtást még összetett diagrammanipulációk esetén is.

## Következtetés
Ebben az oktatóanyagban megtanultad, hogyan állíthatsz be könyvtárakat, hogyan inicializálhatsz Aspose.Slides prezentációkat, hogyan hozhatsz létre és szabhatsz testre szóródási diagramokat, hogyan kezelheted a sorozatadatokat, hogyan módosíthatod a jelölőket, és hogyan mentheted el a munkádat. Az Aspose.Slides képességeinek további felfedezéséhez érdemes lehet belemerülnöd a haladóbb funkciókba, mint például az animáció és a diaátmenetek.

**Következő lépések**Kísérletezzen különböző diagramtípusokkal, vagy integrálja ezeket a technikákat egy nagyobb Java projektbe.

## GYIK

### Hogyan tudom megváltoztatni a jelölők színét?
A jelölő színének megváltoztatásához használja a `series.getMarker().getFillFormat().setFillColor(ColorObject)`, ahol `ColorObject` a kívánt szín.

### Hozzáadhatok kettőnél több adatsort egy szóródási diagramhoz?
Igen, annyi sorozatot adhat hozzá, amennyire szüksége van, az új sorozatok és adatpontok hozzáadásának folyamatának megismétlésével.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}