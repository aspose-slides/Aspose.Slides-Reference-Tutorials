---
date: '2026-09-02'
description: Ismerje meg, hogyan hozhat létre funnel chart-ot PowerPointban az Aspose.Slides
  for Java használatával. Ez a lépésről‑lépésre útmutató a chart data beállítását,
  a colors testreszabását és a presentation exportálását tárgyalja.
keywords:
- create funnel chart
- export powerpoint presentation
- how to create funnel
- how to customize colors
- java data visualization
lastmod: '2026-09-02'
og_description: Ismerje meg, hogyan hozhat létre funnel chart-ot PowerPointban az
  Aspose.Slides for Java segítségével. Ez az útmutató végigvezeti a data setup, a
  color customization és a final presentation exportálásán.
og_image_alt: Guide showing funnel chart creation in PowerPoint with Aspose.Slides
  for Java
og_title: Funnel chart létrehozása PowerPointban az Aspose.Slides for Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-09-02'
  description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  headline: Create funnel chart in PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create funnel chart in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step guide covers setting chart data, customizing colors,
    and exporting the presentation.
  name: Create funnel chart in PowerPoint with Aspose.Slides for Java
  steps:
  - name: '**Add the dependency** – Use the Maven or Gradle snippet above.'
    text: '**Add the dependency** – Use the Maven or Gradle snippet above.'
  - name: '**Obtain a license** –'
    text: '**Obtain a license** –'
  - name: '**Basic initialization** –'
    text: '**Basic initialization** –'
  type: HowTo
- questions:
  - answer: Set the `ChartOrientation` property on the `IChart` object to `ChartOrientation.Vertical`
      or `ChartOrientation.Horizontal`.
    question: How do I change the funnel chart’s orientation?
  - answer: Yes—call `pres.getSlides().get_Item(0).getThumbnail(1, 1)` and write the
      resulting `java.awt.image.BufferedImage` to a PNG or JPEG file.
    question: Can I export the slide as an image after adding the chart?
  - answer: Simply add additional categories using `chart.getChartData().getCategories().add(...)`
      and provide matching data points for each new category.
    question: What if I need more than three categories?
  - answer: Use `chart.getChartTitle().setVisible(false)` and `chart.getLegend().setVisible(false)`
      to remove both the title and legend from the visual.
    question: Is there a way to hide the legend?
  - answer: A temporary license is sufficient for evaluation; a full commercial license
      is required for production deployments.
    question: Do I need a license for development builds?
  type: FAQPage
tags:
- funnel chart
- Aspose.Slides
- Java data visualization
title: Funnel chart létrehozása PowerPointban az Aspose.Slides for Java segítségével
url: /hu/java/charts-graphs/create-funnel-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# A tölcsérdiagramok létrehozásának elsajátítása PowerPointban az Aspose.Slides for Java segítségével

## Bevezetés
A meggyőző prezentációk készítése egy olyan művészet, amely ötvözi az adatvizualizációt, a tervezést és a történetmesélést. Az egyik erőteljes vizuális elem, amely azonnal tisztáz egy többlépcsős folyamatot, a tölcsérdiagram. Akár egy értékesítési csővezeték, egy konverziós folyamat vagy egy termelési szűk keresztmetszet ábrázolására van szükséged, egy jól megtervezett tölcsérdiagram a nyers számokat intuitív narratívává alakítja. Ebben az útmutatóban megtanulod, hogyan **tölcsérdiagramot hozz létre** PowerPointban programozott módon az Aspose.Slides for Java használatával, hogyan konfiguráld az adatokat, testreszabd az egyes szeletek színét, és exportáld a kész prezentációt.

**Mit fogsz megtanulni**
- Hogyan add hozzá az Aspose.Slides for Java-t egy Maven vagy Gradle projekthez  
- Hogyan példányosíts egy `Presentation` objektumot, és érhesd el a diákját  
- Hogyan szúrj be egy tölcsérdiagramot, határozd meg a kategóriákat, és töltsd fel a sorozat adatokat  
- Hogyan formázd a tölcsér egyes szeleteit szilárd kitöltésekkel vagy márkaspecifikus színekkel  
- Hogyan mentsd el a prezentációt PPTX fájlként, vagy exportáld a diát képként  

## Gyors válaszok
- **Mi a fő könyvtár a java adatvizualizációhoz?** Aspose.Slides for Java.  
- **Hogyan hozol létre tölcsérdiagramot PowerPointban?** Hívd meg a `slide.addChart(ChartType.Funnel, …)` metódust a cél dián.  
- **Melyik API állítja be a diagram adatforrását?** Használd az `IChartDataWorkbook`-ot a `chart.getChartData()`-val együtt.  
- **Testreszabhatók a színek az egyes tölcsérszegmensekhez?** Igen – állítsd be a `FillFormat.setFillType(FillType.Solid)`-t, és rendelj hozzá egy `java.awt.Color`-t.  
- **Szükséges licenc a termelési használathoz?** Egy megvásárolt Aspose.Slides licenc szükséges a kereskedelmi telepítésekhez.  

## Mi az a Java adatvizualizáció?
A Java adatvizualizáció a nyers adatok diagramok, grafikonok vagy interaktív grafikák formájában történő átalakítását jelenti közvetlenül Java alkalmazásokból. Az Aspose.Slides for Java egy vezető könyvtár, amely lehetővé teszi a fejlesztők számára több mint 100 diagramtípus – köztük a tölcsérdiagramok – generálását anélkül, hogy manuálisan elindítanák a PowerPointot, támogatja akár 500 diát is, miközben alacsony memóriahasználatot biztosít.  

## Miért használjunk tölcsérdiagramokat PowerPointban?
A tölcsérdiagramok azonnal feltárják a lecsökkenési arányokat a szekvenciális szakaszok között, így ideálisak értékesítési csővezetékek, konverzióelemzések vagy folyamat hatékonysági áttekintések esetén. Az Aspose.Slides pixel‑pontos irányítást biztosít az elrendezés, a szegmensszínek és az adatcímkék felett, így fenntarthatod a márka konzisztenciáját, és elkerülheted a diagramok kézi szerkesztését a PowerPoint felhasználói felületén.  

## Előfeltételek

### Szükséges könyvtárak, verziók és függőségek
Az Aspose.Slides for Java projektedbe való beépítéséhez add hozzá a megfelelő Maven vagy Gradle koordinátákat. A könyvtár a Java 8‑21 verziókkal kompatibilis, és nem igényel külső natív függőségeket.

**Maven:**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

A JAR‑t közvetlenül letöltheted a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

### Környezet beállítási követelmények
Győződj meg róla, hogy JDK 8 vagy újabb van telepítve, és a `JAVA_HOME` a megfelelő JDK könyvtárra mutat. Az Aspose.Slides bármely, a JDK‑t támogató operációs rendszeren fut, beleértve a Windows, macOS és Linux platformokat.

### Tudás előfeltételek
Alapvető ismeretek a Java szintaxisról, az objektum‑orientált programozásról és a prezentációs fájlok koncepciójáról segítenek, de a kódrészletek minden fejlesztő számára részletesen magyarázva vannak, függetlenül a tapasztalattól.  

## Az Aspose.Slides for Java beállítása

1. **Add the dependency** – Használd a fentebb bemutatott Maven vagy Gradle kódrészletet.  
2. **Obtain a license** –  
   - **Free trial** – Tölts le egy ideiglenes licencet a [Aspose weboldaláról](https://purchase.aspose.com/temporary-license/) értékeléshez.  
   - **Full license** – Vásárolj termelési licencet a [vásárlási oldalon](https://purchase.aspose.com/buy).  
3. **Basic initialization** –  

A `Presentation` az Aspose.Slides központi osztálya, amely egy PowerPoint fájlt reprezentál a memóriában. Hozzáférést biztosít a diákhoz, alakzatokhoz és diagramobjektumokhoz.

```java
   import com.aspose.slides.Presentation;
   
   public class FunnelChartDemo {
       public static void main(String[] args) {
           Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
           try {
               // Your code here
           } finally {
               if (pres != null) pres.dispose();
           }
       }
   }
   ```

A fenti kód egy új `Presentation` példányt hoz létre, készen áll a dia manipulációra, és garantálja, hogy a `dispose()` hívásával az erőforrások felszabadulnak.  

## Megvalósítási útmutató

Áttekintjük a teljes tölcsérdiagram felépítéséhez szükséges minden funkciót, minden kódrészlet előtt rövid magyarázó szöveget adva.

### Feature 1: creating a presentation (H2)

#### Áttekintés
Kezdj egy `Presentation` osztálypéldánnyal. Ez az objektum a kiindulópont minden további művelethez.

A `Presentation` az Aspose.Slides felső szintű objektuma, amely a dia gyűjteményt és a globális dokumentumbeállításokat tartalmazza.

```java
import com.aspose.slides.Presentation;

// Create a new presentation
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Operations on the presentation object
} finally {
    if (pres != null) pres.dispose();
}
```

A kódrészlet egy üres prezentációt nyit meg, amelyet később `.pptx` fájlként menthetsz.  

### Feature 2: adding a funnel chart to a slide (H2)

#### Áttekintés
Helyezz el egy tölcsérdiagramot az első dián, határozd meg a méretét, és állítsd be a diagram típusát.

A `ChartType.Funnel` azt mondja az Aspose.Slides‑nek, hogy tölcsér‑stílusú vizualizációt jelenítsen meg a szokásos oszlop‑ vagy vonaldiagram helyett.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;

// Get the first slide
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    // Add a funnel chart to the first slide at position (50, 50) with width 500 and height 400
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
} finally {
    if (pres != null) pres.dispose();
}
```

Az `addChart` hívás létrehozza a diagram alakzatot, a `(50, 50)` pontban pozícionálja, és `500` szélességet, `400` magasságot ad neki.  

### Feature 3: clearing chart data (H2)

#### Áttekintés
Mielőtt feltöltenéd a diagramot, töröld a sablonban esetlegesen jelenlévő helyőrző kategóriákat vagy sorozatokat.

A `chart.getChartData().getCategories().clear()` eltávolítja az összes meglévő kategória bejegyzést, míg a `chart.getChartData().getSeries().clear()` törli az előre kitöltött sorozatokat.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

// Access the first slide's chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Clear all categories and series data
    chart.getChartData().getCategories().clear();
    chart.getChartData().getSeries().clear();
} finally {
    if (pres != null) pres.dispose();
}
```

Ez biztosítja a tiszta kiindulási állapotot, hogy a saját adataid pontosan úgy jelenjenek meg, ahogy szeretnéd.  

### Feature 4: setting up chart data workbook (H2)

#### Áttekintés
Az `IChartDataWorkbook` objektum tárolja a nyers értékeket, amelyek a diagramot vezérlik. Inicializálásával közvetlenül cellákba írhatsz adatokat.

Az `IChartDataWorkbook` egy könnyű, memóriában tárolt táblázat, amelyet az Aspose.Slides a diagram sorozatok és kategóriák feltöltésére használ.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Initialize a presentation and add a funnel chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    // Get the data workbook
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Clear all cells starting from cell index 0
    wb.clear(0);
} finally {
    if (pres != null) pres.dispose();
}
```

A kód törli a meglévő cellákat, felkészítve a munkafüzetet az új bejegyzésekre.  

### Feature 5: adding categories to a chart (H2)

#### Áttekintés
Határozd meg a bal oldalon megjelenő szöveges címkéket – ezek a folyamatod egyes szakaszait jelölik.

A `chart.getChartData().getCategories().add()` új kategóriaobjektumot hoz létre, amely egy konkrét munkafüzetcellához kapcsolódik.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.IChartDataWorkbook;

// Prepare presentation and chart with cleared data workbook
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    // Add categories to the chart
    chart.getChartData().getCategories().add(wb.getCell(0, "A1", "Category 1"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A2", "Category 2"));
    chart.getChartData().getCategories().add(wb.getCell(0, "A3", "Category 3"));
} finally {
    if (pres != null) pres.dispose();
}
```

Itt három szakaszt adunk hozzá: „Prospects”, „Qualified Leads” és „Closed Deals”.  

### Feature 6: adding data series to a chart (H2)

#### Áttekintés
Töltsd fel a tölcsért numerikus értékekkel, és opcionálisan rendelj egyedi színt minden szelethez.

Az `IDataPoint` egyetlen adatpontot képvisel egy diagram sorozaton belül.  

A `chart.getChartData().getSeries().add()` sorozatot hoz létre, amely a numerikus adatpontokat tartalmazza; minden `IDataPoint` saját kitöltőszínt kaphat.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.ChartType;
import com.aspose.slides.FillType;
import com.aspose.slides.IChartDataWorkbook;

// Add data series to the chart
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
try {
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Funnel, 50, 50, 500, 400);
    
    IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
    
    chart.getChartData().getSeries().clear(); // Clear any existing series
    
    // Add a new data series
    com.aspose.slides.ISeries series = chart.getChartData().getSeries().add(
        wb.getCell(0, "B1", "Series 1"), ChartType.Funnel);
    
    // Populate the series with data points
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B2", 50));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B3", 100));
    series.getDataPoints().addDataPointForFunnelChart(wb.getCell(0, "B4", 150));
    
    // Customize the fill color of data points
    for (int i = 0; i < series.getDataPoints().getCount(); i++) {
        com.aspose.slides.IDataPoint point = series.getDataPoints().get_Item(i);
        point.getFormat().getFill().setFillType(FillType.Solid);
        point.getFormat().getFill().getSolidFillColor().setColor(
            new java.awt.Color((int)(Math.random() * 0x1000000)));
    }
} finally {
    if (pres != null) pres.dispose();
}
```

A ciklus bemutatja, hogyan állíthatsz be szilárd kitöltést minden ponthoz, akár márkaspecifikus `java.awt.Color` konstansokkal, akár véletlenszerűen generált színekkel a változatosság kedvéért.  

## Gyakori felhasználási esetek és tippek

- **Értékesítési csővezeték jelentés** – Mutasd be, hány lead halad át a prospect szakasztól a lezárt‑nyert szintig minden lépésnél.  
- **Folyamat hatékonysági elemzés** – Vizualizáld az anyagveszteséget vagy az időbeli késéseket a gyártási lépések során.  
- **Marketing tölcsér áttekintés** – Hasonlítsd össze a konverziós arányokat kampányok vagy forgalmi források szerint.  

**Pro tipp:** A véletlenszerű színek helyett használd a vállalat márkapalettáját (pl. `new Color(0, 112, 192)`) a prezentáció egységes megjelenésének biztosításához.  

## Gyakran ismételt kérdések

**K: Hogyan változtathatom meg a tölcsérdiagram orientációját?**  
V: Állítsd be a `ChartOrientation` tulajdonságot az `IChart` objektumon `ChartOrientation.Vertical` vagy `ChartOrientation.Horizontal` értékre.

**K: Exportálhatom a diát képként a diagram hozzáadása után?**  
V: Igen – hívd meg a `pres.getSlides().get_Item(0).getThumbnail(1, 1)` metódust, és írd ki a kapott `java.awt.image.BufferedImage`‑t PNG vagy JPEG fájlba.

**K: Mit tegyek, ha több mint három kategóriára van szükségem?**  
V: Egyszerűen adj hozzá további kategóriákat a `chart.getChartData().getCategories().add(...)` segítségével, és biztosítsd a megfelelő adatpontokat minden új kategóriához.

**K: Van mód a jelmagyarázat elrejtésére?**  
V: Használd a `chart.getChartTitle().setVisible(false)` és a `chart.getLegend().setVisible(false)` hívásokat a cím és a jelmagyarázat eltávolításához.

**K: Szükséges licenc a fejlesztői buildhez?**  
V: Ideiglenes licenc elegendő az értékeléshez; a teljes kereskedelmi licenc a termelési környezetben kötelező.  

---

**Utoljára frissítve:** 2026-09-02  
**Tesztelve:** Aspose.Slides for Java 25.4 (jdk16)  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}