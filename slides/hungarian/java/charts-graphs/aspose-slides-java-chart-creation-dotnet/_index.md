---
date: '2026-06-03'
description: Ismerje meg, hogyan hozhat létre diagramokat .NET prezentációkban, és
  hogyan adhat hozzá diagramot egy diára az Aspose.Slides for Java segítségével. Kövesse
  ezt a lépésről‑lépésre útmutatót az adatvizualizációhoz.
keywords:
- create charts in .net
- generate chart in presentation
- add chart to slide
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  headline: Create charts in .NET using Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create charts in .NET presentations and add chart to slide
    with Aspose.Slides for Java. Follow this step‑by‑step guide for data visualization.
  name: Create charts in .NET using Aspose.Slides for Java
  steps:
  - name: Import Necessary Packages
    text: '`Presentation` and related classes are part of the `com.aspose.slides`
      namespace.'
  - name: Create a New Presentation Object
    text: Instantiate a `Presentation` object and wrap it in a try‑with‑resources
      block to guarantee disposal. *This ensures that the presentation object is properly
      disposed of after use, preventing memory leaks.*
  - name: Import Necessary Packages
    text: The `Chart` class represents a chart shape that can be placed on a slide
      and customized.
  - name: Initialize Presentation and Add Chart
    text: Create a slide, then call `addChart` with `ChartType.ClusteredColumn` and
      the desired position and size. *Here, we add a clustered column chart to the
      first slide at specified coordinates and dimensions.*
  - name: Import Necessary Packages
    text: '`IChartDataWorkbook` provides access to the underlying Excel‑like workbook
      used by charts.'
  - name: Access and Clear Data Workbook
    text: Retrieve the workbook from the chart and clear any existing data to start
      fresh. *Clearing the workbook is crucial for starting with a clean slate when
      adding new series and categories.*
  - name: Add Series and Categories
    text: Use `chart.getChartData().getSeries().add()` and `chart.getChartData().getCategories().add()`
      to define structure. *Adding series and categories allows for a more organized
      data presentation.*
  - name: Populate Series Data
    text: Assign numeric values to each cell in the workbook and apply a red fill
      for negative numbers. *This section demonstrates how to populate data and apply
      color formatting for better visualization.*
  type: HowTo
- questions:
  - answer: Yes, Aspose.Slides for Java is fully headless and works on servers without
      any graphical components.
    question: Can I generate a chart in presentation files without a GUI?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5, and .NET 6 are all supported.
    question: Which .NET versions are supported?
  - answer: Over 20 chart types are available, including column, line, pie, area,
      and radar charts.
    question: How many chart types can I add?
  - answer: Absolutely – you can set fill colors, borders, and markers for each data
      point via the `IDataPoint` API.
    question: Is it possible to style individual data points?
  - answer: No, the Aspose.Slides for Java .NET wrapper handles type conversion automatically.
    question: Do I need to convert Java objects to .NET types manually?
  type: FAQPage
title: Diagramok létrehozása .NET-ben az Aspose.Slides for Java használatával
url: /hu/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# .NET-ben diagramok létrehozása az Aspose.Slides for Java segítségével

## Bevezetés
Lenyűgöző prezentációk létrehozása gyakran magában foglalja a vizuális adatmegjelenítések, például diagramok integrálását, hogy javítsa a közönség megértését és elkötelezettségét. **Ha .NET-ben szeretnél diagramokat létrehozni**, az Aspose.Slides for Java egy erőteljes, nyelvfüggetlen API-t biztosít, amely zökkenőmentesen működik .NET alkalmazásokon belül. Ebben az útmutatóban megtanulod, hogyan inicializáld a prezentációt, adj hozzá különféle diagramtípusokat, kezeld a diagram adatkönyvtárát, és formázd a sorozat adatokat – beleértve a negatív értékek kezelését is. A végére programozottan képes leszel diagramot generálni a prezentációs fájlokban, és csak néhány sor kóddal diagramot hozzáadni a diára.

## Gyors válaszok
- **Mi a fő cél?** .NET prezentációkban diagramok létrehozása az Aspose.Slides for Java használatával.  
- **Melyik könyvtárverzió szükséges?** Aspose.Slides for Java 25.4 vagy újabb.  
- **Szükségem van licencre?** A ingyenes próba verzió fejlesztéshez megfelelő; a kereskedelmi licenc a termeléshez kötelező.  
- **Használhatok Maven‑t vagy Gradle‑t?** Igen – mindkét build rendszer támogatott.  
- **Milyen diagramtípusok érhetők el?** Csoportosított oszlop, vonal, kör, sáv, terület és továbbiak.

## Hogyan hozhatók létre diagramok .NET prezentációkban az Aspose.Slides for Java segítségével?
`Presentation` osztály egy PowerPoint fájlt képvisel, és módszereket biztosít a diák manipulálásához. Tölts be egy új `Presentation` objektumot, hívd a `slides.addEmptySlide()` metódust egy dia létrehozásához, majd használd a `slide.getShapes().addChart()`-ot a kívánt diagramtípus a megadott koordinátákon való beszúrásához. A diagram hozzáadása után töltsd fel az adatkönyvtárát sorozatokkal és kategóriákkal, alkalmazz bármilyen formázást (például színek a negatív értékekhez), és végül mentsd a prezentációt .pptx fájlba. Ez a folyamat lehetővé teszi, hogy **diagramokat hozz létre .NET‑ben** egy tömör API hívássorozattal.

## Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy platformfüggetlen API, amely lehetővé teszi a fejlesztők számára PowerPoint fájlok létrehozását, módosítását és renderelését a Microsoft Office nélkül. **50+ bemeneti és kimeneti formátumot** támogat, és képes több ezer diát tartalmazó prezentációkat feldolgozni, miközben a memóriahasználat 200 MB alatt marad.

## Miért használjuk az Aspose.Slides for Java‑t .NET projektben?
Az Aspose.Slides for Java a Java Virtual Machine-en fut, és .NET‑ből natív wrapperen keresztül hívható, így a .NET fejlesztők hozzáférnek egy kiforrott diagrammotorhoz, nagy adathalmazok nagy teljesítményű feldolgozásához, és teljes kompatibilitást kapnak a meglévő Java kóddal anélkül, hogy át kellene írniuk a logikát.

## Előfeltételek
Mielőtt elkezdenél diagramokat létrehozni az Aspose.Slides for Java‑val, tekintsük át, mire van szükséged:

### Szükséges könyvtárak és verziók
- **Aspose.Slides for Java**: 25.4 vagy újabb verzió.

### Környezet beállítási követelmények
- Egy .NET alkalmazásokat támogató fejlesztői környezet.  
- Alapvető Java programozási ismeretek.

### Tudás előfeltételek
- Ismeret a prezentációk létrehozásában .NET alkalmazási környezetben.  
- Java függőségek és azok kezelése (Maven/Gradle) megértése.

## Az Aspose.Slides for Java beállítása
Az Aspose.Slides használatához a projektedben függőségként kell felvenned. Íme, hogyan teheted ezt:

### Maven
A Maven függőségi kódrészlet hozzáadja az Aspose.Slides for Java‑t a projektedhez.

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Add ezt a sort a `build.gradle` fájlodba a könyvtár Maven Central‑ról való lekéréséhez.

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés
Alternatívaként letöltheted a legújabb verziót innen: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Licenc beszerzési lépések
- **Ingyenes próba**: Kezd egy ideiglenes licenccel a funkciók felfedezéséhez.  
- **Vásárlás**: Licenc vásárlása korlátlan termelési használathoz.

#### Alapvető inicializálás és beállítás
`Slides` inicializálásához a licenc beállítása és egy `Presentation` példány létrehozása szükséges.

```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

Ez a beállítás biztosítja, hogy az erőforrás-kezelés hatékonyan történjen.

## Megvalósítási útmutató
Lépésről lépésre végigvezetünk a funkciók megvalósításán.

### Prezentáció inicializálása
**Áttekintés:**  
Prezentáció példány létrehozása előkészíti a további műveleteket. Ez a funkció bemutatja, hogyan kezdjünk nulláról az Aspose.Slides használatával.

#### 1. lépés: Szükséges csomagok importálása
`Presentation` és a kapcsolódó osztályok a `com.aspose.slides` névtér részei.

```java
import com.aspose.slides.Presentation;
```

#### 2. lépés: Új Presentation objektum létrehozása
Példányosíts egy `Presentation` objektumot, és helyezd try‑with‑resources blokkba a garantált felszabadítás érdekében.

```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```

*Ez biztosítja, hogy a prezentáció objektum megfelelően felszabadul a használat után, elkerülve a memória szivárgásokat.*

### Diagram hozzáadása a diára
**Áttekintés:**  
Diagram hozzáadása a diádhoz hatékonyabbá és vonzóbbá teheti az adatmegjelenítést.

#### 1. lépés: Szükséges csomagok importálása
A `Chart` osztály egy diagram alakzatot képvisel, amely a diára helyezhető és testreszabható.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### 2. lépés: Prezentáció inicializálása és diagram hozzáadása
Hozz létre egy diát, majd hívd az `addChart` metódust a `ChartType.ClusteredColumn` és a kívánt pozíció és méret megadásával.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```

*Itt egy csoportosított oszlop diagramot adunk hozzá az első diához a megadott koordinátákon és méretekkel.*

### Diagram adatkönyvtár kezelése
**Áttekintés:**  
A diagram adatkönyvtárának hatékony kezelése lehetővé teszi a sorozatok és kategóriák zökkenőmentes manipulálását.

#### 1. lépés: Szükséges csomagok importálása
`IChartDataWorkbook` hozzáférést biztosít a diagramok által használt alapul szolgáló Excel‑szerű munkafüzethez.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### 2. lépés: Adatkönyvtár elérése és törlése
Szerezd meg a munkafüzetet a diagramról, és töröld a meglévő adatokat, hogy frissen kezdj.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```

*A munkafüzet törlése kulcsfontosságú, hogy tiszta lappal kezdj új sorozatok és kategóriák hozzáadásakor.*

### Sorozatok és kategóriák hozzáadása a diagramhoz
**Áttekintés:**  
Ez a funkció bemutatja, hogyan adhatsz hozzá értelmes adatpontokat sorozatok és kategóriák kezelése révén.

#### 1. lépés: Sorozatok és kategóriák hozzáadása
Használd a `chart.getChartData().getSeries().add()` és a `chart.getChartData().getCategories().add()` metódusokat a struktúra meghatározásához.

```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```

*Sorozatok és kategóriák hozzáadása lehetővé teszi a rendezettebb adatmegjelenítést.*

### Sorozat adatok feltöltése és formázása
**Áttekintés:**  
Töltsd fel a diagramot adatpontokkal, és formázd a megjelenést a jobb olvashatóság érdekében, különösen negatív értékek esetén.

#### 1. lépés: Sorozat adatok feltöltése
Rendelj számértékeket a munkafüzet minden cellájához, és alkalmazz piros kitöltést a negatív számokhoz.

```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

*Ez a rész bemutatja, hogyan töltsd fel az adatokat és alkalmazz színformázást a jobb vizualizáció érdekében.*

## Gyakori problémák és megoldások
- **LicenseNotFoundException** – Győződj meg róla, hogy a licencfájl útvonala helyes, és a fájl futásidőben elérhető.  
- **NullPointerException a diagram adatoknál** – Mindig töröld a munkafüzetet új sorozatok hozzáadása előtt, hogy elkerüld a maradék adatokat.  
- **Diagram nem jelenik meg .NET‑ben** – Ellenőrizd, hogy a Aspose.Slides JAR .NET kompatibilis verzióját használod, és a Java futtatókörnyezet megfelelően van konfigurálva a .NET projektedben.

## Gyakran feltett kérdések

**Q: Létrehozhatok diagramot prezentációs fájlokban GUI nélkül?**  
A: Igen, az Aspose.Slides for Java teljesen fej nélküli és szervereken működik grafikus komponensek nélkül.

**Q: Mely .NET verziók támogatottak?**  
A: A .NET Framework 4.5+, .NET Core 3.1+, .NET 5 és .NET 6 mind támogatott.

**Q: Hány diagramtípus adható hozzá?**  
A: Több mint 20 diagramtípus érhető el, beleértve az oszlop, vonal, kör, terület és radar diagramokat.

**Q: Lehet egyedi adatpontokat stílusozni?**  
A: Természetesen – a `IDataPoint` API-n keresztül beállíthatod a kitöltőszíneket, szegélyeket és jelölőket minden egyes adatponthoz.

**Q: Kézzel kell Java objektumokat .NET típusokra konvertálni?**  
A: Nem, az Aspose.Slides for Java .NET wrapper automatikusan kezeli a típuskonverziót.

---

**Legutóbbi frissítés:** 2026-06-03  
**Tesztelve:** Aspose.Slides for Java 25.4  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [Hogyan ágyazzunk be diagramokat .NET prezentációkba az Aspose.Slides segítségével a hatékony adatmegjelenítéshez](/slides/net/charts-graphs/embed-charts-net-presentations-aspose-slides/)
- [Hogyan nyerjünk ki diagram adatforrás típust az Aspose.Slides for .NET használatával – Diagramok és grafikonok](/slides/net/charts-graphs/retrieve-chart-data-source-aspose-slides-dotnet/)
- [Diagram sorozatok létrehozásának és manipulálásának mestersége az Aspose.Slides .NET segítségével a hatékony adatmegjelenítéshez](/slides/net/charts-graphs/create-manipulate-chart-series-aspose-slides-net/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}