---
title: Bemutató diavetítés beállítása Java Slides-ben
linktitle: Bemutató diavetítés beállítása Java Slides-ben
second_title: Aspose.Slides Java PowerPoint Processing API
description: Optimalizálja Java diavetítését az Aspose.Slides segítségével. Hozzon létre lenyűgöző prezentációkat testreszabott beállításokkal. Fedezze fel a lépésenkénti útmutatókat és a GYIK-et.
weight: 16
url: /hu/java/presentation-properties/presentation-slide-show-setup-in-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Bemutató diavetítés beállítása Java Slides-ben


## Bevezetés a Java Slides bemutató diavetítés beállításába

Ebben az oktatóanyagban megvizsgáljuk, hogyan állíthat be bemutató diavetítést az Aspose.Slides for Java használatával. Lépésről lépésre végigjárjuk a PowerPoint prezentáció létrehozásának és a különböző diavetítés-beállítások konfigurálásának folyamatát.

## Előfeltételek

 Mielőtt elkezdené, győződjön meg arról, hogy az Aspose.Slides for Java könyvtár hozzáadva van a projekthez. Letöltheti a[Aspose honlapja](https://releases.aspose.com/slides/java/).

## 1. lépés: Hozzon létre egy PowerPoint-bemutatót

Először is létre kell hoznunk egy új PowerPoint bemutatót. Java-ban a következőképpen teheti meg:

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
```

 A fenti kódban megadjuk prezentációnk kimeneti fájljának elérési útját, és létrehozunk egy újat`Presentation` tárgy.

## 2. lépés: Konfigurálja a diavetítés beállításait

Ezután különféle diavetítés-beállításokat konfigurálunk a bemutatónkhoz. 

### Időzítési paraméter használata

Az "Időzítés használata" paraméterrel szabályozhatjuk, hogy a diavetítés során automatikusan vagy manuálisan haladjanak-e a diak.

```java
SlideShowSettings slideShow = pres.getSlideShowSettings();
slideShow.setUseTimings(false); // Állítsa be hamisra a kézi előrelépéshez
```

 Ebben a példában azt állítottuk be`false` hogy lehetővé tegye a diák kézi mozgatását.

### Állítsa be a toll színét

A diavetítés során használt tollszínt is testreszabhatja. Ebben a példában a toll színét zöldre állítjuk.

```java
IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
penColor.setColor(Color.GREEN);
```

### Diák hozzáadása

Adjunk hozzá néhány diát bemutatónkhoz. A dolgok egyszerűsége érdekében klónozunk egy meglévő diát.

```java
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
pres.getSlides().addClone(pres.getSlides().get_Item(0));
```

Ebben a kódban négyszer klónozzuk az első diát. Ezt a részt módosíthatja saját tartalom hozzáadásához.

## 3. lépés: Adja meg a diatartományt a diavetítéshez

Megadhatja, hogy mely diák szerepeljenek a diavetítésben. Ebben a példában egy diatartományt állítunk be a második diától az ötödik diáig.

```java
SlidesRange slidesRange = new SlidesRange();
slidesRange.setStart(2);
slidesRange.setEnd(5);
slideShow.setSlides(slidesRange);
```

kezdő és záró diaszámok beállításával szabályozhatja, hogy mely diák legyenek a diavetítés részei.

## 4. lépés: Mentse el a bemutatót

Végül a beállított prezentációt elmentjük egy fájlba.

```java
pres.save(outPptxPath, SaveFormat.Pptx);
```

Ügyeljen arra, hogy megadja a kívánt kimeneti fájl elérési utat.

## Teljes forráskód a bemutató diavetítés beállításához a Java Slides-ben

```java
String outPptxPath = "Your Output Directory" + "PresentationSlideShowSetup.pptx";
Presentation pres = new Presentation();
try {
	// Lekéri a diavetítés beállításait
	SlideShowSettings slideShow = pres.getSlideShowSettings();
	// Beállítja az „Időzítés használata” paramétert
	slideShow.setUseTimings(false);
	// Beállítja a toll színét
	IColorFormat penColor = (ColorFormat)slideShow.getPenColor();
	penColor.setColor(Color.GREEN);
	// Diák hozzáadása ehhez
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	pres.getSlides().addClone(pres.getSlides().get_Item(0));
	// Beállítja a Dia megjelenítése paramétert
	SlidesRange slidesRange = new SlidesRange();
	slidesRange.setStart(2);
	slidesRange.setEnd(5);
	slideShow.setSlides(slidesRange);
	// Prezentáció mentése
	pres.save(outPptxPath, SaveFormat.Pptx);
} finally {
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultuk, hogyan állíthat be bemutató diavetítést Java nyelven az Aspose.Slides for Java használatával. A különböző diavetítés-beállításokat testreszabhatja, beleértve az időzítést, a toll színét és a diatartományt, hogy interaktív és lebilincselő prezentációkat készítsen.

## GYIK

### Hogyan módosíthatom a diaátmenetek időzítését?

 A diaátmenetek időzítésének módosításához módosíthatja az „Időzítés használata” paramétert a diavetítés beállításainál. Állítsa be`true` automatikus előrelépéshez előre meghatározott időzítésekkel ill`false`kézi előrelépéshez diavetítés közben.

### Hogyan szabhatom testre a diavetítés során használt toll színét?

 Testreszabhatja a toll színét a diavetítés beállításaiban található tollszínbeállítások elérésével. Használja a`setColor` módszerrel állíthatja be a kívánt színt. Például a toll színének zöldre állításához használja a`penColor.setColor(Color.GREEN)`.

### Hogyan adhatok hozzá adott diákat a diavetítéshez?

 Ha konkrét diákat szeretne bevonni a diavetítésbe, hozzon létre a`SlidesRange` objektumot, és állítsa be a dia kezdő és záró számát a segítségével`setStart` és`setEnd` mód. Ezután rendelje hozzá ezt a tartományt a diavetítés beállításaihoz a segítségével`slideShow.setSlides(slidesRange)`.

### Hozzáadhatok több diát a prezentációhoz?

 Igen, további diákat is hozzáadhat a prezentációhoz. Használja a`pres.getSlides().addClone()` módszer a meglévő diák klónozására vagy szükség szerint új diák létrehozására. Ügyeljen arra, hogy igényei szerint szabja testre ezeknek a diáknak a tartalmát.

### Hogyan menthetem el a beállított prezentációt fájlba?

 A konfigurált bemutató fájlba mentéséhez használja a`pres.save()`módszert, és adja meg a kimeneti fájl elérési útját, valamint a kívánt formátumot. Például elmentheti PPTX formátumban a használatával`pres.save(outPptxPath, SaveFormat.Pptx)`.

### Hogyan szabhatom tovább a diavetítés beállításait?

 Fedezze fel az Aspose.Slides for Java által biztosított további diavetítés-beállításokat, hogy a diavetítés élményét az Ön igényeihez igazítsa. Tekintse meg a dokumentációt a címen[itt](https://reference.aspose.com/slides/java/) az elérhető opciókkal és konfigurációkkal kapcsolatos részletes információkért.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
