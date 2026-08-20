---
date: '2026-08-06'
description: Tanulja meg, hogyan változtathatja meg a jelmagyarázat betűszínét, és
  módosíthatja a diagram jelmagyarázat szövegét az Aspose.Slides for Java használatával.
  Kövesse a lépésről‑lépésre útmutatót a diagram jelmagyarázatok gyors testreszabásához.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Tanulja meg, hogyan változtathatja meg a jelmagyarázat betűszínét,
  és módosíthatja a diagram jelmagyarázat szövegét az Aspose.Slides for Java segítségével.
  Ez az útmutató bemutatja a pontos lépéseket és a legjobb gyakorlatokat.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Hogyan változtassuk meg a jelmagyarázat betűszínét az Aspose.Slides for
  Java-ban
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Hogyan változtassuk meg a jelmagyarázat betűszínét az Aspose.Slides for Java-ban
url: /hu/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan változtassuk meg a jelmagyarázat betűszínét az Aspose.Slides for Java-ban

## Bevezetés
Ha egy diagramon **a jelmagyarázat betűszínét** kell megváltoztatni, az Aspose.Slides for Java teljes irányítást biztosít minden jelmagyarázati elem felett. Ez az útmutató végigvezet a jelmagyarázat szövegstílusainak testreszabásán, a félkövér vagy dőlt betűk alkalmazásán, valamint a szilárd színek beállításán, hogy a diagramok pontosan úgy nézzenek ki, ahogy szeretnéd. A útmutató végére magabiztosan tudod módosítani a diagram jelmagyarázat szövegét, és beépíteni a változtatásokat bármely meglévő bemutatóba.

**Mit fogsz megtanulni**
- Hogyan **változtassuk meg a jelmagyarázat betűszínét** programozottan.
- Módszerek a **diagram jelmagyarázat szövegének módosítására**, például félkövér, dőlt és méret.
- Tippek a változtatások több diagramra történő alkalmazásához egy bemutatóban.
- Hogyan integráljuk ezeket a lépéseket egy nagyobb automatizálási munkafolyamatba.

## Gyors válaszok
- **Megváltoztathatom egyetlen jelmagyarázati elem színét?** Igen – az elemet az indexével érheted el, és a kitöltési formátumot szilárd színre állíthatod.  
- **Szükségem van licencre ezeknek az API-knak a használatához?** Ideiglenes vagy fizetett licenc szükséges a termeléshez; egy ingyenes próba a kiértékeléshez megfelelő.  
- **Melyik Java verzió támogatott?** Az Aspose.Slides for Java 25.4+ működik a JDK 16 és újabb verziókkal.  
- **A változtatások hatással lesznek más diagram elemekre?** Nem, a jelmagyarázat formázása elkülönül az adat sorozatok stílusától.  
- **Lehetséges a kötegelt feldolgozás?** Teljesen – ciklusban végig a diákon és diagramokon, hogy ugyanazokat a jelmagyarázati beállításokat alkalmazd az egész bemutatón.

## Mi a jelmagyarázat betűszínének módosítása?
`change legend font color` a programozott műveletet jelenti, amely a diagram jelmagyarázat bejegyzéseinek szövegszínét állítja be az Aspose.Slides API segítségével. Ez a művelet frissíti a jelmagyarázat vizuális megjelenését anélkül, hogy a háttéradatokat módosítaná.

## Miért testre szabjuk a diagram jelmagyarázatokat?
Az Aspose.Slides **50+ bemeneti és kimeneti formátumot** támogat, és képes **500+ diát** tartalmazó bemutatókat kezelni, miközben a memóriahasználat 200 MB alatt marad. A jelmagyarázatok testreszabása javítja az olvashatóságot, erősíti a márkaszínek megjelenését, és biztosítja, hogy a kulcsfontosságú adatok kiemelkedjenek – különösen üzleti vagy oktatási bemutatók esetén, ahol a vizuális tisztaság a döntéshozatalt befolyásolja.

## Előfeltételek
- **Aspose.Slides for Java** könyvtár (25.4 vagy újabb verzió).  
- Java Development Kit (JDK) 16 vagy újabb.  
- IDE, például IntelliJ IDEA, Eclipse vagy NetBeans.  
- Maven vagy Gradle a függőségkezeléshez.  
- Alapvető Java programozási ismeretek.

## Az Aspose.Slides for Java beállítása
A diagram jelmagyarázatainak testreszabásához add hozzá a könyvtárat a projektedhez az alábbi módszerek egyikével.

### Maven
Add the following dependency to your `pom.xml` file:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Include this line in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direct download
A legújabb JAR-t letöltheted a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

#### Licenc megszerzésének lépései
- **Free trial:** Kezd egy ingyenes próbaidőszakkal az Aspose.Slides funkcióinak felfedezéséhez.  
- **Temporary license:** Kérj ideiglenes licencet a kiterjesztett értékeléshez.  
- **Purchase:** A teljes hozzáféréshez fontold meg a licenc megvásárlását a [Aspose Purchase](https://purchase.aspose.com/buy) oldalon.

#### Alapvető inicializálás és beállítás
A könyvtár hozzáadása után a projektedhez:
1. Inicializáld az Aspose.Slides-t a Java alkalmazásodban.  
2. Tölts be egy meglévő bemutatót, vagy hozz létre egy újat.

## Hogyan változtassuk meg a jelmagyarázat betűszínét?
A jelmagyarázat betűszínének megváltoztatásához töltsd be a bemutatót, szerezd meg a diagram objektumot, kapd meg a jelmagyarázatát, majd módosítsd minden jelmagyarázati bejegyzés szövegformátumát úgy, hogy a kitöltés típusát szilárdra állítod és megadod a kívánt színt. Ez az egyetlen művelet azonnal frissíti a jelmagyarázat szövegének színét anélkül, hogy újra kellene rajzolni az egész diát. Példa: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Ez a megközelítés bármely diagramtípusra működik, és nem igényli a teljes dia újrarenderelését.

### A jelmagyarázat szövegtulajdonságainak elérése és módosítása

#### Definíció horgony
Az `IChart` interfész egy diagram objektumot képvisel egy dián, és a `getLegend()` metódusa egy `ILegend` objektumot ad vissza, amely `ILegendEntry` elemek gyűjteményét tartalmazza.

#### Diagram hozzáadása a bemutatóhoz
1. **Töltsd be a bemutatót:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Adj hozzá egy csoportosított oszlopdiagramot:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Betűtulajdonságok testreszabása
3. **A jelmagyarázat bejegyzés szövegformátumának elérése:**  
   Itt a `legendEntry` egy `ILegendEntry` objektum, amely a diagram jelmagyarázatának egyetlen bejegyzését képviseli.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Állítsd be a félkövér és dőlt stílusokat egy adott magassággal:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **A kitöltés típusát állítsd szilárd színre a jobb láthatóság érdekében:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### A bemutató mentése
6. **Mentsd el a módosításokat:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Gyakori buktatók és hibakeresés
- Ellenőrizd, hogy a jelmagyarázat bejegyzés indexe megegyezik a diagram sorozatainak sorrendjével.  
- Győződj meg róla, hogy olyan könyvtárverziót használsz, amely támogatja a `setSolidFillColor` metódust (elérhető a 20.9-es verziótól).  

## Gyakorlati alkalmazások
A jelmagyarázat szövegének testreszabása számos valós helyzetben hasznos:

1. **Üzleti bemutatók:** Igazítsd a jelmagyarázat színeit a vállalati arculathoz a kifinomult megjelenés érdekében.  
2. **Oktatási anyagok:** Emeld ki a kulcsfontosságú adat sorozatokat kontrasztos jelmagyarázat színekkel.  
3. **Marketing anyagok:** Hangsúlyozd a teljesítménymutatókat félkövér, színes jelmagyarázatokkal a döntéshozók figyelmének felkeltéséhez.  

Automatizálhatod a jelmagyarázat frissítéseket is, ha a színértékeket adatbázisból vagy konfigurációs fájlból húzod be.

## Teljesítmény szempontok
Nagy bemutatók feldolgozásakor tartsd szem előtt a következő tippeket:

- **Hatékony memória kezelés:** A mentés után hívd meg a `presentation.dispose()`-t a natív erőforrások felszabadításához.  
- **Csak a szükséges diák betöltése:** Használd a `Presentation.load(String path, LoadOptions options)`-t a `LoadOptions.setLoadOnlySlideIds()`-val, ha csak egy részhalmazra van szükség.  
- **Kötegelt feldolgozás:** Csoportosítsd a jelmagyarázat frissítéseket diánként, hogy csökkentsd az API hívások számát és növeld a teljesítményt.

## Következtetés
Most már tudod, hogyan **változtasd meg a jelmagyarázat betűszínét** és **módosítsd a diagram jelmagyarázat szövegét** az Aspose.Slides for Java segítségével. Ezek a testreszabások javítják a vizuális tisztaságot és segítenek hatékonyabban közvetíteni az adatokat. Kísérletezz különböző betűtípusokkal, méretekkel és színekkel, hogy megfeleljenek a bemutatód stílus útmutatójának, és fedezd fel a többi diagram‑stílus funkciót, hogy valóban professzionális bemutatókat hozz létre.

**Következő lépések**
- Próbáld meg ugyanazt a jelmagyarázat stílust alkalmazni kör- és vonaldiagramokra.  
- Kombináld a jelmagyarázat testreszabását az adatcímke formázással egy teljesen márkás diagramhoz.  

Készen állsz, hogy feljebb emeld a bemutatóidat? Valósítsd meg a fenti lépéseket, és azonnal lásd a különbséget!

## GyIK szakasz
1. **Hogyan változtathatom meg egy jelmagyarázat bejegyzés szövegének színét?**  
   Használd a `getFillFormat().setFillType(FillType.Solid)`-t, majd a `setSolidFillColor(Color.YOUR_COLOR)`-t a jelmagyarázat bejegyzés szövegformátumán.

2. **Alkalmazhatom ezeket a változtatásokat a bemutató minden jelmagyarázatára?**  
   Igen – iterálj végig minden dián, keresd meg a diagramot, és egy cikluson belül frissítsd a jelmagyarázat bejegyzéseit.

3. **Lehetséges dinamikusan a betűméretet a szöveg hossza alapján állítani?**  
   A szükséges méretet kiszámíthatod a `TextFrame.getTextFrameFormat().getFontHeight()` segítségével, és beállíthatod a `setFontHeight(double)` metódussal.

4. **Mi a teendő, ha problémák merülnek fel a jelmagyarázat bejegyzés indexelésével?**  
   Ellenőrizd, hogy az általad használt index megegyezik a sorozat sorrendjével; ne feledd, hogy az indexek nullától indulnak.

5. **Hol találok további Aspose.Slides példákat?**  
   Tekintsd meg az [Aspose Documentation](https://reference.aspose.com/slides/java/) oldalt a részletes útmutatókért és API‑referenciákért.

**További K&V**

**Q: A jelmagyarázat betűszínének módosítása befolyásolja a PDF exportált fájlokat?**  
A: Nem, a színváltoztatás megmarad az összes Aspose.Slides által támogatott exportformátumban, beleértve a PDF‑et és a PPTX‑et.

**Q: Használhatok‑e színátmenetet a szilárd szín helyett?**  
A: Igen – állítsd be a `FillType.Gradient`‑t, és konfiguráld a gradient‑állomásokat a `getGradientStyle()` segítségével.

**Q: Hány jelmagyarázat bejegyzés lehet egy diagramon?**  
A: Egy diagram legfeljebb 256 jelmagyarázat bejegyzést tartalmazhat, ami csak a hozzáadott adat sorozatok számától függ.

## Erőforrások
- **Dokumentáció:** Átfogó útmutató az Aspose.Slides funkciók használatához ([Link](https://reference.aspose.com/slides/java/)).  
- **Letöltés:** A legújabb Aspose.Slides for Java verzió letöltése ([Link](https://releases.aspose.com/slides/java/)).  
- **Vásárlás:** Licenc vásárlása a teljes funkcionalitás feloldásához ([Link](https://purchase.aspose.com/buy)).  
- **Ingyenes próba és ideiglenes licenc:** Kezd ingyenes próbával és kérj ideiglenes licencet ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Támogatás:** Kérj segítséget a közösségtől az Aspose támogatási fórumon ([Link](https://forum.aspose.com/c/slides/11)).

**Utoljára frissítve:** 2026-08-06  
**Tesztelve:** Aspose.Slides for Java 25.4  
**Szerző:** Aspose

## Kapcsolódó oktatóanyagok

- [Enhancing PowerPoint Charts: Font & Axis Customization with Aspose.Slides for Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides for Java: Dynamic Text Frames & Font Customization Guide](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animate Charts PowerPoint Using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}