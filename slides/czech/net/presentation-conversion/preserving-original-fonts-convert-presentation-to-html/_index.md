---
title: Zachování původních písem – Převeďte prezentaci do HTML
linktitle: Zachování původních písem – Převeďte prezentaci do HTML
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se, jak zachovat původní písma při převodu prezentací do HTML pomocí Aspose.Slides for .NET. Zajistěte konzistenci písma a vizuální dopad bez námahy.
weight: 14
url: /cs/net/presentation-conversion/preserving-original-fonts-convert-presentation-to-html/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Zachování původních písem – Převeďte prezentaci do HTML


V tomto komplexním průvodci vás provedeme procesem zachování původních písem při převodu prezentace do HTML pomocí Aspose.Slides for .NET. Poskytneme vám potřebný zdrojový kód C# a podrobně vysvětlíme každý krok. Na konci tohoto kurzu budete schopni zajistit, aby písma v převedeném HTML dokumentu zůstala věrná původní prezentaci.

## 1. Úvod

Při převodu prezentací PowerPoint do HTML je důležité zachovat původní písma, aby byla zajištěna vizuální konzistence obsahu. Aspose.Slides for .NET poskytuje výkonné řešení, jak toho dosáhnout. V tomto tutoriálu vás provedeme kroky potřebnými k zachování původních písem během procesu převodu.

## 2. Předpoklady

Než začneme, ujistěte se, že máte splněny následující předpoklady:

- Visual Studio nainstalované na vašem počítači.
- Knihovna Aspose.Slides for .NET byla přidána do vašeho projektu.

## 3. Nastavení vašeho projektu

Chcete-li začít, vytvořte nový projekt v aplikaci Visual Studio a přidejte knihovnu Aspose.Slides for .NET jako referenci.

## 4. Načtení prezentace

K načtení prezentace PowerPoint použijte následující kód:

```csharp
string dataDir = "Your Document Directory";

using (Presentation pres = new Presentation("input.pptx"))
{
    // Váš kód zde
}
```

 Nahradit`"Your Document Directory"` s cestou k souboru prezentace.

## 5. Vyloučení výchozích písem

Chcete-li vyloučit výchozí písma jako Calibri a Arial, použijte následující kód:

```csharp
string[] fontNameExcludeList = { "Calibri", "Arial" };
```

Tento seznam můžete upravit podle potřeby.

## 6. Vkládání všech písem

Dále vložíme všechna písma do dokumentu HTML. Tím je zajištěno zachování původních písem. Použijte následující kód:

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

 Nahradit`"output.html"` s požadovaným názvem výstupního souboru.

## 8. Závěr

V tomto tutoriálu jsme si ukázali, jak zachovat původní písma při převodu prezentace PowerPoint do HTML pomocí Aspose.Slides for .NET. Pomocí těchto kroků můžete zajistit, že převedený dokument HTML zachová vizuální integritu původní prezentace.

## 9. Nejčastější dotazy

### Q1: Mohu přizpůsobit seznam vyloučených písem?

 Ano můžeš. Upravte`fontNameExcludeList`pole pro zahrnutí nebo vyloučení konkrétních písem podle vašich požadavků.

### Q2: Co když nechci vkládat všechna písma?

Pokud chcete vložit pouze konkrétní písma, můžete odpovídajícím způsobem upravit kód. Další podrobnosti naleznete v dokumentaci Aspose.Slides for .NET.

### Q3: Existují nějaké licenční požadavky pro používání Aspose.Slides pro .NET?

Ano, možná budete potřebovat platnou licenci k použití Aspose.Slides for .NET ve svých projektech. Informace o licencích naleznete na webu Aspose.

### Q4: Mohu převést jiné formáty souborů do HTML pomocí Aspose.Slides for .NET?

Aspose.Slides for .NET se primárně zaměřuje na prezentace v PowerPointu. Pro převod jiných formátů souborů do HTML možná budete muset prozkoumat další produkty Aspose přizpůsobené pro tyto formáty.

### Q5: Kde mohu získat přístup k dalším zdrojům a podpoře?

 Další dokumentaci, návody a podporu najdete na webu Aspose. Návštěva[Aspose.Slides pro .NET dokumentaci](https://reference.aspose.com/slides/net/) pro podrobné informace.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
