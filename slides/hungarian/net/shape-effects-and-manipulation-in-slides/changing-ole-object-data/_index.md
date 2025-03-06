---
title: Az OLE-objektumadatok módosítása a prezentációban az Aspose.Slides segítségével
linktitle: Az OLE-objektumadatok módosítása a prezentációban az Aspose.Slides segítségével
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Fedezze fel az Aspose.Slides for .NET erejét az OLE objektumadatok könnyed megváltoztatásában. Növelje prezentációit dinamikus tartalommal.
weight: 25
url: /hu/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Az OLE-objektumadatok módosítása a prezentációban az Aspose.Slides segítségével

## Bevezetés
A dinamikus és interaktív PowerPoint prezentációk készítése általános követelmény a mai digitális világban. Ennek egyik hatékony eszköze az Aspose.Slides for .NET, egy robusztus könyvtár, amely lehetővé teszi a fejlesztők számára a PowerPoint prezentációk programozott kezelését és fejlesztését. Ebben az oktatóanyagban az OLE (Object Linking and Embedding) objektumadatok módosításának folyamatába fogunk belemenni a bemutató diákon belül az Aspose.Slides segítségével.
## Előfeltételek
Mielőtt elkezdené dolgozni az Aspose.Slides for .NET programmal, győződjön meg arról, hogy a következő előfeltételek teljesülnek:
1. Fejlesztői környezet: Hozzon létre egy fejlesztői környezetet telepített .NET-tel.
2.  Aspose.Slides Library: Töltse le és telepítse az Aspose.Slides for .NET könyvtárat. Megtalálhatod a könyvtárat[itt](https://releases.aspose.com/slides/net/).
3. Alapvető ismeretek: Ismerkedjen meg a C# programozás és a PowerPoint prezentációk alapvető fogalmaival.
## Névterek importálása
A C# projektben importálja a szükséges névtereket az Aspose.Slides funkciók használatához:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## 1. lépés: Állítsa be projektjét
Kezdje egy új C# projekt létrehozásával és az Aspose.Slides könyvtár importálásával. Győződjön meg arról, hogy a projekt megfelelően van konfigurálva, és megvannak a szükséges függőségek.
## 2. lépés: Nyissa meg a bemutatót és a diát
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## 3. lépés: Keresse meg az OLE objektumot
Lapozzon végig a dia összes alakján, hogy megtalálja az OLE objektumkeretet:
```csharp
OleObjectFrame ole = null;
foreach (IShape shape in slide.Shapes)
{
    if (shape is OleObjectFrame)
    {
        ole = (OleObjectFrame)shape;
    }
}
```
## 4. lépés: Olvassa el és módosítsa a munkafüzet adatait
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Objektumadatok olvasása a munkafüzetben
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // A munkafüzet adatainak módosítása
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Ole frame objektum adatok módosítása
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## 5. lépés: Mentse el a prezentációt
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Következtetés
Az alábbi lépések követésével az Aspose.Slides for .NET segítségével zökkenőmentesen módosíthatja az OLE-objektumadatokat a bemutató diákon belül. Ez a lehetőségek világát nyitja meg dinamikus és testreszabott, az Ön egyedi igényeire szabott prezentációk létrehozásához.
## Gyakran Ismételt Kérdések
### Mi az Aspose.Slides for .NET?
Az Aspose.Slides for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak PowerPoint-prezentációkkal, lehetővé téve az egyszerű kezelést és fejlesztést.
### Hol találom az Aspose.Slides dokumentációját?
 Az Aspose.Slides for .NET dokumentációja megtalálható[itt](https://reference.aspose.com/slides/net/).
### Hogyan tölthetem le az Aspose.Slides for .NET programot?
 A könyvtár letölthető a kiadási oldalról[itt](https://releases.aspose.com/slides/net/).
### Létezik ingyenes próbaverzió az Aspose.Slides számára?
 Igen, hozzáférhet az ingyenes próbaverzióhoz[itt](https://releases.aspose.com/).
### Hol kaphatok támogatást az Aspose.Slides for .NET-hez?
 Támogatásért és megbeszélésekért keresse fel a[Aspose.Slides fórum](https://forum.aspose.com/c/slides/11).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
