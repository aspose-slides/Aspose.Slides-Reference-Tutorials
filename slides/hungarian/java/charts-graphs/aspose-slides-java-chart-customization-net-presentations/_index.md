---
date: '2026-06-08'
description: Ismerje meg, hogyan adhat sorozatot a diagramhoz, és testreszabhatja
  a réteges oszlopdiagramokat .NET prezentációkban az Aspose.Slides for Java használatával.
keywords:
- add series to chart
- stacked column chart example
- populate chart data
- create empty presentation
- Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-06-08'
  description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  headline: Add Series to Chart with Aspose.Slides for Java in .NET
  type: TechArticle
- description: Learn how to add series to chart and customize stacked column charts
    in .NET presentations using Aspose.Slides for Java.
  name: Add Series to Chart with Aspose.Slides for Java in .NET
  steps:
  - name: Create an Empty Presentation
    text: '`Presentation` is the entry point class that represents a PowerPoint file
      in memory. *We start with a clean PPTX file, which gives us a canvas for adding
      charts.*'
  - name: Add a Stacked Column Chart to the Slide
    text: '`Chart` represents a chart shape within a slide. `ChartType.StackedColumn`
      specifies a stacked column chart. *The `addChart` method creates a **stacked
      column chart** and places it at the top‑left corner of the slide.*'
  - name: Add Series to the Chart (Primary Goal)
    text: '`Series` encapsulates a single data series in a chart. *Here we **add series
      to chart** – each call creates a new data series that will appear as a separate
      column group.*'
  - name: Add Categories to the Chart
    text: '`Category` defines an X‑axis label for chart data. *Categories act as the
      X‑axis labels, giving meaning to each column.*'
  - name: Populate Series Data
    text: '`DataPoint` holds a numeric value for a series at a specific category.
      *Data points give each series its numeric values, which the chart will render
      as bar heights.*'
  - name: Set Gap Width for Chart Series Group
    text: '`SeriesGroup` controls layout properties for a group of series, such as
      gap width. *Adjusting the gap width improves readability, especially when many
      categories are present.*'
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides supports line, pie, area, radar, bubble, and 50+ other
      chart types, all accessible through the same `addChart` method.
    question: Can I add other chart types besides stacked column?
  - answer: No, the same Java license works for all output formats, including .NET
      PPTX files.
    question: Do I need a separate license for .NET output?
  - answer: Use `series.getFormat().getFill().setFillType(FillType.Solid)` and then
      set the desired `Color` object for each series.
    question: How do I change the chart’s color palette?
  - answer: Absolutely. Call `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the numeric value on each column.
    question: Is it possible to add data labels programmatically?
  - answer: Load the file with `new Presentation("existing.pptx")`, modify the chart
      using the same API calls, and save it back to disk.
    question: What if I need to update an existing presentation?
  type: FAQPage
title: Sorozat hozzáadása diagramhoz az Aspose.Slides for Java segítségével .NET-ben
url: /hu/java/charts-graphs/aspose-slides-java-chart-customization-net-presentations/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# A diagram testreszabásának elsajátítása .NET prezentációkban az Aspose.Slides for Java segítségével

## Bevezetés
Adata‑vezérelt prezentációk világában a diagramok nélkülözhetetlen eszközök, amelyek a nyers számokat lebilincselő vizuális történetekké alakítják. Amikor programozottan kell **add series to chart** műveletet végrehajtani, különösen .NET prezentációs fájlokban, a feladat ijesztőnek tűnhet. Szerencsére a **Aspose.Slides for Java** egy erőteljes, nyelvfüggetlen API-t biztosít, amely egyszerűvé teszi a diagramok létrehozását és testreszabását – még akkor is, ha a célformátum egy .NET PPTX. Ez az útmutató végigvezet a sorok hozzáadásán, egy halmozott oszlopdiagram felépítésén, és a vizuális elemek, például a hézag szélességének finomhangolásán, hogy dinamikus, adat‑gazdag diák készülhessenek, amelyek kifinomultak és professzionálisak.

## Gyors válaszok
A `Presentation` osztály egy PPTX fájlt képvisel, és a `slide.getShapes().addChart(...)` egy diagram alakzatot szúr be. A `chart.getChartData().getSeries().add(...)` használatával lehet sorozatot hozzáadni, a `setGapWidth()` pedig a távolságot állítja be.

- **Mi a fő osztály egy prezentáció elindításához?** `Presentation` – egy PPTX fájlt képvisel a memóriában.  
- **Melyik metódus ad diagramot egy diára?** `slide.getShapes().addChart(...)` létrehozza a diagram objektumot a dián.  
- **Hogyan adsz hozzá egy új sorozatot?** `chart.getChartData().getSeries().add(...)` egy új adat sorozatot szúr be.  
- **Meg lehet változtatni az oszlopok közötti hézag szélességét?** Igen – hívd a `chart.getChartData().getSeriesGroups().get_Item(0).setGapWidth(50)` metódust (az érték százalékban van).  
- **Szükség van licencre a termeléshez?** Teljesen szükséges – egy érvényes Aspose.Slides for Java licenc feloldja az összes funkciót és eltávolítja a kiértékelési vízjeleket.

## Mi a „add series to chart”?
A sorozat hozzáadása egy diagramhoz azt jelenti, hogy egy új adatpont-gyűjteményt szúrunk be, amelyet a diagram különálló vizuális elemként (pl. külön oszlopcsoportként) jelenít meg. Minden sorozat saját értékekkel, színekkel és formázással rendelkezhet, lehetővé téve több adathalmaz oldalról‑oldalra történő összehasonlítását.

## Miért használjuk az Aspose.Slides for Java‑t .NET prezentációk módosításához?
Aspose.Slides for Java lehetővé teszi PPTX fájlok generálását vagy szerkesztését, amelyek teljes mértékben kompatibilisek a .NET PowerPoint nézőkkel, anélkül, hogy bármilyen Microsoft Office telepítésre lenne szükség. Használd az Aspose.Slides for Java‑t, ha szerver‑oldali, platform‑független megoldásra van szükséged, amely .NET PPTX fájlokat hoz létre vagy frissít, több mint 50 diagramtípust támogat, és akár 500 MB‑os fájlokat is feldolgoz anélkül, hogy a teljes dokumentumot a memóriába kellene tölteni. API-ja Java, Kotlin, Scala vagy bármely JVM nyelven működik, ugyanazt a kimenetet biztosítva, amelyet a .NET fejlesztők elvárnak.

## Előfeltételek
- **Aspose.Slides for Java** könyvtár (25.4 vagy újabb verzió).  
- Maven, Gradle vagy kézi JAR letöltés.  
- Alapvető Java ismeretek és a PPTX fájlstruktúra ismerete.  

## Az Aspose.Slides for Java beállítása
### Maven telepítés
Adja hozzá a következő függőséget a `pom.xml` fájlhoz:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle telepítés
Adja hozzá ezt a sort a `build.gradle` fájlhoz:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés
Alternatívaként töltse le a legújabb JAR‑t a hivatalos kiadási oldalról: [Aspose.Slides for Java kiadások](https://releases.aspose.com/slides/java/).

**Licenc beszerzése**  
Kezdje egy ingyenes próbaverzióval, ideiglenes licenc letöltésével innen: [itt](https://purchase.aspose.com/temporary-license/). Termelési használathoz vásároljon teljes licencet, amely feloldja az összes funkciót és eltávolítja a kiértékelési vízjeleket.

## Lépés‑ről‑lépésre megvalósítási útmutató
Az egyes lépések alatt egy tömör kódrészletet (az eredeti útmutatóból változatlanul) és egy magyarázatot találsz arról, hogy mit csinál.

### 1. lépés: Üres prezentáció létrehozása
`Presentation` az a belépő osztály, amely egy PowerPoint fájlt képvisel a memóriában.

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

### 2. lépés: Halmozott oszlopdiagram hozzáadása a diára
`Chart` egy diagram alakzatot képvisel egy dián belül. A `ChartType.StackedColumn` egy halmozott oszlopdiagramot határoz meg.

```java
// Import necessary Aspose.Slides classes
import com.aspose.slides.*;

// Add a chart of type StackedColumn
IChart chart = slide.getShapes().addChart(ChartType.StackedColumn, 0, 0, 500, 500);

// Save the presentation with the new chart
presentation.save("YOUR_OUTPUT_DIRECTORY/Chart_Added.pptx", SaveFormat.Pptx);
```  
*Az `addChart` metódus egy **halmozott oszlopdiagramot** hoz létre, és a dia bal‑felső sarkába helyezi.*

### 3. lépés: Sorozatok hozzáadása a diagramhoz (elsődleges cél)
`Series` egyetlen adat sorozatot foglal magába egy diagramon.

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
`Category` egy X‑tengely címkét definiál a diagram adataihoz.

```java
// Adding categories to the chart
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 1, 0, "Category 1"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 2, 0, "Category 2"));
chart.getChartData().getCategories().add(fact.getCell(defaultWorksheetIndex, 3, 0, "Category 3"));

// Save the presentation after adding categories
presentation.save("YOUR_OUTPUT_DIRECTORY/Categories_Added.pptx", SaveFormat.Pptx);
```  
*A kategóriák az X‑tengely címkéként működnek, értelmet adva minden oszlopnak.*

### 5. lépés: Sorozat adatok feltöltése
`DataPoint` egy numerikus értéket tárol egy sorozathoz egy adott kategóriában.

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
*Az adatpontok minden sorozathoz a numerikus értékeket adják, amelyeket a diagram oszlopmagasságként jelenít meg.*

### 6. lépés: Hézag szélességének beállítása a diagram sorozatcsoporthoz
`SeriesGroup` a sorozatcsoport elrendezési tulajdonságait szabályozza, például a hézag szélességét.

```java
// Setting the gap width between bars
series.getParentSeriesGroup().setGapWidth(50);

// Save the presentation after adjusting the gap width
presentation.save("YOUR_OUTPUT_DIRECTORY/Set_GapWidth.pptx", SaveFormat.Pptx);
```  
*A hézag szélességének módosítása javítja az olvashatóságot, különösen sok kategória esetén.*

## Gyakori felhasználási esetek
- **Pénzügyi jelentés** – negyedéves bevételek összehasonlítása az üzleti egységek között.  
- **Projekt irányítópultok** – feladatok teljesítési százalékának megjelenítése csapatonként.  
- **Marketing elemzés** – kampány teljesítményének oldalról‑oldalra történő megjelenítése.  

Ezek a forgatókönyvek a **halmozott oszlopdiagram példát** használják, mivel kiemelik az egyes kategóriák hozzájárulását az összeghez.

## Teljesítmény tippek
- **Használd újra a `Presentation` objektumot** több diagram létrehozásakor, hogy csökkentsd a memóriahasználatot.  
- **Korlátozd az adatpontok számát** csak a vizuális történethez szükséges mennyiségre; az Aspose.Slides 10 000 pontot képes kezelni, de a renderelési sebesség ~5 000 pont után csökken.  
- **Felszabadítsd az objektumokat** (`presentation.dispose()`) mentés után, hogy erőforrásokat szabadíts fel és elkerüld a memória szivárgásokat.  

## Gyakran ismételt kérdések
**Q: Hozzáadhatok más diagramtípusokat is a halmozott oszlopon kívül?**  
A: Igen, az Aspose.Slides támogatja a vonal, kör, terület, radar, buborék és 50+ egyéb diagramtípust, mindegyik elérhető ugyanazzal az `addChart` metódussal.

**Q: Szükség van külön licencre a .NET kimenethez?**  
A: Nem, ugyanaz a Java licenc működik minden kimeneti formátumhoz, beleértve a .NET PPTX fájlokat is.

**Q: Hogyan változtathatom meg a diagram színpalettáját?**  
A: Használd a `series.getFormat().getFill().setFillType(FillType.Solid)` metódust, majd állítsd be a kívánt `Color` objektumot minden sorozathoz.

**Q: Lehet programozottan adatcímkéket hozzáadni?**  
A: Teljesen lehetséges. Hívd a `series.getDataPoints().get_Item(j).getLabel().setShowValue(true)` metódust, hogy megjelenjen a numerikus érték minden oszlopon.

**Q: Mi a teendő, ha egy meglévő prezentációt kell frissíteni?**  
A: Töltsd be a fájlt a `new Presentation("existing.pptx")` segítségével, módosítsd a diagramot ugyanazokkal az API hívásokkal, majd mentsd vissza a lemezre.

## Összegzés
Most már egy teljes, vég‑től‑végig útmutatóval rendelkezel arról, hogyan **add series to chart**, hogyan hozz létre egy **halmozott oszlopdiagramot**, és hogyan finomhangold megjelenését .NET prezentációkban az Aspose.Slides for Java segítségével. Kísérletezz különböző diagramtípusokkal, színekkel és adatforrásokkal, hogy meggyőző vizuális jelentéseket készíts, amelyek lenyűgözik az érintetteket és elősegítik az adat‑vezérelt döntéseket.

---

**Legutóbb frissítve:** 2026-06-08  
**Tesztelve:** Aspose.Slides for Java 25.4 (JDK 16)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Hogyan hozzunk létre százalékos alapú halmozott oszlopdiagramokat .NET-ben az Aspose.Slides használatával](/slides/net/charts-graphs/create-stacked-column-charts-asposeslides-dotnet/)
- [Diagram sorozatok létrehozása és manipulálása az Aspose.Slides .NET segítségével a hatékony adatvizualizációért](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)
- [Specifikus diagram sorozat adatpontok törlése az Aspose.Slides .NET segítségével](/slides/net/additional-chart-features/clear-specific-chart-series-data-points-data/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}