---
title: Formázza a táblázaton belüli szöveget a PowerPointban Java használatával
linktitle: Formázza a táblázaton belüli szöveget a PowerPointban Java használatával
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ebből az oktatóanyagból megtudhatja, hogyan formázhat szöveget a táblázat oszlopaiban a PowerPointban az Aspose.Slides for Java segítségével. Fejlessze prezentációit programozottan.
weight: 11
url: /hu/java/java-powerpoint-table-formatting-updates/format-text-inside-table-column-powerpoint-java/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Bevezetés
Készen állsz, hogy belemerülj a PowerPoint-prezentációk világába, de egy csavarral? A diák kézi formázása helyett válasszunk egy hatékonyabb utat az Aspose.Slides for Java használatával. Ez az oktatóanyag végigvezeti a PowerPoint-prezentációk táblázatoszlopaiban lévő szövegek programozott formázásának folyamatán. Kapcsold be, mert ez egy jó móka lesz!
## Előfeltételek
Mielőtt elkezdenénk, van néhány dolog, amire szüksége lesz:
1.  Java Development Kit (JDK): Győződjön meg arról, hogy a JDK telepítve van a gépen. Ha nem, letöltheti innen[Az Oracle webhelye](https://www.oracle.com/java/technologies/javase-jdk11-downloads.html).
2.  Aspose.Slides for Java: Töltse le a legújabb verziót a[Aspose.Slides letöltési oldal](https://releases.aspose.com/slides/java/).
3. Integrált fejlesztői környezet (IDE): Az olyan IDE, mint az IntelliJ IDEA vagy az Eclipse, simábbá teszi a kódolási utat.
4.  PowerPoint-bemutató: Legyen egy PowerPoint-fájlja egy táblázattal, amelyet teszteléshez használhat. Úgy fogjuk hivatkozni`SomePresentationWithTable.pptx`.

## Csomagok importálása
Először állítsuk be a projektet, és importáljuk a szükséges csomagokat. Ez lesz az alapja az oktatóanyagnak.
```java
import com.aspose.slides.*;
```
## 1. lépés: Töltse be a prezentációt
Utunk első lépése a PowerPoint prezentáció betöltése programunkba.
```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// Hozzon létre egy példányt a Prezentáció osztályból
Presentation pres = new Presentation(dataDir + "SomePresentationWithTable.pptx");
```
 Ez a kódsor létrehozza a`Presentation` osztály, amely a PowerPoint fájlunkat képviseli.
## 2. lépés: Nyissa meg a Dia és a táblázatot
Ezután el kell érnünk a diát és a dián belüli táblázatot. Az egyszerűség kedvéért tegyük fel, hogy a táblázat az első alakzat az első dián.
### Nyissa meg az első diát
```java
ISlide slide = pres.getSlides().get_Item(0);
```
Ez a sor az első diát kéri le a prezentációból.
### Nyissa meg a táblázatot
```java
ITable someTable = (ITable) slide.getShapes().get_Item(0);
```
Itt az első dián lévő első alakzatot érjük el, amelyről feltételezzük, hogy a mi táblázatunk.
## 3. lépés: Állítsa be a betűmagasságot az első oszlophoz
Most állítsuk be a táblázat első oszlopában lévő szöveg betűmagasságát.
```java
PortionFormat portionFormat = new PortionFormat();
portionFormat.setFontHeight(25);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
 Ezekben a sorokban definiáljuk a`PortionFormat` objektumot, hogy a betűmagasságot 25 pontra állítsa az első oszlopban.
## 4. lépés: Igazítsa a szöveget jobbra
A szövegigazítás nagy változást hozhat a diák olvashatóságában. Igazítsuk jobbra a szöveget az első oszlopban.

```java
ParagraphFormat paragraphFormat = new ParagraphFormat();
paragraphFormat.setAlignment(TextAlignment.Right);
paragraphFormat.setMarginRight(20);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
 Itt használjuk a`ParagraphFormat` objektum segítségével állítsa be a szöveg igazítását jobbra, és adjon hozzá egy 20-as jobb margót.
## 5. lépés: Állítsa be a szöveg függőleges típusát
A szöveg egyedi tájolása érdekében beállíthatjuk a szöveg függőleges típusát.
```java
TextFrameFormat textFrameFormat = new TextFrameFormat();
textFrameFormat.setTextVerticalType(TextVerticalType.Vertical);
someTable.getColumns().get_Item(0).setTextFormat(portionFormat);
```
Ez a részlet függőlegesre állítja a szöveg tájolását az első oszlopban.
## 6. lépés: Mentse el a bemutatót
Végül az összes formázási változtatást követően el kell mentenünk a módosított prezentációt.
```java
pres.save(dataDir + "result.pptx", SaveFormat.Pptx);
```
 Ez a parancs elmenti a prezentációt az új formátumban, amely egy nevű fájlra van alkalmazva`result.pptx`.

## Következtetés
Tessék, itt van! Éppen most formázta meg a szöveget egy táblázat oszlopában egy PowerPoint-prezentációban az Aspose.Slides for Java segítségével. A feladatok automatizálásával időt takaríthat meg, és biztosíthatja a prezentációk egységességét. Boldog kódolást!
## GYIK
### Formázhatok több oszlopot egyszerre?
Igen, ugyanazt a formázást több oszlopra is alkalmazhatja, ha végignézi őket, és beállítja a kívánt formátumokat.
### Az Aspose.Slides kompatibilis a PowerPoint összes verziójával?
Az Aspose.Slides PowerPoint formátumok széles skáláját támogatja, biztosítva a kompatibilitást a legtöbb verzióval.
### Hozzáadhatok más típusú formázást az Aspose.Slides segítségével?
Teljesen! Az Aspose.Slides kiterjedt formázási lehetőségeket tesz lehetővé, beleértve a betűstílusokat, színeket és egyebeket.
### Hogyan juthatok hozzá az Aspose.Slides ingyenes próbaverziójához?
 Ingyenes próbaverziót letölthet a webhelyről[Aspose ingyenes próbaoldal](https://releases.aspose.com/).
### Hol találok további példákat és dokumentációt?
 Nézze meg a[Aspose.Slides dokumentáció](https://reference.aspose.com/slides/java/) részletes példákért és útmutatókért.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
