---
date: '2026-02-17'
description: Ismerje meg, hogyan adhat hozzá kördiagramot PowerPoint-prezentációkhoz
  az Aspose.Slides for Java használatával. Kövesse ezt a lépésről‑lépésre útmutatót,
  hogy professzionális kördiagramokat hozzon létre és testreszabjon.
keywords:
- Create Pie Charts in PowerPoint Java
- Customize Pie Chart Aspose.Slides Java
- Aspose.Slides for Java Pie Chart
title: Hogyan adjunk hozzá kördiagramot a PowerPoint-hoz az Aspose.Slides for Java
  használatával
url: /hu/java/charts-graphs/aspose-slides-java-create-pie-chart/
weight: 1
---

-backtop-button >}}

Now ensure we kept all shortcodes unchanged.

Check for any missed bold formatting: we need to keep ** markers.

We translated bold phrases; ensure they still have **.

Check list items: we need to keep bullet markers.

Now produce final content.

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Kördiagramok létrehozása és testreszabása PowerPointban az Aspose.Slides for Java használatával

## Bevezetés

Küzd a hatékony adatmegjelenítéssel PowerPoint prezentációiban? **Kördiagram PowerPoint** dia hozzáadása azonnal átalakítja a nyers számokat egyértelmű vizuális történetté. Az Aspose.Slides for Java segítségével programozottan **kördiagram PowerPoint** fájlokat adhat hozzá, teljes irányítást biztosítva a tervezés és az adatok felett anélkül, hogy manuálisan megnyitná a PowerPointot. Ebben az útmutatóban végigvezetjük a teljes folyamatot – a könyvtár beállításától az egyes adatpontok testreszabásáig – hogy percek alatt kifinomult, adat‑vezérelt diákot tudjon bemutatni.

### Gyors válaszok
- **Milyen könyvtárra van szükségem?** Aspose.Slides for Java (legújabb verzió).  
- **Létrehozhatok diagramot PowerPoint telepítése nélkül?** Igen, az API teljesen offline működik.  
- **Melyik Java verzió szükséges?** JDK 16 vagy újabb ajánlott.  
- **Hogyan változtathatom meg egy szelet színét?** Használja a `setFillType` és `setSolidFillColor` metódusokat az adatponton.  
- **Kötelező-e licenc?** A próbaverzió fejlesztéshez működik; egy állandó licenc eltávolítja a kiértékelési korlátokat.

### Mit fog megtanulni
- Hogyan **kördiagram PowerPoint** hozzáadása programozottan Java-val.  
- Módszerek a szelet robbanás, színek és egyéb vizuális tulajdonságok testreszabására.  
- Legjobb gyakorlatok az erőforrás‑kezeléshez és a teljesítményhez nagy prezentációk kezelésekor.

## Miért érdemes kördiagram PowerPointot hozzáadni az Aspose.Slides for Java használatával?
A kördiagram közvetlen beágyazása a kódból lehetővé teszi naprakész jelentések generálását, havi műszerfalak automatizálását vagy személyre szabott diakészletek gyors létrehozását. Ez megszünteti a kézi másolás‑beillesztés hibáit, biztosítja a konzisztenciát a prezentációk között, és zökkenőmentesen integrálódik a meglévő Java háttérrendszerekkel.

## Előfeltételek

A kezdés előtt győződjön meg róla, hogy rendelkezik:

- **Aspose.Slides for Java könyvtár** – az útmutató a 25.4-es verzióra hivatkozik (a legújabb kiadás a írás időpontjában).  
- Kompatibilis **Java Development Kit (JDK)** – JDK 16+ ajánlott.  
- Alapvető ismeretek a **Maven** vagy **Gradle** használatáról a függőségkezeléshez.  

## Az Aspose.Slides for Java beállítása

A kezdéshez adja hozzá az Aspose.Slides könyvtárat a projektjéhez.

### Maven
Adja hozzá ezt a függőséget a `pom.xml` fájlhoz:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Tegye a következőt a `build.gradle` fájlba:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternatívaként töltse le a legújabb verziót közvetlenül a [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/) oldalról.

### Licencelés
Az Aspose.Slides korlátok nélküli használatához:

- Kezdje egy **ingyenes próbaverzióval**, hogy kiértékelje az API-t.  
- Kérjen **ideiglenes licencet** a kiterjesztett teszteléshez a [Temporary License](https://purchase.aspose.com/temporary-license/) oldalon.  
- Vásároljon teljes előfizetést a [Purchase page](https://purchase.aspose.com/buy) oldalon.  

## Hogyan adjon hozzá kördiagram PowerPointot az Aspose.Slides for Java használatával

Az alábbi lépésről‑lépésre útmutató pontosan bemutatja, hogyan hozhat létre és testreszabhat egy kördiagramot.

### 1. lépés: A prezentáció inicializálása
Először hozzon létre egy új `Presentation` objektumot. Ez egy üres PowerPoint fájlt reprezentál.
```java
Presentation pres = new Presentation();
```

### 2. lépés: A kördiagram hozzáadása
Helyezzen be egy kördiagramot az első diára. A (50, 50) koordináták és a (600 × 400) méret jól működik egy szabványos 16:9-es dián.
```java
pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
```

### 3. lépés: A prezentáció mentése
Írja a prezentációt a lemezre. Cserélje le a `YOUR_OUTPUT_DIRECTORY`-t arra a mappára, ahová a fájlt menteni szeretné.
```java
pres.save("YOUR_OUTPUT_DIRECTORY/output.pptx", SaveFormat.Pptx);
```

### 4. lépés: Erőforrások tisztítása
Felszabadítja a `Presentation` objektumot a natív erőforrások felszabadításához.
```java
if (pres != null) pres.dispose();
```

## Az adatpont robbanás és szín testreszabása

Az egyes szeletek testreszabása könnyebbé teszi a diagram olvasását, különösen ha egy adott értéket szeretne kiemelni.

### 1. lépés: Létező prezentáció betöltése (vagy az imént létrehozott újrahasználata)
```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

### 2. lépés: A diagram és a cél adatpont elérése
Itt a második adatpontot (index 1) nyerjük ki az első sorozatból.
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 600, 400);
IChartDataPoint point = chart.getChartData().getSeries().get_Item(0).getDataPoints().get_Item(1);
```

### 3. lépés: Robbanás és szín alkalmazása
Vizuálisan elkülöníti a szeletet, és megváltoztatja a kitöltő színét kékre.
```java
point.setExplosion(30); // Set explosion distance
point.getFormat().getFill().setFillType(FillType.Solid);
point.getFormat().getFill().getSolidFillColor().setColor(Color.BLUE); // Change fill color
```

### 4. lépés: Mentés és felszabadítás
```java
pres.save("YOUR_OUTPUT_DIRECTORY/customized.pptx", SaveFormat.Pptx);
if (pres != null) pres.dispose();
```

## Gyakorlati alkalmazások
- **Értékesítési jelentések:** Kiemeli a legjobban eladott termékeket robbantott szeletekkel.  
- **Költségvetés elemzése:** Különböző színeket rendel az osztályokhoz a gyors vizuális összehasonlítás érdekében.  
- **Oktatási diák:** Bontja le a komplex koncepciókat könnyen emészthető diagramrészletekre.

## Teljesítmény szempontok
- **Objektumok felszabadítása** gyorsan a memória szivárgások elkerülése érdekében, különösen ha sok diát generál egy ciklusban.  
- **Halomhasználat figyelése** nagy prezentációk esetén; fontolja meg a kimenet streamelését a `Save` túlterhelésekkel, amelyek `OutputStream`-et fogadnak.  
- Tartsa meg a **JDK 16+** verziót, hogy élvezze a legújabb szemétgyűjtési fejlesztéseket.

## Összegzés
Most már rendelkezik egy teljes, termelésre kész munkafolyammal a **kördiagram PowerPoint** fájlok hozzáadásához az Aspose.Slides for Java használatával. Kísérletezzen különböző robbanási távolságokkal, színekkel és adatkészletekkel, hogy illeszkedjen a márkájához. Amikor készen áll, fedezze fel a többi diagramtípust – oszlop, vonal vagy szórt – hogy egy teljes analitikai műszerfalat építsen a PowerPointba.

## GYIK szekció
1. **Mi a fő előnye az Aspose.Slides for Java használatának?**  
   - Egyszerűsíti a PowerPoint fájlok programozott létrehozását és manipulálását, számos funkciót kínálva.  
2. **Testreszabhatok más diagramtípusokat az Aspose.Slides segítségével?**  
   - Természetesen! Az Aspose.Slides különféle diagramtípusokat támogat, például oszlop, vonal és szórt diagramokat.  
3. **Hogyan kezelem a több diát diagramok létrehozásakor?**  
   - Az egyes diákat index szerint érheti el a `get_Item()` metódussal, hogy változtatásokat alkalmazzon a különböző diákon.  
4. **Mi a teendő, ha a kördiagram nem jelenik meg helyesen a testreszabás után?**  
   - Ellenőrizze a `addChart()`‑ben használt koordinátákat és méreteket, hogy azok illeszkednek‑e a diák elrendezésébe.  
5. **Hol találhatok további fejlett funkciókat az Aspose.Slides‑hez?**  
   - Tekintse meg a [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/) oldalt, hogy többet megtudjon a további funkciókról és lehetőségekről.

## Erőforrások
- **Dokumentáció:** [Aspose.Slides Java Docs](https://reference.aspose.com/slides/java/)  
- **Könyvtár letöltése:** [Aspose Releases](https://releases.aspose.com/slides/java/)  
- **Licenc vásárlása:** [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Ingyenes próba:** [Try Aspose.Slides](https://releases.aspose.com/slides/java/)  
- **Ideiglenes licenc:** [Request Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Támogatási fórum:** [Aspose Support](https://forum.aspose.com/c/slides/11)

---

**Utoljára frissítve:** 2026-02-17  
**Tesztelve:** Aspose.Slides for Java 25.4 (JDK 16 classifier)  
**Szerző:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}