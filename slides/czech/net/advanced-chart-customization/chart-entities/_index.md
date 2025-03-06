---
title: Vytváření krásných grafů pomocí Aspose.Slides pro .NET
linktitle: Entity grafu a formátování
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se vytvářet úžasné grafy pomocí Aspose.Slides pro .NET. Vylepšete svou hru s vizualizací dat pomocí našeho podrobného průvodce.
weight: 13
url: /cs/net/advanced-chart-customization/chart-entities/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


V dnešním světě založeném na datech je efektivní vizualizace dat klíčem k předávání informací vašemu publiku. Aspose.Slides for .NET je výkonná knihovna, která vám umožní vytvářet úžasné prezentace a snímky, včetně poutavých grafů. V tomto tutoriálu vás provedeme procesem vytváření krásných grafů pomocí Aspose.Slides pro .NET. Každý příklad rozdělíme do několika kroků, které vám pomohou pochopit a implementovat entity grafu a formátování. Takže, pojďme začít!

## Předpoklady

Než se vrhneme na vytváření krásných grafů pomocí Aspose.Slides pro .NET, musíte se ujistit, že máte splněny následující předpoklady:

1.  Aspose.Slides for .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides for .NET. Můžete si jej stáhnout z[webová stránka](https://releases.aspose.com/slides/net/).

2. Vývojové prostředí: Měli byste mít funkční vývojové prostředí s Visual Studio nebo jiným IDE, které podporuje vývoj .NET.

3. Základní znalost C#: Znalost programování v C# je pro tento tutoriál nezbytná.

Nyní, když máme naše předpoklady seřazené, pojďme přistoupit k vytváření krásných grafů pomocí Aspose.Slides pro .NET.

## Importovat jmenné prostory

Nejprve musíte importovat potřebné jmenné prostory pro práci s Aspose.Slides pro .NET:

```csharp
using System.IO;
using Aspose.Slides;
using System.Drawing;
using Aspose.Slides.Export;
using Aspose.Slides.Charts;
```

## Krok 1: Vytvořte prezentaci

Začneme vytvořením nové prezentace, se kterou budeme pracovat. Tato prezentace bude sloužit jako plátno pro náš graf.

```csharp
// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";

// Vytvořte adresář, pokud ještě není přítomen.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Okamžitá prezentace
Presentation pres = new Presentation();
```

## Krok 2: Otevřete první snímek

Zpřístupníme první snímek v prezentaci, kam umístíme náš graf.

```csharp
// Přístup k prvnímu snímku
ISlide slide = pres.Slides[0];
```

## Krok 3: Přidejte vzorový graf

Nyní do našeho snímku přidáme vzorový graf. V tomto příkladu vytvoříme spojnicový graf se značkami.

```csharp
// Přidání vzorového grafu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Krok 4: Nastavte název grafu

Náš graf pojmenujeme, aby byl informativnější a vizuálně přitažlivější.

```csharp
// Nastavení názvu grafu
chart.HasTitle = true;
chart.ChartTitle.AddTextFrameForOverriding("");
IPortion chartTitle = chart.ChartTitle.TextFrameForOverriding.Paragraphs[0].Portions[0];
chartTitle.Text = "Sample Chart";
chartTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
chartTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
chartTitle.PortionFormat.FontHeight = 20;
chartTitle.PortionFormat.FontBold = NullableBool.True;
chartTitle.PortionFormat.FontItalic = NullableBool.True;
```

## Krok 5: Přizpůsobte čáry mřížky svislé osy

tomto kroku přizpůsobíme čáry mřížky na svislé ose, aby byl náš graf vizuálně přitažlivější.

```csharp
// Nastavení formátu hlavních čar mřížky pro osu hodnot
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;

// Nastavení formátu vedlejších čar mřížky pro osu hodnot
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;

// Nastavení formátu čísla osy hodnot
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Krok 6: Definujte rozsah vertikální osy

V tomto kroku nastavíme maximální, minimální a jednotkové hodnoty pro vertikální osu.

```csharp
// Nastavovací tabulka maximální, minimální hodnoty
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Krok 7: Přizpůsobte text svislé osy

Nyní přizpůsobíme vzhled textu na svislé ose.

```csharp
// Nastavení vlastností textu osy hodnot
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");

// Nastavení názvu osy hodnot
chart.Axes.VerticalAxis.HasTitle = true;
chart.Axes.VerticalAxis.Title.AddTextFrameForOverriding("");
IPortion valtitle = chart.Axes.VerticalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
valtitle.Text = "Primary Axis";
valtitle.PortionFormat.FillFormat.FillType = FillType.Solid;
valtitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
valtitle.PortionFormat.FontHeight = 20;
valtitle.PortionFormat.FontBold = NullableBool.True;
valtitle.PortionFormat.FontItalic = NullableBool.True;
```

## Krok 8: Přizpůsobte čáry mřížky vodorovné osy

Nyní přizpůsobíme čáry mřížky pro vodorovnou osu.

```csharp
// Nastavení formátu hlavních čar mřížky pro osu kategorie
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Nastavení formátu vedlejších čar mřížky pro osu kategorie
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Nastavení vlastností textu osy kategorie
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Krok 9: Přizpůsobte popisky vodorovné osy

V tomto kroku upravíme polohu a rotaci popisků vodorovné osy.

```csharp
// Nastavení polohy štítku osy kategorie
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Nastavení úhlu natočení štítku osy kategorie
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Krok 10: Přizpůsobte legendy

Vylepšeme legendy v našem grafu pro lepší čitelnost.

```csharp
// Nastavení vlastností textu legend
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Nastavit legendy grafu bez překrývání grafu
chart.Legend.Overlay = true;
```

## Krok 11: Přizpůsobte pozadí grafu

Přizpůsobíme barvy pozadí grafu, zadní stěny a podlahy.

```csharp
// Nastavení barvy zadní stěny grafu
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Nastavení barvy oblasti plotru
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;
```

## Krok 12: Uložte prezentaci

Nakonec uložme naši prezentaci s formátovaným grafem.

```csharp
// Uložit prezentaci
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Závěr

Vytváření krásných a informativních grafů ve vašich prezentacích je nyní s Aspose.Slides pro .NET snazší než kdy dříve. V tomto tutoriálu jsme probrali základní kroky k přizpůsobení různých aspektů grafu, aby byl vizuálně přitažlivý a informativní. Pomocí těchto technik můžete vytvářet úžasné grafy, které efektivně předávají vaše data vašemu publiku.

Začněte experimentovat s Aspose.Slides pro .NET a posuňte vizualizaci dat na další úroveň!

## Často kladené otázky

### 1. Co je Aspose.Slides pro .NET?

Aspose.Slides for .NET je výkonná knihovna, která umožňuje vývojářům .NET vytvářet, manipulovat a převádět prezentace Microsoft PowerPoint. Poskytuje širokou škálu funkcí pro práci se snímky, tvary, grafy a dalšími.

### 2. Kde si mohu stáhnout Aspose.Slides pro .NET?

 Aspose.Slides for .NET si můžete stáhnout z webu[tady](https://releases.aspose.com/slides/net/).

### 3. Je k dispozici bezplatná zkušební verze pro Aspose.Slides pro .NET?

 Ano, můžete získat bezplatnou zkušební verzi Aspose.Slides pro .NET od[tady](https://releases.aspose.com/).

### 4. Jak mohu získat dočasnou licenci pro Aspose.Slides pro .NET?

 Pokud potřebujete dočasnou licenci, můžete ji získat od[tento odkaz](https://purchase.aspose.com/temporary-license/).

### 5. Existuje komunita nebo fórum podpory pro Aspose.Slides for .NET?

 Ano, můžete najít komunitu a fórum podpory Aspose.Slides[tady](https://forum.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
