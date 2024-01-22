---
title: Chart Marker Options on Data Point a Java Slides-ben
linktitle: Chart Marker Options on Data Point a Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Optimalizálja Java diákjait az egyéni diagramjelölő opciókkal. Ismerje meg az adatpontok vizuális javítását az Aspose.Slides for Java segítségével. Fedezze fel a lépésről lépésre szóló útmutatót és a GYIK-et.
type: docs
weight: 14
url: /hu/java/data-manipulation/chart-marker-options-data-point-java-slides/
---

## Bevezetés a Chart Marker Options on Data Point a Java Slides

Ha hatásos prezentációk létrehozásáról van szó, az adatpontokon lévő diagramjelölők testreszabásának és manipulálásának képessége mindent megváltoztathat. Az Aspose.Slides for Java segítségével dinamikus és vizuálisan vonzó elemekké alakíthatja diagramjait.

## Előfeltételek

Mielőtt belemerülnénk a kódolási részbe, győződjön meg arról, hogy a következő előfeltételekkel rendelkezik:

- Java fejlesztői környezet
- Aspose.Slides for Java Library
- Java integrált fejlesztői környezet (IDE)
- Prezentációs dokumentum minta (pl. "Test.pptx")

## 1. lépés: A környezet beállítása

Először is győződjön meg arról, hogy a szükséges eszközök telepítve és készen vannak. Hozzon létre egy Java-projektet az IDE-ben, és importálja az Aspose.Slides for Java könyvtárat.

## 2. lépés: A prezentáció betöltése

A kezdéshez töltse be a bemutató dokumentum mintáját. A megadott kódban feltételezzük, hogy a dokumentum neve "Test.pptx".

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
```

## 3. lépés: Diagram létrehozása

Most hozzunk létre egy diagramot a bemutatóban. Ebben a példában jelölőkkel ellátott vonaldiagramot fogunk használni.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

## 4. lépés: A diagramadatok kezelése

A diagramadatok kezeléséhez hozzá kell férnünk a diagramadatok munkafüzetéhez, és el kell készítenünk az adatsorokat. Töröljük az alapértelmezett sorozatokat, és hozzáadjuk egyéni adatainkat.

```java
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
```

## 5. lépés: Egyéni jelölők hozzáadása

Itt jön az izgalmas rész – az adatpontokon lévő markerek testreszabása. Ebben a példában képeket fogunk használni jelölőként.

```java
BufferedImage img = ImageIO.read(new File(dataDir + "aspose-logo.jpg"));
IPPImage imgx1 = pres.getImages().addImage(img);

BufferedImage img2 = ImageIO.read(new File(dataDir + "Tulips.jpg"));
IPPImage imgx2 = pres.getImages().addImage(img2);

IChartSeries series = chart.getChartData().getSeries().get_Item(0);

// Egyéni markerek hozzáadása az adatpontokhoz
IChartDataPoint point = series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5));
point.getMarker().getFormat().getFill().setFillType(FillType.Picture);
point.getMarker().getFormat().getFill().getPictureFillFormat().getPicture().setImage(imgx1);

// Ismételje meg a többi adatpont esetében is
// ...

// diagramsorozat-jelölő méretének módosítása
series.getMarker().setSize(15);
```

## 6. lépés: A prezentáció mentése

Miután személyre szabta a diagramjelölőket, mentse a prezentációt, hogy megtekinthesse a változásokat.

```java
pres.save(dataDir + "CustomizedChart.pptx", SaveFormat.Pptx);
```

## A Java Slides adatpontján található diagramjelölő opciók teljes forráskódja

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");
ISlide slide = pres.getSlides().get_Item(0);
//Az alapértelmezett diagram létrehozása
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
//Az alapértelmezett diagramadat-munkalapindex lekérése
int defaultWorksheetIndex = 0;
//A diagram adatlapjának lekérése
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
//Vegyük az első diagramsorozatot
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
//Adjon hozzá új pontot (1:3).
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

Az Aspose.Slides for Java segítségével az adatpontokon lévő diagramjelölők testreszabásával emelheti prezentációit. Ez lehetővé teszi, hogy vizuálisan lenyűgöző és informatív diákat készítsen, amelyek lenyűgözik a közönséget.

## GYIK

### Hogyan változtathatom meg az adatpontok marker méretét?

 Az adatpontok markerméretének módosításához használja a`series.getMarker().setSize()` módszert, és argumentumként adja meg a kívánt méretet.

### Használhatok képeket egyéni markerként?

Igen, használhat képeket egyéni jelölőkként az adatpontokhoz. Állítsa be a kitöltés típusát`FillType.Picture` és adja meg a használni kívánt képet.

### Az Aspose.Slides for Java alkalmas dinamikus diagramok készítésére?

Teljesen! Az Aspose.Slides for Java kiterjedt lehetőségeket kínál dinamikus és interaktív diagramok létrehozásához prezentációiban.

### Testreszabhatom a diagram egyéb szempontjait az Aspose.Slides segítségével?

Igen, az Aspose.Slides for Java segítségével testreszabhatja a diagram különböző aspektusait, beleértve a címeket, tengelyeket, adatcímkéket és egyebeket.

### Hol érhetem el az Aspose.Slides for Java dokumentációját és letöltéseit?

 A dokumentációt megtalálod a címen[itt](https://reference.aspose.com/slides/java/) és töltse le a könyvtárat a címről[itt](https://releases.aspose.com/slides/java/).