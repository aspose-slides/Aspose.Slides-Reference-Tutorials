---
title: A PowerPoint mentése alapértelmezett normál betűtípussal Java használatával
linktitle: A PowerPoint mentése alapértelmezett normál betűtípussal Java használatával
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan kezelheti programozottan a PowerPoint-prezentációkat az Aspose.Slides for Java segítségével. Sajátítsa el a Java PowerPoint kezelését lépésről-lépésre bemutató oktatóanyagokkal.
weight: 12
url: /hu/java/java-powerpoint-text-font-customization/save-powerpoint-default-regular-font-java/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# A PowerPoint mentése alapértelmezett normál betűtípussal Java használatával

## Bevezetés
A Java fejlesztés területén a PowerPoint prezentációk programozott létrehozása és kezelése nagymértékben növelheti a termelékenységet és a testreszabási lehetőségeket. Az Aspose.Slides for Java egy robusztus könyvtár, amely lehetővé teszi a fejlesztők számára a PowerPoint fájlok hatékony kezelését, és a szolgáltatások átfogó készletét kínálja az egyszerű módosításoktól a bonyolult prezentációkig.
## Előfeltételek
Mielőtt belevágna az Aspose.Slides for Java használatába, győződjön meg arról, hogy beállította a következő előfeltételeket:
1. Java Development Kit (JDK): Az Aspose.Slides for Java megfelelő működéséhez a JDK 1.8 vagy újabb verziója szükséges.
2. Aspose.Slides for Java JAR: Töltse le az Aspose.Slides for Java legújabb verzióját innen:[itt](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Használja az IntelliJ IDEA-t, az Eclipse-t vagy egy másik választott Java IDE-t.
4. A Java alapvető ismerete: A Java programozási nyelv alapjainak ismerete szükséges.

## Csomagok importálása
Az Aspose.Slides for Java használatának megkezdéséhez importálja a szükséges csomagokat:
```java
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.PdfOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```
Ez biztosítja, hogy hozzáférjen az Aspose.Slides for Java által biztosított összes osztályhoz és metódushoz.
## 1. lépés: Állítsa be projektjét
Először hozzon létre egy új Java-projektet az IDE-ben, és foglalja bele az Aspose.Slides for Java JAR fájlt a projekt felépítési útvonalába.
## 2. lépés: Inicializálja a bemutató objektumot
 Példányosítás a`Presentation` objektumot egy meglévő PowerPoint-fájl (.pptx) betöltésével a helyi könyvtárból.
```java
String dataDir = "Your Document Directory";
String outPath = "Your Output Directory";
// Bemutató betöltése
Presentation pres = new Presentation(dataDir + "DefaultFonts.pptx");
```
 Cserélje ki`"Your Document Directory"` és`"Your Output Directory"` a tényleges fájlútvonalakkal.
## 3. lépés: Mentse el a bemutatót az alapértelmezett normál betűtípusokkal
 Adja meg az alapértelmezett normál betűtípust a kimeneti formátumokhoz (HTML és PDF) a használatával`HtmlOptions` és`PdfOptions` illetőleg.
```java
try {
    // HTML mentési beállítások
    HtmlOptions htmlOpts = new HtmlOptions();
    htmlOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.html", SaveFormat.Html, htmlOpts);
    htmlOpts.setDefaultRegularFont("Lucida Console");
    pres.save(outPath + "Presentation-out-LucidaConsole.html", SaveFormat.Html, htmlOpts);
    // PDF mentési lehetőségek
    PdfOptions pdfOpts = new PdfOptions();
    pdfOpts.setDefaultRegularFont("Arial Black");
    pres.save(outPath + "Presentation-out-ArialBlack.pdf", SaveFormat.Pdf, pdfOpts);
} finally {
    if (pres != null) pres.dispose();
}
```
 Győződjön meg a cseréről`"Arial Black"` és`"Lucida Console"` a kívánt alapértelmezett normál betűtípusokkal.

## Következtetés
Az alábbi lépések követésével megtanulta, hogyan kezelheti hatékonyan a PowerPoint-prezentációkat az Aspose.Slides for Java használatával. Ez a képesség lehetővé teszi a feladatok automatizálását, a prezentációk testreszabását és a Java-alkalmazások fejlesztését fejlett PowerPoint kezelési funkciókkal.
## GYIK
### Működhet az Aspose.Slides for Java a JDK régebbi verzióival?
Az Aspose.Slides for Java kompatibilitásához a JDK 1.8 vagy újabb verziója szükséges.
### Hogyan szerezhetek ideiglenes licencet az Aspose.Slides for Java számára?
 Ideiglenes jogosítványt szerezhet be[itt](https://purchase.aspose.com/temporary-license/).
### Hol találok részletesebb dokumentációt az Aspose.Slides for Java-ról?
 Tekintse meg az átfogó dokumentációt[itt](https://reference.aspose.com/slides/java/).
### Elérhető közösségi támogatás az Aspose.Slides for Java számára?
 Igen, kaphat közösségi támogatást[itt](https://forum.aspose.com/c/slides/11).
### Kipróbálhatom ingyenesen az Aspose.Slides for Java programot?
 Igen, tölts le egy ingyenes próbaverziót[itt](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
