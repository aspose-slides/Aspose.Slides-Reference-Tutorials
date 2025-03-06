---
title: Szülői megjegyzések hozzáadása a diához az Aspose.Slides segítségével
linktitle: Szülői megjegyzések hozzáadása a diához
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg, hogyan adhat hozzá interaktív megjegyzéseket és válaszokat PowerPoint-prezentációihoz az Aspose.Slides for .NET segítségével. Fokozza az elkötelezettséget és az együttműködést.
weight: 12
url: /hu/net/slide-comments-manipulation/add-parent-comments/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


Interaktív funkciókkal szeretné bővíteni PowerPoint-prezentációit? Az Aspose.Slides for .NET lehetővé teszi megjegyzések és válaszok beillesztését, így dinamikus és vonzó élményt nyújt a közönség számára. Ebben a lépésenkénti oktatóanyagban bemutatjuk, hogyan adhat hozzá szülői megjegyzéseket a diákhoz az Aspose.Slides for .NET segítségével. Merüljünk el, és fedezzük fel ezt az izgalmas funkciót.

## Előfeltételek

Mielőtt elkezdené, győződjön meg arról, hogy a következő előfeltételek teljesülnek:

1.  Aspose.Slides for .NET: Győződjön meg arról, hogy telepítve van az Aspose.Slides for .NET. Letöltheti[itt](https://releases.aspose.com/slides/net/).

2. Visual Studio: A .NET-alkalmazás létrehozásához és futtatásához szükség lesz a Visual Studiora.

3. Alapvető C# ismeretek: Ez az oktatóanyag feltételezi, hogy rendelkezik alapvető ismeretekkel a C# programozásról.

Most, hogy megvannak az előfeltételek, folytassuk a szükséges névterek importálását.

## Névterek importálása

Először is importálnia kell a megfelelő névtereket a projektbe. Ezek a névterek biztosítják az Aspose.Slides for .NET használatához szükséges osztályokat és metódusokat.

```csharp
using Aspose.Slides;
using Aspose.Slides.SlideComments;
```

Ha az előfeltételek és a névterek adottak, bontsuk le a folyamatot több lépésre a szülő megjegyzések diához való hozzáadásához.

## 1. lépés: Hozzon létre egy prezentációt

A kezdéshez létre kell hoznia egy új prezentációt az Aspose.Slides for .NET segítségével. Ez a prezentáció lesz az a vászon, amelyen megjegyzéseket fűzhet hozzá.

```csharp
// A kimeneti könyvtár elérési útja.
string outPptxFile = "Output Path";

using (Presentation pres = new Presentation())
{
    // Ide kerül a megjegyzések hozzáadásához szükséges kód.
    
    pres.Save(outPptxFile + "parent_comment.pptx", SaveFormat.Pptx);
}
```

 A fenti kódban cserélje ki`"Output Path"` a kimeneti prezentáció kívánt elérési útjával.

## 2. lépés: Megjegyzés szerzők hozzáadása

Megjegyzések hozzáadása előtt meg kell határoznia a megjegyzések szerzőit. Ebben a példában két szerzőnk van, a „Szerző_1” és a „Szerző_2”, amelyek mindegyikét egy példány képviseli`ICommentAuthor`.

```csharp
// Megjegyzés hozzáadása
ICommentAuthor author1 = pres.CommentAuthors.AddAuthor("Author_1", "A.A.");
IComment comment1 = author1.Comments.AddComment("comment1", pres.Slides[0], new PointF(10, 10), DateTime.Now);

// Válasz hozzáadása a megjegyzéshez1
ICommentAuthor author2 = pres.CommentAuthors.AddAuthor("Autror_2", "B.B.");
IComment reply1 = author2.Comments.AddComment("reply 1 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply1.ParentComment = comment1;
```

Ebben a lépésben létrehozunk két megjegyzés szerzőt, és hozzáadjuk a kezdeti megjegyzést és egy választ a megjegyzéshez.

## 3. lépés: További válaszok hozzáadása

A megjegyzések hierarchikus szerkezetének létrehozásához további válaszokat adhat a meglévő megjegyzésekhez. Itt egy második választ adunk a "comment1"-hez.

```csharp
// Válasz hozzáadása a megjegyzéshez1
IComment reply2 = author2.Comments.AddComment("reply 2 for comment 1", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply2.ParentComment = comment1;
```

Ez beszélgetési folyamatot hoz létre az előadáson belül.

## 4. lépés: Beágyazott válaszok hozzáadása

A megjegyzésekhez beágyazott válaszok is lehetnek. Ennek demonstrálására egy választ adunk a „2. válasz az 1. megjegyzéshez” szöveghez, amivel egy alválaszt hozunk létre.

```csharp
// Válasz hozzáadása a válaszhoz
IComment subReply = author1.Comments.AddComment("subreply 3 for reply 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
subReply.ParentComment = reply2;
```

Ez a lépés kiemeli az Aspose.Slides for .NET sokoldalúságát a megjegyzéshierarchiák kezelésében.

## 5. lépés: További megjegyzések és válaszok

Szükség szerint továbbra is hozzáadhat további megjegyzéseket és válaszokat. Ebben a példában további két megjegyzést és az egyikre választ adunk.

```csharp
IComment comment2 = author2.Comments.AddComment("comment 2", pres.Slides[0], new PointF(10, 10), DateTime.Now);
IComment comment3 = author2.Comments.AddComment("comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);

IComment reply3 = author1.Comments.AddComment("reply 4 for comment 3", pres.Slides[0], new PointF(10, 10), DateTime.Now);
reply3.ParentComment = comment3;
```

Ez a lépés bemutatja, hogyan hozhat létre vonzó és interaktív tartalmat prezentációihoz.

## 6. lépés: Jelenítse meg a hierarchiát

A megjegyzéshierarchia megjelenítéséhez megjelenítheti azt a konzolon. Ez a lépés nem kötelező, de hasznos lehet a hibakereséshez és a szerkezet megértéséhez.

```csharp
ISlide slide = pres.Slides[0];
var comments = slide.GetSlideComments(null);
for (int i = 0; i < comments.Length; i++)
{
    IComment comment = comments[i];
    while (comment.ParentComment != null)
    {
        Console.Write("\t");
        comment = comment.ParentComment;
    }

    Console.Write("{0} : {1}", comments[i].Author.Name, comments[i].Text);
    Console.WriteLine();
}
```

## 7. lépés: Távolítsa el a megjegyzéseket

Bizonyos esetekben előfordulhat, hogy el kell távolítania a megjegyzéseket és a rájuk adott válaszokat. Az alábbi kódrészlet bemutatja, hogyan távolíthatja el a „comment1” elemet és az összes választ.

```csharp
comment1.Remove();
pres.Save(outPptxFile + "remove_comment.pptx", SaveFormat.Pptx);
```

Ez a lépés hasznos a prezentáció tartalmának kezeléséhez és frissítéséhez.

Ezekkel a lépésekkel prezentációkat hozhat létre interaktív megjegyzésekkel és válaszokkal az Aspose.Slides for .NET segítségével. Ez a funkció a lehetőségek széles skáláját kínálja, akár a közönség bevonását, akár a csapattagokkal való együttműködést szeretné elérni.

## Következtetés

Az Aspose.Slides for .NET hatékony eszközkészletet kínál a PowerPoint-prezentációk tökéletesítéséhez. A megjegyzések és válaszok hozzáadásának lehetőségével dinamikus és interaktív tartalmat hozhat létre, amely magával ragadja közönségét. Ez a lépésenkénti útmutató bemutatja, hogyan adhat hozzá szülői megjegyzéseket a diákhoz, hogyan állíthat fel hierarchiát, és hogyan távolíthat el megjegyzéseket, ha szükséges. Az alábbi lépések követésével és az Aspose.Slides dokumentációjának tanulmányozásával[itt](https://reference.aspose.com/slides/net/), akkor a következő szintre emelheti prezentációit.

## GYIK

### Hozzáfűzhetek megjegyzéseket a prezentációm egyes diáihoz?
Igen, megjegyzéseket fűzhet a prezentáció bármely diájához, ha megjegyzés létrehozásakor megadja a céldiát.

### Testreszabható a hozzászólások megjelenése a prezentációban?
Az Aspose.Slides for .NET lehetővé teszi a megjegyzések megjelenésének testreszabását, beleértve a szövegüket, a szerzői információkat és a dián elfoglalt helyet.

### Exportálhatom a megjegyzéseket és válaszokat egy külön fájlba?
Igen, exportálhatja a megjegyzéseket és válaszokat egy külön prezentációs fájlba, amint azt a 7. lépésben bemutattuk.

### Az Aspose.Slides for .NET kompatibilis a PowerPoint legújabb verzióival?
Az Aspose.Slides for .NET a PowerPoint verziók széles skálájával való együttműködésre készült, biztosítva a kompatibilitást a legújabb kiadásokkal.

### Rendelkezésre állnak-e licencelési lehetőségek az Aspose.Slides for .NET számára?
 Igen, megtekintheti a licencelési lehetőségeket, beleértve az ideiglenes licenceket is, az Aspose webhelyén[itt](https://purchase.aspose.com/buy) vagy próbálja ki az ingyenes próbaverziót[itt](https://releases.aspose.com/temporary-license/).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
