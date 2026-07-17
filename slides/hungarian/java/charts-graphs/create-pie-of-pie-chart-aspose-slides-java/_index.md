---
date: '2026-07-17'
description: Ismerje meg, hogyan adhat diagramot a PowerPointhoz egy Pie of Pie diagram
  létrehozásával az Aspose.Slides for Java használatával. Tartalmazza a beállítást,
  a kódot, a testreszabást és a PPTX formátumba mentést.
keywords:
- add chart to powerpoint
- how to create pie
- create pie of pie
- save presentation as pptx
- customize pie chart labels
lastmod: '2026-07-17'
og_description: Diagram hozzáadása a PowerPointhoz az Aspose.Slides for Java segítségével.
  Ez az útmutató megmutatja, hogyan hozhat létre, testreszabhat és menthet egy Pie
  of Pie diagramot PPTX formátumban percek alatt.
og_image_alt: 'Guide: add chart to PowerPoint using Aspose.Slides Java'
og_title: Diagram hozzáadása a PowerPointhoz – Pie of Pie diagram létrehozása Java-ban
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  headline: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  type: TechArticle
- description: Learn how to add chart to PowerPoint by creating a Pie of Pie chart
    using Aspose.Slides for Java. Includes setup, code, customization, and saving
    as PPTX.
  name: Add Chart to PowerPoint – Create a Pie of Pie Chart in Java with Aspose.Slides
  steps:
  - name: Create an Instance of the Presentation Class
    text: This initializes the container for all subsequent slides and charts.
  - name: Add a 'Pie of Pie' Chart on the First Slide
    text: Here we specify `ChartType.PieOfPie` and define the chart’s position (X,
      Y) and size (width, height) on the slide canvas.
  - name: Set Data Labels to Show Values for the Series
    text: Enabling `showValue` makes each slice display its numeric value, which is
      essential for quick data interpretation.
  - name: Configure the Second Pie Size and Split by Percentage
    text: These options let you decide how much of the chart is allocated to the secondary
      pie and which slices are moved based on a percentage threshold.
  - name: Save the Presentation to Disk in PPTX Format
    text: '> **Pro tip:** Use an absolute path or Java’s `Paths.get()` to avoid platform‑specific
      separators.'
  type: HowTo
- questions:
  - answer: Yes, instantiate a new `IChart` for each slide or location; the API allows
      unlimited chart objects per file.
    question: Can I generate multiple charts in a single presentation?
  - answer: Absolutely – call `presentation.save("output.pdf", SaveFormat.Pdf)` to
      export the same slide deck to PDF.
    question: Does Aspose.Slides support saving as PDF as well?
  - answer: The library supports up to **10,000** data points per series, limited
      only by available memory.
    question: What is the maximum number of data points a Pie of Pie chart can handle?
  - answer: Yes, access each `IPortion` via `chart.getChartData().getSeries().get_Item(0).getPortions()`
      and set `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))`.
    question: Is it possible to customize the colors of individual slices?
  - answer: 'After saving the file, stream it directly to the client using `HttpServletResponse`
      with `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation`.'
    question: How do I embed the generated PPTX into a web application?
  type: FAQPage
tags:
- add chart to powerpoint
- Aspose.Slides
- Java charting
- PPTX generation
title: Diagram hozzáadása a PowerPointhoz – Pie of Pie diagram létrehozása Java-ban
  az Aspose.Slides segítségével
url: /hu/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagram hozzáadása PowerPoint-hoz – Pie of Pie diagram létrehozása Java-val az Aspose.Slides segítségével

## Diagramok és grafikonok

### Bevezetés

A modern adat‑központú prezentációkban a **diagram hozzáadása PowerPoint-hoz** gyakran a leggyorsabb módja a nyers számok vizuális betekintéssé alakításának. Egy hagyományos kördiagram jól működik néhány kategória esetén, de ha néhány szelet nagyon kicsi, olvashatatlanná válik. Egy *Pie of Pie* diagram megoldja ezt a problémát, azáltal, hogy a kis szeleteket egy másodlagos körbe helyezi, így a fő diagram tiszta marad, a részletek pedig könnyen hozzáférhetők.

Ebben az oktatóanyagban megtanulja, hogyan **diagram hozzáadása PowerPoint-hoz** egy Pie of Pie diagram létrehozásával az Aspose.Slides for Java segítségével. Végigvezetjük a környezet beállításán, a diagram létrehozásán, a címkék testreszabásán, a felosztási pozíció finomhangolásán, és végül a prezentáció PPTX fájlba mentésén. A végére készen áll majd, hogy kifinomult diagramokat ágyazzon be bármely diakészletbe.

## Gyors válaszok
Az Aspose.Slides-ben a `Presentation` egy PPTX fájlt képvisel, a `ChartType.PieOfPie` a Pie of Pie diagramot választja, a `setShowValue(true)` megjeleníti az értékeket a címkéken, a `save` pedig írja a fájlt.

- **Mi a fő osztály a PowerPoint manipulációhoz?** `Presentation` – egy teljes PPTX fájlt képvisel a memóriában.  
- **Melyik diagramtípus hoz létre másodlagos kördiagramot a kis szeletekhez?** `ChartType.PieOfPie`.  
- **Hogyan jeleníti meg az értékeket minden szeletnél?** Állítsa be `chart.getChartData().getSeries().get_Item(0).getLabels().setShowValue(true)`.  
- **Mentheti a fájlt közvetlenül PPTX formátumban?** Igen – hívja meg `presentation.save("output.pptx", SaveFormat.Pptx)`.  
- **Szüksége van licencre a fejlesztéshez?** Egy ingyenes 30‑napos próba elegendő a teszteléshez; egy állandó licenc eltávolítja a kiértékelési vízjeleket.

## Mi az a Pie of Pie diagram?
A **Pie of Pie chart** egy két‑szintű körvizualizáció, amely egy vagy több kis szeletet egy külön, összekapcsolt körbe izolál, így könnyebben olvashatóvá válik. Az Aspose.Slides natívan támogatja ezt a diagramtípust, lehetővé téve a felosztási méret, a pozíció és a címkeformázás szabályozását.

## Miért adjunk diagramot PowerPoint-hoz az Aspose.Slides segítségével?
Az Aspose.Slides képes PowerPoint fájlok generálására, szerkesztésére és renderelésére Microsoft Office telepítése nélkül. **50+ bemeneti és kimeneti formátumot** támogat, **akár 500 diát** dolgoz fel kevesebb, mint egy másodperc alatt tipikus szerverhardveren, és **teljes API‑vezérlést** biztosít a diagram stílusához, adatcímkékhez és elrendezéshez – tökéletes automatizált jelentéskészítő csővezetékekhez.

## Előfeltételek

- **Java Development Kit (JDK) 16+** telepítve.  
- IDE, például **IntelliJ IDEA**, **Eclipse**, vagy **NetBeans**.  
- Maven vagy Gradle a függőségek kezeléséhez (lásd az alábbi szakaszokat).  
- Alapvető Java ismeretek és a projektek felépítésének ismerete.

## Aspose.Slides beállítása Java-hoz

### Telepítési információk

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

**Direct Download:** Letöltheti a legújabb verziót a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

### Licenc beszerzési lépések
- **Ingyenes próba:** Kezdje egy 30 napos próbaidőszakkal a funkciók kipróbálásához.  
- **Ideiglenes licenc:** Kérjen ideiglenes kulcsot a kiterjesztett értékeléshez.  
- **Vásárlás:** Szerezzen be egy állandó licencet a termeléshez, hogy eltávolítsa a kiértékelési vízjeleket.

### Alapvető inicializálás és beállítás
A `Presentation` a fő objektum PowerPoint fájlok létrehozásához, a `Chart` pedig egy diagram alakzatot képvisel egy dián.

```java
Presentation presentation = new Presentation();
```  

Ez egy üres prezentációt hoz létre, amely készen áll diákra és diagramokra.

## Megvalósítási útmutató

### Hogyan adhat hozzá diagramot PowerPoint-hoz az Aspose.Slides for Java használatával?

Töltsön be egy új `Presentation`‑t, adjon hozzá egy diát, és szúrjon be egy `Chart`‑ot `PieOfPie` típusúként. Az API híváslánc tömör: hozza létre a diagramot, töltse fel a sorozat adatokat, állítsa be a címke láthatóságát, konfigurálja a másodlagos kör méretét, majd mentse. Az egész folyamat általában kevesebb, mint 20 sor kódban fér el, így ideális automatizált jelentéskészítéshez.

### 'Pie of Pie' diagram létrehozása

#### Áttekintés
Egy Pie of Pie diagramot építünk az első diára, kiválasztjuk a legkisebb szeleteket, és minden szegmenst felcímkézünk a saját értékével.

#### 1. lépés: A Presentation osztály példányának létrehozása
```java
// Create a new presentation
ePresentation presentation = new Presentation();
```  
Ez inicializálja a tárolót az összes későbbi dia és diagram számára.

#### 2. lépés: 'Pie of Pie' diagram hozzáadása az első diára
```java
// Add a Pie of Pie chart to the first slide at position (50, 50) with size (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```  
Itt megadjuk a `ChartType.PieOfPie` típusát, és definiáljuk a diagram pozícióját (X, Y) és méretét (szélesség, magasság) a dia vásznán.

#### 3. lépés: Adatcímkék beállítása az értékek megjelenítéséhez a sorozatban
```java
// Configure data labels to display values
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```  
A `showValue` engedélyezése minden szeletnél megjeleníti a numerikus értéket, ami a gyors adatértelmezéshez elengedhetetlen.

#### 4. lépés: A másodlagos kör méretének és a százalékos felosztás beállítása
```java
// Set the size of the secondary pie
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Split the pie by percentage
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Set the split position
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```  
Ezek az opciók lehetővé teszik, hogy meghatározza, a diagram mekkora része kerül a másodlagos körbe, és mely szeletek kerülnek áthelyezésre egy százalékos küszöb alapján.

#### 5. lépés: A prezentáció mentése lemezre PPTX formátumban
```java
// Define output directory
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Save the presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\
```

> **Pro tip:** Használjon abszolút elérési utat vagy a Java `Paths.get()` metódusát a platform‑specifikus elválasztók elkerülése érdekében.

## Gyakori problémák és megoldások

A `License` osztály egy licencfájlt tölt be, hogy eltávolítsa a kiértékelési korlátozásokat.

- **Hiányzó licenc figyelmeztetés:** Ha a diagramon a „Evaluation Only” feliratot látja, győződjön meg róla, hogy egy érvényes licencfájlt alkalmazott a `License license = new License(); license.setLicense("Aspose.Slides.lic");` kóddal.
- **Helytelen szelet felosztás:** Ellenőrizze, hogy a `splitBy` tulajdonság `SplitBy.Percentage`‑ra van állítva, és a `secondPieSize` értéke 0 és 100 között van.
- **Adatok nem jelennek meg:** Győződjön meg róla, hogy a diagram sorozata legalább egy adatpontot tartalmaz; ellenkező esetben a diagram üres lesz.

## Gyakran feltett kérdések

Az `IChart` egy diagramobjektum, amely hozzáadható egy diához.

**Q: Létrehozhatok több diagramot egyetlen prezentációban?**  
A: Igen, minden diára vagy helyre hozhat létre egy új `IChart`‑ot; az API korlátlan számú diagramobjektumot engedélyez fájlonként.

A `SaveFormat.Pdf` a PDF kimeneti formátumot jelöli a mentéshez.

**Q: Az Aspose.Slides támogatja a PDF‑ként való mentést is?**  
A: Teljes mértékben – hívja meg `presentation.save("output.pdf", SaveFormat.Pdf)` a diakészlet PDF‑be exportálásához.

Az `IPortion` egy egyedi szeletet képvisel egy kördiagramon.

**Q: Mekkora a maximális adatpontszám, amelyet egy Pie of Pie diagram kezelni tud?**  
A: A könyvtár legfeljebb **10 000** adatpontot támogat sorozatonként, csak a rendelkezésre álló memória korlátozza.

**Q: Lehet-e testreszabni az egyes szeletek színeit?**  
A: Igen, minden `IPortion`‑t elérhet a `chart.getChartData().getSeries().get_Item(0).getPortions()` segítségével, és beállíthatja a `portion.getFillFormat().setSolidFillColor(Color.getRGB(...))` metódussal.

**Q: Hogyan ágyazhatom be a generált PPTX‑et egy webalkalmazásba?**  
A: A fájl mentése után közvetlenül streamelje a kliensnek a `HttpServletResponse` használatával, a `Content-Type: application/vnd.openxmlformats-officedocument.presentationml.presentation` fejléccel.

## Összegzés

Most már rendelkezik egy teljes, termelés‑kész recepttel a **diagram hozzáadása PowerPoint-hoz** egy Pie of Pie diagram létrehozásával az Aspose.Slides for Java segítségével. Kísérletezzen különböző felosztási küszöbökkel, címkeformátumokkal és színsémákkal, hogy megfeleljen a márka irányelveinek. Ezután fedezze fel a többi diagramtípust – például a halmozott oszlopot vagy a radart – hogy tovább gazdagítsa az automatizált diakészleteket.

---

**Last Updated:** 2026-07-17  
**Tested With:** Aspose.Slides for Java 24.12  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Dinamikus diagram létrehozása Java – PowerPoint diagramok oktatóanyagai az Aspose.Slides számára](/slides/java/charts-graphs/)
- [Hogyan adjunk hozzá kördiagramot PowerPoint-hoz az Aspose.Slides for Java használatával](/slides/java/charts-graphs/aspose-slides-java-create-pie-chart/)
- [Hogyan adjunk diagramokat PowerPoint-hoz az Aspose.Slides for Java használatával: Lépésről lépésre útmutató](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}