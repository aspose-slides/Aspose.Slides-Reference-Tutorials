---
date: '2026-05-29'
description: Ismerje meg, hogyan hozhat létre kördiagramot az Aspose.Slides Maven
  segítségével, hogyan adhat hozzá kördiagramot Java-val egy diára, és hogyan testreszabhatja
  a diagram adatait. Lépésről‑lépésre útmutató Maven beállítással és valós példákkal.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Kördiagram létrehozása Aspose – Diagram hozzáadása egy prezentációhoz Maven
  segítségével
url: /hu/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan adjunk hozzá kördiagramot egy prezentációhoz az Aspose.Slides Java használatával

## Bevezetés
Ebben az útmutatóban **create pie chart aspose**-t hozunk létre az Aspose.Slides Maven segítségével, és megmutatjuk, hogyan ágyazzuk be egy PowerPoint diára. A vizuálisan vonzó prezentációk készítése kulcsfontosságú az információ hatékony közvetítéséhez, különösen akkor, amikor az adatvizualizáció központi szerepet játszik. Ha automatizálni szeretnéd ezt a folyamatot a **aspose slides maven** használatával, jó helyen jársz. Lépésről‑lépésre végigvezetünk egy diagram hozzáadásán egy diára — konkrétan egy kördiagramra — és testreszabásán valós helyzetekhez.

### Mit fogsz megtanulni
- Hogyan inicializáljunk egy prezentáció objektumot Java‑ban.  
- Lépések a **add a pie chart java** hozzáadásához a prezentáció első diájára.  
- A diagram adatkönyvtárak elérése és a bennük lévő munkalapok felsorolása.  

Merüljünk el abban, hogyan használhatod az Aspose.Slides Java‑t a prezentációid dinamikus diagramokkal való gazdagításához!

## Gyors válaszok
- **Melyik könyvtár ad hozzá diagramokat Maven‑en keresztül?** aspose slides maven  
- **Melyik diagramtípust mutatja be?** Pie chart (add chart to slide)  
- **Minimum Java verzió szükséges?** JDK 16 vagy újabb  
- **Szükségem van licencre a teszteléshez?** A free trial works; production needs a license  
- **Hol találom a Maven függőséget?** In the setup section below  

## Mi az Aspose Slides Maven?
Az Aspose.Slides for Java egy erőteljes API, amely lehetővé teszi a fejlesztők számára, hogy programozottan hozzanak létre, módosítsanak és rendereljenek PowerPoint fájlokat. A Maven csomag (`aspose-slides`) egyszerűsíti a függőségkezelést, így a diagramok – például egy kördiagram – hozzáadására és testreszabására koncentrálhatsz anélkül, hogy alacsony szintű fájlkezeléssel kellene foglalkoznod.

## Miért használjuk az Aspose.Slides Maven‑t diagram hozzáadásához egy diára?
Az Aspose.Slides Maven lehetővé teszi diagramok generálását közvetlenül Java kódból manuális PowerPoint szerkesztés nélkül. Teljes programozási kontrollt biztosít a diagramtípusok, adatforrások és stílusok felett, garantálva a konzisztens márkázást és pontosságot. A Maven artefaktus kezeli a szükséges függőségeket, egyszerűsíti a build folyamatot és zökkenőmentes integrációt tesz lehetővé CI/CD csővezetékekbe.

## Előfeltételek
- **Aspose.Slides for Java** verzió 25.4 vagy újabb (Maven/Gradle).  
- JDK 16+ telepítve.  
- IDE (IntelliJ IDEA, Eclipse, stb.).  
- Alap Java ismeretek és Maven vagy Gradle ismerete.  

## Az Aspose.Slides for Java beállítása
Először is, add hozzá az Aspose.Slides‑t a projektedhez Maven vagy Gradle segítségével.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatívaként letöltheted a legújabb kiadást közvetlenül az Aspose weboldaláról: [download the latest release](https://releases.aspose.com/slides/java/)

### Licenc beszerzése
Az Aspose.Slides for Java ingyenes próbaverziót kínál ideiglenes licenccel teszteléshez. Korlátlan termelési használathoz vásárolj licencet a [purchase page](https://purchase.aspose.com/buy) oldalon.

## Megvalósítási útmutató
Az alábbiakban a megoldást két funkcióra bontjuk: kördiagram hozzáadása és a diagram adatkönyvtárának elérése.

### Feature 1: Prezentáció létrehozása és diagram hozzáadása
#### Áttekintés
Ez a rész bemutatja, hogyan hozzunk létre egy új prezentációt és **add a pie chart**‑t adjunk hozzá az első diához.

#### Hogyan hozzunk létre kördiagramot aspose?
Töltsd be a `Presentation` osztályt, adj hozzá egy `ChartType.Pie` típusú diagramot, és mentsd el a fájlt. A teljes művelet csak három API‑hívást igényel, és egy tipikus 10‑diás előadás esetén egy másodpercnél gyorsabban lefut, így ideális automatizált jelentéskészítéshez.

#### Lépésről‑lépésre

**1. lépés: Új Presentation objektum inicializálása**  
A `Presentation` osztály az Aspose.Slides felső szintű objektuma, amely egy PowerPoint fájlt reprezentál a memóriában.  
```java
Presentation pres = new Presentation();
```
*Létrehozza a `Presentation` példányt, amely az összes diát tartalmazza.*

**2. lépés: Kördiagram hozzáadása**  
A `ChartType.Pie` azt mondja az Aspose‑nek, hogy kördiagramot rendereljen.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Egy kördiagramot helyez el a (50, 50) koordinátákon, 400 szélességgel és 500 magassággal.*

**3. lépés: Erőforrások felszabadítása**  
A `dispose()` meghívása felszabadítja a natív erőforrásokat és megakadályozza a memória szivárgást.  
```java
if (pres != null) pres.dispose();
```
*Natív erőforrások felszabadítása; mindig hívd meg a `dispose()`‑t, amikor befejezted.*

### Feature 2: Diagram adatkönyvtár és munkalapok elérése
#### Áttekintés
Tanuld meg, hogyan érheted el a diagram adatait tároló alaprendszert, és hogyan iterálhatsz a munkalapokon.

#### Hogyan érjük el a diagram adatkönyvtárát?
Szerezd meg a `IChartDataWorkbook`‑ot a diagramról, majd járd be a `Worksheets` gyűjteményt. Ez a munkafüzet egy Excel‑hez hasonló fájlt utánoz, lehetővé téve az adatsorok programozott olvasását, módosítását vagy hozzáadását, amely a diagram frissítésekor azonnal megjelenik újraindítás nélkül.

#### Lépésről‑lépésre

**(Újrahasználat) Új Presentation objektum inicializálása**  
*Ugyanaz, mint az 1. funkció, 1. lépés.*

**(Újrahasználat) Kördiagram hozzáadása**  
*Ugyanaz, mint az 1. funkció, 2. lépés.*

**A diagram adatkönyvtár lekérése**  
Az `IChartDataWorkbook` interfész olvasási/írási hozzáférést biztosít a diagram belső Excel‑szerű munkafüzetéhez.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Lekéri a diagramhoz kapcsolódó `IChartDataWorkbook`‑ot.*

**Iterálás a munkalapokon**  
A `Worksheet` objektumok a munkafüzet egyes lapjait képviselik.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Kiírja minden munkalap nevét, így ellenőrizheted az adatstruktúrát.*

**Erőforrások felszabadítása**  
*Ugyanaz, mint az 1. funkció, 3. lépés.*

## Gyakorlati alkalmazások
- **Adatjelentés:** Automatikusan generálj diakészleteket a legfrissebb üzleti intelligencia mutatókkal.  
- **Akademiai prezentációk:** Kutatási eredmények vizualizálása manuális diagramkészítés nélkül.  
- **Marketing anyagok:** Termék teljesítmény vagy felmérési eredmények azonnali bemutatása.

## Teljesítménybeli megfontolások
- Az Aspose.Slides **50+** bemeneti és kimeneti formátumot támogat, és több száz oldalas prezentációkat dolgoz fel anélkül, hogy az egész fájlt a memóriába töltené.  
- Tartsd mérsékeltnek a diák és diagramok számát; minden diagram natív memóriát foglal.  
- Mindig hívd meg a `dispose()`‑t az erőforrások gyors felszabadításához.  
- Optimalizáld a munkafüzet adatkezelést – kerüld a hatalmas adatkészletek egyetlen diagramba való betöltését.

## Következtetés
Áttekintettük, hogyan teszi lehetővé a **aspose slides maven** a **add chart to slide** programozott hozzáadását, valamint a diagram adatkönyvtárának kezelését. Ezekkel az építőelemekkel automatizálhatod a jelentéskészítési munkafolyamatokat, amelyek professzionális PowerPoint kimenetet igényelnek.

### Következő lépések
- Fedezd fel a diagram stílusbeállítási lehetőségeket (színek, legendák, adatcímkék).  
- Csatlakoztasd külső adatforrásokhoz (CSV, adatbázisok) a diagramok dinamikus feltöltéséhez.  
- Kombinálj több diagramtípust egyetlen prezentációban a gazdagabb történetmesélésért.

## Gyakran Ismételt Kérdések

**K: Hogyan telepíthetem az Aspose.Slides for Java-t?**  
A: Használd a fent bemutatott Maven vagy Gradle függőséget, vagy töltsd le a könyvtárat a kiadási oldalról.

**K: Mik a rendszerkövetelmények az Aspose.Slides-hez?**  
A: JDK 16 vagy újabb; a könyvtár bármely, Java‑t támogató platformon fut.

**K: Hozzáadhatok más diagramtípusokat is a kördiagramok mellett?**  
A: Igen, az Aspose.Slides támogatja az oszlop, vonal, szórt, radar és több mint 20 diagramtípust.

**K: Hogyan kezeljem hatékonyan a nagy prezentációkat?**  
A: Felszabadítsd időben az objektumokat, korlátozd a nagy felbontású képek használatát, és használd újra a diagram sablonokat a memóriahasználat alacsonyan tartásához.

**K: Hol találok további részleteket az Aspose.Slides funkcióiról?**  
A: Látogasd meg a [Aspose documentation](https://reference.aspose.com/slides/java/) oldalt a teljes API‑referenciáért.

**K: Szükséges licenc a kereskedelmi felhasználáshoz?**  
A: A termeléshez érvényes licenc szükséges; a teszteléshez ingyenes próbaverzió elérhető.

**K: Tartalmazza a Maven csomag az összes diagramfunkciót?**  
A: Igen, a `aspose-slides` Maven artefaktus a teljes diagrammotorral rendelkezik.

## Erőforrások
- Dokumentáció: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Letöltés: [Latest Releases](https://releases.aspose.com/slides/java/)
- Vásárlás és próba: [Purchase Page](https://purchase.aspose.com/buy)
- Ingyenes próba: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Ideiglenes licenc: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Támogatási fórum: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Legutóbb frissítve:** 2026-05-29  
**Tesztelve a következővel:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose

## Kapcsolódó oktatóanyagok

- [Hogyan testre szabjuk a kördiagram színeit Java-ban az Aspose.Slides segítségével – Teljes útmutató](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Kördiagramon belüli kördiagram létrehozása Java-ban az Aspose.Slides segítségével: Átfogó útmutató](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Diagramok animálása PowerPointban az Aspose.Slides for Java segítségével – Lépésről‑lépésre útmutató](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}