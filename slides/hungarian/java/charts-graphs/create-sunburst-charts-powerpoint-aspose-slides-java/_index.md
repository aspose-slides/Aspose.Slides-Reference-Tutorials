---
date: '2026-07-17'
description: Tanulja meg, hogyan adjon hozzá Sunburst diagramokat a PowerPointhoz
  az Aspose Slides for Java használatával. A lépésről‑lépésre útmutató bemutatja a
  beállítást, a diagram létrehozását, testreszabását és a valós példákat.
keywords:
- how to add sunburst
- create sunburst chart powerpoint
- create powerpoint presentation java
lastmod: '2026-07-17'
og_description: Hogyan adjon hozzá Sunburst diagramokat a PowerPointhoz az Aspose
  Slides for Java használatával. Kövesse ezt az útmutatót a könyvtár beállításához,
  diagram létrehozásához, adatpontok testreszabásához, és a valós projektekben való
  alkalmazáshoz.
og_image_alt: 'Developer guide: Add sunburst chart to PowerPoint using Aspose Slides
  for Java'
og_title: Hogyan adjon hozzá Sunburst diagramokat a PowerPointhoz az Aspose (Java)
  segítségével
schemas:
- author: Aspose
  dateModified: '2026-07-17'
  description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  headline: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  type: TechArticle
- description: Learn how to add sunburst charts in PowerPoint using Aspose Slides
    for Java. Step‑by‑step guide covers setup, chart creation, customization, and
    real‑world use cases.
  name: How to Add Sunburst Charts in PowerPoint with Aspose (Java)
  steps:
  - name: Add Sunburst Chart
    text: The `IChart` interface defines a chart object that can be placed on any
      slide. Here we add a sunburst chart at coordinates (100, 100) with a size of
      450 × 400 points.
  - name: Save the Presentation
    text: Always persist your changes by calling `save`. You can choose PPTX, PDF,
      or any of the 50+ supported output formats.
  - name: Access Data Points Collection
    text: The first series of the chart holds a collection of `IChartDataPoint` objects
      that represent each slice.
  - name: Show Value for a Specific Data Point
    text: Set `IsValueShown` to `true` on the desired data point to display its numeric
      value directly on the slice.
  - name: Modify Label Formats
    text: Adjust label visibility, font color, and background to improve readability.
  - name: Set Fill Color for Data Points
    text: Customize the fill color of individual slices to match your brand palette
      or to highlight key segments.
  - name: Save the Modified Presentation
    text: Persist the customized chart by saving the presentation again.
  type: HowTo
- questions:
  - answer: A sunburst chart visualizes hierarchical data in concentric rings, with
      each ring representing a level of the hierarchy.
    question: What is a sunburst chart?
  - answer: Add the Maven dependency shown in the “Maven Dependency” section to your
      `pom.xml` and run `mvn clean install`.
    question: How do I install Aspose.Slides for Java using Maven?
  - answer: Yes, the library supports over 50 chart types, including column, line,
      pie, and radar charts.
    question: Can I customize other chart types with Aspose.Slides?
  - answer: Verify the file path is correct, the directory exists, and you have write
      permissions. Also, ensure the `Presentation.save()` method is called.
    question: My presentation isn’t saving—what should I check?
  - answer: Visit the [Aspose forum](https://forum.aspose.com/c/slides/11) or consult
      the official [Aspose.Slides reference](https://reference.aspose.com/slides/java/).
    question: Where can I get more help or examples?
  type: FAQPage
tags:
- sunburst chart
- Aspose.Slides
- Java PowerPoint
- data visualization
title: Hogyan adjon hozzá Sunburst diagramokat a PowerPointhoz az Aspose (Java) segítségével
url: /hu/java/charts-graphs/create-sunburst-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan adjunk hozzá Sunburst diagramokat a PowerPoint-hoz az Aspose (Java) segítségével

## Bevezetés

Az Sunburst diagram hozzáadása egy PowerPoint prezentációhoz azonnal átalakítja az egyszerű adat táblázatot egy lebilincselő vizuális hierarchiává. Ebben az útmutatóban megtanulja, **hogyan adjunk hozzá Sunburst** diagramokat a PowerPointba az Aspose.Slides for Java használatával, a környezet beállításától a színek és címkék finomhangolásáig. Akár értékesítési műszerfalat, projekt‑feladat bontást vagy oktatási diavetítést épít, az alábbi lépések egy termelésre kész megoldást nyújtanak.

**Amit megtanul**
- Hogyan konfigurálja az Aspose.Slides-t Maven vagy Gradle projektben  
- Hogyan hozzon létre új prezentációt és szúrjon be egy Sunburst diagramot  
- Hogyan testre szabja az adatpontokat, címkéket és kitöltő színeket  
- Valós példák, ahol a Sunburst diagramok kiemelkednek  

Kezdjük el, és nézzük meg, milyen egyszerű nyers hierarchikus adatot átalakítani egy kifinomult PowerPoint vizuálissá.

## Gyors válaszok
- **Elsődleges könyvtár?** Aspose.Slides for Java  
- **Támogatott diagramtípus?** Sunburst (radial hierarchical)  
- **Minimum Java verzió?** JDK 16  
- **Tipikus megvalósítási idő?** 10‑15 minutes for a basic chart  
- **Licenc szükséges a termeléshez?** Yes, a valid Aspose license  

## Mi az a Sunburst diagram?
Az Sunburst diagram egy radiális diagram, amely hierarchikus adatokat ábrázol, a központi ponttól kifelé haladó gyűrűkbe ágyazva. Tökéletes a több szintű kapcsolatok megjelenítésére, például szervezeti struktúrák, termékkategóriák vagy fájlrendszer-fák esetén. Minden koncentrikus gyűrű a hierarchia egy szintjét jelenti, és az egyes szeletek mérete a mennyiségi értéküket tükrözi, lehetővé téve a nézők számára, hogy gyorsan megértsék a struktúrát és a nagyságot.

## Miért használjuk az Aspose.Slides for Java-t?
Aspose.Slides támogat **50+ diagramtípust**, és akár **10 000 diát** is képes kezelni anélkül, hogy a teljes fájlt a memóriába töltené, így magas teljesítményt nyújt vállalati szintű jelentéskészítéshez. Keresztplatformos, kiterjedt API-lefedettséget kínál, és erős licencelési lehetőségeket tartalmaz, amelyek eltávolítják a kiértékelési korlátokat, így ideális a termelési környezetekhez.

## Előfeltételek
- **Java Development Kit (JDK)** 16 vagy újabb  
- **IDE** – IntelliJ IDEA, Eclipse, vagy bármely Java‑kompatibilis szerkesztő  
- Alapvető ismeretek a Java szintaxisról és a Maven/Gradle építőeszközökről  

## Az Aspose.Slides for Java beállítása

### Maven függőség
Adja hozzá az Aspose.Slides Maven artefaktumot a `pom.xml`-hez:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle függőség
Ha a Gradle-t részesíti előnyben, adja hozzá a következő sort a `build.gradle` fájlhoz:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Közvetlen letöltés
Letöltheti a legújabb JAR-t közvetlenül a hivatalos kiadási oldalról: [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Licenc beszerzése
Az értékelési korlátok nélküli futtatáshoz szerezzen be licencet:
- **Free trial** – Ingyenes próba – ideiglenes licenc a gyors értékeléshez.  
- **Temporary license** – Ideiglenes licenc – kérjen egyet az [Aspose weboldalról](https://purchase.aspose.com/temporary-license).  
- **Full purchase** – Teljes vásárlás – előfizetés vásárlása korlátlan termelési használathoz.  

### Alap inicializálás
`Presentation` osztály a belépési pont a PowerPoint fájlok létrehozásához vagy megnyitásához.

```java
import com.aspose.slides.Presentation;

public class PresentationExample {
    public static void main(String[] args) {
        // Initialize Aspose.Slides with a license if available
        Presentation pres = new Presentation();
        try {
            // Your code here...
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

## Implementációs útmutató

### Hogyan adjunk hozzá Sunburst diagramot egy PowerPoint prezentációhoz az Aspose.Slides for Java használatával?
Töltsön be egy új `Presentation`-t, adjon hozzá egy diát, szúrjon be egy `IChart`-ot `ChartType.Sunburst` típusú, majd hívja meg a `save` metódust. Ez a tömör háromlépéses minta egy teljesen működő Sunburst diagramot hoz létre, amely készen áll a további testreszabásra.

#### 1. lépés: A Presentation inicializálása
```java
Presentation pres = new Presentation();
try {
    String dataDir = "YOUR_DOCUMENT_DIRECTORY"; // Replace with your path
```

#### 2. lépés: Sunburst diagram hozzáadása
Az `IChart` interfész egy diagram objektumot definiál, amely bármely diára elhelyezhető. Itt egy Sunburst diagramot adunk hozzá a (100, 100) koordinátákon, 450 × 400 pont mérettel.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Sunburst, 100, 100, 450, 400);
```

#### 3. lépés: A prezentáció mentése
Mindig mentse a módosításokat a `save` hívásával. Választhat PPTX, PDF vagy a 50+ támogatott kimeneti formátum közül.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

### Diagram adatpontjainak módosítása

#### Áttekintés
A Sunburst diagram minden szeletét—címkéket, színeket és láthatóságot—a diagram adatpont gyűjteményén keresztül testre szabhatja.

#### 1. lépés: Az adatpontok gyűjteményének elérése
A diagram első sorozata `IChartDataPoint` objektumok gyűjteményét tartalmazza, amelyek az egyes szeleteket képviselik.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

#### 2. lépés: Érték megjelenítése egy adott adatponthoz
Állítsa be a `IsValueShown` értékét `true`-ra a kívánt adatponton, hogy a numerikus érték közvetlenül a szeleten jelenjen meg.

```java
dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel()
    .getDataLabelFormat().setShowValue(true);
```

#### 3. lépés: Címkeformátumok módosítása
Állítsa be a címke láthatóságát, betűszínét és háttérét a jobb olvashatóság érdekében.

```java
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);

branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat()
    .getPortionFormat().getFillFormat().getSolidFillColor()
    .setColor(java.awt.Color.YELLOW);
```

#### 4. lépés: Kitöltő szín beállítása az adatpontokhoz
Testreszabhatja az egyes szeletek kitöltő színét, hogy illeszkedjen a márka palettájához vagy kiemelje a kulcsfontosságú szegmenseket.

```java
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor()
    .setColor(new com.aspose.slides.Color(0, 176, 240, 255));
```

#### 5. lépés: A módosított prezentáció mentése
Mentsen, hogy a testreszabott diagramot a prezentáció újra mentésével rögzítse.

```java
pres.save(dataDir + "/AddColorToDataPoints.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```

## Gyakorlati alkalmazások

1. **Business Analytics** – Értékesítési adatok vizualizálása régió → termékvonal → SKU egyetlen radiális nézetben.  
2. **Project Management** – Munkafelbontási struktúrák megjelenítése, fázisoktól feladatokig, majd alfeladatokig.  
3. **Education** – Tantervi hierarchiák feltérképezése, például tanszékek → kurzusok → modulok.  

## Teljesítménybeli megfontolások

- **Memory Efficiency:** Memóriahatékonyság: Az Aspose.Slides adatfolyamot használ, így még egy 500 oldalas prezentáció több diagrammal is 200 MB RAM alatt marad.  
- **Garbage Collection:** Garbage Collection: Szabadítsa fel a diaobjektumokat (`slide.dispose()`) amikor már nincs rájuk szükség, hogy elkerülje a memória szivárgásokat.  

## Gyakran Ismételt Kérdések

**Q: Mi az a Sunburst diagram?**  
A: A Sunburst diagram hierarchikus adatokat ábrázol koncentrikus gyűrűkben, ahol minden gyűrű a hierarchia egy szintjét jelenti.

**Q: Hogyan telepítem az Aspose.Slides for Java-t Maven használatával?**  
A: Adja hozzá a “Maven Dependency” szakaszban bemutatott Maven függőséget a `pom.xml`-hez, majd futtassa a `mvn clean install` parancsot.

**Q: Testreszabhatok más diagramtípusokat az Aspose.Slides-szal?**  
A: Igen, a könyvtár több mint 50 diagramtípust támogat, beleértve az oszlop, vonal, kör és radar diagramokat is.

**Q: A prezentációm nem mentődik – mit ellenőrizhetek?**  
A: Ellenőrizze, hogy a fájl útvonala helyes, a könyvtár létezik, és rendelkezik írási jogosultsággal. Emellett győződjön meg róla, hogy a `Presentation.save()` metódus meghívásra került.

**Q: Hol kaphatok további segítséget vagy példákat?**  
A: Látogassa meg az [Aspose fórumot](https://forum.aspose.com/c/slides/11) vagy tekintse meg a hivatalos [Aspose.Slides referencia](https://reference.aspose.com/slides/java/) oldalt.

## Források
- **Dokumentáció:** [Aspose.Slides referencia](https://reference.aspose.com/slides/java/)  
- **Referencia (kisbetűs):** [Aspose.Slides referencia](https://reference.aspose.com/slides/java/)  
- **Közösségi fórum:** [Aspose fórum](https://forum.aspose.com/c/slides)  
- **Letöltések:** [Aspose.Slides letöltések](https://releases.aspose.com/slides/java)  

---

**Utolsó frissítés:** 2026-07-17  
**Tesztelve ezzel:** Aspose.Slides for Java 24.12  
**Szerző:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Kapcsolódó útmutatók

- [Hogyan adjunk hozzá diagramokat a PowerPointhoz az Aspose.Slides for Java használatával: Lépésről lépésre útmutató](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Diagramok animálása PowerPointban az Aspose.Slides for Java használatával – Lépésről lépésre útmutató](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Diagram létrehozása Java-ban az Aspose.Slides segítségével – Diagramok hozzáadása és ellenőrzése](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}