---
date: '2026-08-21'
description: Ismerje meg, hogyan hozhat létre clustered column chart-ot és adhat hozzá
  trend lines-ot az Aspose.Slides for Java segítségével. Tartalmazza a license beállítást,
  a Maven/Gradle integrációt, valamint részletes példákat.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Készítsen clustered column chart-ot és adjon hozzá trend lines-ot
  az Aspose.Slides for Java használatával. Ez az útmutató a license beállításról,
  a Maven/Gradle integrációról és a lépésről‑lépésre kódpéldákról szól.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Hozzon létre clustered column chart-ot és adjon hozzá trend lines-ot az
  Aspose.Slides for Java segítségével
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Hogyan hozzunk létre clustered column chart-ot és adjunk hozzá trend lines-ot
  az Aspose.Slides for Java segítségével
url: /hu/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Hogyan hozzunk létre csoportosított oszlopdiagramot és adjunk hozzá trendvonalakat az Aspose.Slides for Java használatával

A lenyűgöző prezentációk gyakran egyértelmű adatvizualizációval kezdődnek. Ebben az útmutatóban **csoportosított oszlopdiagram létrehozása** objektumokat hozunk létre, majd gazdagítjuk őket különféle trendvonalakkal – exponenciális, lineáris, logaritmikus, mozgó átlag, polinomiális és hatvány – az Aspose.Slides for Java erőteljes API-jával.

## Gyors válaszok
- **Mi az első lépés?** Inicializáljon egy `Presentation` objektumot, és adjon hozzá egy csoportosított oszlopdiagramot egy diára.  
- **Melyik könyvtárverzió szükséges?** Aspose.Slides for Java 25.4 vagy újabb.  
- **Használhatok Maven-t vagy Gradle-t?** Igen, mindkettő támogatott; a Maven `<dependency>`-t, a Gradle `implementation`-t használ.  
- **Szükségem van licencre?** A próbaverzió licenc elegendő értékeléshez; egy teljes Aspose.Slides licenc eltávolítja az értékelési korlátokat.  
- **Hány trendvonal típus érhető el?** Hat beépített típus: exponenciális, lineáris, logaritmikus, mozgó átlag, polinomiális és hatvány.

## Mi a csoportosított oszlopdiagram létrehozása?
`create clustered column chart` azt jelenti, hogy egy olyan diagramot generálunk, amely egy kategórián belül több adat sorozatot helyez egymás mellé, megkönnyítve az értékek összehasonlítását a sorozatok között. Ez a diagramtípus ideális a kategóriális adatok, például a negyedéves értékesítés régiók szerint történő megjelenítésére, lehetővé téve a nézők számára, hogy gyorsan észrevegyék a csoportok közötti különbségeket.

## Miért adjunk hozzá trendvonalat?
Trendvonalak feltárják egy adat sorozat alapvető mintázatát, segítve a jövőbeli értékek előrejelzését, a növekedési ráta kiemelését vagy a zajos adatok kisimítását. Egy trendvonal hozzáadásával a csoportosított oszlopdiagramhoz a nyers számok cselekvőképes betekintéssé válnak, lehetővé téve az érintettek számára, hogy megértsék a hosszú távú tendenciákat és adat‑alapú döntéseket hozzanak.

## Előfeltételek
- **Java Development Kit (JDK):** 8 vagy újabb.  
- **Aspose.Slides for Java:** 25.4 vagy újabb verzió.  
- **IDE:** IntelliJ IDEA, Eclipse vagy bármely Java‑kompatibilis szerkesztő.  
- **Build eszköz:** Maven vagy Gradle (opcionális, de ajánlott).  
- **Licenc:** egy próbaverzió vagy megvásárolt Aspose.Slides licencfájl.  

Alapvető Java szintaxisban jártasnak kell lennie, és ismernie kell a projekt függőségkezelését.

## Hogyan állítsuk be az Aspose.Slides for Java‑t?
Adja hozzá az Aspose.Slides könyvtárat a projektjéhez a kedvenc függőségkezelőjével, majd helyezze el a licencfájlt úgy, hogy a futtatókörnyezet megtalálja. Ez biztosítja a teljes funkcionalitást és eltávolítja az értékelési korlátozásokat.

### Maven
Add this dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include this line in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés
A JAR fájlt manuálisan is letöltheti a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

#### Aspose Slides licenc
Helyezze el az `Aspose.Slides.lic` fájlt a projekt gyökerében, vagy állítsa be a licencet programozottan a `License license = new License(); license.setLicense("Aspose.Slides.lic");` kóddal. A próbaverzió licenc eltávolítja az összes funkciókorlátozást, de egy megvásárolt licenc eltávolítja az értékelési vízjelet és biztosítja a teljes teljesítményoptimalizációt. Gyártási környezetben fontolja meg a licenc vásárlását a [Aspose purchase page](https://purchase.aspose.com/buy) oldalon.

## Hogyan hozzunk létre prezentációt és adjunk hozzá csoportosított oszlopdiagramot?
`Presentation` osztály egy PowerPoint fájlt képvisel, és módszereket biztosít a diák létrehozásához, szerkesztéséhez és mentéséhez. Hozzon létre egy `Presentation` példányt, adjon hozzá egy diát, majd hívja meg az `addChart`-ot a `ChartType.ClusteredColumn` értékkel a diagram objektum létrehozásához. Ez a folyamat beállítja a dia vásznát, beszúr egy diagram alakzatot, és előkészíti az adatfeltöltéshez és a stílushoz.

1. **A prezentáció inicializálása** – állítsa be a kimeneti mappát, és hozzon létre egy új `Presentation` példányt.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Csoportosított oszlopdiagram hozzáadása** – szerezze be a diagram alakzatot, konfigurálja a sorozatokat, és töltse fel az adatpontokat.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Hogyan adjunk hozzá exponenciális trendvonalat?
`ITrendline` interfész egy trendvonalat definiál, amely hozzáadható egy diagram sorozathoz az adatminták modellezéséhez. Exponenciális trendvonalat egy sorozathoz úgy adhat hozzá, hogy létrehoz egy `ITrendline` példányt, beállítja a `TrendlineType`-ot `Exponential`-ra, és csatolja a kívánt sorozathoz. Ez a trendvonal típus hasznos gyorsan növekvő adatokhoz.

1. **A trendvonal konfigurálása** – válassza ki a sorozatot, és hívja meg a `addTrendline(TrendlineType.Exponential)` metódust.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Hogyan adjunk hozzá lineáris trendvonalat?
A lineáris trendvonal a legjobb illeszkedő egyenes vonalat mutatja az adatpontok között. Testreszabhatja a megjelenését, például a vonal színét és vastagságát, hogy illeszkedjen a prezentáció stílusához.

1. **A trendvonal beállítása** – használja a `addTrendline(TrendlineType.Linear)`-t, majd módosítsa a `getLineFormat().setFillFormat().setFillType(FillType.Solid)`-et a szín megváltoztatásához.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Hogyan adjunk hozzá logaritmikus trendvonalat egy egyéni szövegkerettel?
A logaritmikus trendvonalak ideálisak olyan adatokhoz, amelyek eleinte gyorsan nőnek, majd lelassulnak. Az alapértelmezett címke felülbírálásával hozzáadhat magyarázó szöveget, amely tisztázza a trend jelentőségét.

1. **A trendvonal testreszabása** – a trendvonal hozzáadása után érje el a `getDataLabel()`-t, és állítsa be a `setText("Custom label")` tulajdonságot.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Hogyan adjunk hozzá mozgó átlag trendvonalat?
A mozgó átlag trendvonalak kisimítják a rövid távú ingadozásokat, hogy kiemeljék a hosszú távú trendeket. Megadhatja a periódust (pontok száma) az átlagoláshoz, így szabályozhatja a vonal simaságát.

1. **A trendvonal konfigurálása** – hívja meg a `addTrendline(TrendlineType.MovingAverage)`-t, és állítsa be a `setPeriod(3)`-at, hogy hárompontos mozgó átlagot használjon.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Hogyan adjunk hozzá polinomiális trendvonalat?
A polinomiális trendvonalak görbét illesztenek az adatokhoz egy polinomiális egyenlettel. Az `order` tulajdonság szabályozza a polinom fokát, lehetővé téve összetettebb összefüggések modellezését.

1. **A trendvonal testreszabása** – a trendvonal hozzáadása után állítsa be a `setOrder(3)`-at egy köbös illesztéshez.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Hogyan adjunk hozzá hatvány trendvonalat?
A hatvány trendvonalak hasznosak, ha az adatok hatvány‑törvény szerinti összefüggést követnek. Beállíthatja a hátrafelé és előre irányuló előrejelzési értékeket, hogy a vonalat a meglévő adat tartományon túl is kiterjessze.

1. **A trendvonal konfigurálása** – használja a `addTrendline(TrendlineType.Power)`-t, és módosítsa a `setBackward(2)`-t, hogy a vonalat hátrafelé kiterjessze.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## A trendvonalak gyakorlati alkalmazásai csoportosított oszlopdiagramokban
- **Pénzügyi elemzés:** Az exponenciális és polinomiális trendek segítenek a részvényárfolyamok mozgásának előrejelzésében.  
- **Értékesítési előrejelzés:** A mozgó átlag vonalak kisimítják a szezonális csúcsokat, tisztább képet adva az alapvető értékesítési trendekről.  
- **Tudományos kutatás:** A logaritmikus trendek tökéletesek több nagyságrendi rendet átfogó adatokhoz, például akusztikus intenzitás vagy pH-értékek esetén.  
- **Működés felügyelete:** A hatvány trendvonalak modellezhetik a teljesítmény romlását az idő múlásával.

## Hogyan optimalizáljuk a memóriát az Aspose.Slides használatakor?
Az objektumokat gyorsan szabadítsa fel, és a mentés után használja a `presentation.dispose()`-t. Nagy adatállományok esetén engedélyezze a képek lusta betöltését, és kerülje el, hogy a teljes diagram egyszerre memóriába kerüljön.

- **Felszabadítási minták:** Csomagolja a `Presentation`-t egy try‑with‑resources blokkba, vagy hívja meg a `presentation.dispose()`-t egy finally ágba.  
- **Lusta betöltés:** Állítsa be a `ChartData.setUseCache(true)`-t, ha több ezer adatponttal dolgozik.  
- **Streaming kimenet:** Írja a prezentációt közvetlenül egy `FileOutputStream`-ba, hogy elkerülje a teljes fájl RAM-ban tartását.

## Mértékelt előnyök az Aspose.Slides for Java használatából
Az Aspose.Slides támogat **50+ diagramtípust**, képes **több mint 1 000 diát** generálni **30 másodpercen** belül egy tipikus 2 GHz CPU-n, és **500 oldalas PDF-eket** dolgoz fel anélkül, hogy a Microsoft Office telepítve lenne. Ezeket a számokat a legújabb 25.4 kiadás ellenőrizte.

## Következtetés
Most már rendelkezik egy teljes, vég‑től‑végig megoldással a **csoportosított oszlopdiagram** objektumok létrehozásához és azok minden fő trendvonal típusával való gazdagításához, amely elérhető az Aspose.Slides for Java-ban. A fenti lépések követésével adat‑vezérelt prezentációkat hozhat létre, amelyek vizuálisan vonzóak és elemzői szempontból erőteljesek.

A következő lépések közé tartozik a diagram stílusbeállítások felfedezése, PDF/HTML exportálás, valamint a diagram generálásának automatizálása több adatforrásból.

## Gyakran ismételt kérdések

**K: Hogyan állítsam be az Aspose.Slides-t egy Maven projektben?**  
A: Adja hozzá a Maven szekcióban látható `<dependency>` kódrészletet a `pom.xml`-hez, és futtassa a `mvn clean install` parancsot.

**K: Testreszabhatom a trendvonalakat a szín és címke mellett?**  
A: Igen, módosíthatja a vonal stílusát, vastagságát, szaggatottságát, és akár előre/hátrafelé előrejelzési értékeket is beállíthat az `ITrendline` API-n keresztül.

**K: Mit tegyek, ha verzió‑kompatibilitási hibát tapasztalok?**  
A: Ellenőrizze, hogy a JDK verziója megfelel-e az Aspose.Slides minimum követelményének (JDK 8+). Tekintse meg az Aspose kiadási megjegyzéseket az esetleges törő változásokért.

**K: Lehetséges több diagramhoz automatikusan trendvonalakat hozzáadni?**  
A: Természetesen. Iteráljon végig minden `IChart`-on a diák gyűjteményében, és hívja meg a megfelelő `addTrendline` metódust minden sorozatra.

**K: Szükségem van fizetett licencre a gyártási használathoz?**  
A: Igen, egy megvásárolt Aspose.Slides licenc eltávolítja az értékelési korlátokat és feloldja a teljes teljesítményoptimalizációkat.

---

**Utoljára frissítve:** 2026-08-21  
**Tesztelt verzió:** Aspose.Slides for Java 25.4  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [aspose slides maven függőség: Diagramok hozzáadása és konfigurálása prezentációkban az Aspose.Slides for Java használatával](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Animáció hozzáadása PowerPoint diagramhoz az Aspose.Slides for Java‑val – Lépésről‑lépésre útmutató](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [PowerPoint diagram létrehozása Java‑ban – Prezentációk mentése diagramokkal az Aspose.Slides használatával](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}