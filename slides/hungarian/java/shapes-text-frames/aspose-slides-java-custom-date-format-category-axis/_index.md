---
"date": "2025-04-17"
"description": "Tanuld meg, hogyan szabhatod testre a kategóriatengelyek dátumformátumait az Aspose.Slides for Java segítségével. Javítsd diagramjaidat egyéni adatmegjelenítéssel, amely tökéletes éves jelentésekhez és egyebekhez."
"title": "Egyéni dátumformátum beállítása a kategóriatengelyen az Aspose.Slides Java-ban | Adatvizualizációs útmutató"
"url": "/hu/java/shapes-text-frames/aspose-slides-java-custom-date-format-category-axis/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Egyéni dátumformátum beállítása a kategóriatengelyen az Aspose.Slides Java-ban | Adatvizualizációs útmutató

A mai adatvezérelt világban az információk világos bemutatása kulcsfontosságú a hatékony döntéshozatalhoz. Amikor diagramokat hoz létre az Aspose.Slides for Java segítségével, a kategóriatengely dátumformátumának testreszabása jelentősen javíthatja mind a megértést, mind a megjelenítés minőségét. Ez az útmutató végigvezeti Önt egy egyéni dátumformátum beállításán az Aspose.Slides-ban, hogy fokozza diák vizuális vonzerejét és az adatok átláthatóságát.

**Amit tanulni fogsz:**
- Az Aspose.Slides beállítása Java-hoz
- Egyéni dátumformátumok megvalósítása a kategóriatengelyen
- GregorianCalendar dátumok konvertálása OLE Automation dátumformátumba
- Ezen funkciók gyakorlati alkalmazásai valós helyzetekben

Nézzük meg, hogyan érheted ezt el könnyedén!

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg arról, hogy a következő előfeltételeknek megfeleltünk:

### Szükséges könyvtárak és verziók:
- **Aspose.Slides Java-hoz**: 25.4-es vagy újabb verzióra lesz szükséged.

### Környezeti beállítási követelmények:
- Java kód futtatására alkalmas fejlesztői környezet (például IntelliJ IDEA, Eclipse vagy NetBeans).
- A projektben konfigurált Maven vagy Gradle a függőségek kezelésére.

### Előfeltételek a tudáshoz:
- Java programozási alapismeretek.
- Ismerkedés a diagram komponensek prezentációkban való használatával.

## Az Aspose.Slides beállítása Java-hoz

Az Aspose.Slides Java-alapú használatához függőségként kell beilleszteni a projektbe. Az alábbiakban a telepítési utasításokat találja:

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

Vagy választhatja a [töltsd le a legújabb kiadást](https://releases.aspose.com/slides/java/) közvetlenül az Aspose hivatalos oldaláról.

### Licenc beszerzése:
- **Ingyenes próbaverzió**: Kezdje egy ingyenes próbaverzióval a funkciók felfedezését.
- **Ideiglenes engedély**: Kérjen ideiglenes engedélyt meghosszabbított teszteléshez.
- **Vásárlás**Hosszú távú használat esetén érdemes előfizetést vásárolni. Látogasson el ide: [Aspose vásárlás](https://purchase.aspose.com/buy) a részletekért.

### Alapvető inicializálás:

Így inicializálhatod az Aspose.Slides-t a projektedben:
```java
import com.aspose.slides.Presentation;
// Prezentációs fájlt reprezentáló Presentation objektum példányosítása
Presentation pres = new Presentation();
```

Most pedig térjünk át az útmutató lényegére!

## Megvalósítási útmutató

### Dátumformátum beállítása a kategóriatengelyhez

Ez a funkció lehetővé teszi a dátumok diagram kategóriatengelyén való megjelenítésének testreszabását. Az alábbiakban részletes útmutatót talál:

#### 1. Hozzon létre egy új prezentációt és diagramot
Kezdje egy példány létrehozásával `Presentation` és egy új területdiagram hozzáadása.
```java
import com.aspose.slides.*;
import java.text.ParseException;
import java.util.GregorianCalendar;

public class DateFormatFeature {
    public static void main(String[] args) throws ParseException {
        // Prezentáció inicializálása
        Presentation pres = new Presentation();
        
        try {
            // Területdiagram hozzáadása az első diához a megadott helyen és méretben
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Area, 50, 50, 450, 300);

            // Hozzáférési diagramadat-munkafüzet a diagramadatok kezeléséhez
            IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
            wb.clear(0); // Törölje a diagramban található meglévő adatokat

            // Távolítson el minden meglévő kategóriát és sorozatot
            chart.getChartData().getCategories().clear();
            chart.getChartData().getSeries().clear();

            // Dátumok hozzáadása a kategóriatengelyhez konvertált OLE Automation dátumok használatával
            chart.getChartData().getCategories().add(wb.getCell(0, "A2", convertToOADate(new GregorianCalendar(2015, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A3", convertToOADate(new GregorianCalendar(2016, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A4", convertToOADate(new GregorianCalendar(2017, 1, 1))));
            chart.getChartData().getCategories().add(wb.getCell(0, "A5", convertToOADate(new GregorianCalendar(2018, 1, 1))));

            // Hozz létre egy új sorozatot, és adj hozzá adatpontokat
            IChartSeries series = chart.getChartData().getSeries().add(ChartType.Line);
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B2", 1));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B3", 2));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B4", 3));
            series.getDataPoints().addDataPointForLineSeries(wb.getCell(0, "B5", 4));

            // Állítsa a kategóriatengely típusát Dátumra, és konfigurálja a számformátumát
            chart.getAxes().getHorizontalAxis().setCategoryAxisType(CategoryAxisType.Date);
            chart.getAxes().getHorizontalAxis().setNumberFormatLinkedToSource(false); 
            chart.getAxes().getHorizontalAxis().setNumberFormat("yyyy"); // Dátumok formázása csak évként

            // Mentse a prezentációt egy megadott könyvtárba
            pres.save("YOUR_OUTPUT_DIRECTORY/test.pptx", SaveFormat.Pptx);
        } finally {
            if (pres != null) pres.dispose();
        }
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Az OLE Automation konverziójának alapdátuma
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60)); // OLE automatizálási dátumra konvertálás
        return String.valueOf(oaDate);
    }
}
```

#### 2. GregorianCalendar dátumformátum konvertálása OLE automatizált dátumformátumra

Az Aspose.Slides OLE Automation formátumú dátumokat igényel, ami egy szabványos Excel dátumformátum. Így konvertálhatja a Java-fájlt `GregorianCalendar` dátumok:
```java
import java.text.ParseException;
import java.text.SimpleDateFormat;
import java.util.GregorianCalendar;
import java.util.concurrent.TimeUnit;

public class OADateConversionFeature {
    public static void main(String[] args) throws ParseException {
        GregorianCalendar date = new GregorianCalendar(2021, 0, 15); // 2021. január 15.
        String oaDate = convertToOADate(date);
        System.out.println("OLE Automation Date: " + oaDate); 
    }

    public static String convertToOADate(GregorianCalendar date) throws ParseException {
        double oaDate;
        SimpleDateFormat myFormat = new SimpleDateFormat("dd MM yyyy");
        java.util.Date baseDate = myFormat.parse("30 12 1899"); // Az Excel OLE-automatizálás alapdátuma
        Long days = TimeUnit.DAYS.convert(date.getTimeInMillis() - baseDate.getTime(), TimeUnit.MILLISECONDS);

        oaDate = (double) days + ((double) date.get(Calendar.HOUR_OF_DAY) / 24)
                  + ((double) date.get(Calendar.MINUTE) / (60 * 24))
                  + ((double) date.get(Calendar.SECOND) / (60 * 24 * 60));
        return String.valueOf(oaDate);
    }
}
```

### Hibaelhárítási tippek:
- Győződjön meg az átváltás alapdátumáról (`30 Dec 1899`) helyesen van elemezve.
- Ellenőrizd, hogy a Java környezeted támogatja-e a szükséges könyvtárakat és osztályokat.
- Probléma esetén ellenőrizze az Aspose.Slides frissítéseit vagy javításait.

### Gyakorlati alkalmazások

A dátumformátumok testreszabása különösen hasznos lehet az alábbi esetekben:
- **Éves jelentések:** Az éves adattrendek egyértelmű megjelenítése.
- **Pénzügyi diagramok:** A pénzügyi időszakok pontos bemutatása.
- **Projekt ütemtervek:** Meghatározott időkeretek vagy mérföldkövek kiemelése.

Ezt az útmutatót követve pontos és vizuálisan vonzó dátumformátumokkal gazdagíthatod prezentációidat az Aspose.Slides for Java használatával.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}