---
title: Převést PPT do formátu PPTX
linktitle: Převést PPT do formátu PPTX
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se, jak bez námahy převést PPT na PPTX pomocí Aspose.Slides pro .NET. Podrobný průvodce s příklady kódu pro bezproblémovou transformaci formátu.
weight: 25
url: /cs/net/presentation-manipulation/convert-ppt-to-pptx-format/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Převést PPT do formátu PPTX


Pokud jste někdy potřebovali převést soubory PowerPoint ze staršího formátu PPT do novějšího formátu PPTX pomocí .NET, jste na správném místě. V tomto podrobném tutoriálu vás provedeme procesem pomocí rozhraní Aspose.Slides for .NET API. S touto výkonnou knihovnou můžete takové převody bez námahy zvládnout. Začněme!

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte následující nastavení:

- Visual Studio: Ujistěte se, že máte Visual Studio nainstalované a připravené na vývoj .NET.
-  Aspose.Slides for .NET: Stáhněte si a nainstalujte knihovnu Aspose.Slides for .NET z[tady](https://releases.aspose.com/slides/net/).

## Nastavení projektu

1. Vytvoření nového projektu: Otevřete Visual Studio a vytvořte nový projekt C#.

2. Přidat odkaz na Aspose.Slides: Klikněte pravým tlačítkem na svůj projekt v Průzkumníku řešení, zvolte "Spravovat balíčky NuGet" a vyhledejte "Aspose.Slides." Nainstalujte balíček.

3. Import požadovaných jmenných prostorů:

```csharp
using Aspose.Slides;
```

## Převod PPT na PPTX

Nyní, když máme náš projekt nastaven, napíšeme kód pro převod souboru PPT na PPTX.

```csharp
string dataDir = "Your Document Directory";
string outPath = "Your Output Directory";

string srcFileName = dataDir + "Conversion PPT to PPTX.ppt";
string destFileName = dataDir + "Conversion PPT to PPTX.pptx";

// Vytvořte instanci objektu Presentation, který představuje soubor PPT
Presentation pres = new Presentation(srcFileName);

//Uložení prezentace ve formátu PPTX
pres.Save(outPath, SaveFormat.Pptx);
```

V tomto fragmentu kódu:

- `dataDir` by měla být nahrazena cestou k adresáři, kde se nachází váš soubor PPT.
- `outPath` by měl být nahrazen adresářem, kam chcete uložit převedený soubor PPTX.
- `srcFileName` je název vašeho vstupního souboru PPT.
- `destFileName` je požadovaný název pro výstupní soubor PPTX.

## Závěr

Gratulujeme! Úspěšně jste převedli prezentaci PowerPoint z formátu PPT do formátu PPTX pomocí rozhraní Aspose.Slides for .NET API. Tato výkonná knihovna zjednodušuje složité úkoly, jako je tato, a usnadňuje tak vývoj .NET.

 Pokud jste to ještě neudělali,[stáhnout Aspose.Slides pro .NET](https://releases.aspose.com/slides/net/) a dále zkoumat jeho možnosti.

 Pro další návody a tipy navštivte naše[dokumentace](https://reference.aspose.com/slides/net/).

## Často kladené otázky

### 1. Co je Aspose.Slides pro .NET?
Aspose.Slides for .NET je knihovna .NET, která umožňuje vývojářům vytvářet, manipulovat a převádět PowerPointové prezentace programově.

### 2. Mohu pomocí Aspose.Slides for .NET převést jiné formáty na PPTX?
Ano, Aspose.Slides for .NET podporuje různé formáty, včetně PPT, PPTX, ODP a dalších.

### 3. Je Aspose.Slides for .NET zdarma k použití?
 Ne, je to komerční knihovna, ale můžete prozkoumat a[zkušební verze zdarma](https://releases.aspose.com/) zhodnotit jeho vlastnosti.

### 4. Existují nějaké další formáty dokumentů podporované Aspose.Slides pro .NET?
Ano, Aspose.Slides for .NET také podporuje práci s dokumenty aplikace Word, tabulkami aplikace Excel a dalšími formáty souborů.

### 5. Kde mohu získat podporu nebo se ptát na Aspose.Slides pro .NET?
 Můžete najít odpovědi na své otázky a hledat podporu v[Aspose.Slides fóra](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
