---
"description": "PowerPoint prezentációk HTML-be konvertálása az eredeti betűtípusok megőrzésével az Aspose.Slides for Java segítségével."
"linktitle": "Prezentáció HTML-be konvertálása az eredeti betűtípusok megőrzésével Java diákban"
"second_title": "Aspose.Slides Java PowerPoint feldolgozó API"
"title": "Prezentáció HTML-be konvertálása az eredeti betűtípusok megőrzésével Java diákban"
"url": "/hu/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Prezentáció HTML-be konvertálása az eredeti betűtípusok megőrzésével Java diákban


## Bevezetés a prezentációk HTML-be konvertálásához az eredeti betűtípusok megőrzésével Java diákban

Ebben az oktatóanyagban azt vizsgáljuk meg, hogyan lehet egy PowerPoint prezentációt (PPTX) HTML-be konvertálni az eredeti betűtípusok megőrzése mellett az Aspose.Slides for Java segítségével. Ez biztosítja, hogy a kapott HTML megjelenése szorosan hasonlítson az eredeti prezentáció megjelenésére.

## 1. lépés: A projekt beállítása
Mielőtt belemerülnénk a kódba, ellenőrizzük, hogy megvannak-e a szükséges beállítások:

1. Aspose.Slides letöltése Java-hoz: Ha még nem tetted meg, töltsd le és építsd be az Aspose.Slides for Java könyvtárat a projektedbe.

2. Java projekt létrehozása: Hozz létre egy Java projektet a kedvenc IDE-dben, és győződj meg róla, hogy van egy "lib" mappa, ahová elhelyezheted az Aspose.Slides JAR fájlt.

3. Szükséges osztályok importálása: Importálja a szükséges osztályokat a Java fájl elejéről:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 2. lépés: Prezentáció konvertálása HTML-be eredeti betűtípusokkal

Most konvertáljunk egy PowerPoint bemutatót HTML-be az eredeti betűtípusok megőrzése mellett:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Töltsd be a prezentációt
Presentation pres = new Presentation("input.pptx");

try {
    // Az alapértelmezett prezentációs betűtípusok, például a Calibri és az Arial kizárása
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // HTML-beállítások létrehozása és egyéni HTML-formázó beállítása
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Mentse el a prezentációt HTML formátumban
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // A prezentációs objektum eltávolítása
    if (pres != null) pres.dispose();
}
```

Ebben a kódrészletben:

- A bemeneti PowerPoint prezentációt a következővel töltjük be: `Presentation`.

- Definiálunk egy betűtípuslistát (`fontNameExcludeList`), amelyeket ki szeretnénk zárni a HTML-be való beágyazásból. Ez akkor hasznos, ha ki szeretnénk zárni az olyan gyakori betűtípusokat, mint a Calibri és az Arial, és így csökkenteni szeretnénk a fájlméretet.

- Létrehozunk egy példányt `EmbedAllFontsHtmlController` és adja át neki a betűtípus-kizárási listát.

- Alkotunk `HtmlOptions` és állítson be egyéni HTML formázót a következővel: `HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Végül HTML formátumban mentjük el a prezentációt a megadott beállításokkal.

## Teljes forráskód a prezentációk HTML-be konvertálásához az eredeti betűtípusok megőrzésével Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// alapértelmezett prezentációs betűtípusok kizárása
	String[] fontNameExcludeList = {"Calibri", "Arial"};
	EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
	HtmlOptions htmlOptionsEmbed = new HtmlOptions();
	htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
	pres.save("input-PFDinDisplayPro-Regular-installed.html", SaveFormat.Html, htmlOptionsEmbed);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Következtetés

Ebben az oktatóanyagban megtanultad, hogyan konvertálhatsz egy PowerPoint bemutatót HTML-be az eredeti betűtípusok megőrzése mellett az Aspose.Slides for Java segítségével. Ez akkor hasznos, ha meg szeretnéd őrizni a bemutatóid vizuális hűségét, amikor megosztod őket a weben.

## GYIK

### Hogyan tölthetem le az Aspose.Slides programot Java-hoz?

Az Aspose.Slides Java-verzióját letöltheted az Aspose weboldaláról. Látogass el ide: [itt](https://downloads.aspose.com/slides/java/) hogy a legújabb verziót szerezd be.

### Testreszabhatom a kizárt betűtípusok listáját?

Igen, testreszabhatja a `fontNameExcludeList` tömb, hogy az igényeidnek megfelelően bizonyos betűtípusokat tartalmazzon vagy kizárjon.

### Ez a módszer működik régebbi PowerPoint formátumokkal, például a PPT-vel?

Ez a kódpélda PPTX fájlokhoz készült. Ha régebbi PPT fájlokat kell konvertálnia, előfordulhat, hogy módosítania kell a kódot.

### Hogyan tudom tovább testreszabni a HTML kimenetet?

Felfedezheted a `HtmlOptions` osztály a HTML-kimenet különböző aspektusainak testreszabásához, például a dia méretének, a képminőségnek és egyebeknek.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}