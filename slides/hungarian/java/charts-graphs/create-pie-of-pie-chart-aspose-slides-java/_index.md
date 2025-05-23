---
"date": "2025-04-17"
"description": "Tanuld meg, hogyan hozhatsz létre és szabhatsz testre egy kördiagramot az Aspose.Slides for Java segítségével. Ez az útmutató a beállítást, a megvalósítást és a gyakorlati alkalmazásokat ismerteti."
"title": "Kördiagram létrehozása Java nyelven az Aspose.Slides segítségével – Átfogó útmutató"
"url": "/hu/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Kördiagram létrehozása Java nyelven az Aspose.Slides segítségével: Átfogó útmutató

## Táblázatok és grafikonok

### Bevezetés

Az adatvizualizációban a kördiagramok intuitív módon ábrázolják az arányokat egy adathalmazon belül. Azonban összetett adathalmazok esetén, ahol egyes szegmensek jelentősen kisebbek, mint mások, a hagyományos kördiagramok zsúfolttá és nehezen értelmezhetővé válhatnak. A kördiagramok ezt úgy oldják meg, hogy kis szeleteket osztanak fel egy másodlagos diagramra, javítva az olvashatóságot.

Ebben az oktatóanyagban megtanulod, hogyan hozhatsz létre és manipulálhatsz kördiagramot az Aspose.Slides Java verziójával. Áttekinted a környezet beállítását, a diagram létrehozását, a tulajdonságok, például az adatcímkék és a felosztási pozíciók testreszabását, valamint a prezentáció PPTX formátumban történő mentését. A végére elsajátítod ezeket a funkciókat, gyakorlati alkalmazásokkal és teljesítménynövelő tippekkel.

**Amit tanulni fogsz:**
- Az Aspose.Slides beállítása Java-hoz
- Kördiagram létrehozása
- Diagramtulajdonságok, például adatcímkék és felosztási konfigurációk testreszabása
- A prezentáció mentése lemezre

Készen állsz a kezdésre? Először nézzük meg az előfeltételeket!

## Előfeltételek

A kördiagram elkészítése előtt győződjön meg arról, hogy rendelkezik a következőkkel:

### Szükséges könyvtárak, verziók és függőségek:
- **Aspose.Slides Java-hoz**Nélkülözhetetlen a PowerPoint-bemutatók programozott kezeléséhez.

### Környezeti beállítási követelmények:
- Telepítve van egy Java fejlesztői készlet (JDK) a gépeden. Javasoljuk a JDK 16-os vagy újabb verziójának használatát.
- Integrált fejlesztői környezet (IDE), mint például az IntelliJ IDEA, az Eclipse vagy a NetBeans.

### Előfeltételek a tudáshoz:
- A Java programozás alapjainak ismerete
- Maven vagy Gradle ismeretek függőségkezelés terén

## Az Aspose.Slides beállítása Java-hoz

### Telepítési információk:

**Szakértő:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Fokozat:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Közvetlen letöltés**A legújabb verziót letöltheti innen: [Aspose.Slides Java kiadásokhoz](https://releases.aspose.com/slides/java/).

### Licenc megszerzésének lépései:
- **Ingyenes próbaverzió**: Kezdje egy 30 napos próbaidőszakkal, hogy felfedezhesse az összes funkciót.
- **Ideiglenes engedély**Ideiglenes engedélyt kell kérni a meghosszabbított értékeléshez.
- **Vásárlás**: Fontolja meg a licenc megvásárlását, ha az Aspose.Slides megfelel az igényeinek.

### Alapvető inicializálás és beállítás

Miután beállítottad a könyvtárat a projektedben, inicializáld egy példány létrehozásával a `Presentation` osztály:

```java
Presentation presentation = new Presentation();
```

Ez előkészíti a terepet különféle diagramok hozzáadásához a diákhoz. Ezután térjünk át a kördiagram megvalósítására.

## Megvalósítási útmutató

### „Kördiagram” létrehozása

#### Áttekintés
Kezdjük egy példány létrehozásával egy `Presentation` és adj hozzá egy kördiagramot az első diához. Ez a diagram hatékonyan jeleníti meg az adatokat azáltal, hogy kisebb szegmenseket választ szét egy másodlagos kördiagramra, javítva az olvashatóságot.

#### 1. lépés: Példány létrehozása a Presentation osztályból
```java
// Új prezentáció létrehozása
ePresentation presentation = new Presentation();
```
Ez a kód inicializálja a prezentációdat, ahová a diagramokat fogjuk hozzáadni.

#### 2. lépés: „Kördiagram” hozzáadása az első diához
```java
// Kördiagram hozzáadása az első diához az (50, 50) pozícióban, (500x400) méretben
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Itt adjuk meg a diagram típusát (`PieOfPie`) valamint a helyzetét és méreteit a dián.

#### 3. lépés: Adatcímkék beállítása az adatsorok értékeinek megjelenítéséhez
```java
// Adatcímkék konfigurálása értékek megjelenítéséhez
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Ez a lépés biztosítja, hogy a kördiagram minden szegmense a megfelelő értéket jelenítse meg, ami segíti a gyors adatértelmezést.

#### 4. lépés: A második kördiagram méretének és százalékos felosztásának konfigurálása
```java
// Másodlagos kördiagram méretének beállítása
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Ossza fel a tortát százalékosan
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Állítsa be az osztási pozíciót
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Ezek a konfigurációk lehetővé teszik a diagram felosztásának és kisebb szegmensek megjelenítésének testreszabását, ami javítja a megtekintők számára láthatóságot.

#### 5. lépés: Mentse a prezentációt lemezre PPTX formátumban
```java
// Kimeneti könyvtár definiálása
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Mentse el a presentation\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\ fájlt

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}