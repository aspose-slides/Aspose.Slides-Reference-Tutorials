---
"description": "Tanuld meg, hogyan őrizheted meg az eredeti betűtípusokat, miközben prezentációkat HTML-be konvertálsz az Aspose.Slides for .NET segítségével. Gondoskodj a betűtípusok egységességéről és a vizuális hatásról erőfeszítés nélkül."
"linktitle": "Eredeti betűtípusok megőrzése - Prezentáció konvertálása HTML-be"
"second_title": "Aspose.Slides .NET PowerPoint feldolgozási API"
"title": "Eredeti betűtípusok megőrzése - Prezentáció konvertálása HTML-be"
"url": "/hu/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Eredeti betűtípusok megőrzése - Prezentáció konvertálása HTML-be


Ebben az átfogó útmutatóban végigvezetünk az eredeti betűtípusok megőrzésének folyamatán, amikor egy prezentációt HTML-be konvertálsz az Aspose.Slides for .NET segítségével. Biztosítjuk a szükséges C# forráskódot, és részletesen elmagyarázzuk az egyes lépéseket. A bemutató végére biztosítani fogod, hogy a konvertált HTML dokumentumban lévő betűtípusok hűek maradjanak az eredeti prezentációhoz.

## 1. Bevezetés

PowerPoint prezentációk HTML-be konvertálásakor kulcsfontosságú az eredeti betűtípusok megőrzése a tartalom vizuális konzisztenciájának biztosítása érdekében. Az Aspose.Slides for .NET hatékony megoldást kínál ennek elérésére. Ebben az oktatóanyagban végigvezetjük az eredeti betűtípusok megőrzéséhez szükséges lépéseken a konvertálási folyamat során.

## 2. Előfeltételek

Mielőtt elkezdenénk, győződjünk meg arról, hogy a következő előfeltételek teljesülnek:

- Visual Studio telepítve a gépedre.
- Az Aspose.Slides for .NET könyvtár hozzáadva a projektedhez.

## 3. A projekt beállítása

Első lépésként hozz létre egy új projektet a Visual Studioban, és add hozzá az Aspose.Slides for .NET könyvtárat referenciaként.

## 4. A prezentáció betöltése

A PowerPoint prezentáció betöltéséhez használd a következő kódot:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // A kódod itt
}
```

Csere `"Your Document Directory"` a prezentációs fájl elérési útjával.

## 5. Az alapértelmezett betűtípusok kizárása

Az alapértelmezett betűtípusok, például a Calibri és az Arial kizárásához használja a következő kódot:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Szükség szerint testreszabhatja ezt a listát.

## 6. Az összes betűtípus beágyazása

Ezután beágyazzuk az összes betűtípust a HTML dokumentumba. Ez biztosítja az eredeti betűtípusok megőrzését. Használd a következő kódot:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Mentés HTML-ként

Most mentse el a prezentációt HTML dokumentumként beágyazott betűtípusokkal:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Csere `"output.html"` a kívánt kimeneti fájlnévvel.

## 8. Következtetés

Ebben az oktatóanyagban bemutattuk, hogyan őrizhetjük meg az eredeti betűtípusokat egy PowerPoint-bemutató HTML-be konvertálásakor az Aspose.Slides for .NET segítségével. A következő lépések követésével biztosíthatjuk, hogy a konvertált HTML-dokumentum megőrizze az eredeti bemutató vizuális integritását.

## 9. GYIK

### 1. kérdés: Testreszabhatom a kizárt betűtípusok listáját?

Igen, módosíthatja. `fontNameExcludeList` tömböt, hogy az igényeidnek megfelelően bizonyos betűtípusokat tartalmazzon vagy kizárjon.

### 2. kérdés: Mi van, ha nem akarok minden betűtípust beágyazni?

Ha csak bizonyos betűtípusokat szeretne beágyazni, ennek megfelelően módosíthatja a kódot. További részletekért tekintse meg az Aspose.Slides for .NET dokumentációját.

### 3. kérdés: Vannak-e licenckövetelmények az Aspose.Slides .NET-hez való használatához?

Igen, érvényes licencre lehet szüksége az Aspose.Slides for .NET használatához a projektjeiben. A licencelési információkért látogasson el az Aspose weboldalára.

### 4. kérdés: Konvertálhatok más fájlformátumokat HTML-re az Aspose.Slides for .NET segítségével?

Az Aspose.Slides for .NET elsősorban PowerPoint prezentációkra összpontosít. Más fájlformátumok HTML-re konvertálásához érdemes lehet más, az adott formátumokhoz igazított Aspose termékeket is megvizsgálni.

### 5. kérdés: Hol férhetek hozzá további forrásokhoz és támogatáshoz?

További dokumentációt, oktatóanyagokat és támogatást az Aspose weboldalán talál. Látogasson el ide: [Aspose.Slides .NET dokumentációhoz](https://reference.aspose.com/slides/net/) részletes információkért.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}