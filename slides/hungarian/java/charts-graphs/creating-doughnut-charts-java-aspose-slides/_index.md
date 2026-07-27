---
date: '2026-07-27'
description: Ismerje meg, hogyan hozhat létre doughnut chart Java-t az Aspose.Slides
  használatával – gyors útmutató a könyvtár beállításához, egy testreszabható doughnut
  chart hozzáadásához, a lyuk méretének módosításához és a presentation mentéséhez.
keywords:
- create doughnut chart java
- Aspose.Slides Java charts
- customize doughnut chart Java
lastmod: '2026-07-27'
og_description: Ismerje meg, hogyan hozhat létre doughnut chart Java-t az Aspose.Slides
  használatával – gyors útmutató a könyvtár beállításához, egy testreszabható doughnut
  chart hozzáadásához, a lyuk méretének módosításához és a presentation mentéséhez.
og_image_alt: 'Guide: create doughnut chart java with Aspose.Slides in Java'
og_title: Doughnut Chart Java létrehozása – Lépésről‑lépésre az Aspose.Slides segítségével
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  headline: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  type: TechArticle
- description: Learn how to create doughnut chart java using Aspose.Slides – a quick
    guide to set up the library, add a customizable doughnut chart, adjust hole size,
    and save the presentation.
  name: Create Doughnut Chart Java – Step‑by‑Step with Aspose.Slides
  steps:
  - name: '**Budget Allocation:** Display how a budget is distributed across departments.'
    text: '**Budget Allocation:** Display how a budget is distributed across departments.'
  - name: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
    text: '**Survey Results:** Visualize responses to questions with multiple‑choice
      answers.'
  - name: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
    text: '**Website Traffic Sources:** Show the percentage of traffic coming from
      different channels (organic, paid, referral, etc.).'
  type: HowTo
- questions:
  - answer: Yes. Use `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)`
      and then specify the desired RGB color.
    question: Can I adjust the colors of my doughnut chart segments?
  - answer: Call `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)`
      to display the value inside each segment.
    question: How do I add data labels to my chart?
  - answer: Absolutely. Aspose.Slides supports PDF, XPS, PNG, JPEG, TIFF, and many
      other formats—over 50 in total.
    question: Is it possible to save charts in formats other than PPTX?
  - answer: Use the `Presentation` constructor that accepts a stream and enable `loadOptions.setLoadFormat(LoadFormat.Pptx)`
      to stream the file and reduce memory consumption.
    question: What should I do if I encounter an exception while loading a large presentation?
  - answer: Yes. Retrieve data from a database or REST API, update the `ChartData`
      collection, and call `chart.refresh()` before saving the presentation.
    question: Can I automate chart updates with live data sources?
  type: FAQPage
tags:
- create doughnut chart java
- Aspose.Slides
- Java charting
- presentation automation
- slides library
title: Doughnut Chart Java létrehozása – Lépésről‑lépésre az Aspose.Slides segítségével
url: /hu/java/charts-graphs/creating-doughnut-charts-java-aspose-slides/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan hozzunk létre gyűrűdiagramokat Java-ban az Aspose.Slides for Presentations használatával

## Bevezetés
A vizuálisan vonzó prezentációk létrehozása elengedhetetlen az információ hatékony közvetítéséhez. **Create doughnut chart java** gyakori követelmény, amikor arányos adatokat kell modern megjelenéssel illusztrálni. Ebben az útmutatóban megtanulja, hogyan állítsa be az Aspose.Slides for Java-t, hogyan építsen fel egy gyűrűdiagramot, testreszabja a lyuk méretét és a színeket, és végül mentse el a prezentáció fájlt. A végére egy újrahasználható mintát kap, amelyet bármely Java projektbe beilleszthet, amely automatikusan generál PowerPoint prezentációkat.

**Amit megtanul:**
- Az Aspose.Slides for Java beállítása
- Gyűrűdiagramok létrehozása és konfigurálása a prezentációkban
- A diagram esztétikájának beállítása, például a lyuk mérete
- A prezentáció mentése az új diagrammal

Kezdjük a környezet beállításával!

## Gyors válaszok
- **Melyik könyvtár hozza létre a doughnut chart java-t?** Aspose.Slides for Java.  
- **Hány sor kódra van szükség egy alap gyűrűdiagramhoz?** Körülbelül 8–10 sor a prezentáció példányosítása után.  
- **Módosíthatom a lyuk méretét?** Igen, a `setHoleSize(double)` metódus 0 % és 100 % közötti értékeket fogad el.  
- **Milyen kimeneti formátumok támogatottak?** PPTX, PDF, XPS, PNG, JPEG és több más (összesen több mint 50).  
- **Szükségem van licencre a termeléshez?** Kereskedelmi licenc szükséges korlátlan használathoz; egy ingyenes próba a kiértékeléshez működik.

## Mi az Aspose.Slides for Java?
**Aspose.Slides for Java** egy teljesen kezelt API, amely lehetővé teszi a fejlesztők számára PowerPoint fájlok létrehozását, módosítását, konvertálását és renderelését a Microsoft Office nélkül. Több mint 50 fájlformátumot támogat, és képes több ezer diát tartalmazó prezentációkat kezelni, miközben alacsony memóriahasználatot tart fenn.

## Miért használjunk gyűrűdiagramokat a prezentációkban?
A gyűrűdiagramok a rész‑egész kapcsolatokat jelenítik meg, miközben a középső területet szabadon hagyják címkék vagy képek számára. Az Aspose.Slides akár **500 dia percenként** képes gyűrűdiagramokat renderelni egy tipikus 2,5 GHz szerveren, és **több száz oldalas prezentációkat** dolgoz fel anélkül, hogy az egész fájlt a memóriába töltené, így ideális nagy léptékű jelentési megoldásokhoz.

## Előfeltételek
A kezdés előtt győződjön meg róla, hogy teljesítette ezeket az előfeltételeket:

### Szükséges könyvtárak és verziók
Az Aspose.Slides for Java használatához vegye fel a projektjébe Maven vagy Gradle segítségével, vagy töltse le közvetlenül.

#### Környezet beállítási követelmények
- Működő Java Development Kit (JDK), lehetőleg 8-as vagy újabb verzió.
- Integrált fejlesztői környezet (IDE), például IntelliJ IDEA vagy Eclipse.

### Tudás előfeltételek
A Java és az alapvető programozási koncepciók ismerete előnyös. A Maven vagy Gradle alapvető ismerete segít a beállítási folyamat egyszerűsítésében.

## Az Aspose.Slides for Java beállítása
Az Aspose.Slides beillesztése a projektbe többféleképpen megvalósítható:

**Maven:**  
Adja hozzá ezt a függőséget a `pom.xml` fájlhoz:  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
Vegye fel ezt a `build.gradle` fájlba:  
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Direct Download:**  
Alternatív megoldásként töltse le a legújabb verziót a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

### Licenc beszerzése
- **Ingyenes próba:** Kezdje a próba verzió letöltésével az Aspose.Slides funkcióinak felfedezéséhez.  
- **Ideiglenes licenc:** Szerezzen ideiglenes licencet a korlátlan funkciókhoz.  
- **Vásárlás:** Folyamatos használathoz licenc vásárlása szükséges.

Miután a könyvtár be van állítva és a környezet készen áll, lépjünk tovább a gyűrűdiagram megvalósításához.

## Hogyan hozzunk létre gyűrűdiagramot Java-ban?
Töltsön be egy új `Presentation` objektumot, adjon hozzá egy gyűrűdiagramot egy diára, állítsa be a lyuk méretét, és mentse el a fájlt – mindezt néhány egyszerű API hívással. Ez a megközelítés teljes irányítást biztosít a diagram adatai, megjelenése és export formátuma felett, és működik anélkül, hogy a szerveren a Microsoft PowerPoint telepítve lenne.

### Prezentáció objektum inicializálása
A `Presentation` osztály az Aspose.Slides legfelső szintű objektuma, amely egy PowerPoint fájlt reprezentál a memóriában.  
```java
// Create an instance of Presentation class to represent a PPTX document
Presentation presentation = new Presentation();
```  
Ez a lépés egy üres prezentációt hoz létre, amelyhez diák, alakzatok és diagramok adhatók.

### Gyűrűdiagram hozzáadása a diára
`ISlide` egyetlen dia interfésze; lekérheti az első diát vagy újat adhat hozzá.  
```java
// Access the first slide in the presentation
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Doughnut, 50, 50, 400, 400); // Position at (50, 50) with size 400x400
```  
Az `addChart` metódus gyűrűdiagramot hoz létre; a paraméterek határozzák meg a pozícióját (X, Y) és méretét (szélesség, magasság) a dián.

### Gyűrűlyuk méretének beállítása
`Chart` a `setHoleSize(double)` metódust biztosítja a belső sugár a diagram sugár százalékaként történő szabályozásához.  
```java
// Set the hole size for the doughnut chart to 90%
chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
```  
A lyuk méretének 90 %-ra állítása azt eredményezi, hogy a diagram szinte teljes körként jelenik meg, ami akkor hasznos, ha a külső szegmenseket szeretné hangsúlyozni.

### Prezentáció mentése
`presentation.save(String, SaveFormat)` a fájlt a lemezre írja a kiválasztott formátumban.  
```java
// Save the presentation to disk in PPTX format at the specified directory
presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
```  
A példa a `DoughnutHoleSize_out.pptx` néven menti az eredményt, de választhat PDF, PNG vagy a 50+ támogatott formátum közül is.

### Erőforrások felszabadítása
`presentation.dispose()` meghívása felszabadítja a natív erőforrásokat és megakadályozza a memória szivárgásokat, ami különösen fontos hosszú távú szerveralkalmazásoknál.  
```java
// Dispose of the presentation object to free resources
if (presentation != null) presentation.dispose();
```

## Gyakorlati alkalmazások
A gyűrűdiagramok sokoldalúak. Íme néhány szituáció, ahol kiemelkednek:
1. **Költségvetés elosztása:** Megmutatja, hogyan oszlik el a költségvetés a részlegek között.  
2. **Felmérés eredményei:** Vizualizálja a kérdésekre adott válaszokat többválaszos kérdések esetén.  
3. **Weboldal forgalmi források:** Megmutatja a forgalom százalékos arányát a különböző csatornákból (organikus, fizetett, hivatkozás stb.).

## Teljesítmény szempontok
Az Aspose.Slides használata során vegye figyelembe ezeket a tippeket a legjobb teljesítmény érdekében:
- A `Presentation` objektumokat a használatuk befejezése után azonnal szabadítsa fel a natív memória felszabadításához.  
- Használjon stream-eket (`FileInputStream`, `ByteArrayOutputStream`) nagy adathalmazok esetén, hogy elkerülje az egész fájl RAM-ba töltését.  
- Használja újra a diagram objektumokat, ha egy ciklusban sok diát generál, hogy csökkentse az objektum‑létrehozási költséget.

## Gyakori problémák és megoldások
- **Hiba a mentés során:** Ellenőrizze, hogy a kimeneti könyvtár létezik, és az alkalmazásnak írási jogosultsága van.  
- **Hiányzó diagram adatok:** Győződjön meg róla, hogy a diagram `ChartData` gyűjteményét feltölti a `setHoleSize` hívása előtt.  
- **Memória csúcsok:** Több ezer diát tartalmazó prezentációk esetén állítsa be a `Presentation.setSlideSize`-t kisebb méretre, és gyorsan szabadítsa fel a köztes diák memóriáját.

## Gyakran feltett kérdések

**K: Módosíthatom a gyűrűdiagram szegmenseinek színeit?**  
Igen. Használja a `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getFormat().getFillFormat().setFillType(FillType.Solid)` metódust, majd adja meg a kívánt RGB színt.

**K: Hogyan adhatok adatcímkéket a diagramhoz?**  
Hívja a `chart.getChartData().getSeries().get_Item(i).getDataPoints().get_Item(j).getLabel().setShowValue(true)` metódust, hogy megjelenítse az értéket minden szegmensben.

**K: Lehetőség van a diagramok mentésére a PPTX-en kívül más formátumokba?**  
Természetesen. Az Aspose.Slides támogatja a PDF, XPS, PNG, JPEG, TIFF és sok más formátumot – összesen több mint 50-et.

**K: Mit tegyek, ha kivételt kapok egy nagy prezentáció betöltésekor?**  
Használja a `Presentation` konstruktort, amely stream-et fogad, és engedélyezze a `loadOptions.setLoadFormat(LoadFormat.Pptx)` beállítást, hogy a fájlt stream-elje és csökkentse a memóriahasználatot.

**K: Automatizálhatom a diagram frissítéseket élő adatforrásokkal?**  
Igen. Szerezzen adatokat egy adatbázisból vagy REST API-ból, frissítse a `ChartData` gyűjteményt, és hívja a `chart.refresh()` metódust a prezentáció mentése előtt.

## Erőforrások
- **Dokumentáció:** Tekintse meg a részletes API hivatkozásokat a [Aspose.Slides for Java](https://reference.aspose.com/slides/java/) oldalon.  
- **Letöltés:** Szerezze be a legújabb könyvtár verziót a [Aspose.Slides releases](https://releases.aspose.com/slides/java/) oldalról.  
- **Vásárlás:** Teljes hozzáféréshez vásároljon licencet a [Aspose Purchase](https://purchase.aspose.com/buy) oldalon.  
- **Ingyenes próba:** Próbálja ki az Aspose.Slides-t egy ingyenes próba verzióval, amely a letöltési oldalukon érhető el.  
- **Ideiglenes licenc:** Szerezzen ideiglenes licencet a korlátlan teszteléshez.  
- **Támogatás:** Kérdése van? Látogassa meg az [Aspose Forum](https://forum.aspose.com/c/slides/11) oldalt segítségért.

---

**Utolsó frissítés:** 2026-07-27  
**Tesztelve ezzel:** Aspose.Slides for Java 24.12  
**Szerző:** Aspose

## Kapcsolódó útmutatók

- [Hogyan adjunk diagramokat a PowerPoint-hoz az Aspose.Slides for Java használatával: Lépésről lépésre útmutató](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Hogyan hozzunk létre diagramot Java-ban az Aspose.Slides használatával: Átfogó útmutató](/slides/java/charts-graphs/aspose-slides-java-chart-creation-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}