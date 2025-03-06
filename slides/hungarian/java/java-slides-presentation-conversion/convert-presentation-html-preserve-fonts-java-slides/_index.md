---
title: Prezentáció konvertálása HTML-be az eredeti betűtípusok megőrzésével a Java diákban
linktitle: Prezentáció konvertálása HTML-be az eredeti betűtípusok megőrzésével a Java diákban
second_title: Aspose.Slides Java PowerPoint Processing API
description: Az Aspose.Slides for Java segítségével PowerPoint-prezentációkat alakíthat HTML-formátumba, miközben megőrzi az eredeti betűtípusokat.
weight: 14
url: /hu/java/presentation-conversion/convert-presentation-html-preserve-fonts-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Bevezetés a prezentáció konvertálásába HTML-be az eredeti betűtípusok megőrzésével a Java diákban

Ebben az oktatóanyagban megvizsgáljuk, hogyan konvertálhat PowerPoint prezentációt (PPTX) HTML formátumba, miközben megőrzi az eredeti betűtípusokat az Aspose.Slides for Java használatával. Ez biztosítja, hogy az eredményül kapott HTML nagyon hasonlítson az eredeti prezentáció megjelenésére.

## 1. lépés: A projekt beállítása
Mielőtt belemerülnénk a kódba, győződjünk meg arról, hogy a szükséges beállítások a helyükön vannak:

1. Az Aspose.Slides for Java letöltése: Ha még nem tette meg, töltse le és foglalja bele a projektébe az Aspose.Slides for Java könyvtárat.

2. Java-projekt létrehozása: Állítson be egy Java-projektet kedvenc IDE-jében, és győződjön meg arról, hogy rendelkezik egy "lib" mappával, ahol elhelyezheti az Aspose.Slides JAR fájlt.

3. Szükséges osztályok importálása: Importálja a szükséges osztályokat a Java fájl elejére:

```java
import com.aspose.slides.EmbedAllFontsHtmlController;
import com.aspose.slides.HtmlFormatter;
import com.aspose.slides.HtmlOptions;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## 2. lépés: Prezentáció konvertálása HTML-be eredeti betűtípusokkal

Most konvertáljunk egy PowerPoint-prezentációt HTML-be, miközben megőrizzük az eredeti betűtípusokat:

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";

// Töltse be a prezentációt
Presentation pres = new Presentation("input.pptx");

try {
    // Az alapértelmezett prezentációs betűtípusok, például a Calibri és az Arial kizárása
    String[] fontNameExcludeList = {"Calibri", "Arial"};
    EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
    
    // Hozzon létre HTML-beállításokat, és állítsa be az egyéni HTML-formázót
    HtmlOptions htmlOptionsEmbed = new HtmlOptions();
    htmlOptionsEmbed.setHtmlFormatter(HtmlFormatter.createCustomFormatter(embedFontsController));
    
    // Mentse el a prezentációt HTML-ként
    pres.save("output.html", SaveFormat.Html, htmlOptionsEmbed);
} finally {
    // Dobja el a bemutató objektumot
    if (pres != null) pres.dispose();
}
```

Ebben a kódrészletben:

-  A bemeneti PowerPoint prezentációt a segítségével töltjük be`Presentation`.

- Meghatározzuk a betűtípusok listáját (`fontNameExcludeList`), amelyet ki szeretnénk zárni a HTML-be való beágyazásból. Ez akkor hasznos, ha kizárja az olyan általános betűtípusokat, mint a Calibri és az Arial a fájlméret csökkentése érdekében.

-  Létrehozunk egy példányt`EmbedAllFontsHtmlController` és adja át neki a betűtípus-kizárási listát.

-  Mi alkotunk`HtmlOptions` és állítson be egyéni HTML-formázót a használatával`HtmlFormatter.createCustomFormatter(embedFontsController)`.

- Végül a prezentációt HTML-ként mentjük el a megadott opciókkal.

## Teljes forráskód a prezentáció HTML-be konvertálásához az eredeti betűtípusok megőrzésével a Java diákban

```java
// A dokumentumok könyvtárának elérési útja.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation("input.pptx");
try
{
	// az alapértelmezett megjelenítési betűtípusok kizárása
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

Ebből az oktatóanyagból megtanulta, hogyan alakíthat át PowerPoint-prezentációt HTML-be, miközben megőrzi az eredeti betűtípusokat az Aspose.Slides for Java használatával. Ez akkor hasznos, ha meg szeretné őrizni prezentációinak vizuális hűségét, amikor megosztja azokat az interneten.

## GYIK

### Hogyan tölthetem le az Aspose.Slides for Java programot?

 Az Aspose.Slides for Java letölthető az Aspose webhelyéről. Látogatás[itt](https://downloads.aspose.com/slides/java/) hogy megszerezze a legújabb verziót.

### Testreszabhatom a kizárt betűtípusok listáját?

 Igen, testreszabhatja a`fontNameExcludeList` tömbben, hogy az Ön igényei szerint felvegyen vagy kizárjon bizonyos betűtípusokat.

### Működik ez a módszer régebbi PowerPoint formátumok, például PPT esetén?

Ez a kódpélda PPTX fájlokhoz készült. Ha régebbi PPT-fájlokat kell konvertálnia, előfordulhat, hogy módosítania kell a kódon.

### Hogyan szabhatom tovább a HTML-kimenetet?

 Feltárhatod a`HtmlOptions` osztályt a HTML-kimenet különböző szempontjainak testreszabásához, például a diamérethez, a képminőséghez és egyebekhez.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
