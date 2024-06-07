---
title: Mentés előre meghatározott nézettípusként a Java Slides alkalmazásban
linktitle: Mentés előre meghatározott nézettípusként a Java Slides alkalmazásban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Ismerje meg, hogyan állíthat be előre meghatározott nézettípusokat a Java Slides alkalmazásban az Aspose.Slides for Java segítségével. Lépésről lépésre, kódpéldákkal és GYIK-vel.
type: docs
weight: 10
url: /hu/java/saving-options/save-as-predefined-view-type-in-java-slides/
---

## Bevezetés az előre meghatározott nézettípusként történő mentéshez a Java Slides alkalmazásban

Ebben a lépésről lépésre bemutatjuk, hogyan menthetünk el egy prezentációt előre meghatározott nézettípussal az Aspose.Slides for Java segítségével. A feladat sikeres végrehajtásához megadjuk a szükséges kódot és magyarázatokat.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy rendelkezik a következőkkel:

- Java programozási alapismeretek.
- Aspose.Slides for Java könyvtár telepítve.
- Ön által választott integrált fejlesztői környezet (IDE).

## Környezetének beállítása

A kezdéshez kövesse az alábbi lépéseket a fejlesztői környezet beállításához:

1. Hozzon létre egy új Java-projektet az IDE-ben.
2. Adja hozzá az Aspose.Slides for Java könyvtárat a projekthez függőségként.

Most, hogy a környezet be van állítva, folytassuk a kóddal.

## 1. lépés: Prezentáció készítése

Egy prezentáció előre meghatározott nézettípussal történő mentésének demonstrálásához először létrehozunk egy új bemutatót. Íme a kód a prezentáció létrehozásához:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// A bemutató fájl megnyitása
Presentation presentation = new Presentation();
```

 Ebben a kódban létrehozunk egy újat`Presentation` objektum, amely a PowerPoint bemutatónkat képviseli.

## 2. lépés: A nézet típusának beállítása

Ezután beállítjuk a bemutatónk nézettípusát. A nézettípusok határozzák meg, hogy a prezentáció hogyan jelenjen meg megnyitáskor. Ebben a példában "Slide Master View"-ra állítjuk. Íme a kód:

```java
// Nézettípus beállítása
presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
```

 A fenti kódban a`setLastView` módszere a`ViewProperties` osztályban a nézet típusának beállításához`SlideMasterView`. Igény szerint más nézettípusokat is választhat.

## 3. lépés: A prezentáció mentése

Most, hogy elkészítettük a bemutatónkat és beállítottuk a nézet típusát, ideje elmenteni a bemutatót. Elmentjük PPTX formátumban. Íme a kód:

```java
// Prezentáció mentése
presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
```

 Ebben a kódban a`save` módszere a`Presentation` osztályba, hogy elmentse a prezentációt a megadott fájlnévvel és formátummal.

## Teljes forráskód az előre meghatározott nézettípusként történő mentéshez a Java Slides-ben

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
// A bemutató fájl megnyitása
Presentation presentation = new Presentation();
try
{
	// Nézettípus beállítása
	presentation.getViewProperties().setLastView(ViewType.SlideMasterView);
	// Prezentáció mentése
	presentation.save(dataDir + "SetViewType_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan menthetünk el egy prezentációt előre meghatározott nézettípussal Java nyelven az Aspose.Slides for Java segítségével. A megadott kód és lépések követésével könnyedén beállíthatja prezentációinak nézettípusát, és elmentheti azokat a kívánt formátumban.

## GYIK

### Hogyan módosíthatom a nézet típusát a „Slide Master View” helyett?

 Ha a nézet típusát a „Slide Master View” helyett másra szeretné módosítani, egyszerűen cserélje ki`ViewType.SlideMasterView` a kívánt nézettípussal, mint pl`ViewType.NormalView` vagy`ViewType.SlideSorterView`, abban a kódban, ahol beállítottuk a nézet típusát.

### Beállíthatom a nézet tulajdonságait a prezentáció egyes diákjaihoz?

Igen, az Aspose.Slides for Java segítségével beállíthatja az egyes diák nézettulajdonságait. Az egyes diák tulajdonságait külön-külön érheti el és módosíthatja a bemutató diákjai között.

### Milyen más formátumokba menthetem a prezentációmat?

Az Aspose.Slides for Java különféle kimeneti formátumokat támogat, beleértve a PPTX, PDF, TIFF, HTML és egyebeket. A megfelelő formátum használatával megadhatja a kívánt formátumot a prezentáció mentésekor`SaveFormat` enum érték.

### Az Aspose.Slides for Java alkalmas prezentációk kötegelt feldolgozására?

Igen, az Aspose.Slides for Java kiválóan alkalmas kötegelt feldolgozási feladatokra. Több prezentáció feldolgozását automatizálhatja, módosításokat alkalmazhat, és tömegesen mentheti őket Java kóddal.

### Hol találok további információt és dokumentációt az Aspose.Slides for Java programhoz?

 Az Aspose.Slides for Java-hoz kapcsolódó átfogó dokumentációért és hivatkozásokért látogasson el a dokumentációs webhelyre:[Aspose.Slides a Java dokumentációhoz](https://reference.aspose.com/slides/java/).