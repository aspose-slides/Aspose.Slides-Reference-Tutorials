---
date: '2026-01-17'
description: Tanulja meg, hogyan adhat hozzá sorozatokat a diagramhoz, és testreszabhatja
  a halmozott oszlopdiagramokat .NET prezentációkban az Aspose.Slides for Java használatával.
keywords:
- Aspose.Slides for Java
- .NET Presentations
- Chart Customization
title: Sorozat hozzáadása diagramhoz az Aspose.Slides for Java .NET környezetben
url: /hu/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# A diagram testreszabásának elsajátítása .NET prezentációkban az Aspose.Slides for Java segítségével

## Bevezetés
Az adat‑vezérelt prezentációk világában a diagramok elengedhetetlen eszközök, amelyek a nyers számokat megragadó vizuális történetekké alakítják. Amikor programozottan kell **add series to chart** műveletet végrehajtani, különösen .NET prezentációs fájlokban, a feladat ijesztőnek tűnhet. Szerencsére a **Aspose.Slides for Java** egy erőteljes, nyelv‑független API‑t biztosít, amely egyszerűvé teszi a diagramok létrehozását és testreszabását – még akkor is, ha a célformátum egy .NET PPTX.

Ebben az útmutatóban megtanulod, hogyan **add series to chart**, hogyan **how to add chart** a halmozott oszlop típusú diagramot, és hogyan finomhangolhatod a vizuális elemeket, például a részsáv szélességét. A végére képes leszel dinamikus, adat‑gazdag diák generálására, amelyek kifinomultak és professzionálisak.

**Mit fogsz megtanulni**
- Hogyan hozzunk létre egy üres prezentációt az Aspose.Slides segítségével  
- Hogyan **add stacked column chart** adjunk egy diára  
- Hogyan **add series to chart** és definiáljunk kategóriákat  
- Hogyan töltsünk fel adatpontokat és állítsuk be a vizuális beállításokat  

Készítsük elő a fejlesztői környezetet.

## Gyors válaszok
- **Mi a fő osztály egy prezentáció elindításához?** `Presentation`  
- **Melyik metódus ad diagramot egy diára?** `slide.getShapes().addChart(...)`  
- **Hogyan adsz hozzá új sorozatot?** `chart.getChartData().getSeries().add(...)`  
- **Módosítható a sávok közötti részsáv szélessége?** Igen, a `setGapWidth()` használatával a sorozatcsoporton  
- **Szükség van licencre a termeléshez?** Igen, egy érvényes Aspose.Slides for Java licenc szükséges  

## Mi az a “add series to chart”?
Egy sorozat diagramhoz adása azt jelenti, hogy egy új adatgyűjteményt illesztünk be, amelyet a diagram különálló vizuális elemeként (pl. új oszlop, vonal vagy szelet) jelenít meg. Minden sorozat saját értékekkel, színekkel és formázással rendelkezhet, lehetővé téve több adatkészlet egymás melletti összehasonlítását.

## Miért használjuk az Aspose.Slides for Java‑t .NET prezentációk módosításához?
- **Cross‑platform**: Írj Java kódot egyszer, és célozd meg a .NET alkalmazások által használt PPTX fájlokat.  
- **Nincs COM vagy Office függőség**: Szervereken, CI csővezetékeken és konténerekben is működik.  
- **Gazdag diagram API**: Több mint 50 diagramtípust támogat, beleértve a halmozott oszlop diagramokat.  

## Előkövetelmények
1. **Aspose.Slides for Java** könyvtár (25.4 vagy újabb verzió).  
2. Maven vagy Gradle build eszköz, vagy manuális JAR letöltés.  
3. Alap Java ismeretek és a PPTX struktúra ismerete.  

## Az Aspose.Slides for Java beállítása
### Maven telepítés
Add hozzá a következő függőséget a `pom.xml`-hez:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle telepítés
Add ezt a sort a `build.gradle` fájlodba:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés
Alternatívaként szerezd be a legújabb JAR‑t a hivatalos kiadási oldalról: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Licenc beszerzése**  
Kezdd egy ingyenes próbaidőszakkal, a [itt](https://purchase.aspose.com/temporary-license/) elérhető ideiglenes licenc letöltésével. Termelési használathoz vásárolj teljes licencet, hogy minden funkció elérhető legyen.

## Lépés‑ről‑lépésre megvalósítási útmutató
Minden lépés alatt találsz egy tömör kódrészletet (az eredeti útmutatóból változatlan), amelyet egy magyarázat követ, hogy mit csinál.

### 1. lépés: Üres prezentáció létrehozása
```java
import com.aspose.slides.*;

// Initialize an empty presentation
Presentation presentation = new Presentation();

// Access the first slide (automatically created)
ISlide slide = presentation.getSlides().get_Item(0);

// Save the presentation to a specified path
presentation.save("YOUR_OUTPUT_DIRECTORY/Empty_Presentation.pptx", SaveFormat.Pptx);
```
*Egy tiszta PPTX fájllal kezdünk, amely vászonként szolgál a diagramok hozzáadásához.*

### 2. lépés: Halmozott oszlop diagram hozzáadása a diára
```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```
*Az `addChart` metódus egy **add stacked column chart**-ot hoz létre, és a dia bal‑felső sarkába helyezi.*

### 3. lépés: Sorozatok hozzáadása a diagramhoz (fő cél)
```java
// Accessing the default worksheet index for chart data
int defaultWorksheetIndex = 0;

// Adding series to the chart
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 0, 2, "Series 2"), chart.getType());

// Save the presentation after adding series
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Added.pptx", SaveFormat.Pptx);
```
*Itt **add series to chart** – minden hívás egy új adat sorozatot hoz létre, amely külön oszlopcsoportként jelenik meg.*

### 4. lépés: Kategóriák hozzáadása a diagramhoz
```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```
*A kategóriák az X‑tengely feliratai, amelyek értelmet adnak minden oszlopnak.*

### 5. lépés: Sorozat adatok feltöltése
```java
// Accessing a particular series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(1);

// Adding data points to the series
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));

// Save the presentation with populated data
presentation.save("YOUR_OUTPUT_DIRECTORY/Series_Data_Populated.pptx", SaveFormat.Pptx);
```
*Az adatpontok minden sorozatnak numerikus értékeket adnak, amelyeket a diagram oszlopmagasságként jelenít meg.*

### 6. lépés: Részsáv szélességének beállítása a diagram sorozatcsoporthoz
```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```
*A részsáv szélességének módosítása javítja az olvashatóságot, különösen sok kategória esetén.*

## Általános felhasználási esetek
- **Pénzügyi jelentés** – negyedéves bevételek összehasonlítása az üzleti egységek között.  
- **Projekt irányítópultok** – feladat befejezési százalékok megjelenítése csapatonként.  
- **Marketing elemzés** – kampány teljesítményének vizualizálása egymás mellett.

## Teljesítmény tippek
- **Használd újra a `Presentation` objektumot** több diagram létrehozásakor, hogy csökkentsd a memóriahasználatot.  
- **Korlátozd az adatpontok számát** csak a vizuális történethez szükségesekre.  
- **Felszabadítsd az objektumokat** (`presentation.dispose()`) a mentés után, hogy erőforrásokat szabadíts fel.

## Gyakran ismételt kérdések
**K: Hozzáadhatok más diagramtípusokat a halmozott oszlopon kívül?**  
V: Igen, az Aspose.Slides támogatja a vonal, kör, terület és számos más diagramtípust.

**K: Szükség van külön licencre a .NET kimenethez?**  
V: Nem, ugyanaz a Java licenc működik minden kimeneti formátumhoz, beleértve a .NET PPTX fájlokat is.

**K: Hogyan változtathatom meg a diagram színpalettáját?**  
V: Használd a `chart.getChartData().getSeries().get_Item(i).getFormat().getFill().setFillType(FillType.Solid)` metódust, és állítsd be a kívánt `Color`‑t.

**K: Lehet programozottan adatcímkéket hozzáadni?**  
V: Természetesen. Hívd a `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` metódust az értékek megjelenítéséhez.

**K: Mi a teendő, ha egy meglévő prezentációt kell frissíteni?**  
V: Töltsd be a fájlt a `new Presentation("existing.pptx")` segítségével, módosítsd a diagramot, majd mentsd vissza.

## Összegzés
Most már egy teljes, vég‑től‑végig útmutatóval rendelkezel arról, hogyan **add series to chart**, hogyan hozz létre egy **stacked column chart**-ot, és hogyan finomhangold megjelenését .NET prezentációkban az Aspose.Slides for Java segítségével. Kísérletezz különböző diagramtípusokkal, színekkel és adatforrásokkal, hogy meggyőző vizuális jelentéseket készíts, amelyek lenyűgözik az érintetteket.

---

**Utolsó frissítés:** 2026-01-17  
**Tesztelve ezzel:** Aspose.Slides for Java 25.4 (jdk16)  
**Szerző:** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
