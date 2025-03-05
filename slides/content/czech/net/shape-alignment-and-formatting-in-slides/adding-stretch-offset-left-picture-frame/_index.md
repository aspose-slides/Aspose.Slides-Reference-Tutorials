---
title: Přidání odsazení roztažení doleva v PowerPointu pomocí Aspose.Slide
linktitle: Přidání odsazení roztažení doleva pro rámeček obrázku v Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se, jak vylepšit prezentace PowerPoint pomocí Aspose.Slides pro .NET. Postupujte podle našeho podrobného průvodce a přidejte posun roztažení doleva pro rámečky obrázků.
type: docs
weight: 14
url: /cs/net/shape-alignment-and-formatting-in-slides/adding-stretch-offset-left-picture-frame/
---
## Úvod
Aspose.Slides for .NET je výkonná knihovna, která umožňuje vývojářům snadno manipulovat s prezentacemi v PowerPointu. V tomto tutoriálu prozkoumáme proces přidání posunutí roztažení doleva pro rám obrazu pomocí Aspose.Slides pro .NET. Postupujte podle tohoto podrobného průvodce, abyste zlepšili své dovednosti v práci s obrázky a tvary v prezentacích PowerPoint.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
-  Aspose.Slides for .NET: Ujistěte se, že máte nainstalovanou knihovnu. Pokud ne, stáhněte si jej z[Aspose.Slides pro dokumentaci .NET](https://reference.aspose.com/slides/net/).
- Vývojové prostředí: Mějte funkční vývojové prostředí s možnostmi .NET.
## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do vašeho projektu .NET:
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Krok 1: Nastavte svůj projekt
Vytvořte nový projekt nebo otevřete existující. Ujistěte se, že máte ve svém projektu odkaz na knihovnu Aspose.Slides.
## Krok 2: Vytvořte objekt prezentace
 Vytvořte instanci`Presentation` třída, představující soubor PPTX:
```csharp
using (Presentation pres = new Presentation())
{
    // Zde bude váš kód pro další kroky.
}
```
## Krok 3: Získejte první snímek
Načtěte první snímek z prezentace:
```csharp
ISlide slide = pres.Slides[0];
```
## Krok 4: Vytvořte instanci obrázku
Načtěte obrázek, který chcete použít:
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgEx = pres.Images.AddImage(img);
```
## Krok 5: Přidejte automatický tvar obdélníku
Vytvořte automatický tvar typu obdélník:
```csharp
IAutoShape aShape = slide.Shapes.AddAutoShape(ShapeType.Rectangle, 100, 100, 300, 300);
```
## Krok 6: Nastavte Typ výplně a Režim výplně obrázku
Nakonfigurujte typ výplně tvaru a režim výplně obrázku:
```csharp
aShape.FillFormat.FillType = FillType.Picture;
aShape.FillFormat.PictureFillFormat.PictureFillMode = PictureFillMode.Stretch;
```
## Krok 7: Nastavte obrázek tak, aby vyplnil tvar
Zadejte obrázek, který má vyplnit tvar:
```csharp
aShape.FillFormat.PictureFillFormat.Picture.Image = imgEx;
```
## Krok 8: Zadejte odsazení roztažení
Definujte odsazení obrazu od odpovídajících okrajů ohraničovacího rámečku tvaru:
```csharp
aShape.FillFormat.PictureFillFormat.StretchOffsetLeft = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetRight = 25;
aShape.FillFormat.PictureFillFormat.StretchOffsetTop = -20;
aShape.FillFormat.PictureFillFormat.StretchOffsetBottom = -10;
```
## Krok 9: Uložte prezentaci
Zapište soubor PPTX na disk:
```csharp
pres.Save(dataDir + "StretchOffsetLeftForPictureFrame_out.pptx", SaveFormat.Pptx);
```
Gratulujeme! Úspěšně jste přidali posunutí roztažení doleva pro rám obrazu pomocí Aspose.Slides pro .NET.
## Závěr
V tomto tutoriálu jsme prozkoumali proces manipulace s rámečky obrázků v prezentacích PowerPoint pomocí Aspose.Slides pro .NET. Sledováním tohoto podrobného průvodce jste získali přehled o práci s obrázky, tvary a posuny.
## Často kladené otázky
### Otázka: Mohu použít odsazení roztažení na jiné tvary kromě obdélníků?
Odpověď: I když se tento tutoriál zaměřuje na obdélníky, posuny roztažení lze použít na různé tvary podporované Aspose.Slides.
### Otázka: Jak mohu upravit posuny roztažení pro různé efekty?
Odpověď: Experimentujte s různými hodnotami odsazení, abyste dosáhli požadovaného vizuálního dopadu. Dolaďte hodnoty tak, aby vyhovovaly vašim specifickým požadavkům.
### Otázka: Je Aspose.Slides kompatibilní s nejnovějším rámcem .NET?
Odpověď: Aspose.Slides je pravidelně aktualizován, aby byla zajištěna kompatibilita s nejnovějšími verzemi .NET frameworku.
### Otázka: Kde najdu další příklady a zdroje pro Aspose.Slides?
 A: Prozkoumejte[Dokumentace Aspose.Slides](https://reference.aspose.com/slides/net/) pro komplexní příklady a návody.
### Otázka: Mohu použít více odsazení roztažení na jeden tvar?
Odpověď: Ano, můžete kombinovat více odsazení roztažení a dosáhnout tak komplexních a přizpůsobených vizuálních efektů.