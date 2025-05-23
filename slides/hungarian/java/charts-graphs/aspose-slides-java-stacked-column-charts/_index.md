---
"date": "2025-04-17"
"description": "Tanulj meg professzionális prezentációkat készíteni az Aspose.Slides for Java segítségével. Ez az útmutató bemutatja a környezet beállítását, a halmozott oszlopdiagramok hozzáadását és az áttekinthetőség érdekében történő testreszabását."
"title": "Sajátítsd el a halmozott oszlopdiagramokat Java nyelven az Aspose.Slides segítségével – Átfogó útmutató"
"url": "/hu/java/charts-graphs/aspose-slides-java-stacked-column-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Halmozott oszlopdiagramok elsajátítása Java-ban az Aspose.Slides segítségével: Átfogó útmutató

## Bevezetés

Emeld magasabb szintre prezentációidat az Aspose.Slides for Java erejével, hasznos adatvizualizációk beépítésével. Professzionális megjelenésű diák létrehozása halmozott oszlopdiagramokkal egyszerűen, akár üzleti jelentéseket készítesz, akár projektstatisztikákat mutatsz be.

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan használható az Aspose.Slides Java-ban dinamikus prezentációk készítéséhez és vizuálisan vonzó halmozott oszlopdiagramok hozzáadásához. Az útmutató végére elsajátítod a szükséges készségeket:
- Állítsa be a környezetét az Aspose.Slides használatához
- Prezentáció létrehozása a semmiből
- Százalékos halmozott oszlopdiagramok hozzáadása és testreszabása
- Formázza a diagram tengelyeit és az adatfeliratokat az áttekinthetőség érdekében

Vágjunk bele abba, hogy olyan prezentációkat készítsünk, amelyek lenyűgözik a közönséget.

## Előfeltételek
Mielőtt elkezdenénk, győződjünk meg arról, hogy a következőkkel rendelkezünk:
- **Java fejlesztőkészlet (JDK):** 8-as vagy újabb verzió.
- **IDE:** Bármely integrált fejlesztői környezet, mint például az IntelliJ IDEA vagy az Eclipse.
- **Maven/Gradle:** Függőségek kezelésére (opcionális, de ajánlott).
- **Alapvető Java ismeretek:** Ismerkedés a Java programozási alapfogalmakkal.

## Az Aspose.Slides beállítása Java-hoz
A kezdéshez be kell illesztened az Aspose.Slides könyvtárat a projektedbe. Így teheted meg:

**Szakértő:**
Adja hozzá ezt a függőséget a `pom.xml` fájl:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Fokozat:**
Vedd bele ezt a `build.gradle` fájl:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Közvetlen letöltés:**
Vagy töltse le a legújabb JAR fájlt innen: [Aspose.Slides Java kiadásokhoz](https://releases.aspose.com/slides/java/).

### Licencszerzés
Ingyenes próbaverzióval kezdheted az Aspose.Slides funkcióinak felfedezését. A tesztelési korlátozások megszüntetéséhez érdemes lehet ideiglenes vagy vásárolt licencet beszerezni.
- **Ingyenes próbaverzió:** Korlátozott funkciókhoz férhet hozzá azonnali költségek nélkül.
- **Ideiglenes engedély:** Kérelem ezen keresztül: [Aspose weboldala](https://purchase.aspose.com/temporary-license/).
- **Vásárlás:** teljes hozzáférésért látogassa meg a vásárlási oldalt.

### Alapvető inicializálás
Így inicializálhatod az Aspose.Slides-t a Java alkalmazásodban:
```java
import com.aspose.slides.Presentation;

public class InitializeAspose {
    public static void main(String[] args) {
        // Hozz létre egy példányt a Presentation osztályból
        Presentation presentation = new Presentation();
        
        // Műveletek végrehajtása a prezentációs objektumon
        System.out.println("Aspose.Slides initialized successfully.");
    }
}
```

## Megvalósítási útmutató

### Prezentáció létrehozása és dia hozzáadása
**Áttekintés:**
Kezdj egy egyszerű prezentáció létrehozásával, amelyhez egy kezdő diát kell használni. Ez az alapja a további fejlesztéseknek.

#### 1. lépés: A prezentációs objektum inicializálása
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;

public class CreatePresentation {
    public static void main(String[] args) throws Exception {
        // Új prezentációs példány létrehozása
        Presentation presentation = new Presentation();
        
        // Hivatkozás az első diára (automatikusan létrehozott)
        System.out.println("Slide count: " + presentation.getSlides().size());
    }
}
```

#### 2. lépés: Mentse el a prezentációt
```java
// Mentse el a prezentációt egy fájlba
presentation.save("YOUR_OUTPUT_DIRECTORY/CreatePresentation_out.pptx", SaveFormat.Pptx);
```

### Százalékos halmozott oszlopdiagram hozzáadása diához
**Áttekintés:**
Javítsa diáját egy százalékos halmozott oszlopdiagram hozzáadásával, amely lehetővé teszi az adatok egyszerű összehasonlítását.

#### 1. lépés: Dia inicializálása és elérése
```java
import com.aspose.slides.ISlide;
import com.aspose.slides.ChartType;

public class AddChartToSlide {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        // Folytassa a diagram hozzáadásával a következő lépésben
    }
}
```

#### 2. lépés: Diagram hozzáadása a diához
```java
import com.aspose.slides.IChart;

IChart chart = slide.getShapes().addChart(
    ChartType.PercentsStackedColumn, 20, 20, 500, 400);
```

### Diagramtengelyek számformátumának testreszabása
**Áttekintés:**
diagram függőleges tengelyének számformátumát testreszabhatja a jobb olvashatóság érdekében.

#### 1. lépés: Diagram hozzáadása és elérése
```java
public class CustomizeChartAxis {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);
    }
}
```

#### 2. lépés: Egyéni számformátum beállítása
```java
import com.aspose.slides.IAxis;

IAxis verticalAxis = chart.getAxes().getVerticalAxis();
verticalAxis.setNumberFormatLinkedToSource(false);
verticalAxis.setNumberFormat("0.00%");
```

### Sorozatok és adatpontok hozzáadása a diagramhoz
**Áttekintés:**
Töltse ki a diagramot adatsorokkal, hogy informatív és vizuálisan vonzó legyen.

#### 1. lépés: A prezentáció és a diagram inicializálása
```java
import com.aspose.slides.IChartSeries;
import com.aspose.slides.ChartDataWorkbook;

public class AddSeriesToChart {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 2. lépés: Adatsorok hozzáadása
```java
// Töröld a meglévő sorozatokat és adj hozzá újakat
chart.getChartData().getSeries().clear();

IChartSeries series1 = chart.getChartData().getSeries().add(
    workbook.getCell(defaultWorksheetIndex, 0, 1, "Reds"), chart.getType());
series1.getDataPoints().addDataPointForBarSeries(workbook.getCell(defaultWorksheetIndex, 1, 1, 0.30));
// Szükség szerint adjon hozzá további adatpontokat
```

### Formázási sorozat kitöltési színe
**Áttekintés:**
Javítsa diagramja esztétikáját az egyes sorozatok kitöltési színének formázásával.

#### 1. lépés: Diagram inicializálása és elérése
```java
import java.awt.Color;
import com.aspose.slides.FillType;

public class FormatSeriesFillColor {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
    }
}
```

#### 2. lépés: Kitöltőszínek beállítása
```java
IChartSeries series1 = chart.getChartData().getSeries().get_Item(0);
series1.getFormat().getFill().setFillType(FillType.Solid);
series1.getFormat().getFill().getSolidFillColor().setColor(Color.RED);

// Ismételd meg a többi, különböző színekkel készült sorozattal
```

### Adatcímkék formázása
**Áttekintés:**
Az adatcímkék formátumának testreszabásával olvashatóbbá teheti azokat.

#### 1. lépés: Diagramsorozatok és adatpontok elérése
```java
public class FormatDataLabels {
    public static void main(String[] args) throws Exception {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);
        
        IChart chart = slide.getShapes().addChart(
            ChartType.PercentsStackedColumn, 20, 20, 500, 400);

        int defaultWorksheetIndex = 0;
        ChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
    }
}
```

#### 2. lépés: Adatcímkék testreszabása
```java
import com.aspose.slides.ITextFrame;
import com.aspose.slides.IChartDataPoint;

for (IChartSeries series : chart.getChartData().getSeries()) {
    for (IChartDataPoint point : series.getDataPoints()) {
        ITextFrame textFrame = point.getLabel().getTextFrameForOverriding();
        if (textFrame != null) {
            textFrame.setText("Custom Label: " + point.getValue());
        }
    }
}
```

## Következtetés
Az útmutató követésével megtanultad, hogyan állíthatod be az Aspose.Slides-t Java-hoz, és hogyan hozhatsz létre dinamikus prezentációkat százalékos halmozott oszlopdiagramokkal. Szabd testre a diagramokat a színek és a feliratok igényeidnek megfelelő módosításával.

Jó kódolást!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}