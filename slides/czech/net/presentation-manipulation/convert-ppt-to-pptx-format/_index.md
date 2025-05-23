---
"description": "Naučte se, jak snadno převést PPT do PPTX pomocí Aspose.Slides pro .NET. Podrobný návod s příklady kódu pro bezproblémovou transformaci formátu."
"linktitle": "Převod PPT do formátu PPTX"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Převod PPT do formátu PPTX"
"url": "/cs/net/presentation-manipulation/convert-ppt-to-pptx-format/"
"weight": 25
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Převod PPT do formátu PPTX


Pokud jste někdy potřebovali převést soubory PowerPointu ze staršího formátu PPT do novějšího formátu PPTX pomocí .NET, jste na správném místě. V tomto podrobném návodu vás provedeme procesem s využitím rozhraní Aspose.Slides pro .NET API. S touto výkonnou knihovnou zvládnete takové převody snadno a bez námahy. Pojďme na to!

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte následující nastavení:

- Visual Studio: Ujistěte se, že máte nainstalované Visual Studio a připravené pro vývoj v .NET.
- Aspose.Slides pro .NET: Stáhněte a nainstalujte knihovnu Aspose.Slides pro .NET z [zde](https://releases.aspose.com/slides/net/).

## Nastavení projektu

1. Vytvoření nového projektu: Otevřete Visual Studio a vytvořte nový projekt C#.

2. Přidání odkazu na Aspose.Slides: Klikněte pravým tlačítkem myši na projekt v Průzkumníku řešení, vyberte možnost „Spravovat balíčky NuGet“ a vyhledejte „Aspose.Slides“. Nainstalujte balíček.

3. Importovat požadované jmenné prostory:

```csharp
using Aspose.Slides;
```

## Převod PPT do PPTX

Nyní, když máme náš projekt nastavený, pojďme napsat kód pro převod souboru PPT do formátu PPTX.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// Vytvoření instance objektu Presentation, který představuje soubor PPT
Presentation pres = new Presentation(srcFileName);

// Uložení prezentace ve formátu PPTX
pres.Save(outPath, SaveFormat.Pptx);
```

V tomto úryvku kódu:

- `dataDir` by mělo být nahrazeno cestou k adresáři, kde se nachází váš soubor PPT.
- `outPath` by měl být nahrazen adresářem, kam chcete uložit převedený soubor PPTX.
- `srcFileName` je název vašeho vstupního souboru PPT.
- `destFileName` je požadovaný název výstupního souboru PPTX.

## Závěr

Gratulujeme! Úspěšně jste převedli prezentaci v PowerPointu z formátu PPT do formátu PPTX pomocí rozhraní Aspose.Slides pro .NET API. Tato výkonná knihovna zjednodušuje složité úkoly, jako je tento, a usnadňuje vám vývoj v .NET.

Pokud jste tak ještě neučinili, [Stáhněte si Aspose.Slides pro .NET](https://releases.aspose.com/slides/net/) a dále prozkoumat jeho možnosti.

Pro více návodů a tipů navštivte naše [dokumentace](https://reference.aspose.com/slides/net/).

## Často kladené otázky

### 1. Co je Aspose.Slides pro .NET?
Aspose.Slides pro .NET je knihovna pro .NET, která umožňuje vývojářům programově vytvářet, manipulovat a převádět prezentace v PowerPointu.

### 2. Mohu převést jiné formáty do PPTX pomocí Aspose.Slides pro .NET?
Ano, Aspose.Slides pro .NET podporuje různé formáty, včetně PPT, PPTX, ODP a dalších.

### 3. Je Aspose.Slides pro .NET zdarma?
Ne, je to komerční knihovna, ale můžete si prohlédnout [bezplatná zkušební verze](https://releases.aspose.com/) aby zhodnotili jeho vlastnosti.

### 4. Jsou v Aspose.Slides pro .NET podporovány i nějaké další formáty dokumentů?
Ano, Aspose.Slides pro .NET také podporuje práci s dokumenty Word, tabulkami Excel a dalšími formáty souborů.

### 5. Kde mohu získat podporu nebo se zeptat na otázky ohledně Aspose.Slides pro .NET?
Odpovědi na své otázky a podporu můžete najít v [Fóra Aspose.Slides](https://forum.aspose.com/).



{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}