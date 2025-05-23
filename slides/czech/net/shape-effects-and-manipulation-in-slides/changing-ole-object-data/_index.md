---
"description": "Prozkoumejte sílu Aspose.Slides pro .NET, která vám umožní snadno měnit data objektů OLE. Vylepšete své prezentace dynamickým obsahem."
"linktitle": "Změna dat OLE objektu v prezentaci pomocí Aspose.Slides"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Změna dat OLE objektu v prezentaci pomocí Aspose.Slides"
"url": "/cs/net/shape-effects-and-manipulation-in-slides/changing-ole-object-data/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Změna dat OLE objektu v prezentaci pomocí Aspose.Slides

## Zavedení
Vytváření dynamických a interaktivních prezentací v PowerPointu je v dnešním digitálním světě běžným požadavkem. Jedním z účinných nástrojů pro dosažení tohoto cíle je Aspose.Slides pro .NET, robustní knihovna, která vývojářům umožňuje programově manipulovat s prezentacemi v PowerPointu a vylepšovat je. V tomto tutoriálu se ponoříme do procesu změny dat objektů OLE (Object Linking and Embedding) v rámci snímků prezentace pomocí Aspose.Slides.
## Předpoklady
Než začnete pracovat s Aspose.Slides pro .NET, ujistěte se, že máte splněny následující předpoklady:
1. Vývojové prostředí: Nastavte vývojové prostředí s nainstalovaným .NET.
2. Knihovna Aspose.Slides: Stáhněte a nainstalujte knihovnu Aspose.Slides pro .NET. Knihovnu najdete [zde](https://releases.aspose.com/slides/net/).
3. Základní znalosti: Seznamte se se základními koncepty programování v jazyce C# a prezentací v PowerPointu.
## Importovat jmenné prostory
Ve vašem projektu C# importujte potřebné jmenné prostory pro použití funkcí Aspose.Slides:
```csharp
using System.IO;
using Aspose.Cells;
using Aspose.Slides;
using Aspose.Slides.DOM.Ole;
using SaveFormat = Aspose.Slides.Export.SaveFormat;
```
## Krok 1: Nastavení projektu
Začněte vytvořením nového projektu v C# a importem knihovny Aspose.Slides. Ujistěte se, že je váš projekt správně nakonfigurován a že máte nainstalovány požadované závislosti.
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
## Krok 3: Vyhledání objektu OLE
Procházejte všemi tvary na snímku a najděte rámec objektu OLE:
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
            // Úprava dat v sešitu
            Wb.Worksheets[0].Cells[0, 4].PutValue("E");
            Wb.Worksheets[0].Cells[1, 4].PutValue(12);
            Wb.Worksheets[0].Cells[2, 4].PutValue(14);
            Wb.Worksheets[0].Cells[3, 4].PutValue(15);
            OoxmlSaveOptions so1 = new OoxmlSaveOptions(Aspose.Cells.SaveFormat.Xlsx);
            Wb.Save(msout, so1);
            // Změna dat objektu Ole frame
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
Dodržováním těchto kroků můžete bez problémů měnit data objektů OLE v rámci prezentačních snímků pomocí Aspose.Slides pro .NET. To otevírá svět možností pro vytváření dynamických a přizpůsobených prezentací přizpůsobených vašim specifickým potřebám.
## Často kladené otázky
### Co je Aspose.Slides pro .NET?
Aspose.Slides pro .NET je výkonná knihovna, která umožňuje vývojářům programově pracovat s prezentacemi v PowerPointu, což umožňuje snadnou manipulaci a vylepšování.
### Kde najdu dokumentaci k Aspose.Slides?
Dokumentaci k Aspose.Slides pro .NET naleznete [zde](https://reference.aspose.com/slides/net/).
### Jak si stáhnu Aspose.Slides pro .NET?
Knihovnu si můžete stáhnout ze stránky s vydáním [zde](https://releases.aspose.com/slides/net/).
### Je k dispozici bezplatná zkušební verze Aspose.Slides?
Ano, máte přístup k bezplatné zkušební verzi [zde](https://releases.aspose.com/).
### Kde mohu získat podporu pro Aspose.Slides pro .NET?
Pro podporu a diskuzi navštivte [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}