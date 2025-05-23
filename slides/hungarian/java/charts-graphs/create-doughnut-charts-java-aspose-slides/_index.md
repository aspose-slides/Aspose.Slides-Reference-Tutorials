---
"date": "2025-04-17"
"description": "Tanuld meg, hogyan készíthetsz lenyűgöző fánkdiagramokat Java nyelven az Aspose.Slides segítségével. Ez az átfogó útmutató az inicializálást, az adatkonfigurációt és a prezentációk mentését tárgyalja."
"title": "Fánkdiagramok létrehozása Java nyelven az Aspose.Slides használatával – Átfogó útmutató"
"url": "/hu/java/charts-graphs/create-doughnut-charts-java-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Fánkdiagramok létrehozása Java-ban az Aspose.Slides használatával: lépésről lépésre útmutató

## Bevezetés

mai adatvezérelt környezetben az információk hatékony vizualizációja kulcsfontosságú a megértés és az elköteleződés fokozásához. Bár a professzionális diagramok programozott létrehozása kihívást jelenthet, különösen Java nyelven, ez az útmutató végigvezeti Önt az Aspose.Slides Java-beli használatán, hogy könnyedén készíthessen fánkdiagramokat.

A következő lépéseket követve a fejlesztők gyakorlati tapasztalatot szerezhetnek a prezentációs diák manipulálásában és az adatvizualizáció zökkenőmentes integrálásában.

**Főbb tanulságok:**
- Presentation objektum inicializálása Aspose.Slides Java használatával.
- Diagramadatok konfigurálása és meglévő sorozatok vagy kategóriák kezelése.
- Sorozatok és kategóriák hozzáadása és testreszabása a diagramokhoz.
- Adatpontok hatékony formázása és megjelenítése.
- Mentsd el prezentációdat könnyedén különböző formátumokban.

Mielőtt belevágnál a megvalósításba, győződj meg róla, hogy minden a rendelkezésedre áll, ami a kezdéshez szükséges.

## Előfeltételek

A bemutató követéséhez győződjön meg arról, hogy rendelkezik a következőkkel:

- **Szükséges könyvtárak:**
  - Aspose.Slides Java 25.4-es vagy újabb verzióhoz.
  
- **Környezet beállítása:**
  - JDK 16 vagy újabb verzió telepítve a rendszereden.
  - Egy IDE, mint például az IntelliJ IDEA, az Eclipse vagy a NetBeans.

- **Előfeltételek a tudáshoz:**
  - Java programozási fogalmak alapvető ismerete.
  - Jártasság a Maven vagy Gradle projektek függőségeinek kezelésében.

## Az Aspose.Slides beállítása Java-hoz

Az Aspose.Slides projektbe való integrálásához kövesse az alábbi lépéseket az építőeszközétől függően:

**Maven beállítás:**
Adja hozzá a következő függőséget a `pom.xml` fájl:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle beállítása:**
A következőket is vedd bele a listádba `build.gradle` fájl:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Közvetlen letöltés:**
Vagy töltse le a legújabb verziót közvetlenül innen: [Aspose.Slides Java kiadásokhoz](https://releases.aspose.com/slides/java/).

### Licenc megszerzése

Az Aspose.Slides használatához kiértékelési korlátozások nélkül:
- **Ingyenes próbaverzió:** Kezdjen egy ideiglenes licenccel a teljes funkciók felfedezéséhez.
- **Ideiglenes engedély:** Szerezzen be egyet a következőn keresztül: [Aspose weboldal](https://purchase.aspose.com/temporary-license/).
- **Vásárlás:** Fontolja meg a folyamatos használatra történő vásárlást.

Alkalmazd a licencedet a Java alkalmazásodban a következőképpen:
```java
License license = new License();
license.setLicense("path/to/your/license.lic");
```

## Megvalósítási útmutató

### Bemutató és diagram inicializálása

#### Áttekintés
Kezdje egy prezentációs objektum inicializálásával és egy fánkdiagram hozzáadásával az első diához.

**1. lépés: A prezentáció inicializálása**
Töltsön be egy meglévő PPTX fájlt, vagy hozzon létre egy újat:
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/testc.pptx");
```

**2. lépés: Fánkdiagram hozzáadása**
Hozz létre egy diagramot az első dián a megadott koordinátákon:
```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.Doughnut, 10, 10, 500, 500, false);
```

### Diagramadat-munkafüzet konfigurálása és meglévő sorozatok/kategóriák törlése

#### Áttekintés
Konfigurálja a diagramadatok munkafüzetét, és távolítsa el a már meglévő sorozatokat vagy kategóriákat.

**1. lépés: Diagramadatok munkafüzetének elérése**
A diagramhoz kapcsolt munkafüzet lekérése:
```java
IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();
```

**2. lépés: Törölje a meglévő sorozatokat és kategóriákat**
Győződjön meg arról, hogy nincsenek maradék adatpontok:
```java
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
chart.setLegend(false);
```

### Sorozat hozzáadása a diagramhoz

#### Áttekintés
Töltse fel a diagramot több adatsorral, amelyek mindegyikének megjelenése és viselkedése testreszabható.

**1. lépés: Sorozatok hozzáadása iteratívan**
Indexek ismétlése sorozatok hozzáadásához:
```java
int seriesIndex = 0;
while (seriesIndex < 15) {
    IChartSeries series = chart.getChartData().getSeries().add(
        workBook.getCell(0, 0, seriesIndex + 1, "SERIES " + seriesIndex),
        chart.getType()
    );

    // A sorozat testreszabása
    series.setExplosion(0);
    series.getParentSeriesGroup().setDoughnutHoleSize((byte) 20);
    series.getParentSeriesGroup().setFirstSliceAngle(351);
    seriesIndex++;
}
```

### Kategóriák és adatpontok hozzáadása a diagramhoz

#### Áttekintés
Kategóriák konfigurálása és adatpontok hozzáadása a címkékhez meghatározott formázással.

**1. lépés: Kategóriák hozzáadása**
Végigfutjuk az egyes kategóriák indexeit:
```java
int categoryIndex = 0;
while (categoryIndex < 15) {
    chart.getChartData().getCategories().add(
        workBook.getCell(0, categoryIndex + 1, 0, "CATEGORY " + categoryIndex)
    );
```

**2. lépés: Adatpontok hozzáadása minden sorozathoz**
Ismételje meg az aktuális kategória minden egyes sorozatát:
```java
int i = 0;
while (i < chart.getChartData().getSeries().size()) {
    IChartSeries iCS = chart.getChartData().getSeries().get_Item(i);
    IChartDataPoint dataPoint = iCS.getDataPoints()
        .addDataPointForDoughnutSeries(workBook.getCell(0, categoryIndex + 1, i + 1, 1));

    // Adatpont formátumbeállításai
    dataPoint.getFormat().getFill().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
    dataPoint.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.WHITE);
    dataPoint.getFormat().getLine().setWidth(1);
    dataPoint.getFormat().getLine().setStyle(LineStyle.Single);
    dataPoint.getFormat().getLine().setDashStyle(LineDashStyle.Solid);

    // Az utolsó sorozat címkeformázása
    if (i == chart.getChartData().getSeries().size() - 1) {
        IDataLabel lbl = dataPoint.getLabel();
        lbl.getTextFormat().getTextBlockFormat().setAutofitType(TextAutofitType.Shape);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontBold(NullableBool.True);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setLatinFont(new FontData("DINPro-Bold"));
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().setFontHeight(12);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .setFillType(FillType.Solid);
        lbl.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat()
            .getSolidFillColor().setColor(Color.LIGHT_GRAY);

        // Megjelenítési beállítások módosítása
        lbl.getDataLabelFormat().setShowValue(false);
        lbl.getDataLabelFormat().setShowCategoryName(true);
        lbl.getDataLabelFormat().setShowSeriesName(false);
        lbl.getDataLabelFormat().setShowLeaderLines(true);
        lbl.getDataLabelFormat().setShowLabelAsDataCallout(false);

        // Címke pozíciójának beállítása
        chart.validateChartLayout();
        lbl.setX(lbl.getX() + (float) 0.5);
        lbl.setY(lbl.getY() + (float) 0.5);
    }
    i++;
}
categoryIndex++;
```

### A prezentáció mentése

#### Áttekintés
Miután beállította a diagramot, mentse el a prezentációt egy megadott könyvtárba.

**1. lépés: Mentse el a prezentációt**
Használd a `save` A változtatások írásának módja:
```java
pres.save("YOUR_OUTPUT_DIRECTORY/chart_presentation.pptx", SaveFormat.Pptx);
```

## Következtetés

Most már megtanultad, hogyan hozhatsz létre és szabhatsz testre fánkdiagramokat Java nyelven az Aspose.Slides segítségével. Ezek a lépések alapot biztosítanak a kifinomult adatvizualizációk integrálásához a prezentációidba.

**Következő lépések:**
- Kísérletezz az Aspose.Slides-ban elérhető különböző diagramtípusokkal.
- Fedezzen fel további testreszabási lehetőségeket, például színeket, betűtípusokat és stílusokat, hogy megfeleljenek márkaépítési igényeinek.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}