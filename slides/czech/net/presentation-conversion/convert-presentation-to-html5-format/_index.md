---
"description": "Naučte se, jak převést prezentace v PowerPointu do formátu HTML5 pomocí Aspose.Slides pro .NET. Snadná a efektivní konverze pro sdílení na webu."
"linktitle": "Převod prezentace do formátu HTML5"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Převod prezentace do formátu HTML5"
"url": "/cs/net/presentation-conversion/convert-presentation-to-html5-format/"
"weight": 22
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Převod prezentace do formátu HTML5

## Převod prezentace do formátu HTML5 pomocí Aspose.Slides pro .NET

této příručce vás provedeme procesem převodu prezentace v PowerPointu (PPT/PPTX) do formátu HTML5 pomocí knihovny Aspose.Slides pro .NET. Aspose.Slides je výkonná knihovna, která umožňuje manipulovat s prezentacemi v PowerPointu a převádět je v různých formátech.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Visual Studio: V systému musíte mít nainstalované Visual Studio.
2. Aspose.Slides pro .NET: Stáhněte a nainstalujte knihovnu Aspose.Slides pro .NET z [zde](https://downloads.aspose.com/slides/net).

## Kroky konverze

Chcete-li převést prezentaci do formátu HTML5, postupujte takto:

### Vytvořit nový projekt

Otevřete Visual Studio a vytvořte nový projekt.

### Přidat odkaz na Aspose.Slides

Ve vašem projektu klikněte pravým tlačítkem myši na „Reference“ v Průzkumníku řešení a vyberte „Přidat referenci“. Vyhledejte a přidejte staženou knihovnu DLL Aspose.Slides.

### Napište konverzní kód

editoru kódu napište následující kód pro převod prezentace do formátu HTML5:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

namespace PresentationToHTML5Converter
{
    class Program
    {
        static void Main(string[] args)
        {
            // Načíst prezentaci
            using (Presentation presentation = new Presentation("input.pptx"))
            {
                // Definování možností HTML5
                Html5Options options = new Html5Options();

                // Uložit prezentaci jako HTML5
                presentation.Save("output.html", SaveFormat.Html, options);
            }
        }
    }
}
```

Nahradit `"input.pptx"` s cestou k vaší vstupní prezentaci a `"output.html"` s požadovanou cestou k výstupnímu HTML souboru.

## Spusťte aplikaci

Sestavte a spusťte aplikaci. Aplikace převede prezentaci do formátu HTML5 a uloží ji jako soubor HTML.

## Závěr

Pomocí těchto kroků můžete snadno převést prezentace PowerPointu do formátu HTML5 pomocí knihovny Aspose.Slides pro .NET. To vám umožní sdílet vaše prezentace na webu bez nutnosti použití softwaru PowerPoint.

## Často kladené otázky

### Jak mohu přizpůsobit vzhled výstupu HTML5?

Vzhled výstupu HTML5 si můžete přizpůsobit nastavením různých možností v `Html5Options` třída. Viz [dokumentace](https://reference.aspose.com/slides/net/aspose.slides.export/html5options) pro dostupné možnosti přizpůsobení.

### Mohu převádět prezentace s animacemi a přechody?

Ano, Aspose.Slides pro .NET podporuje převod prezentací s animacemi a přechody do formátu HTML5.

### Je k dispozici zkušební verze Aspose.Slides?

Ano, můžete získat bezplatnou zkušební verzi Aspose.Slides pro .NET z [stránka ke stažení](https://releases.aspose.com/slides/net).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}