---
"description": "Naučte se, jak zachovat původní písma při převodu prezentací do HTML pomocí Aspose.Slides pro .NET. Zajistěte konzistenci písma a vizuální dojem bez námahy."
"linktitle": "Zachování původních písem - Převod prezentace do HTML"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Zachování původních písem - Převod prezentace do HTML"
"url": "/cs/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/"
"weight": 14
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Zachování původních písem - Převod prezentace do HTML


V tomto komplexním průvodci vás provedeme procesem zachování původních písem při převodu prezentace do HTML pomocí Aspose.Slides pro .NET. Poskytneme vám potřebný zdrojový kód v jazyce C# a podrobně vysvětlíme každý krok. Po dokončení tohoto tutoriálu budete schopni zajistit, aby písma ve vašem převedeném HTML dokumentu zůstala věrná původní prezentaci.

## 1. Úvod

Při převodu prezentací v PowerPointu do HTML je zásadní zachovat původní písma, aby byla zajištěna vizuální konzistence obsahu. Aspose.Slides pro .NET nabízí výkonné řešení, jak toho dosáhnout. V tomto tutoriálu vás provedeme kroky potřebnými k zachování původních písem během procesu převodu.

## 2. Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

- Visual Studio nainstalované na vašem počítači.
- Do vašeho projektu byla přidána knihovna Aspose.Slides pro .NET.

## 3. Nastavení projektu

Chcete-li začít, vytvořte nový projekt ve Visual Studiu a přidejte do něj knihovnu Aspose.Slides for .NET jako referenci.

## 4. Načítání prezentace

Pro načtení prezentace v PowerPointu použijte následující kód:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Váš kód zde
}
```

Nahradit `"Your Document Directory"` s cestou k souboru s prezentací.

## 5. Vyloučení výchozích písem

Chcete-li vyloučit výchozí fonty jako Calibri a Arial, použijte následující kód:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Tento seznam si můžete upravit dle potřeby.

## 6. Vkládání všech písem

Dále vložíme všechna písma do HTML dokumentu. Tím zajistíme zachování původních písem. Použijte následující kód:

```csharp
EmbedAllFontsHtmlController embedFontsController = new EmbedAllFontsHtmlController(fontNameExcludeList);

HtmlOptions htmlOptionsEmbed = new HtmlOptions
{
    HtmlFormatter = HtmlFormatter.CreateCustomFormatter(embedFontsController)
};
```

## 7. Uložení jako HTML

Nyní uložte prezentaci jako dokument HTML s vloženými fonty:

```csharp
pres.Save("output.html", SaveFormat.Html, htmlOptionsEmbed);
```

Nahradit `"output.html"` s požadovaným názvem výstupního souboru.

## 8. Závěr

V tomto tutoriálu jsme si ukázali, jak zachovat původní písma při převodu prezentace v PowerPointu do HTML pomocí Aspose.Slides pro .NET. Dodržením těchto kroků zajistíte, že si váš převedený dokument HTML zachová vizuální integritu původní prezentace.

## 9. Často kladené otázky

### Q1: Mohu si přizpůsobit seznam vyloučených písem?

Ano, můžete. Upravit `fontNameExcludeList` pole pro zahrnutí nebo vyloučení konkrétních písem podle vašich požadavků.

### Q2: Co když nechci vkládat všechna písma?

Pokud chcete vložit pouze konkrétní písma, můžete kód odpovídajícím způsobem upravit. Další podrobnosti naleznete v dokumentaci k Aspose.Slides pro .NET.

### Q3: Existují nějaké licenční požadavky pro používání Aspose.Slides pro .NET?

Ano, k používání Aspose.Slides pro .NET ve vašich projektech budete možná potřebovat platnou licenci. Informace o licencování naleznete na webových stránkách Aspose.

### Q4: Mohu převést jiné formáty souborů do HTML pomocí Aspose.Slides pro .NET?

Aspose.Slides pro .NET se primárně zaměřuje na prezentace v PowerPointu. Pro převod jiných formátů souborů do HTML budete možná muset prozkoumat další produkty Aspose určené pro tyto formáty.

### Q5: Kde mohu získat další zdroje a podporu?

Další dokumentaci, návody a podporu naleznete na webových stránkách Aspose. Navštivte [Dokumentace k Aspose.Slides pro .NET](https://reference.aspose.com/slides/net/) pro podrobné informace.


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}