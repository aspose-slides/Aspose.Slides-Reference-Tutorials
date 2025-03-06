---
title: Eredeti betűtípusok megőrzése – A prezentáció konvertálása HTML-be
linktitle: Eredeti betűtípusok megőrzése – A prezentáció konvertálása HTML-be
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg, hogyan őrizheti meg az eredeti betűtípusokat, miközben a prezentációkat HTML-formátumba konvertálja az Aspose.Slides for .NET segítségével. Gondoskodjon a betűtípus konzisztenciájáról és a vizuális hatásról.
weight: 14
url: /hu/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Eredeti betűtípusok megőrzése – A prezentáció konvertálása HTML-be


Ebben az átfogó útmutatóban végigvezetjük az eredeti betűtípusok megőrzésének folyamatán, amikor egy prezentációt HTML formátumba konvertál az Aspose.Slides for .NET használatával. Biztosítjuk Önnek a szükséges C# forráskódot, és minden lépést részletesen elmagyarázunk. Ennek az oktatóanyagnak a végére biztosítani tudja, hogy a konvertált HTML-dokumentumban lévő betűtípusok hűek maradjanak az eredeti megjelenítéshez.

## 1. Bemutatkozás

A PowerPoint-prezentációk HTML-formátumba konvertálásakor kulcsfontosságú az eredeti betűtípusok megőrzése a tartalom vizuális egységességének biztosítása érdekében. Az Aspose.Slides for .NET hatékony megoldást kínál ennek elérésére. Ebben az oktatóanyagban végigvezetjük azokon a lépéseken, amelyek szükségesek az eredeti betűtípusok megőrzéséhez az átalakítási folyamat során.

## 2. Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

- A Visual Studio telepítve van a gépedre.
- Aspose.Slides for .NET könyvtár hozzáadva a projekthez.

## 3. A projekt beállítása

kezdéshez hozzon létre egy új projektet a Visual Studióban, és adja hozzá az Aspose.Slides for .NET könyvtárat referenciaként.

## 4. A prezentáció betöltése

Használja a következő kódot a PowerPoint bemutató betöltéséhez:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Itt a kódod
}
```

 Cserélje ki`"Your Document Directory"` a prezentációs fájl elérési útjával.

## 5. Az alapértelmezett betűtípusok kizárása

Az alapértelmezett betűtípusok, például a Calibri és az Arial kizárásához használja a következő kódot:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Ezt a listát igény szerint személyre szabhatja.

## 6. Minden betűtípus beágyazása

Ezután az összes betűtípust beágyazzuk a HTML dokumentumba. Ez biztosítja az eredeti betűtípusok megőrzését. Használja a következő kódot:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Mentés HTML-ként

Most mentse a prezentációt HTML-dokumentumként beágyazott betűtípusokkal:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

 Cserélje ki`"output.html"` a kívánt kimeneti fájlnévvel.

## 8. Következtetés

Ebben az oktatóanyagban bemutattuk, hogyan őrizheti meg az eredeti betűtípusokat, amikor egy PowerPoint-prezentációt HTML-be konvertál az Aspose.Slides for .NET használatával. Az alábbi lépések követésével biztosíthatja, hogy a konvertált HTML-dokumentum megőrizze az eredeti prezentáció vizuális integritását.

## 9. GYIK

### 1. kérdés: Testreszabhatom a kizárt betűtípusok listáját?

 Igen tudsz. Módosítsa a`fontNameExcludeList`tömbben, hogy az Ön igényei szerint bizonyos betűtípusokat vegyen fel vagy zárjon ki.

### 2. kérdés: Mi van, ha nem akarok minden betűtípust beágyazni?

Ha csak meghatározott betűtípusokat szeretne beágyazni, akkor ennek megfelelően módosíthatja a kódot. További részletekért tekintse meg az Aspose.Slides for .NET dokumentációját.

### 3. kérdés: Vannak-e licenckövetelmények az Aspose.Slides for .NET használatához?

Igen, lehet, hogy érvényes licencre van szüksége az Aspose.Slides for .NET használatához projektjeiben. Az Aspose webhelyén találhat licencinformációkat.

### 4. kérdés: Átalakíthatok más fájlformátumokat HTML-re az Aspose.Slides for .NET használatával?

Az Aspose.Slides for .NET elsősorban a PowerPoint-bemutatókra összpontosít. Más fájlformátumok HTML-re konvertálásához szükség lehet más, az adott formátumra szabott Aspose-termékek felfedezésére.

### 5. kérdés: Hol férhetek hozzá további forrásokhoz és támogatáshoz?

 További dokumentációt, oktatóanyagokat és támogatást találhat az Aspose webhelyén. Látogatás[Aspose.Slides a .NET-dokumentációhoz](https://reference.aspose.com/slides/net/) részletes információkért.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
