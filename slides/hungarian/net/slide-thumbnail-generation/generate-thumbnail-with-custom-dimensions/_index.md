---
title: Bélyegkép létrehozása a Diákban egyéni méretekkel
linktitle: Indexkép létrehozása egyéni méretekkel
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg, hogyan hozhat létre egyéni bélyegképeket PowerPoint-prezentációkból az Aspose.Slides for .NET segítségével. Növelje a felhasználói élményt és a funkcionalitást.
weight: 13
url: /hu/net/slide-thumbnail-generation/generate-thumbnail-with-custom-dimensions/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


PowerPoint-prezentációk egyéni bélyegképeinek létrehozása értékes eszköz lehet, akár interaktív alkalmazást épít, akár a felhasználói élményt fokozza, akár a tartalmat optimalizálja különböző platformokra. Ebben az oktatóanyagban végigvezetjük a PowerPoint prezentációkból az Aspose.Slides for .NET könyvtár használatával egyéni miniatűrképek létrehozásának folyamatán. Ez a hatékony könyvtár lehetővé teszi a PowerPoint-fájlok programozott kezelését, konvertálását és javítását .NET-alkalmazásokban.

## Előfeltételek

Mielőtt belevágnánk az egyéni indexképek létrehozásába, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

### 1. Aspose.Slides .NET-hez

 A projektben telepíteni kell az Aspose.Slides for .NET könyvtárat. Ha még nem tette meg, megtalálja a szükséges dokumentációt és letöltési linkeket[itt](https://reference.aspose.com/slides/net/).

### 2. PowerPoint-bemutató

Győződjön meg arról, hogy rendelkezik azzal a PowerPoint-prezentációval, amelyből egyéni bélyegképet szeretne létrehozni. Ennek a prezentációnak elérhetőnek kell lennie a projektkönyvtárban.

### 3. Fejlesztési környezet

Az oktatóanyag követéséhez ismernie kell a .NET-programozást C# használatával, és be kell állítania egy fejlesztői környezetet, például a Visual Studio-t.

Most, hogy lefedtük az előfeltételeket, bontsuk le az egyéni miniatűrök létrehozásának folyamatát lépésről lépésre.

## Névterek importálása

Először is bele kell foglalnia a szükséges névtereket a C# kódba. Ezek a névterek lehetővé teszik az Aspose.Slides használatát és a PowerPoint prezentációk kezelését.

```csharp
using Aspose.Slides;
using System.Drawing;
```

## 1. lépés: Töltse be a prezentációt

Kezdésként töltse be azt a PowerPoint-prezentációt, amelyből egyéni bélyegképet szeretne létrehozni. Ez az Aspose.Slides könyvtár használatával érhető el.

```csharp
string FilePath = @"..\..\..\Sample Files\";
string srcFileName = FilePath + "User Defined Thumbnail.pptx";

// Példányosítson egy prezentációs osztályt, amely a prezentációs fájlt reprezentálja
using (Presentation pres = new Presentation(srcFileName))
{
    // Ide kerül az indexkép generálásához szükséges kód
}
```

## 2. lépés: Nyissa meg a diát

A betöltött prezentáción belül hozzá kell férnie ahhoz a diához, amelyről az egyéni bélyegképet szeretné előállítani. A diát az indexe alapján választhatja ki.

```csharp
// Nyissa meg az első diát (szükség szerint módosíthatja az indexet)
ISlide sld = pres.Slides[0];
```

## 3. lépés: Adja meg az egyéni miniatűr méreteket

Adja meg az egyéni indexkép kívánt méretét. A szélességet és magasságot pixelben határozhatja meg az alkalmazás követelményei szerint.

```csharp
int desiredX = 1200; // Szélesség
int desiredY = 800;  // Magasság
```

## 4. lépés: Számítsa ki a méretezési tényezőket

A dia képarányának megőrzéséhez számítsa ki az X és Y méretek méretarányát a dia mérete és a kívánt méretek alapján.

```csharp
float ScaleX = (float)(1.0 / pres.SlideSize.Size.Width) * desiredX;
float ScaleY = (float)(1.0 / pres.SlideSize.Size.Height) * desiredY;
```

## 5. lépés: A miniatűr kép létrehozása

Hozzon létre egy teljes méretű képet a diáról a megadott egyéni méretekkel, és mentse el a lemezre JPEG formátumban.

```csharp
// Hozzon létre egy teljes méretű képet
Bitmap bmp = sld.GetThumbnail(ScaleX, ScaleY);

// Mentse a képet JPEG formátumban lemezre
bmp.Save(destFileName, System.Drawing.Imaging.ImageFormat.Jpeg);
```

Most, hogy követte ezeket a lépéseket, sikeresen létre kellett hoznia egy egyéni bélyegképet a PowerPoint-prezentációból.

## Következtetés

Egyéni miniatűrképek generálása PowerPoint prezentációkból az Aspose.Slides for .NET használatával értékes készség, amely javíthatja az alkalmazások felhasználói élményét és funkcionalitását. Az ebben az oktatóanyagban ismertetett lépések követésével könnyedén létrehozhat egyedi bélyegképeket, amelyek megfelelnek az Ön speciális követelményeinek.

---

## GYIK (Gyakran Ismételt Kérdések)

### Mi az Aspose.Slides for .NET?
Az Aspose.Slides for .NET egy hatékony könyvtár, amely lehetővé teszi a fejlesztők számára, hogy programozottan dolgozzanak PowerPoint-bemutatókkal .NET-alkalmazásokban.

### Hol találom az Aspose.Slides for .NET dokumentációját?
 A dokumentációt megtalálod[itt](https://reference.aspose.com/slides/net/).

### Ingyenesen használható az Aspose.Slides for .NET?
 Az Aspose.Slides for .NET egy kereskedelmi könyvtár. Az árakkal és az engedélyezéssel kapcsolatos információkat találhat[itt](https://purchase.aspose.com/buy).

### Szükségem van fejlett programozási ismeretekre az Aspose.Slides for .NET használatához?
Noha a .NET programozás bizonyos ismerete hasznos, az Aspose.Slides for .NET felhasználóbarát API-t biztosít, amely leegyszerűsíti a PowerPoint prezentációkkal való munkát.

### Rendelkezésre áll technikai támogatás az Aspose.Slides for .NET számára?
 Igen, hozzáférhet a technikai támogatáshoz és a közösségi fórumokhoz[itt](https://forum.aspose.com/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
