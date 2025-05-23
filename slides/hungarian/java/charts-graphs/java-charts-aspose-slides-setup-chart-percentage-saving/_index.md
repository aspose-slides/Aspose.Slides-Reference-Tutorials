---
"date": "2025-04-17"
"description": "Tanuld meg, hogyan hozhatsz létre, szabhatsz testre és menthetsz százalékos címkékkel ellátott diagramokat Java prezentációkban az Aspose.Slides segítségével. Fejleszd prezentációs készségeidet még ma!"
"title": "Diagramok létrehozása és testreszabása Java prezentációkban az Aspose.Slides használatával"
"url": "/hu/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Diagramok létrehozása és testreszabása Java prezentációkban az Aspose.Slides használatával

## Bevezetés
A meggyőző prezentációk készítése gyakran többet jelent, mint pusztán szöveget; dinamikus diagramokra van szükség, amelyek hatékonyan közvetítik az információkat. Ha kifinomult diagramfunkciókkal szeretnéd kiegészíteni Java-alapú prezentációidat az Aspose.Slides segítségével, ez az oktatóanyag neked szól. Végigvezetünk a prezentációk létrehozásán, a diagramok hozzáadásán és konfigurálásán, az összegek kiszámításán, a százalékos címkék megjelenítésén és a munkád mentésén – mindezt mindössze néhány egyszerű lépésben.

**Amit tanulni fogsz:**
- Hogyan hozhatunk létre és szabhatunk testre diagramokkal ellátott prezentációkat az Aspose.Slides for Java használatával
- Kategóriaösszesítések kiszámítása diagramokban
- Adatok megjelenítése százalékos címkékként diagramokon
- Prezentációk mentése továbbfejlesztett diagramfunkciókkal

Nézzük át, milyen előfeltételekre van szükséged, mielőtt belekezdenénk.

## Előfeltételek
A bemutató követéséhez győződjön meg arról, hogy rendelkezik a következőkkel:

- **Java fejlesztőkészlet (JDK)**: 8-as vagy újabb verzió.
- **IDE**Például az IntelliJ IDEA, az Eclipse vagy bármely Java-t támogató IDE.
- **Aspose.Slides Java könyvtárhoz**Ez kulcsfontosságú a prezentációs funkciók kezeléséhez.

### Szükséges könyvtárak és verziók
Szükséged lesz az Aspose.Slides Java-alapú verziójára. Így illesztheted be a projektedbe:

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

Vagy közvetlenül letöltheti a legújabb verziót innen: [Aspose.Slides Java kiadásokhoz](https://releases.aspose.com/slides/java/).

### Környezet beállítása
Győződjön meg arról, hogy a fejlesztői környezete JDK 8-as vagy újabb verzió használatára van konfigurálva, és hogy az IDE be van állítva a függőségek Maven vagy Gradle használatával történő kezelésére.

**Licenc beszerzése:**
- **Ingyenes próbaverzió**: Hozzáférés az alapvető funkciókhoz tesztelési célokra.
- **Ideiglenes engedély**: Speciális funkciók tesztelése értékelési korlátozások nélkül.
- **Vásárlás**Hosszú távú kereskedelmi felhasználás esetén érdemes megfontolni a licenc megvásárlását.

## Az Aspose.Slides beállítása Java-hoz
Kezdd az Aspose.Slides könyvtár beállításával a Java projektedben. Így inicializálhatod és konfigurálhatod:

1. Adja hozzá a függőséget Maven vagy Gradle segítségével a fent látható módon.
2. Importáld a szükséges Aspose.Slides csomagokat:
   ```java
   import com.aspose.slides.*;
   ```

3. Új inicializálása `Presentation` példány:
   ```java
   Presentation presentation = new Presentation();
   ```

Ez a beállítás lehetővé teszi, hogy programozottan kezdj el prezentációkat készíteni.

## Megvalósítási útmutató

### Diagramok létrehozása és testreszabása a prezentációban

#### Áttekintés
Egy diagram létrehozása magában foglalja a prezentáció inicializálását, a diák elérését és egy diagram hozzáadását meghatározott attribútumokkal, például típussal, pozícióval és mérettel.

**Lépések:**
1. **Prezentációs példány létrehozása**: Kezdje egy példány létrehozásával a következőből: `Presentation` osztály.
2. **Hozzáférési csúszda**: Az első dia lekérése a következővel: `get_Item(0)`.
3. **Diagram hozzáadása**Használat `addChart()` halmozott oszlopdiagram hozzáadásához megadott koordinátákon és meghatározott méretekkel.

```java
// Funkció: Diagrammal ellátott bemutató létrehozása
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Kategóriák összegeinek kiszámítása

#### Áttekintés
A kategóriák összesítésének kiszámítása magában foglalja a diagram minden egyes sorozatának ismétlését az értékek kategóriánkénti összegzéséhez.

**Lépések:**
1. **Tömb inicializálása**: Hozz létre egy tömböt az összegzett értékek tárolására.
2. **Iteráció a kategóriákon és sorozatokon keresztül**Használjon beágyazott ciklusokat az összes sorozat minden kategóriájának összegzéséhez.

```java
// Funkció: Összesítések kiszámítása kategóriákhoz egy diagramban
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Adatok megjelenítése százalékos címkékként egy diagramon

#### Áttekintés
Ez a funkció az adatfeliratok konfigurálására összpontosít, hogy százalékos formában jelenítsék meg az értékeket, így biztosítva az áttekinthetőséget a vizualizációban.

**Lépések:**
1. **Sorozatcímkék konfigurálása**: Címketulajdonságok, például a betűméret és a jelmagyarázat kulcsainak láthatóságának beállítása.
2. **Százalékok kiszámítása**: Számítsa ki az egyes adatpontok százalékos értékét a teljes kategóriaérték alapján.
3. **Címke szövegének beállítása**: A címkék formázása úgy, hogy a százalékok két tizedesjegyre esszenek.

```java
// Funkció: Adatok megjelenítése százalékos címkékként egy diagramon
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Prezentáció mentése diagrammal

#### Áttekintés
Végül mentse el a prezentációt a megadott elérési útra PPTX formátumban.

**Lépések:**
1. **Mentési módszer**: Használja a `save()` módszer a `Presentation` példány.
2. **Erőforrások megsemmisítése**: Győződjön meg arról, hogy a mentés után az erőforrások felszabadulnak.

```java
// Funkció: Prezentáció mentése diagrammal
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Gyakorlati alkalmazások

1. **Pénzügyi jelentéstétel**: Diagramok segítségével jelenítse meg a bevételnövekedés százalékos arányát az egyes részlegek között.
2. **Értékesítési adatok elemzése**: Vizualizálja az értékesítési adatokat régiónként százalékos címkékkel a tisztább áttekintés érdekében.
3. **Oktatási prezentációk**: Akadémiai prezentációk vizuális statisztikákkal való gazdagítása.
4. **Marketingkampányok**: Jelenítse meg a kampány teljesítménymutatóit lebilincselő vizuális elemekként.
5. **Üzleti stratégiai megbeszélések**: Használjon diagramokat összetett adatok megjelenítéséhez a stratégiai tervezési megbeszéléseken.

## Teljesítménybeli szempontok
- **Memóriakezelés**Ártalmatlanítsa `Presentation` azonnal felszabadítsa az erőforrásokat.
- **Diagram betöltésének optimalizálása**Csak a lényeges diagramelemeket töltse be a memóriába, ha lehetséges.
- **Kötegelt feldolgozás**Több prezentáció feldolgozásakor érdemes kötegekben kezelni őket az erőforrás-felhasználás hatékony kezelése érdekében.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}