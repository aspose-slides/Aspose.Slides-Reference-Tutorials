---
title: Převést prezentaci na TIFF s výchozí velikostí
linktitle: Převést prezentaci na TIFF s výchozí velikostí
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se, jak snadno převést prezentace na obrázky TIFF s jejich výchozí velikostí pomocí Aspose.Slides for .NET.
type: docs
weight: 27
url: /cs/net/presentation-manipulation/convert-presentation-to-tiff-with-default-size/
---

## Úvod

Aspose.Slides for .NET je robustní knihovna, která poskytuje komplexní funkce pro vytváření, úpravy a převod prezentací PowerPoint programově. Jednou z jeho pozoruhodných vlastností je schopnost převádět prezentace do různých obrazových formátů, včetně TIFF.

## Předpoklady

Než se pustíme do procesu kódování, musíte se ujistit, že máte splněny následující předpoklady:

- Visual Studio nebo jiné vývojové prostředí .NET
-  Aspose.Slides pro knihovnu .NET (stáhnout z[tady](https://downloads.aspose.com/slides/net)
- Základní znalost programování v C#

## Instalace Aspose.Slides pro .NET

Chcete-li začít, nainstalujte knihovnu Aspose.Slides for .NET podle následujících kroků:

1.  Stáhněte si knihovnu Aspose.Slides for .NET z[tady](https://downloads.aspose.com/slides/net).
2. Rozbalte stažený soubor ZIP do vhodného umístění ve vašem systému.
3. Otevřete projekt sady Visual Studio.

## Načítání prezentace

Jakmile budete mít knihovnu Aspose.Slides integrovanou do svého projektu, můžete začít kódovat. Začněte načtením souboru prezentace, který chcete převést na TIFF. Zde je příklad, jak na to:

```csharp
using Aspose.Slides;

// Načtěte prezentaci
using var presentation = new Presentation("your-presentation.pptx");
```

## Převod na TIFF s výchozí velikostí

Po načtení prezentace je dalším krokem její převod do obrazového formátu TIFF při zachování výchozí velikosti. Tím je zajištěno zachování rozvržení a designu obsahu. Můžete toho dosáhnout takto:

```csharp
// Převést na TIFF s výchozí velikostí
var options = new TiffOptions()
{
    CompressionType = TiffCompressionTypes.Default;
};
presentation.Save("output.tiff", SaveFormat.Tiff, options);
```

## Uložení obrázku TIFF

 Nakonec uložte vygenerovaný obrázek TIFF na požadované místo pomocí`Save` metoda:

```csharp
// Uložte obrázek TIFF
presentation.Save("output.tiff", SaveFormat.Tiff,options);
```

## Závěr

V tomto tutoriálu jsme prošli procesem převodu prezentace do formátu TIFF při zachování její výchozí velikosti pomocí Aspose.Slides pro .NET. Probrali jsme načtení prezentace, provedení převodu a uložení výsledného obrázku TIFF. Aspose.Slides zjednodušuje složité úkoly, jako jsou tyto, a umožňuje vývojářům efektivně pracovat se soubory PowerPoint programově.

## FAQ

### Jak mohu upravit kvalitu obrazu TIFF během převodu?

Kvalitu obrazu TIFF můžete ovládat úpravou možností komprese. Pro dosažení požadované kvality obrazu nastavte různé úrovně komprese.

### Mohu převést konkrétní snímky místo celé prezentace?

 Ano, konkrétní snímky můžete selektivně převést do formátu TIFF pomocí`Slide` třídy pro přístup k jednotlivým snímkům a jejich následnou konverzi a uložení jako obrázky TIFF.

### Je Aspose.Slides for .NET kompatibilní s různými verzemi PowerPointu?

Ano, Aspose.Slides for .NET zajišťuje kompatibilitu napříč různými formáty PowerPoint, včetně PPT, PPTX a dalších.

### Mohu dále upravit nastavení převodu TIFF?

Absolutně! Aspose.Slides for .NET poskytuje širokou škálu možností pro přizpůsobení procesu převodu TIFF, jako je úprava rozlišení, barevných režimů a další.

### Kde najdu další informace o Aspose.Slides pro .NET?

 Pro komplexní dokumentaci a příklady navštivte[Aspose.Slides pro dokumentaci .NET](https://reference.aspose.com/slides/net).