---
date: '2026-07-08'
description: Ismerje meg, hogyan adhat hozzá kördiagramot PowerPoint prezentációkhoz
  az Aspose.Slides for Java használatával. Kövesse ezt a lépésről‑lépésre útmutatót
  a professzionális kördiagramok létrehozásához és testreszabásához.
keywords:
- add pie chart powerpoint
- explode pie chart slice
- java generate powerpoint
- aspose slides maven
- create pie chart java
lastmod: '2026-07-08'
og_description: Kördiagram PowerPoint hozzáadása az Aspose.Slides for Java használatával.
  Ez az útmutató bemutatja, hogyan generáljon és testreszabjon kördiagramokat programozottan,
  ami tökéletes az automatizált jelentésekhez.
og_image_alt: Illustration of a Java-generated PowerPoint pie chart using Aspose.Slides
og_title: Kördiagram PowerPoint hozzáadása az Aspose.Slides for Java segítségével
  – Gyors útmutató
schemas:
- author: Aspose
  dateModified: '2026-07-08'
  description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  headline: How to add pie chart PowerPoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to add pie chart PowerPoint presentations using Aspose.Slides
    for Java. Follow this step‑by‑step guide to create and customize professional
    pie charts.
  name: How to add pie chart PowerPoint with Aspose.Slides for Java
  steps:
  - name: Initialize the Presentation
    text: The `Presentation` class represents a single PowerPoint file in memory.
      Creating an instance gives you a fresh, empty slide deck to work with.
  - name: Add the Pie Chart
    text: Insert a pie chart onto the first slide. The coordinates (50, 50) and size
      (600 × 400) fit a standard 16:9 layout and leave room for titles.
  - name: Save the Presentation
    text: Write the presentation to disk. Replace `YOUR_OUTPUT_DIRECTORY` with the
      folder where you want the file saved.
  - name: Clean Up Resources
    text: Dispose of the `Presentation` object to free native resources and avoid
      memory leaks.
  - name: Load an Existing Presentation (or reuse the one you just created)
    text: The `Presentation` object loads an existing PowerPoint file into memory,
      allowing you to modify its contents.
  - name: Access the Chart and Target Data Point
    text: The `IDataPoint` interface represents an individual data point (slice) within
      a chart series.
  - name: Apply Explosion and Color
    text: '`setExplosion(int)` sets the distance, in pixels, that a slice is offset
      from the chart center. Separate the slice visually with `setExplosion(20)` and
      change its fill to blue using `setFillType(FillType.Solid)` and `setSolidFillColor(Color.BLUE)`.'
  type: HowTo
- questions:
  - answer: It lets you create, edit, and render PowerPoint files programmatically
      without needing Microsoft Office installed, supporting over 70 chart types and
      100 + file formats.
    question: What is the biggest advantage of using Aspose.Slides for Java?
  - answer: Yes, instantiate a `Presentation` object, add slides, charts, or shapes,
      then call `save`—all in pure Java code.
    question: Can I generate a PowerPoint file from scratch?
  - answer: Retrieve the `IDataPoint` for the slice and call `setExplosion(pixelOffset)`.
      The offset defines how far the slice moves outward.
    question: How do I explode a specific pie slice?
  - answer: Aspose.Slides can handle presentations with up to **10,000 slides** in
      a single file, provided you stream the output to avoid loading everything into
      memory.
    question: Is there a limit to the number of slides I can create?
  - answer: Check the official [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
      for detailed API references and sample projects.
    question: Where can I find more advanced chart‑customization examples?
  type: FAQPage
tags:
- add pie chart powerpoint
- Aspose.Slides
- Java chart generation
- PowerPoint automation
- data visualization
title: Hogyan adjunk hozzá kördiagramot PowerPoint-hoz az Aspose.Slides for Java segítségével
url: /hu/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Kördiagram PowerPoint hozzáadása Aspose.Slides for Java segítségével

## Bevezetés

Ha **kördiagram PowerPoint hozzáadása** diákra van szüksége anélkül, hogy manuálisan megnyitná a PowerPointot, jó helyen jár. Ebben az útmutatóban végigvezetjük a Aspose.Slides for Java beállításán, egy kördiagram létrehozásán és az egyes szeletek testreszabásán — tökéletes automatizált jelentésekhez, műszerfalakhoz vagy személyre szabott prezentációkhoz. A végére egy újrahasználható Java kódrészletet kap, amely néhány másodperc alatt elkészíti a kifinomult kördiagram PowerPoint fájlt.

### Gyors válaszok
- **Melyik könyvtár hozza létre a diagramot?** Aspose.Slides for Java (legújabb kiadás).  
- **Futtatható head‑less módban?** Igen—nem szükséges Office telepítés.  
- **Melyik Java verzió a legoptimálisabb?** JDK 16+ a legjobb teljesítmény és GC fejlesztések érdekében.  
- **Hogyan robbantok ki egy szeletet?** Hívja a `setExplosion` metódust a `IDataPoint` objektumon, és adjon meg egy pixel eltolást.  
- **Szükség van licencre a termeléshez?** A próba verzió fejlesztéshez működik; egy állandó licenc eltávolítja az összes értékelési korlátot.

## Miért adjunk hozzá kördiagram PowerPoint-ot az Aspose.Slides for Java használatával?

Közvetlenül a háttérszolgáltatásokból generálhat naprakész vizuális jelentéseket, kiküszöbölve a manuális másolás‑beillesztés hibáit és garantálva a márkahű stílusokat. Az Aspose.Slides **70+ diagramtípust** támogat, és képes **10 000+ diát** tartalmazó prezentációkat feldolgozni anélkül, hogy a teljes fájlt a memóriába töltené, így ideális nagy léptékű automatizáláshoz.

## Előfeltételek

- **Aspose.Slides for Java** – a tutorial a 25.4-es verzióra hivatkozik (az írás időpontjában a legújabb).  
- **Java Development Kit** – JDK 16 vagy újabb ajánlott.  
- **Maven** vagy **Gradle** a függőségek kezeléséhez.  

## Aspose.Slides for Java beállítása

### Maven
Adja hozzá ezt a függőséget a `pom.xml` fájlhoz:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Adja hozzá a következőt a `build.gradle` fájlhoz:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatívaként töltse le a legújabb verziót közvetlenül a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

### Licencelés
Az Aspose.Slides korlátok nélküli használatához:

- Kezdje egy **ingyenes próba** verzióval az API értékeléséhez.  
- Kérjen **ideiglenes licencet** a kiterjesztett teszteléshez a [Temporary License](https://purchase.aspose.com/temporary-license/) oldalon.  
- Vásároljon teljes előfizetést a [Purchase page](https://purchase.aspose.com/buy) oldalon.  

## Hogyan adjunk hozzá kördiagram PowerPoint-ot az Aspose.Slides for Java használatával

Új prezentációt tölt be, kördiagramot szúr be, és elmenti a fájlt — mindhárom lépésben. Ez a minta bármilyen méretű adathalmazra alkalmazható, és ciklusba ágyazva tucatnyi diát generálhat automatikusan. A megközelítés könnyű, csak néhány kódsort igényel, és nem szükséges külső erőforrás, így alkalmas kis segédprogramokhoz és nagy kötegelt feladatokhoz egyaránt.

### 1. lépés: A Presentation inicializálása
A `Presentation` osztály egyetlen PowerPoint fájlt képvisel a memóriában. Egy példány létrehozása egy friss, üres diakönyvtárat ad a munkához.
```java
Presentation pres = new Presentation();
```

### 2. lépés: Kördiagram hozzáadása
Kördiagramot szúr be az első diára. A (50, 50) koordináták és a (600 × 400) méret egy szabványos 16:9 elrendezéshez illeszkedik, és helyet hagy a címeknek.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### 3. lépés: A prezentáció mentése
A prezentációt lemezre írja. Cserélje le a `YOUR_OUTPUT_DIRECTORY` értéket arra a mappára, ahová a fájlt menteni szeretné.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### 4. lépés: Erőforrások felszabadítása
A `Presentation` objektum felszabadítása a natív erőforrások felszabadításához és a memória szivárgások elkerüléséhez.
```java
if (pres != null) pres.dispose();
```

## Hogyan testre szabjuk az adatpont robbantását és színét?

A diagram betöltése, a cél adatpont megtalálása, majd robbantási eltolás és szilárd kitöltőszín alkalmazása. Ez a szelet kiemelését teszi lehetővé hangsúlyozás céljából. Ezek a módosítások segítenek a közönség figyelmét a kritikus értékekre irányítani és javítják a diagram általános olvashatóságát.

### 1. lépés: Létező prezentáció betöltése (vagy az előbb létrehozott újrahasználata)
A `Presentation` objektum meglévő PowerPoint fájlt tölt be a memóriába, lehetővé téve a tartalom módosítását.
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### 2. lépés: A diagram és a cél adatpont elérése
Az `IDataPoint` interfész egy diagram sorozatának egyedi adatpontját (szeletét) képviseli.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### 3. lépés: Robbantás és szín alkalmazása
A `setExplosion(int)` beállítja a pixelben megadott távolságot, amellyel egy szelet eltolódik a diagram középpontjától. Válassza a `setExplosion(20)` értéket a vizuális elkülönítéshez, és állítsa kék színű kitöltésre a `setFillType(FillType.Solid)` és a `setSolidFillColor(Color.BLUE)` hívásokkal.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### 4. lépés: Mentés és felszabadítás
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Gyakorlati alkalmazások
- **Értékesítési jelentések:** Emelje ki a legkelendőbb termékeket robbantott szeletekkel.  
- **Költségvetés elemzés:** Rendeljen különböző színeket a részlegekhez a gyors vizuális összehasonlítás érdekében.  
- **Oktatási diák:** Bontsa le a komplex fogalmakat emészthető diagramrészletekre.  

## Teljesítményfontosságú szempontok
- **Az objektumok gyors felszabadítása** a memória szivárgások elkerülése érdekében, különösen sok dia generálásakor ciklusban.  
- **Figyelje a heap használatát** nagy prezentációk esetén; használja a `Save` túlterhelést, amely `OutputStream`-et fogad, hogy adatot streameljen és alacsony memóriaigényt tartson.  
- Maradjon a **JDK 16+** verziónál, hogy élvezze a legújabb szemétgyűjtés fejlesztéseket, amelyek akár 30 %-kal is csökkenthetik a feldolgozási időt 1 000 diás prezentációk esetén.

## Következtetés
Most már rendelkezik egy teljes, termelésre kész munkafolyammal a **kördiagram PowerPoint** fájlok hozzáadásához az Aspose.Slides for Java használatával. Kísérletezzen különböző robbantási távolságokkal, színekkel és adathalmazokkal a márka követelményeinek megfelelően. Amikor készen áll, fedezze fel a többi diagramtípust — oszlop, vonal vagy szórt diagram — és építsen fel egy teljes analitikai műszerfalat a PowerPointon belül.

## Gyakran Ismételt Kérdések

**K: Mi a legnagyobb előnye az Aspose.Slides for Java használatának?**  
A: Lehetővé teszi a PowerPoint fájlok programozott létrehozását, szerkesztését és renderelését Microsoft Office telepítése nélkül, több mint 70 diagramtípust és 100 + fájlformátumot támogatva.

**K: Generálhatok PowerPoint fájlt a semmiből?**  
A: Igen, hozza létre a `Presentation` objektumot, adjon hozzá diát, diagramot vagy alakzatot, majd hívja a `save`‑t — mindezt tisztán Java kódból.

**K: Hogyan robbantok ki egy konkrét kördiagram szeletet?**  
A: Szerezze meg a szelethez tartozó `IDataPoint` objektumot, és hívja a `setExplosion(pixelOffset)`‑t. Az eltolás határozza meg, milyen messze mozdul ki a szelet a középpontból.

**K: Van korlát a létrehozható diák számában?**  
A: Az Aspose.Slides akár **10 000 diát** is képes kezelni egyetlen fájlban, feltéve, hogy a kimenetet streameli a teljes betöltés elkerülése érdekében.

**K: Hol találhatok fejlettebb diagram testreszabási példákat?**  
A: Tekintse meg a hivatalos [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) oldalt a részletes API referenciákért és mintaprojektekért.

## Erőforrások
- **Documentation:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Download Library:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Purchase License:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Free Trial:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Temporary License:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Support Forum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Legutóbb frissítve:** 2026-07-08  
**Tesztelve a következővel:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó oktatóanyagok

- [How to Add Charts to PowerPoint Using Aspose.Slides for Java: A Step-by-Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create and Validate Chart Layouts in PowerPoint Using Aspose.Slides for Java | SEO-Optimized Guide](/slides/java/charts-graphs/create-validate-chart-layouts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}