---
title: Změna dat objektu OLE v prezentaci pomocí Aspose.Slides
linktitle: Změna dat objektu OLE v prezentaci pomocí Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Prozkoumejte sílu Aspose.Slides pro .NET při snadné změně objektových dat OLE. Vylepšete své prezentace dynamickým obsahem.
weight: 25
url: /cs/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}

## Úvod
Vytváření dynamických a interaktivních prezentací v PowerPointu je v dnešním digitálním světě běžným požadavkem. Jedním z mocných nástrojů, jak toho dosáhnout, je Aspose.Slides for .NET, robustní knihovna, která umožňuje vývojářům programově manipulovat a vylepšovat prezentace PowerPoint. V tomto tutoriálu se ponoříme do procesu změny objektových dat OLE (Object Linking and Embedding) v rámci snímků prezentace pomocí Aspose.Slides.
## Předpoklady
Než začnete pracovat s Aspose.Slides for .NET, ujistěte se, že máte splněny následující předpoklady:
1. Vývojové prostředí: Nastavte vývojové prostředí s nainstalovaným .NET.
2.  Knihovna Aspose.Slides: Stáhněte a nainstalujte knihovnu Aspose.Slides for .NET. Knihovnu najdete[tady](https://releases.aspose.com/slides/net/).
3. Základní porozumění: Seznamte se se základními pojmy programování v C# a prezentací v PowerPointu.
## Importovat jmenné prostory
Ve svém projektu C# importujte potřebné jmenné prostory pro použití funkcí Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Krok 1: Nastavte svůj projekt
Začněte vytvořením nového projektu C# a importem knihovny Aspose.Slides. Ujistěte se, že je váš projekt správně nakonfigurován a že máte na svém místě požadované závislosti.
## Krok 2: Přístup k prezentaci a snímku
```csharp
string dataDir = "Your Document Directory";
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);
using (Presentation pres = new Presentation(dataDir + "ChangeOLEObjectData.pptx"))
{
    ISlide slide = pres.Slides[0];
```
## Krok 3: Vyhledejte objekt OLE
Procházejte všechny tvary na snímku a najděte rámeček objektu OLE:
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
## Krok 4: Čtení a úprava dat sešitu
```csharp
if (ole != null)
{
    using (MemoryStream msln = new MemoryStream(ole.EmbeddedData.EmbeddedFileData))
    {
        // Čtení objektových dat v sešitu
        Workbook Wb = new Workbook(msln);
        using (MemoryStream msout = new MemoryStream())
        {
            // Úprava dat sešitu
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Změna dat objektu rámce Ole
            IOleEmbeddedDataInfo newData = new OleEmbeddedDataInfo(msout.ToArray(), ole.EmbeddedData.EmbeddedFileExtension);
            ole.SetEmbeddedData(newData);
        }
    }
}
```
## Krok 5: Uložte prezentaci
```csharp
pres.Save(dataDir + "OleEdit_out.pptx", SaveFormat.Pptx);
```
## Závěr
Pomocí těchto kroků můžete plynule měnit data objektu OLE v rámci snímků prezentace pomocí Aspose.Slides for .NET. To otevírá svět možností pro vytváření dynamických a přizpůsobených prezentací přizpůsobených vašim konkrétním potřebám.
## Často kladené otázky
### Co je Aspose.Slides pro .NET?
Aspose.Slides for .NET je výkonná knihovna, která umožňuje vývojářům pracovat s prezentacemi v PowerPointu programově, což umožňuje snadnou manipulaci a vylepšení.
### Kde najdu dokumentaci Aspose.Slides?
 Dokumentaci k Aspose.Slides pro .NET lze nalézt[tady](https://reference.aspose.com/slides/net/).
### Jak si stáhnu Aspose.Slides pro .NET?
 Knihovnu si můžete stáhnout ze stránky vydání[tady](https://releases.aspose.com/slides/net/).
### Je k dispozici bezplatná zkušební verze pro Aspose.Slides?
 Ano, máte přístup k bezplatné zkušební verzi[tady](https://releases.aspose.com/).
### Kde mohu získat podporu pro Aspose.Slides pro .NET?
 Pro podporu a diskuze navštivte[Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
