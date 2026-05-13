---
date: '2026-02-19'
description: Tanulja meg, hogyan hozhat létre kördiagramot Java-ban az Aspose.Slides
  segítségével, testreszabhatja a kördiagram színeit, hozzáadhat diagram sorozatokat,
  dolgozhat a diagram adatlapjával, és beállíthatja a forgatási szöget.
keywords:
- Aspose.Slides Java
- Java pie charts
- data visualization in Java
title: Hogyan testre szabjuk a kördiagram színeit Java-ban az Aspose.Slides segítségével
  – Teljes útmutató
url: /hu/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/
weight: 1
---

 if needed" but Hungarian is LTR, ignore.

Now craft final answer.{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Pité diagramok létrehozása az Aspose.Slides for Java-val: Teljes útmutató

## Bevezetés
Dinamikus és vizuálisan vonzó prezentációk létrehozása kulcsfontosságú a hatásos információátadáshoz. Az Aspose.Slides for Java-val zökkenőmentesen integrálhatsz összetett diagramokat, például pité diagramokat a diáidba, **testreszabhatod a pité diagram színeit**, és könnyedén javíthatod az adatok megjelenítését. Ez az átfogó útmutató végigvezet a pité diagram létrehozásának és testreszabásának folyamatán az Aspose.Slides Java segítségével, megoldva a gyakori prezentációs kihívásokat egyszerűen.

**Mit fogsz megtanulni:**
- Prezentáció inicializálása és diák hozzáadása.
- Pité diagram létrehozása és konfigurálása a diádon.
- Diagramcímek, adatcímkék beállítása, és **a pité diagram színeinek testreszabása**.
- Teljesítmény optimalizálása és erőforrások hatékony kezelése.
- Az Aspose.Slides integrálása Java projektekbe Maven vagy Gradle használatával.

Kezdjük azzal, hogy biztosítjuk, hogy minden szükséges eszköz és tudás rendelkezésedre álljon!

## Gyors válaszok
- **Mi a fő osztály egy prezentáció elindításához?** `Presentation` from `com.aspose.slides`.
- **Melyik metódus ad hozzá egy pité diagramot a diára?** `addChart(ChartType.Pie, …)`.
- **Hogyan engedélyezed a változatos színeket minden szelethez?** Set `setColorVaried(true)` on the series group.
- **Forgatható a pité diagram?** Yes, use `setRotationAngle(double)` on the chart object.
- **Szükség van licencre a termelésben való használathoz?** An Aspose.Slides license is required for commercial deployments.

## Mi az a „customize pie chart colors”?
A pité diagram színeinek testreszabása azt jelenti, hogy minden szeletnek különféle kitöltőszíneket rendelsz, ezáltal javítva az olvashatóságot és a vizuális hatást. Az Aspose.Slides-ben ezt úgy érheted el, hogy engedélyezed a változatos színeket, majd egyedi szilárd kitöltőszíneket állítasz be az egyes adatpontokhoz.

## Miért használjuk az Aspose.Slides for Java-t pité diagramok létrehozásához?
- **Full control** over chart appearance without needing Microsoft Office.
- **Cross‑platform** compatibility – works on Windows, Linux, and macOS.
- **Rich API** for data binding, styling, and exporting to PPTX, PDF, or images.
- **License flexibility** – start with a free trial and upgrade when you need the full feature set.

## Előkövetelmények
Mielőtt belemerülnél ebbe az útmutatóba, győződj meg róla, hogy a következő környezet készen áll:

### Szükséges könyvtárak, verziók és függőségek
- **Aspose.Slides for Java**: version 25.4 or later.
- **Java Development Kit (JDK)**: version 16 or higher.

### Környezet beállítási követelmények
- Fejlesztői környezet Java-val telepítve és konfigurálva.
- Egy integrált fejlesztőkörnyezet (IDE), például IntelliJ IDEA, Eclipse vagy NetBeans.

### Tudás előkövetelmények
- Alapvető Java programozási ismeretek.
- Ismeret a Maven vagy Gradle függőségkezelésről.

## Az Aspose.Slides for Java beállítása
Az Aspose.Slides használatához a Java projektjeidben hozzá kell adnod a könyvtárat függőségként. Íme, hogyan teheted ezt különböző build eszközökkel:

**Maven**  
Add this snippet to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**  
Include the following in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download**  
If you prefer not using a build tool, download the latest release from [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licenc beszerzési lépések
- **Ingyenes próba**: Kezd egy ingyenes próbával az Aspose.Slides funkcióinak felfedezéséhez.  
- **Ideiglenes licenc**: Szerezz ideiglenes licencet korlátlan használathoz.  
- **Vásárlás**: Fontold meg a vásárlást, ha hosszú távú hozzáférésre van szükséged.

**Basic Initialization and Setup**  
To begin using Aspose.Slides, initialize your project by creating a new presentation object:
```java
import com.aspose.slides.*;

Presentation presentation = new Presentation();
```

## Megvalósítási útmutató
Most bontsuk le a pité diagram hozzáadásának és testreszabásának folyamatát kezelhető lépésekre.

### Prezentáció és dia inicializálása
Start by setting up a new presentation and accessing the first slide. This is your canvas for creating charts:
```java
import com.aspose.slides.*;

// Create a new presentation instance.
Presentation presentation = new Presentation();
// Access the first slide in the presentation.
ISlide slide = presentation.getSlides().get_Item(0);
```

### Pité diagram hozzáadása a diához
Insert a pie chart into the specified position with a default data set:
```java
import com.aspose.slides.*;

// Add a pie chart at position (100, 100) with size (400, 400).
IChart chart = slide.getShapes().addChart(ChartType.Pie, 100, 100, 400, 400);
```

### Diagram címének beállítása
Customize your chart by setting and centering the title:
```java
import com.aspose.slides.*;

// Add a title to the pie chart.
chart.getChartTitle().addTextFrameForOverriding("Sample Title");
chart.getChartTitle().getTextFrameForOverriding().getTextFrameFormat().setCenterText(NullableBool.True);
chart.getChartTitle().setHeight(20);
chart.setTitle(true);
```

### Adatcímkék beállítása a sorozathoz
Ensure that data labels display values for clarity:
```java
import com.aspose.slides.*;

// Show data values on the first series.
chart.getChartData().getSeries().get_Item(0).getLabels().getDefaultDataLabelFormat().setShowValue(true);
```

### Diagram adat munkalap előkészítése
Set up your chart's data worksheet by clearing existing series and categories:
```java
import com.aspose.slides.*;

// Prepare the chart data workbook.
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
```

### Kategóriák hozzáadása a diagramhoz
Define categories for your pie chart:
```java
import com.aspose.slides.*;

// Add new categories.
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "First Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "2nd Qtr"));
chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "3rd Qtr"));
```

### Sorozat hozzáadása és adatpontok feltöltése
Create a series and populate it with data points – this is where we **add chart series**:
```java
import com.aspose.slides.*;

// Add a new series and set its name.
IChartSeries series = chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 1, 1, 20));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 50));
series.getDataPoints().addDataPointForPieSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 30));
```

### Sorozat színeinek és szegélyeinek testreszabása
Enhance visual appeal by setting colors and customizing borders – this directly **customizes pie chart colors**:
```java
import com.aspose.slides.*;

// Set varied colors for the series sectors.
chart.getChartData().getSeriesGroups().get_Item(0).setColorVaried(true);

IChartDataPoint point = series.getDataPoints().get_Item(0);
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.Cyan));
point.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
point.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
point.getFormat().getLine().setWidth(3.0);
point.getFormat().getLine().setStyle(LineStyle.ThinThick);
point.getFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Repeat for other data points with different colors and styles.
```

### Egyedi adatcímkék konfigurálása
Fine‑tune the labels for each data point:
```java
import com.aspose.slides.*;

// Configure custom labels.
IDataLabel lbl1 = series.getDataPoints().get_Item(0).getLabel();
lbl1.getDataLabelFormat().setShowValue(true);

IDataLabel lbl2 = series.getDataPoints().get_Item(1).getLabel();
lbl2.getDataLabelFormat().setShowValue(true);
lbl2.getDataLabelFormat().setShowLegendKey(true);
lbl2.getDataLabelFormat().setShowPercentage(true);

IDataLabel lbl3 = series.getDataPoints().get_Item(2).getLabel();
lbl3.getDataLabelFormat().setShowSeriesName(true);
lbl3.getDataLabelFormat().setShowPercentage(true);

// Enable leader lines for labels.
series.getLabels().getDefaultDataLabelFormat().setShowLeaderLines(true);
```

### Forgatási szög beállítása és a prezentáció mentése
Finalize your pie chart by **set rotation angle** and saving the file:
```java
import com.aspose.slides.*;

// Set rotation angle.
chart.getPlotArea().getPieChartTitle().getTextFrameForOverriding().setText("Sales Data");
chart.setRotationAngle(-10);

// Save the presentation to a file.
presentation.save("PieChartPresentation.pptx", SaveFormat.Pptx);
```

## Gyakori problémák és megoldások
| Issue | Cause | Fix |
|-------|-------|-----|
| **Minden szelet ugyanazt a színt kap** | `setColorVaried(true)` nem lett meghívva | Győződj meg arról, hogy a sorozatcsoporton engedélyezed a változatos színeket. |
| **Az adatcímkék nem jelennek meg** | `showValue` jelző letiltva | `setShowValue(true)` hívása a megfelelő címkeformátumon. |
| **A forgatás nem hat** | Régebbi Aspose.Slides verzió használata | Frissíts a 25.4 vagy újabb verzióra. |
| **Licenc kivétel futás közben** | Hiányzó vagy érvénytelen licencfájl | Töltsd be a licencet a `License license = new License(); license.setLicense("Aspose.Slides.lic");` kóddal a `Presentation` létrehozása előtt. |

## Gyakran Ismételt Kérdések

**Q: Hogyan szerezhetek be egy Aspose.Slides licencet Java-hoz?**  
A: Kérhetsz ingyenes próbát az Aspose weboldaláról, majd vásárolhatsz állandó licencet. Töltsd be futás közben, ahogy a Gyakori problémák táblázatában látható.

**Q: Használhatom ezt a kódot régebbi JDK verziókkal?**  
A: Az API JDK 16 vagy újabb verziót igényel; a régebbi verziók nem támogatottak.

**Q: Lehetséges a diagramot képként exportálni PPTX helyett?**  
A: Igen, hívd a `chart.getChartData().getChartDataWorkbook().save("chart.png", ImageFormat.Png);` metódust a renderelés után.

**Q: Mi van, ha több mint egy sorozatot kell hozzáadni egy pité diagramhoz?**  
A: A pité diagramok általában egyetlen sorozatot jelenítenek meg; több sorozat esetén fontold meg a gyűrűdiagram (doughnut) használatát.

**Q: Működik a könyvtár Linux szervereken?**  
A: Teljes mértékben – az Aspose.Slides for Java platform‑független, és bármely, kompatibilis JDK-val rendelkező operációs rendszeren fut.

**Last Updated:** 2026-02-19  
**Tested With:** Aspose.Slides for Java 25.4 (jdk16)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}