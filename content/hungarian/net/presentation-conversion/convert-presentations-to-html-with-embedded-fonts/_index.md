---
title: Konvertálja a prezentációkat HTML-be beágyazott betűtípusokkal
linktitle: Konvertálja a prezentációkat HTML-be beágyazott betűtípusokkal
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Konvertálja a PowerPoint prezentációkat HTML formátumba beágyazott betűtípusokkal az Aspose.Slides for .NET segítségével. Az eredetiség zökkenőmentes megőrzése.
type: docs
weight: 13
url: /hu/net/presentation-conversion/convert-presentations-to-html-with-embedded-fonts/
---

A mai digitális korban a prezentációk és dokumentumok online megosztása általános gyakorlattá vált. Az egyik gyakran felmerülő kihívás azonban annak biztosítása, hogy a betűtípusok megfelelően jelenjenek meg a prezentációk HTML formátumba konvertálásakor. Ez a lépésenkénti oktatóanyag végigvezeti Önt az Aspose.Slides for .NET használatán a prezentációk HTML-formátumba konvertálásához beágyazott betűtípusokkal, így biztosítva, hogy a dokumentumok pontosan úgy nézzenek ki, ahogyan azt tervezte.

## Az Aspose.Slides .NET-hez bemutatása

Mielőtt belevágnánk az oktatóanyagba, mutassuk be röviden az Aspose.Slides for .NET-et. Ez egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy PowerPoint prezentációkkal dolgozzanak .NET-alkalmazásokban. Az Aspose.Slides segítségével PowerPoint fájlokat hozhat létre, módosíthat és konvertálhat programozottan.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételeket teljesítette:

-  Aspose.Slides for .NET: Az Aspose.Slides könyvtárnak telepítve kell lennie a projektben. Letöltheti innen[itt](https://releases.aspose.com/slides/net/).

## 1. lépés: Állítsa be projektjét

1. Hozzon létre egy új projektet, vagy nyisson meg egy meglévőt a kívánt .NET fejlesztői környezetben.

2. Adjon hozzá hivatkozást az Aspose.Slides könyvtárra a projektben.

3. Importálja a szükséges névtereket a kódba:

   ```csharp
   using Aspose.Slides;
   ```

## 2. lépés: Töltse be a bemutatót

 A kezdéshez be kell töltenie a HTML-be konvertálni kívánt prezentációt. Cserélje ki`"Your Document Directory"` azzal a könyvtárral, ahol a bemutató fájl található.

```csharp
string dataDir = "Your Document Directory";
using (Presentation pres = new Presentation(dataDir + "presentation.pptx"))
{
    // A kódod ide kerül
}
```

## 3. lépés: Az alapértelmezett prezentációs betűtípusok kizárása

Ebben a lépésben megadhat minden olyan alapértelmezett megjelenítési betűtípust, amelyet ki szeretne zárni a beágyazásból. Ez segíthet optimalizálni az eredményül kapott HTML-fájl méretét.

```csharp
string[] fontNameExcludeList = { };
```

## 4. lépés: Válasszon egy HTML-vezérlőt

Most két lehetősége van a betűtípusok HTML-be ágyazására:

### 1. lehetőség: Minden betűtípus beágyazása

 A prezentációban használt összes betűtípus beágyazásához használja a`EmbedAllFontsHtmlController`.

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);
```

### 2. lehetőség: Összes betűtípus összekapcsolása

 A prezentációban használt összes betűtípus hivatkozásához használja a`LinkAllFontsHtmlController`. Meg kell adnia azt a könyvtárat, ahol a betűkészletek találhatók a rendszeren.

```csharp
LinkAllFontsHtmlController linkcont = new LinkAllFontsHtmlController(fontNameExcludeList, @"C:\Windows\Fonts\");
```

## 5. lépés: Adja meg a HTML-beállításokat

 Hozzon létre egy`HtmlOptions` objektumot, és állítsa be a HTML-formázót az előző lépésben kiválasztottra.

```csharp
HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(linkcont) // Az összes betűtípus beágyazásához használja az embedFontsController programot
};
```

## 6. lépés: Mentés HTML-ként

 Végül mentse a prezentációt HTML-fájlként. Bármelyik közül választhat`SaveFormat.Html` vagy`SaveFormat.Html5` az Ön igényeitől függően.

```csharp
pres.Save("pres.html", SaveFormat.Html, htmlOptionsEmbed);
```

## Következtetés

Gratulálunk! Sikeresen átalakította prezentációját beágyazott betűtípusokkal rendelkező HTML formátumba az Aspose.Slides for .NET segítségével. Ez biztosítja, hogy a betűtípusok megfelelően jelenjenek meg prezentációi online megosztása során.

Mostantól könnyedén megoszthatja gyönyörűen formázott prezentációit magabiztosan, tudva, hogy a közönsége pontosan úgy fogja látni őket, ahogyan azt szerette volna.

 További információkért és részletes API-referenciákért tekintse meg a[Aspose.Slides a .NET dokumentációhoz](https://reference.aspose.com/slides/net/).

## GYIK

### 1. Konvertálhatok PowerPoint prezentációkat HTML formátumba az Aspose.Slides for .NET használatával kötegelt módban?

Igen, kötegelt konvertálhat több prezentációt HTML formátumba az Aspose.Slides for .NET segítségével úgy, hogy végignézi a prezentációs fájlokat, és mindegyikre alkalmazza az átalakítási folyamatot.

### 2. Van mód a HTML kimenet megjelenésének testreszabására?

Biztosan! Az Aspose.Slides for .NET különféle lehetőségeket kínál a HTML-kimenet megjelenésének és formázásának testreszabásához, például a színek, a betűtípusok és az elrendezés módosításához.

### 3. Vannak-e korlátozások a betűtípusok HTML-be ágyazására az Aspose.Slides for .NET használatával?

Míg az Aspose.Slides for .NET kiváló betűtípus-beágyazási lehetőségeket kínál, ne feledje, hogy a HTML-fájlok mérete megnőhet a betűtípusok beágyazásakor. Ügyeljen arra, hogy a webhasználathoz optimalizálja a betűtípus-választást.

### 4. Átalakíthatom a PowerPoint prezentációkat más formátumokba az Aspose.Slides for .NET segítségével?

Igen, az Aspose.Slides for .NET a kimeneti formátumok széles skáláját támogatja, beleértve a PDF-et, képeket és egyebeket. Könnyedén konvertálhatja prezentációit a választott formátumra.

### 5. Hol találhatok további forrásokat és támogatást az Aspose.Slides for .NET-hez?

 Rengeteg erőforráshoz, köztük dokumentációhoz férhet hozzá a webhelyen[Aspose.Slides for .NET API Reference](https://reference.aspose.com/slides/net/).
