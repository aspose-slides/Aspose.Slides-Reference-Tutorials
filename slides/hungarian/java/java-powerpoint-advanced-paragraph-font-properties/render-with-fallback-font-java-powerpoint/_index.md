---
title: Rendereljen vissza tartalék betűtípussal a Java PowerPointban
linktitle: Rendereljen vissza tartalék betűtípussal a Java PowerPointban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan lehet szöveget renderelni tartalék betűtípusokkal Java PowerPoint prezentációkban az Aspose.Slides segítségével. Kövesse ezt a lépésről lépésre szóló útmutatót a zökkenőmentes megvalósítás érdekében.
type: docs
weight: 13
url: /hu/java/java-powerpoint-advanced-paragraph-font-properties/render-with-fallback-font-java-powerpoint/
---
## Bevezetés
A PowerPoint prezentációk létrehozása és kezelése Java nyelven kihívást jelenthet, de az Aspose.Slides segítségével ezt hatékonyan megteheti. Az egyik kulcsfontosságú funkció a szöveg tartalék betűtípusokkal történő megjelenítése. Ez a cikk részletes, lépésenkénti útmutatót tartalmaz a tartalék betűtípusok PowerPoint-diákba való implementálásához az Aspose.Slides for Java használatával.
## Előfeltételek
Mielőtt belemerülnénk a megvalósításba, győződjünk meg arról, hogy mindennel rendelkezik, amire szüksége van:
1. Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a rendszeren.
2.  Aspose.Slides for Java: Letöltheti a[Aspose.Slides for Java letöltési oldal](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Az olyan IDE, mint az IntelliJ IDEA vagy az Eclipse, simábbá teszi a fejlesztési folyamatot.
4. Függőségek: Az Aspose.Slides szerepeltetése a projekt függőségei között.
## Csomagok importálása
Először is importálnunk kell a szükséges csomagokat a Java programunkba.
```java
import com.aspose.slides.*;
import javax.imageio.ImageIO;
import java.awt.image.BufferedImage;
import java.io.File;
import java.io.IOException;
```
Bontsuk fel a folyamatot kezelhető lépésekre.
## 1. lépés: Állítsa be projektjét
 Mielőtt bármilyen kódot írna, győződjön meg arról, hogy a projekt megfelelően van beállítva. Ez magában foglalja az Aspose.Slides könyvtár hozzáadását a projekthez. Ezt úgy teheti meg, hogy letölti a könyvtárat innen[Aspose.Slides a Java számára](https://releases.aspose.com/slides/java/) és hozzáadja az építési útvonalához.
## 2. lépés: Inicializálja a Font-visszaállítási szabályokat
 Létre kell hoznia egy példányt a`IFontFallBackRulesCollection` osztályt, és adjunk hozzá szabályokat. Ezek a szabályok határozzák meg a tartalék betűkészleteket bizonyos Unicode-tartományokhoz.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy szabálygyűjtemény új példányát
IFontFallBackRulesCollection rulesList = new FontFallBackRulesCollection();
// Hozzon létre számos szabályt
rulesList.add(new FontFallBackRule(0x0400, 0x04FF, "Times New Roman"));
```
## 3. lépés: Módosítsa a tartalék szabályokat
Ebben a lépésben módosítani fogjuk a tartalék szabályokat a meglévő tartalék betűtípusok eltávolításával és az egyes Unicode-tartományokra vonatkozó szabályok frissítésével.
```java
for (IFontFallBackRule fallBackRule : rulesList) {
    // Megpróbálja eltávolítani a "Tahoma" FallBack betűtípust a betöltött szabályok közül
    fallBackRule.remove("Tahoma");
    // Frissítse a megadott tartomány szabályait
    if ((fallBackRule.getRangeEndIndex() >= 0x4000) && (fallBackRule.getRangeStartIndex() < 0x5000)) {
        fallBackRule.addFallBackFonts("Verdana");
    }
}
//Távolítson el minden létező szabályt a listáról
if (rulesList.size() > 0) {
    rulesList.remove(rulesList.get_Item(0));
}
```
## 4. lépés: Töltse be a prezentációt
Töltse be a módosítani kívánt PowerPoint-prezentációt.
```java
Presentation pres = new Presentation(dataDir + "input.pptx");
```
## 5. lépés: Rendeljen tartalék szabályokat a prezentációhoz
Rendelje hozzá az elkészített tartalék szabályokat a prezentáció betűkészlet-kezelőjéhez.
```java
try {
    // Az elkészített szabálylista felhasználásra való hozzárendelése
    pres.getFontsManager().setFontFallBackRulesCollection(rulesList);
    // Bélyegkép megjelenítése az inicializált szabálygyűjtemény használatával és mentése PNG-be
    BufferedImage image = pres.getSlides().get_Item(0).getThumbnail(1f, 1f);
    ImageIO.write(image, "png", new File(dataDir + "Slide_0.png"));
} catch (IOException e) {
    e.printStackTrace();
} finally {
    if (pres != null) pres.dispose();
}
```
## 6. lépés: Mentés és tesztelés
Végül mentse el munkáját, és tesztelje a megvalósítást, hogy minden a várt módon működjön. Ha bármilyen problémába ütközik, ellenőrizze újra a beállítást, és győződjön meg arról, hogy az összes függőséget helyesen adta hozzá.
## Következtetés
Az útmutató követésével hatékonyan renderelhet szöveget tartalék betűtípusokkal a PowerPoint-prezentációkban az Aspose.Slides for Java használatával. Ez a folyamat biztosítja, hogy prezentációi konzisztens formázással rendelkezzenek, még akkor is, ha az elsődleges betűtípusok nem állnak rendelkezésre. Boldog kódolást!
## GYIK
### Mi az Aspose.Slides for Java?
Az Aspose.Slides for Java egy olyan könyvtár, amely lehetővé teszi a fejlesztők számára, hogy PowerPoint prezentációkat hozzanak létre, módosítsanak és rendereljenek Java alkalmazásokban.
### Hogyan adhatom hozzá az Aspose.Slides-t a projektemhez?
 A könyvtár letölthető a[Aspose.Slides letöltési oldal](https://releases.aspose.com/slides/java/) és adja hozzá a projekt felépítési útvonalához.
### Mik azok a tartalék betűtípusok?
A tartalék betűtípusok alternatív betűtípusok, amelyeket akkor használnak, ha a megadott betűtípus nem elérhető, vagy nem támogat bizonyos karaktereket.
### Használhatok több tartalék szabályt?
Igen, több tartalék szabályt is felvehet a különböző Unicode-tartományok és betűtípusok kezelésére.
### Hol kaphatok támogatást az Aspose.Slides-hez?
 Támogatást kaphat a[Aspose.Slides támogatási fórum](https://forum.aspose.com/c/slides/11).