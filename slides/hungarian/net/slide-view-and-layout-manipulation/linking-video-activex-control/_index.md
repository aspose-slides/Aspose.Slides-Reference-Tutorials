---
title: Videó összekapcsolása ActiveX-vezérlővel a PowerPointban
linktitle: Videó összekapcsolása ActiveX-vezérlőn keresztül
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Ismerje meg, hogyan kapcsolhat össze videókat PowerPoint diákkal az Aspose.Slides for .NET segítségével. Ez a részletes útmutató forráskódot és tippeket tartalmaz az interaktív és lebilincselő prezentációk létrehozásához linkelt videókkal.
weight: 12
url: /hu/net/slide-view-and-layout-manipulation/linking-video-activex-control/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Videó összekapcsolása ActiveX-vezérlővel a PowerPointban

Videó összekapcsolása ActiveX-vezérlőn keresztül egy prezentációban az Aspose.Slides for .NET használatával

Az Aspose.Slides for .NET programban az ActiveX-vezérlő segítségével programozottan összekapcsolhat egy videót egy prezentációs diával. Ez lehetővé teszi interaktív prezentációk létrehozását, ahol a videótartalom közvetlenül a dián belül lejátszható. Ebben a lépésenkénti útmutatóban végigvezetjük a videó és a prezentációs diák összekapcsolásának folyamatán az Aspose.Slides for .NET segítségével.

## Előfeltételek:
- Visual Studio (vagy bármely más .NET fejlesztői környezet)
-  Aspose.Slides a .NET könyvtárhoz. Letöltheti innen[itt](https://releases.aspose.com/slides/net/).

## 1. lépés: Hozzon létre egy új projektet
Hozzon létre egy új projektet a kívánt .NET fejlesztői környezetben (pl. Visual Studio), és adjon hozzá hivatkozásokat az Aspose.Slides for .NET könyvtárhoz.

## 2. lépés: Importálja a szükséges névtereket
projektben importálja az Aspose.Slides használatához szükséges névtereket:

```csharp
using Aspose.Slides;
using Aspose.Slides.ActiveXControls;
```

## 3. lépés: Bemutató betöltése
Töltse be azt a PowerPoint-prezentációt, ahová hozzá szeretné adni a hivatkozott videót:

```csharp
string presentationPath = "path_to_your_presentation.pptx";
using (Presentation presentation = new Presentation(presentationPath))
{
    // Ide kerül a linkelt videó hozzáadásához szükséges kód
}
```

## 4. lépés: Adjon hozzá ActiveX-vezérlőt
 Hozzon létre egy példányt a`IOleObjectFrame` interfész az ActiveX-vezérlő diához való hozzáadásához:

```csharp
ISlide slide = presentation.Slides[0]; // Válassza ki azt a diát, amelyhez hozzá szeretné adni a videót
IOleObjectFrame oleObjectFrame = slide.Shapes.AddOleObjectFrame(0, 0, 640, 480, "Video", "ShockwaveFlash.ShockwaveFlash.10");
```

A fenti kódban egy 640x480 méretű ActiveX vezérlőkeretet adunk a diához. Megadjuk a ProgID-t a ShockwaveFlash ActiveX vezérlőhöz, amelyet általában videók beágyazására használnak.

## 5. lépés: Állítsa be az ActiveX-vezérlő tulajdonságait
Állítsa be az ActiveX-vezérlő tulajdonságait a csatolt videoforrás megadásához:

```csharp
oleObjectFrame.ObjectData = Encoding.UTF8.GetBytes("YourVideoPathHere"); // Cserélje ki a tényleges videofájl elérési útját
oleObjectFrame.AlternativeText = "Linked Video";
```

 Cserélje ki`"YourVideoPathHere"` a videofájl tényleges elérési útjával. A`AlternativeText` tulajdonság leírást ad a linkelt videóhoz.

## 6. lépés: Mentse a bemutatót
Mentse el a módosított prezentációt:

```csharp
string outputPresentationPath = "output_presentation.pptx";
presentation.Save(outputPresentationPath, SaveFormat.Pptx);
```

## GYIK:

### Hogyan tudom megadni a linkelt videó méretét és pozícióját a dián?
Az ActiveX vezérlőkeret méreteit és pozícióját a paraméterek segítségével állíthatja be`AddOleObjectFrame` módszer. A négy numerikus argumentum a bal felső sarok X és Y koordinátáit, illetve a keret szélességét és magasságát jelenti.

### Linkelhetek különböző formátumú videókat ezzel a módszerrel?
Igen, összekapcsolhat különféle formátumú videókat, amennyiben rendelkezésre áll a megfelelő ActiveX-vezérlő az adott formátumhoz. Például az ebben az útmutatóban használt ShockwaveFlash ActiveX vezérlő alkalmas Flash videókhoz (SWF). Más formátumok esetén előfordulhat, hogy más ProgID-ket kell használnia.

### Van korlátozás a linkelt videó méretére?
A linkelt videó mérete befolyásolhatja a prezentáció általános méretét és teljesítményét. Javasoljuk, hogy optimalizálja videóit internetes lejátszásra, mielőtt összekapcsolná őket a bemutatóval.

### Következtetés:
Az ebben az útmutatóban vázolt lépések követésével az Aspose.Slides for .NET használatával egyszerűen összekapcsolhat egy videót az ActiveX-vezérlőn keresztül egy prezentációban. Ez a funkció lehetővé teszi, hogy vonzó és interaktív prezentációkat készítsen, amelyek zökkenőmentesen tartalmazzák a multimédiás tartalmat.

 További részletekért és speciális beállításokért tekintse meg a[Aspose.Slides a .NET dokumentációhoz](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
