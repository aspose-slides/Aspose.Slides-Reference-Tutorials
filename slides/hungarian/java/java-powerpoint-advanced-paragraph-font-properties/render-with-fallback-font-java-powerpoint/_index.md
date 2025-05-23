---
"description": "Tanuld meg, hogyan jeleníthetsz meg szöveget tartalék betűtípusokkal Java PowerPoint prezentációkban az Aspose.Slides segítségével. Kövesd ezt a lépésről lépésre szóló útmutatót a zökkenőmentes megvalósításhoz."
"linktitle": "Tartalék betűtípussal történő renderelés Java PowerPointban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Tartalék betűtípussal történő renderelés Java PowerPointban"
"url": "/hu/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Tartalék betűtípussal történő renderelés Java PowerPointban

## Bevezetés
A PowerPoint-bemutatók létrehozása és kezelése Java nyelven kihívást jelenthet, de az Aspose.Slides segítségével ezt hatékonyan megteheti. Az egyik kulcsfontosságú funkció a szöveg tartalék betűtípusokkal való megjelenítésének lehetősége. Ez a cikk részletes, lépésről lépésre bemutatja, hogyan implementálhat tartalék betűtípusokat PowerPoint-diáiban az Aspose.Slides for Java használatával.
## Előfeltételek
Mielőtt belevágnánk a megvalósításba, győződjünk meg róla, hogy minden szükséges eszközzel rendelkezünk:
1. Java fejlesztőkészlet (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszerén.
2. Aspose.Slides Java-hoz: Letöltheted innen: [Aspose.Slides Java letöltési oldalhoz](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Egy olyan IDE, mint az IntelliJ IDEA vagy az Eclipse, zökkenőmentesebbé teszi a fejlesztési folyamatot.
4. Függőségek: Az Aspose.Slides fájlt is vedd fel a projekted függőségei közé.
## Csomagok importálása
Először is importálnunk kell a szükséges csomagokat a Java programunkba.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Bontsuk le a folyamatot kezelhető lépésekre.
## 1. lépés: A projekt beállítása
Mielőtt bármilyen kódot írnál, győződj meg róla, hogy a projekted megfelelően van beállítva. Ez magában foglalja az Aspose.Slides könyvtár hozzáadását is a projektedhez. Ezt megteheted a könyvtár letöltésével innen: [Aspose.Slides Java-hoz](https://releases.aspose.com/slides/java/) és hozzáadod az építési útvonaladhoz.
## 2. lépés: A betűtípus-tartalék szabályok inicializálása
Létre kell hoznia egy példányt a `IFontFallBackRulesCollection` osztályt, és szabályokat adjunk hozzá. Ezek a szabályok határozzák meg a betűtípus-tartalékokat bizonyos Unicode tartományokhoz.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Szabálygyűjtemény új példányának létrehozása
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Hozz létre néhány szabályt
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## 3. lépés: Tartalék szabályok módosítása
Ebben a lépésben módosítjuk a tartalék szabályokat a meglévő tartalék betűtípusok eltávolításával és az adott Unicode tartományok szabályainak frissítésével.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // "Tahoma" tartalék betűtípus eltávolításának megpróbálása a betöltött szabályok közül
    fallBackRule.remove("Tahoma");
    // A megadott tartományra vonatkozó szabályok frissítése
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
// Távolítson el minden meglévő szabályt a listából
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## 4. lépés: Töltse be a prezentációt
Töltse be a módosítani kívánt PowerPoint bemutatót.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## 5. lépés: Tartalék szabályok hozzárendelése a prezentációhoz
Rendelje hozzá az előkészített tartalék szabályokat a prezentáció betűtípus-kezelőjéhez.
```java
try {
    // Az előkészített szabálylista hozzárendelése használatra
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Inicializált szabálygyűjtemény használatával bélyegkép renderelése és mentése PNG formátumban
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 6. lépés: Mentés és tesztelés
Végül mentsd el a munkádat, és teszteld a megvalósítást, hogy megbizonyosodj arról, hogy minden a várt módon működik. Ha bármilyen problémába ütközöl, ellenőrizd a beállításokat, és győződj meg arról, hogy minden függőség helyesen van hozzáadva.
## Következtetés
Ezt az útmutatót követve hatékonyan jeleníthetsz meg szöveget tartalék betűtípusokkal PowerPoint-bemutatóidban az Aspose.Slides for Java segítségével. Ez a folyamat biztosítja, hogy a bemutatóid formázása egységes maradjon, még akkor is, ha az elsődleges betűtípusok nem érhetők el. Jó kódolást!
## GYIK
### Mi az Aspose.Slides Java-hoz?
Az Aspose.Slides for Java egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára PowerPoint-bemutatók létrehozását, módosítását és megjelenítését Java alkalmazásokban.
### Hogyan adhatok hozzá Aspose.Slides-t a projektemhez?
A könyvtárat letöltheted innen: [Aspose.Slides letöltési oldal](https://releases.aspose.com/slides/java/) és add hozzá a projekted építési útvonalához.
### Mik azok a tartalék betűtípusok?
A tartalék betűtípusok alternatív betűtípusok, amelyeket akkor használunk, ha a megadott betűtípus nem érhető el, vagy nem támogat bizonyos karaktereket.
### Használhatok több tartalék szabályt?
Igen, több tartalék szabályt is hozzáadhat a különböző Unicode-tartományok és betűtípusok kezeléséhez.
### Hol kaphatok támogatást az Aspose.Slides-hez?
Támogatást kaphatsz a [Aspose.Slides támogatási fórum](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}