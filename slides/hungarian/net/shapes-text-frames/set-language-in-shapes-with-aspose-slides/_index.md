---
"date": "2025-04-16"
"description": "Ismerje meg, hogyan állíthat be nyelvi attribútumokat az alakzatokon belüli szöveghez az Aspose.Slides for .NET használatával. Ez az útmutató az automatikus alakzatok hozzáadását, a nyelvi azonosítók beállítását és a prezentációk mentését ismerteti."
"title": "Hogyan állítsunk be nyelvet PowerPoint alakzatokban az Aspose.Slides for .NET használatával"
"url": "/hu/net/shapes-text-frames/set-language-in-shapes-with-aspose-slides/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hogyan állítsunk be nyelvet PowerPoint alakzatokban az Aspose.Slides for .NET használatával

digitális prezentációk világában kihívást jelenthet biztosítani, hogy a tartalom különböző nyelveken is hozzáférhető és helyesen formázott legyen. Az Aspose.Slides for .NET segítségével könnyedén beállíthatja a nyelvi attribútumokat a PowerPoint diák alakzatain belüli szöveghez. Ez a funkció különösen hasznos többnyelvű dokumentumok készítésekor vagy a globális kommunikáció egységességének biztosításakor.

**Amit tanulni fogsz:**
- Automatikus alakzatok hozzáadása és szöveg beszúrása ezekbe.
- Szövegrészek nyelvi azonosítójának beállítása az Aspose.Slides használatával.
- Prezentációk mentése egyéni konfigurációkkal.

Nézzük meg, hogyan valósíthatja meg zökkenőmentesen ezt a funkciót.

## Előfeltételek

Mielőtt elkezdenénk, győződjünk meg arról, hogy a következőkkel rendelkezünk:

- **Könyvtárak és függőségek**Telepítenie kell az Aspose.Slides for .NET programot. Ez a könyvtár elengedhetetlen a PowerPoint-bemutatók C#-ban történő kezeléséhez.
  
- **Környezet beállítása**: .NET Core vagy .NET Framework futtatókörnyezet szükséges.

- **Előfeltételek a tudáshoz**Az alapvető C# programozási fogalmak ismerete és az objektumorientált programozási elvek ismerete előnyös lesz.

## Az Aspose.Slides beállítása .NET-hez

A kezdéshez telepítenie kell az Aspose.Slides könyvtárat. Ezt az alábbi módszerek egyikével teheti meg:

**.NET parancssori felület**
```shell
dotnet add package Aspose.Slides
```

**Csomagkezelő**
```powershell
Install-Package Aspose.Slides
```

**NuGet csomagkezelő felhasználói felület**
Keresd meg az „Aspose.Slides” fájlt, és telepítsd a legújabb verziót.

### Licencszerzés

Ingyenes próbaverziót is kipróbálhatsz egy ideiglenes licenc letöltésével innen: [itt](https://purchase.aspose.com/temporary-license/)Folyamatos használat esetén érdemes lehet licencet vásárolni a következő címen: [ez a link](https://purchase.aspose.com/buy).

Miután elkészült a beállítás, inicializáld az Aspose.Slides fájlt a projektedben:

```csharp
using Aspose.Slides;
```

## Megvalósítási útmutató

Most, hogy készen vagyunk, valósítsuk meg az alakzatszöveg nyelvének beállításához szükséges funkciót.

### Funkcióáttekintés: Alakzat szövegnyelvének beállítása

Ez a funkció lehetővé teszi a PowerPoint-alakzatokon belüli szöveg nyelvének megadását. A nyelvi azonosító beállításával biztosíthatja a helyesírás-ellenőrzés és az egyéb nyelvspecifikus funkciók helyes alkalmazását.

#### 1. lépés: A prezentáció inicializálása

Kezdje egy példány létrehozásával a `Presentation` osztály.

```csharp
using (Presentation pres = new Presentation())
{
    // A kódod itt
}
```

Ez inicializál egy új PowerPoint prezentációs objektumot, amelyet manipulálni fogunk.

#### 2. lépés: Automatikus alakzat és szövegkeret hozzáadása

Téglalap alakú alakzat hozzáadása a diához, és szöveg beszúrása:

```csharp
IAutoShape shape = pres.Slides[0].Shapes.AddAutoShape(ShapeType.Rectangle, 50, 50, 200, 50);
shape.AddTextFrame("Text to apply spellcheck language");
```

Itt, `AddAutoShape` egy téglalapot ad hozzá az első diához. A paraméterek határozzák meg a helyét és méretét.

#### 3. lépés: Nyelvi azonosító beállítása

Állítsa be az alakzaton belüli szövegrész nyelvét:

```csharp
shape.TextFrame.Paragraphs[0].Portions[0].PortionFormat.LanguageId = "en-EN";
```

Ez az angol (Egyesült Királyság) nyelvet jelöli ki a helyesírás-ellenőrzés nyelveként.

#### 4. lépés: Mentse el a prezentációt

Végül mentse el a prezentációt a megadott elérési útra:

```csharp
pres.Save("YOUR_OUTPUT_DIRECTORY\	est1.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}