---
"description": "Ismerd meg, hogyan csatolhatsz videókat PowerPoint diákhoz az Aspose.Slides for .NET segítségével. Ez a lépésről lépésre szóló útmutató forráskódot és tippeket tartalmaz interaktív és lebilincselő prezentációk létrehozásához csatolt videókkal."
"linktitle": "Videó csatolása ActiveX vezérlőn keresztül"
"second_title": "Aspose.Slides .NET PowerPoint feldolgozási API"
"title": "Videó csatolása ActiveX vezérlővel PowerPointban"
"url": "/hu/net/slide-view-and-layout-manipulation/linking-video-activex-control/"
"weight": 12
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Videó csatolása ActiveX vezérlővel PowerPointban

Videó csatolása ActiveX vezérlőn keresztül egy prezentációban az Aspose.Slides for .NET használatával

Az Aspose.Slides for .NET programban programozottan csatolhatsz videót egy prezentációs diához az ActiveX vezérlő segítségével. Ez lehetővé teszi interaktív prezentációk létrehozását, ahol a videó tartalma közvetlenül a dián belül játszható le. Ebben a lépésről lépésre bemutatjuk, hogyan csatolhatsz videót egy prezentációs diához az Aspose.Slides for .NET használatával.

## Előfeltételek:
- Visual Studio (vagy bármilyen más .NET fejlesztői környezet)
- Aspose.Slides .NET könyvtárhoz. Letöltheted innen: [itt](https://releases.aspose.com/slides/net/).

## 1. lépés: Új projekt létrehozása
Hozz létre egy új projektet a kívánt .NET fejlesztői környezetben (pl. Visual Studio), és adj hozzá hivatkozásokat az Aspose.Slides for .NET könyvtárhoz.

## 2. lépés: A szükséges névterek importálása
A projektedben importáld a szükséges névtereket az Aspose.Slides használatához:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## 3. lépés: Prezentáció betöltése
Töltse be a PowerPoint bemutatót oda, ahová a hivatkozott videót hozzá szeretné adni:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // A linkelt videó hozzáadásához szükséges kód ide fog kerülni.
}
```

## 4. lépés: ActiveX-vezérlő hozzáadása
Hozz létre egy példányt a `IOleObjectFrame` felület az ActiveX vezérlő diához való hozzáadásához:

```csharp
ISlide slide = presentation.Slides[0]; // Válaszd ki azt a diát, ahová a videót hozzá szeretnéd adni
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

A fenti kódban egy 640x480 méretű ActiveX vezérlőkeretet adunk a diához. Megadjuk a ShockwaveFlash ActiveX vezérlő ProgID-jét, amelyet általában videók beágyazásához használnak.

## 5. lépés: Az ActiveX-vezérlő tulajdonságainak beállítása
Állítsa be az ActiveX-vezérlő tulajdonságait a csatolt videoforrás megadásához:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Cserélje ki a videofájl tényleges elérési útjára
oleObjectFrame.AlternativeText = "Linked Video";
```

Csere `"YourVideoPathHere"` a videofájl tényleges elérési útjával. `AlternativeText` A tulajdonság leírást ad a hivatkozott videóhoz.

## 6. lépés: Prezentáció mentése
Mentse el a módosított prezentációt:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## GYIK:

### Hogyan tudom megadni a hivatkozott videó méretét és pozícióját a dián?
Az ActiveX vezérlőkeret méreteit és pozícióját a paraméterek segítségével állíthatja be. `AddOleObjectFrame` metódus. A négy numerikus argumentum rendre a bal felső sarok X és Y koordinátáit, illetve a keret szélességét és magasságát jelöli.

### Össze tudom linkelni a különböző formátumú videókat ezzel a módszerrel?
Igen, különböző formátumú videókat is linkelhetsz, amennyiben a megfelelő ActiveX-vezérlő elérhető az adott formátumhoz. Például az ebben az útmutatóban használt ShockwaveFlash ActiveX-vezérlő alkalmas Flash-videókhoz (SWF). Más formátumokhoz eltérő ProgID-ket kell használnod.

### Van méretkorlát a linkelt videóra?
A linkelt videó mérete befolyásolhatja a prezentáció teljes méretét és teljesítményét. Javasoljuk, hogy a videókat a prezentációhoz csatolás előtt optimalizálja webes lejátszásra.

### Következtetés:
Az útmutatóban ismertetett lépéseket követve könnyedén csatolhat videókat ActiveX-vezérlőn keresztül egy Aspose.Slides for .NET bemutatóhoz. Ez a funkció lehetővé teszi, hogy lebilincselő és interaktív bemutatókat készítsen, amelyek zökkenőmentesen beépítik a multimédiás tartalmakat.

További részletekért és a speciális beállításokért tekintse meg a [Aspose.Slides .NET dokumentációhoz](https://reference.aspose.com/slides/net/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}