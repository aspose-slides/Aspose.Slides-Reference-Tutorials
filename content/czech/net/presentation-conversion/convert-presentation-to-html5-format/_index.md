---
title: Převést prezentaci do formátu HTML5
linktitle: Převést prezentaci do formátu HTML5
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se převádět prezentace PowerPoint do formátu HTML5 pomocí Aspose.Slides for .NET. Snadná a efektivní konverze pro sdílení na webu.
type: docs
weight: 22
url: /cs/net/presentation-conversion/convert-presentation-to-html5-format/
---
## Převeďte prezentaci do formátu HTML5 pomocí Aspose.Slides for .NET

V této příručce vás provedeme procesem převodu prezentace PowerPoint (PPT/PPTX) do formátu HTML5 pomocí knihovny Aspose.Slides for .NET. Aspose.Slides je výkonná knihovna, která vám umožňuje manipulovat a převádět PowerPointové prezentace v různých formátech.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

1. Visual Studio: V systému musíte mít nainstalované Visual Studio.
2.  Aspose.Slides for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Slides for .NET z[tady](https://downloads.aspose.com/slides/net).

## Konverzní kroky

Chcete-li převést prezentaci do formátu HTML5, postupujte takto:

### Vytvořit nový projekt

Otevřete Visual Studio a vytvořte nový projekt.

### Přidejte odkaz do Aspose.Slides

Ve svém projektu klikněte pravým tlačítkem na "Reference" v Průzkumníku řešení a vyberte "Přidat odkaz." Procházejte a přidejte Aspose.Slides DLL, kterou jste si stáhli.

### Napište kód konverze

V editoru kódu napište následující kód pro převod prezentace do formátu HTML5:

```csharp
using Aspose.Slides;
using Aspose.Slides.Export;

namespace PresentationToHTML5Converter
{
    class Program
    {
        static void Main(string[] args)
        {
            // Načtěte prezentaci
            using (Presentation presentation = new Presentation("input.pptx"))
            {
                // Definujte možnosti HTML5
                Html5Options options = new Html5Options();

                // Uložit prezentaci jako HTML5
                presentation.Save("output.html", SaveFormat.Html, options);
            }
        }
    }
}
```

 Nahradit`"input.pptx"` s cestou k vaší vstupní prezentaci a`"output.html"` s požadovanou cestou výstupního HTML souboru.

## Spusťte aplikaci

Sestavte a spusťte svou aplikaci. Převede prezentaci do formátu HTML5 a uloží ji jako soubor HTML.

## Závěr

Pomocí těchto kroků můžete snadno převést prezentace PowerPoint do formátu HTML5 pomocí knihovny Aspose.Slides for .NET. To vám umožní sdílet vaše prezentace na webu, aniž byste potřebovali software PowerPoint.

## FAQ

### Jak mohu přizpůsobit vzhled výstupu HTML5?

Vzhled výstupu HTML5 můžete přizpůsobit nastavením různých možností v`Html5Options` třída. Odkazovat na[dokumentace](https://reference.aspose.com/slides/net/aspose.slides.export/html5options) pro dostupné možnosti přizpůsobení.

### Mohu převádět prezentace s animacemi a přechody?

Ano, Aspose.Slides for .NET podporuje převod prezentací s animacemi a přechody do formátu HTML5.

### Je k dispozici zkušební verze Aspose.Slides?

 Ano, můžete získat bezplatnou zkušební verzi Aspose.Slides pro .NET od[stránka ke stažení](https://releases.aspose.com/slides/net).