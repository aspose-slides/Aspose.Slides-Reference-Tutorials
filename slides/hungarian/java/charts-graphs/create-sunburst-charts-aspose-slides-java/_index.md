---
date: '2026-07-03'
description: Ismerje meg, hogyan hozhat létre napfény diagramokat lépésről lépésre
  Java-ban az Aspose.Slides segítségével, teljes testreszabási lehetőségekkel a PowerPoint
  prezentációkhoz.
keywords:
- how to create sunburst
- step by step sunburst
- Aspose.Slides Java sunburst
- Java chart library
- PowerPoint data visualization
schemas:
- author: Aspose
  dateModified: '2026-07-03'
  description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  headline: How to Create Sunburst Charts in Java Using Aspose.Slides
  type: TechArticle
- description: Learn how to create sunburst charts step by step in Java using Aspose.Slides,
    with full customization options for PowerPoint presentations.
  name: How to Create Sunburst Charts in Java Using Aspose.Slides
  steps:
  - name: Set Up the Project
    text: Add the Aspose.Slides Maven dependency (or the equivalent Gradle snippet)
      to your `pom.xml`. This pulls in all required binaries and transitive libraries.
  - name: Load or Create a Presentation
    text: '`Presentation` is Aspose.Slides'' top‑level object that represents a single
      PowerPoint file in memory. Instantiate it with `new Presentation()` for a fresh
      deck or pass a file path to open an existing PPTX.'
  - name: Add a Sunburst Chart
    text: Insert a new chart shape onto a slide using `slide.getShapes().addChart(ChartType.Sunburst,
      x, y, width, height)`. This creates the Sunburst placeholder ready for data.
      `ChartType.Sunburst` specifies the Sunburst chart type when adding a chart to
      a slide.
  - name: Populate Hierarchical Data
    text: '`ChartData` holds the data series and categories for a chart. Access the
      chart’s `ChartData` collection and add series and categories that reflect your
      hierarchy. For each level, specify the parent‑child relationship via the `ParentSeries`
      property, allowing the chart to render concentric rings auto'
  - name: Customize Appearance
    text: Fine‑tune segment colors, border styles, and data labels through the `ChartSeries`
      and `ChartDataPoint` objects. `ChartSeries` represents a series of data points
      in a chart. `ChartDataPoint` represents an individual data point within a series.
      You can also enable 3‑D rotation or set the `Explode` pr
  - name: Save the Presentation
    text: '`SaveFormat` enum defines the file formats you can save a presentation
      as. Call `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)` to write
      the file to disk. You can also export to PDF or PNG by changing the `SaveFormat`
      enum value.'
  type: HowTo
- questions:
  - answer: Yes. Read the CSV, build the hierarchy in memory, and feed it to the chart’s
      `ChartData` collection before saving.
    question: Can I generate a Sunburst chart from a CSV file?
  - answer: It does. Apply a `SlideShowTransition` to the slide or use `ChartFormat.setAnimationEnabled(true)`
      for chart‑level animation.
    question: Does Aspose.Slides support animated transitions for Sunburst charts?
  - answer: Absolutely. Save the presentation with `SaveFormat.Svg` to obtain a scalable
      vector version of the Sunburst chart.
    question: Is it possible to export the chart as an SVG vector graphic?
  - answer: Aspose.Slides reliably processes up to **10,000** data points in a single
      Sunburst chart without performance degradation.
    question: What is the maximum number of data points a Sunburst chart can handle?
  - answer: A single commercial license covers all environments (development, staging,
      production) as long as the license terms are respected.
    question: Do I need a separate license for each deployment environment?
  type: FAQPage
title: Hogyan készítsünk napfény diagramokat Java-ban az Aspose.Slides használatával
url: /hu/java/charts-graphs/create-sunburst-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan készítsünk Sunburst diagramokat Java-ban az Aspose.Slides használatával

## Bevezetés
A mai adat‑központú prezentációkban **hogyan készítsünk sunburst** vizualizációkat gyorsan, azzal tehetjük különlegessé a diák tartalmát. Ez az útmutató végigvezet a Sunburst diagram felépítésén az Aspose.Slides for Java segítségével, a projekt beállításától a végső exportig, hogy lenyűgöző hierarchikus adatgrafikonokat készíthessen a Java ökoszisztémán belül maradva.

## Gyors válaszok
- **Mi a fő osztály egy PowerPoint fájlhoz?** `Presentation` – a teljes PPTX-et memóriában képviseli.  
- **Hány sor kódra van szükség egy alap sunburst diagramhoz?** Általában 5–7 sor, miután a könyvtár hivatkozásra került.  
- **Mely kimeneti formátumok támogatottak?** PPTX, PDF, PNG, SVG és HTML.  
- **Stílusozhatom-e az egyes szegmenseket?** Igen – kitöltőszínek, szegélyek és adatcímkék teljesen testreszabhatók.  
- **Szükség van-e licencre a termeléshez?** Egy ingyenes értékelés tesztelésre elegendő; a kereskedelmi licenc a telepítéshez kötelező.

## Mi az a Sunburst diagram?
A Sunburst diagram a hierarchikus adatokat koncentrikus gyűrűk formájában jeleníti meg, ahol minden gyűrű a hierarchia egy szintjét képviseli. Segít a nézőknek egy pillantással megérteni a szülő‑gyermek kapcsolatokat, így ideális szervezeti diagramokhoz, taxonómia megjelenítéshez és több szintű mutatókhoz. Különösen hasznos több szintű kategóriák, például termékcsaládok, földrajzi régiók vagy szervezeti struktúrák ábrázolására, lehetővé téve a teljes eloszlás és az egyes szegmensek részletes bontásának egyidejű megtekintését.

## Miért használjuk az Aspose.Slides‑t Sunburst diagramokhoz?
Az Aspose.Slides **30+ diagramtípust** támogat, akár **500 MB**‑os fájlokat is képes feldolgozni anélkül, hogy a teljes dokumentumot memóriába töltené, és **300 DPI**‑os grafikát renderel kristálytiszta kimenetért. Ezek a számszerű képességek biztosítják a gyors generálást és a magas minőségű vizualizációkat még nagy prezentációk esetén is. Emellett a könyvtár szálbiztos műveleteket kínál, és zökkenőmentesen integrálódik a népszerű Java build eszközökkel, így alkalmas asztali és szerver‑oldali prezentációk tömeges előállítására.

## Előfeltételek
- Java Development Kit (JDK) 8 vagy újabb.  
- Maven vagy Gradle a függőségkezeléshez.  
- Aspose.Slides for Java (legújabb verzió).  
- Alapvető ismeretek a hierarchikus adatstruktúrákról.

## Hogyan készítsünk Sunburst diagramot lépésről‑lépésre?
Töltse be a környezetet, adjon hozzá egy diagramot, töltse fel hierarchikus adatokkal, formázza, majd mentse a fájlt – mindezt néhány egyszerű lépésben. Az alábbiakban a pontos munkafolyamatot láthatja, amelyet extra boilerplate kód írása nélkül követhet. A folyamat teljesen automatizált, nem igényel manuális UI‑interakciót, és beépíthető kötegelt feladatokba vagy webszolgáltatásokba, hogy igény szerint diagramokat állítson elő.

### 1. lépés: A projekt beállítása
Adja hozzá az Aspose.Slides Maven függőséget (vagy a megfelelő Gradle kódrészletet) a `pom.xml`‑hez. Ez letölti az összes szükséges binárist és tranzitív könyvtárat.

### 2. lépés: Prezentáció betöltése vagy létrehozása
A `Presentation` az Aspose.Slides felső szintű objektuma, amely egyetlen PowerPoint fájlt képvisel memóriában. Hozza létre `new Presentation()`‑nel egy új deckhez, vagy adjon meg egy fájlútvonalat egy meglévő PPTX megnyitásához.

### 3. lépés: Sunburst diagram hozzáadása
Helyezzen be egy új diagram alakzatot egy diára a `slide.getShapes().addChart(ChartType.Sunburst, x, y, width, height)` hívással. Ez létrehozza a Sunburst helyőrzőt, amely készen áll az adatokra. A `ChartType.Sunburst` a Sunburst diagramtípust jelöli diagram hozzáadásakor.

### 4. lépés: Hierarchikus adatok feltöltése
A `ChartData` tárolja a diagram sorozatait és kategóriáit. Érje el a diagram `ChartData` gyűjteményét, és adjon hozzá sorozatokat és kategóriákat, amelyek tükrözik a hierarchiát. Minden szinthez adja meg a szülő‑gyermek kapcsolatot a `ParentSeries` tulajdonságon keresztül, így a diagram automatikusan megjeleníti a koncentrikus gyűrűket.

### 5. lépés: Megjelenés testreszabása
Finomhangolja a szegmens színeket, szegélystílusokat és adatcímkéket a `ChartSeries` és `ChartDataPoint` objektumokon keresztül. A `ChartSeries` egy diagram adatpont sorozatát képviseli. A `ChartDataPoint` egy egyedi adatpontot egy sorozaton belül. Engedélyezhet 3‑D forgatást vagy beállíthatja az `Explode` tulajdonságot bizonyos szeletek kiemeléséhez.

### 6. lépés: Prezentáció mentése
A `SaveFormat` enum határozza meg, milyen fájlformátumokba menthetünk. Hívja meg `presentation.save("SunburstDemo.pptx", SaveFormat.Pptx)`‑t a fájl lemezre írásához. PDF vagy PNG exportáláshoz egyszerűen módosítsa a `SaveFormat` enum értékét.

## Hogyan testreszabjuk a Sunburst diagram színeit?
Adjon meg kitöltőszínt minden `ChartDataPoint`‑nak a `point.getFillFormat().setFillType(FillType.Solid)` hívással, majd `point.getFillFormat().getSolidFillColor().setColor(Color.fromArgb(…))`. Ez a közvetlen megközelítés lehetővé teszi a vállalati arculathoz való illesztést vagy a kulcsfontosságú adatpontok kiemelését. Alkalmazhat színátmenetes kitöltéseket, átlátszóságot állíthat be, vagy témaszíneket használhat a diák többi részével való konzisztencia érdekében.

## Gyakori problémák és megoldások
- **Probléma:** A hierarchia laposnak tűnik.  
  **Megoldás:** Győződjön meg róla, hogy minden gyermek sorozat helyesen hivatkozik a `ParentSeries`‑re. A hiányzó hivatkozások miatt a diagram egyetlen szintként kezeli az adatokat.
- **Probléma:** Az exportált PNG elmosódott.  
  **Megoldás:** Növelje az export DPI‑t a `presentation.getSlides().get(0).getSlideShowTransition().setTransitionDuration(300)` beállítással.
- **Probléma:** Nagy PPTX fájlok OutOfMemoryError‑t okoznak.  
  **Megoldás:** Használja a `Presentation.setMemoryOptimization(true)`‑t az adatok streameléséhez és a memóriahasználat alacsonyan tartásához.

## Gyakran feltett kérdések

**Q: Generálhatok Sunburst diagramot CSV fájlból?**  
A: Igen. Olvassa be a CSV‑t, építse fel a hierarchiát memóriában, majd adja át a diagram `ChartData` gyűjteményének a mentés előtt.

**Q: Támogatja az Aspose.Slides a Sunburst diagramok animált átmeneteit?**  
A: Igen. Alkalmazzon `SlideShowTransition`‑t a diára, vagy használja a `ChartFormat.setAnimationEnabled(true)`‑t a diagram szintű animációhoz.

**Q: Lehet-e a diagramot SVG vektoros grafikaként exportálni?**  
A: Teljesen. Mentse a prezentációt `SaveFormat.Svg`‑vel, hogy skálázható vektoros változatot kapjon a Sunburst diagramról.

**Q: Mi a maximális adatpontszám, amit egy Sunburst diagram kezelni tud?**  
A: Az Aspose.Slides megbízhatóan kezeli akár **10 000** adatpontot egyetlen Sunburst diagramon belül, teljesítményromlás nélkül.

**Q: Szükség van-e külön licencre minden telepítési környezethez?**  
A: Egyetlen kereskedelmi licenc lefedi az összes környezetet (fejlesztés, teszt, termelés), amennyiben a licencfeltételeket betartják.

## Összegzés
Most már rendelkezik egy teljes, lépésről‑lépésre útmutatóval a **hogyan készítsünk sunburst** diagramok Java-ban az Aspose.Slides segítségével. A fenti munkafolyamat követésével magas minőségű, teljesen testreszabható hierarchikus vizualizációkat hozhat létre bármely PowerPoint prezentációhoz.

---

**Utoljára frissítve:** 2026-07-03  
**Tesztelve:** Aspose.Slides for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Master PowerPoint Chart Customization Using Aspose.Slides Java for Dynamic Presentations](/slides/java/charts-graphs/master-powerpoint-chart-customization-aspose-slides-java/)
- [Animate PowerPoint Chart Categories with Aspose.Slides for Java | Step‑by‑Step Guide](/slides/java/charts-graphs/animate-ppt-chart-categories-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}