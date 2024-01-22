---
title: Přidání odsazení roztažení pro výplň obrázku v prezentacích PowerPoint
linktitle: Přidání odsazení roztažení pro snímky výplně obrázků
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se, jak vylepšit prezentace PowerPoint pomocí Aspose.Slides pro .NET. Postupujte podle podrobného průvodce a přidejte odsazení roztažení pro výplň obrazu.
type: docs
weight: 18
url: /cs/net/shape-effects-and-manipulation-in-slides/adding-stretch-offset-image-fill/
---
## Úvod
V dynamickém světě prezentací hrají vizuální prvky klíčovou roli při upoutání pozornosti publika. Aspose.Slides for .NET umožňuje vývojářům vylepšit jejich prezentace v PowerPointu poskytnutím robustní sady funkcí. Jednou z takových funkcí je možnost přidat odsazení roztažení pro výplň obrazu, což umožňuje kreativní a vizuálně přitažlivé snímky.
## Předpoklady
Než se pustíte do výukového programu, ujistěte se, že máte splněny následující předpoklady:
1.  Aspose.Slides for .NET Library: Stáhněte a nainstalujte knihovnu z[Aspose.Slides pro dokumentaci .NET](https://reference.aspose.com/slides/net/).
2. Vývojové prostředí: Ujistěte se, že máte nastavené funkční vývojové prostředí .NET.
Nyní začneme s průvodcem krok za krokem.
## Importovat jmenné prostory
Nejprve naimportujte potřebné jmenné prostory, abyste mohli využít funkcionalitu Aspose.Slides ve vaší aplikaci .NET.
```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
```
## Krok 1: Nastavte svůj projekt
Vytvořte nový projekt .NET ve vámi preferovaném vývojovém prostředí. Ujistěte se, že je správně odkazováno na Aspose.Slides for .NET.
## Krok 2: Inicializujte třídu prezentace
 Vytvořte instanci`Presentation` třídy reprezentovat soubor PowerPoint.
```csharp
string dataDir = "Your Document Directory";
bool isExists = System.IO.Directory.Exists(dataDir);
if (!isExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation())
{
    // Váš kód je zde
}
```
## Krok 3: Získejte první snímek
Načtěte první snímek z prezentace, se kterým budete pracovat.
```csharp
ISlide sld = pres.Slides[0];
```
## Krok 4: Vytvořte instanci třídy ImageEx
 Vytvořte instanci souboru`ImageEx` třídy pro zpracování obrázku, který chcete přidat na snímek.
```csharp
System.Drawing.Image img = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx = pres.Images.AddImage(img);
```
## Krok 5: Přidejte rámeček obrázku
 Využijte`AddPictureFrame` způsob přidání rámečku obrázku na snímek. Zadejte rozměry a polohu rámu.
```csharp
sld.Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 150, imgx.Width, imgx.Height, imgx);
```
## Krok 6: Uložte prezentaci
Uložte upravenou prezentaci na disk.
```csharp
pres.Save(dataDir + "AddStretchOffsetForImageFill_out.pptx", SaveFormat.Pptx);
```
A je to! Pomocí Aspose.Slides for .NET jste úspěšně přidali posunutí roztažení pro snímky výplně obrázků.
## Závěr
Vylepšení vašich prezentací v PowerPointu je nyní s Aspose.Slides pro .NET snazší než kdy dříve. Sledováním tohoto tutoriálu jste se naučili, jak začlenit odsazení roztažení pro výplň obrazu, což vašim snímkům přináší novou úroveň kreativity.
## Nejčastější dotazy
### Mohu používat Aspose.Slides for .NET ve svých webových aplikacích?
Ano, Aspose.Slides for .NET je vhodný pro desktopové i webové aplikace.
### Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro .NET?
 Ano, můžete si stáhnout bezplatnou zkušební verzi z[tady](https://releases.aspose.com/).
### Jak mohu získat podporu pro Aspose.Slides pro .NET?
 Navštivte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) za podporu komunity.
### Kde najdu kompletní dokumentaci k Aspose.Slides pro .NET?
 Odkazovat na[dokumentace](https://reference.aspose.com/slides/net/) pro podrobné informace.
### Mohu si zakoupit Aspose.Slides pro .NET?
 Ano, produkt si můžete koupit[tady](https://purchase.aspose.com/buy).