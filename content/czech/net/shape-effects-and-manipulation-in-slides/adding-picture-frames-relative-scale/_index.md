---
title: Výukový program přidávání rámečků obrázků s Aspose.Slides .NET
linktitle: Přidání rámečků obrázků s relativní výškou měřítka v Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se přidávat rámečky obrázků s relativní výškou měřítka v Aspose.Slides pro .NET. Postupujte podle tohoto podrobného průvodce pro bezproblémové prezentace.
type: docs
weight: 17
url: /cs/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/
---
## Úvod
Aspose.Slides for .NET je výkonná knihovna, která umožňuje vývojářům snadno vytvářet, manipulovat a převádět PowerPointové prezentace v jejich aplikacích .NET. V tomto tutoriálu se ponoříme do procesu přidávání rámečků obrázků s relativní výškou měřítka pomocí Aspose.Slides pro .NET. Postupujte podle tohoto podrobného průvodce, abyste zlepšili své dovednosti při vytváření prezentací.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
- Základní znalost programovacího jazyka C#.
- Nainstalované Visual Studio nebo jakékoli jiné preferované vývojové prostředí C#.
- Knihovna Aspose.Slides for .NET byla přidána do vašeho projektu.
## Importovat jmenné prostory
Začněte importováním potřebných jmenných prostorů do kódu C#. Tento krok zajistí, že budete mít přístup ke třídám a funkcím poskytovaným knihovnou Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Krok 1: Nastavte svůj projekt
Začněte vytvořením nového projektu C# ve vámi preferovaném vývojovém prostředí. Nezapomeňte do projektu přidat knihovnu Aspose.Slides for .NET odkazem na ni.
## Krok 2: Načtěte prezentaci a obrázek
```csharp
string dataDir = "Your Document Directory";
using (Presentation presentation = new Presentation())
{
    // Načíst obrázek, který má být přidán do kolekce obrázků prezentace
    Image img = new Bitmap(dataDir + "aspose-logo.jpg");
    IPPImage image = presentation.Images.AddImage(img);
    // ...
}
```
V tomto kroku vytvoříme nový objekt prezentace a načteme obrázek, který chceme do prezentace přidat.
## Krok 3: Přidejte rámeček obrázku do snímku
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Nyní přidejte rámeček obrázku na první snímek prezentace. Upravte parametry, jako je typ tvaru, poloha a rozměry, podle vašich požadavků.
## Krok 4: Nastavte relativní šířku a výšku měřítka
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Nastavte relativní výšku a šířku měřítka pro rám obrazu, abyste dosáhli požadovaného efektu měřítka.
## Krok 5: Uložte prezentaci
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Nakonec uložte prezentaci s přidaným rámečkem obrázku v určeném výstupním formátu.
## Závěr
Gratulujeme! Úspěšně jste se naučili přidávat rámečky obrázků s relativní výškou měřítka pomocí Aspose.Slides pro .NET. Experimentujte s různými obrázky, pozicemi a měřítky a vytvořte vizuálně přitažlivé prezentace přizpůsobené vašim potřebám.
## Často kladené otázky
### Mohu používat Aspose.Slides pro .NET s jinými programovacími jazyky?
Aspose.Slides primárně podporuje jazyky .NET, ale můžete prozkoumat další produkty Aspose kvůli kompatibilitě s různými platformami.
### Kde najdu podrobnou dokumentaci k Aspose.Slides pro .NET?
 Odkazovat na[dokumentace](https://reference.aspose.com/slides/net/) pro vyčerpávající informace a příklady.
### Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro .NET?
 Ano, můžete získat a[zkušební verze zdarma](https://releases.aspose.com/) zhodnotit možnosti knihovny.
### Jak mohu získat podporu pro Aspose.Slides pro .NET?
 Navštivte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) požádat o pomoc komunitu a odborníky Aspose.
### Kde mohu zakoupit Aspose.Slides pro .NET?
 Aspose.Slides pro .NET si můžete koupit od[nákupní stránku](https://purchase.aspose.com/buy).