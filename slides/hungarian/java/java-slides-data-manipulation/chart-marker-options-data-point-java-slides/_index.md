---
"description": "Optimalizáld Java diáidat egyéni diagramjelölő beállításokkal. Tanuld meg, hogyan javíthatod vizuálisan az adatpontokat az Aspose.Slides for Java segítségével. Tekintsd meg a lépésenkénti útmutatót és a GYIK-et."
"linktitle": "Diagramjelölő beállítások az adatpontokon Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Diagramjelölő beállítások az adatpontokon Java diákban"
"url": "/hu/java/data-manipulation/chart-marker-options-data-point-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Diagramjelölő beállítások az adatpontokon Java diákban


## Bevezetés a Java diák adatpontjainak diagramjelölő beállításaiba

Hatásos prezentációk készítéséhez a diagramjelölők adatpontokon való testreszabásának és kezelésének lehetősége döntő lehet. Az Aspose.Slides Java verziójával diagramjait dinamikus és vizuálisan lebilincselő elemekké alakíthatja.

## Előfeltételek

Mielőtt belevágnánk a kódolás részébe, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:

- Java fejlesztői környezet
- Aspose.Slides Java könyvtárhoz
- Java integrált fejlesztői környezet (IDE)
- Minta prezentációs dokumentum (pl. "Test.pptx")

## 1. lépés: A környezet beállítása

Először is győződj meg róla, hogy telepítve és készen állnak a szükséges eszközök. Hozz létre egy Java projektet az IDE-ben, és importáld az Aspose.Slides for Java könyvtárat.

## 2. lépés: A prezentáció betöltése

Kezdésként töltse be a minta prezentációs dokumentumot. A megadott kódban feltételezzük, hogy a dokumentum neve „Test.pptx”.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## 3. lépés: Diagram létrehozása

Most hozzunk létre egy diagramot a prezentációban. Ebben a példában jelölőkkel ellátott vonaldiagramot fogunk használni.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## 4. lépés: Diagramadatokkal való munka

A diagramadatok kezeléséhez hozzá kell férnünk a diagramadatok munkafüzetéhez, és elő kell készítenünk az adatsorokat. Töröljük az alapértelmezett sorozatokat, és hozzáadjuk az egyéni adatainkat.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## 5. lépés: Egyéni jelölők hozzáadása

És itt jön az izgalmas rész - az adatpontok jelölőinek testreszabása. Ebben a példában képeket fogunk használni jelölőként.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Egyéni jelölők hozzáadása adatpontokhoz
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Ismételje meg a többi adatponttal
// ...

// Diagramsorozat-jelölő méretének módosítása
series.getMarker().setSize(15);
```

## 6. lépés: A prezentáció mentése

Miután testreszabtad a diagramjelölőket, mentsd el a prezentációt, hogy lásd a változásokat működés közben.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## Teljes forráskód a diagramjelölő opciókhoz az adatpontokon Java diákban

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Az alapértelmezett diagram létrehozása
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Az alapértelmezett diagramadat-munkalap indexének lekérése
int defaultWorksheetIndex = 0;
//A diagramadatok munkalapjának beszerzése
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
//Demósorozat törlése
chart.getChartData().getSeries().clear();
//Új sorozat hozzáadása
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
//Állítsa be a képet
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);
//Állítsa be a képet
BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);
//Vegye az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Adjon hozzá egy új pontot (1:3).
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);
point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx2);
//A diagramsorozat-jelölő módosítása
series.getMarker().setSize(15);
pres.save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

## Következtetés

Az Aspose.Slides Java verziójával magasabb szintre emelheted prezentációidat az adatpontokon elhelyezett diagramjelölők testreszabásával. Ez lehetővé teszi, hogy vizuálisan lenyűgöző és informatív diákat hozz létre, amelyek lenyűgözik a közönségedet.

## GYIK

### Hogyan tudom megváltoztatni az adatpontok jelölőméretét?

Az adatpontok jelölőméretének módosításához használja a `series.getMarker().setSize()` metódust, és argumentumként adja meg a kívánt méretet.

### Használhatok képeket egyéni jelölőkként?

Igen, képeket használhat egyéni jelölőkként az adatpontokhoz. Állítsa be a kitöltési típust erre: `FillType.Picture` és add meg a használni kívánt képet.

### Alkalmas az Aspose.Slides Java-ban dinamikus diagramok létrehozására?

Abszolút! Az Aspose.Slides Java-ban széleskörű lehetőségeket kínál dinamikus és interaktív diagramok létrehozására a prezentációidban.

### Testreszabhatom a diagram más aspektusait az Aspose.Slides segítségével?

Igen, a diagram különböző aspektusait, beleértve a címeket, tengelyeket, adatfeliratokat és egyebeket, testreszabhatja az Aspose.Slides for Java használatával.

### Hol férhetek hozzá az Aspose.Slides Java dokumentációjához és letöltéseihez?

A dokumentációt megtalálod a következő címen: [itt](https://reference.aspose.com/slides/java/) és töltse le a könyvtárat innen [itt](https://releases.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}