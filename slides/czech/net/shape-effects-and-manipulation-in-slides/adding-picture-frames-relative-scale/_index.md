---
"description": "Naučte se přidávat obrazové rámečky s relativní výškou v Aspose.Slides pro .NET. Postupujte podle tohoto podrobného návodu pro bezproblémové prezentace."
"linktitle": "Přidání obrazových rámů s relativní výškou v Aspose.Slides"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Výukový program pro přidání obrazových rámů pomocí Aspose.Slides .NET"
"url": "/cs/net/shape-effects-and-manipulation-in-slides/adding-picture-frames-relative-scale/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Výukový program pro přidání obrazových rámů pomocí Aspose.Slides .NET

## Zavedení
Aspose.Slides pro .NET je výkonná knihovna, která umožňuje vývojářům bez námahy vytvářet, manipulovat a převádět prezentace v PowerPointu v jejich aplikacích .NET. V tomto tutoriálu se ponoříme do procesu přidávání obrazových rámečků s relativní výškou měřítka pomocí Aspose.Slides pro .NET. Sledujte tento podrobný návod a zlepšete si své dovednosti v oblasti tvorby prezentací.
## Předpoklady
Než začneme, ujistěte se, že máte následující:
- Základní znalost programovacího jazyka C#.
- Nainstalované Visual Studio nebo jakékoli jiné preferované vývojové prostředí C#.
- Do vašeho projektu byla přidána knihovna Aspose.Slides pro .NET.
## Importovat jmenné prostory
Začněte importem potřebných jmenných prostorů do kódu C#. Tento krok vám zajistí přístup ke třídám a funkcím poskytovaným knihovnou Aspose.Slides.
```csharp
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides;
```
## Krok 1: Nastavení projektu
Začněte vytvořením nového projektu C# ve vámi preferovaném vývojovém prostředí. Nezapomeňte do projektu přidat knihovnu Aspose.Slides for .NET odkazováním na ni.
## Krok 2: Načtení prezentace a obrázku
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
## Krok 3: Přidání rámečku obrázku do snímku
```csharp
IPictureFrame pf = presentation.Slides[0].Shapes.AddPictureFrame(ShapeType.Rectangle, 50, 50, 100, 100, image);
```
Nyní přidejte rámeček obrázku na první snímek prezentace. Upravte parametry, jako je typ tvaru, umístění a rozměry, podle svých požadavků.
## Krok 4: Nastavení relativní šířky a výšky měřítka
```csharp
pf.RelativeScaleHeight = 0.8f;
pf.RelativeScaleWidth = 1.35f;
```
Nastavte relativní výšku a šířku měřítka rámečku obrázku pro dosažení požadovaného efektu škálování.
## Krok 5: Uložení prezentace
```csharp
presentation.Save(dataDir + "Adding Picture Frame with Relative Scale_out.pptx", SaveFormat.Pptx);
```
Nakonec uložte prezentaci s přidaným rámečkem obrázku v zadaném výstupním formátu.
## Závěr
Gratulujeme! Úspěšně jste se naučili, jak přidávat obrazové rámečky s relativní výškou měřítka pomocí Aspose.Slides pro .NET. Experimentujte s různými obrázky, pozicemi a měřítky a vytvářejte vizuálně poutavé prezentace přizpůsobené vašim potřebám.
## Často kladené otázky
### Mohu používat Aspose.Slides pro .NET s jinými programovacími jazyky?
Aspose.Slides primárně podporuje jazyky .NET, ale můžete si prohlédnout i další produkty Aspose, abyste zjistili kompatibilitu s různými platformami.
### Kde najdu podrobnou dokumentaci k Aspose.Slides pro .NET?
Viz [dokumentace](https://reference.aspose.com/slides/net/) pro komplexní informace a příklady.
### Je k dispozici bezplatná zkušební verze Aspose.Slides pro .NET?
Ano, můžete získat [bezplatná zkušební verze](https://releases.aspose.com/) zhodnotit možnosti knihovny.
### Jak mohu získat podporu pro Aspose.Slides pro .NET?
Navštivte [Fórum Aspose.Slides](https://forum.aspose.com/c/slides/11) vyhledat pomoc od komunity a odborníků z Aspose.
### Kde mohu zakoupit Aspose.Slides pro .NET?
Aspose.Slides pro .NET si můžete koupit od [stránka nákupu](https://purchase.aspose.com/buy).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}