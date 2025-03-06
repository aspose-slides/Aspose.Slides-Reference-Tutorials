---
title: Pokročilé přizpůsobení grafu v Aspose.Slides
linktitle: Pokročilé přizpůsobení grafu v Aspose.Slides
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se pokročilé přizpůsobení grafu v Aspose.Slides pro .NET. Vytvářejte vizuálně přitažlivé grafy s podrobnými pokyny.
weight: 10
url: /cs/net/advanced-chart-customization/advanced-chart-customization/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Pokročilé přizpůsobení grafu v Aspose.Slides


Vytváření vizuálně přitažlivých a informativních grafů je nezbytnou součástí prezentace dat v mnoha aplikacích. Aspose.Slides for .NET poskytuje robustní nástroje pro přizpůsobení grafů, což vám umožní doladit každý aspekt vašich grafů. V tomto tutoriálu prozkoumáme pokročilé techniky přizpůsobení grafu pomocí Aspose.Slides pro .NET.

## Předpoklady

Než se ponoříte do pokročilého přizpůsobení grafu pomocí Aspose.Slides pro .NET, ujistěte se, že máte splněny následující předpoklady:

1. Knihovna Aspose.Slides for .NET: Ve svém projektu .NET musíte mít nainstalovanou a správně nakonfigurovanou knihovnu Aspose.Slides. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/net/).

2. Vývojové prostředí .NET: Měli byste mít nastavené vývojové prostředí .NET, včetně Visual Studia nebo jakéhokoli jiného IDE dle vašeho výběru.

3. Základní znalost C#: Pomůže nám znalost programovacího jazyka C#, protože budeme psát kód C# pro práci s Aspose.Slides.

Nyní rozdělíme pokročilé přizpůsobení grafu do několika kroků, které vás celým procesem provedou.

## Krok 1: Vytvořte prezentaci

Nejprve vytvořte novou prezentaci pomocí Aspose.Slides.

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

V tomto kroku zahájíme novou prezentaci, která bude držet náš graf.

## Krok 2: Otevřete první snímek

Dále otevřete první snímek v prezentaci, kam chcete graf přidat.

```csharp
// Přístup k prvnímu snímku
ISlide slide = pres.Slides[0];
```

Tento fragment kódu vám umožňuje pracovat s prvním snímkem prezentace.

## Krok 3: Přidání vzorového grafu

Nyní přidáme na snímek ukázkový graf. V tomto příkladu vytvoříme spojnicový graf se značkami.

```csharp
// Přidání vzorového grafu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

Zde určíme typ grafu (LineWithMarkers) a jeho polohu a rozměry na snímku.

## Krok 4: Nastavení názvu grafu

Nastavíme název grafu, který poskytne kontext.

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

Tento kód nastavuje název grafu, určuje jeho text, vzhled a styl písma.

## Krok 5: Přizpůsobte hlavní čáry mřížky

Nyní přizpůsobíme hlavní čáry mřížky pro osu hodnot.

```csharp
// Nastavení formátu hlavních čar mřížky pro osu hodnot
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Blue;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.Width = 5;
chart.Axes.VerticalAxis.MajorGridLinesFormat.Line.DashStyle = LineDashStyle.DashDot;
```

Tento krok nakonfiguruje vzhled hlavních čar mřížky na ose hodnot.

## Krok 6: Přizpůsobte vedlejší čáry mřížky

Podobně můžeme přizpůsobit vedlejší čáry mřížky pro osu hodnot.

```csharp
// Nastavení formátu vedlejších čar mřížky pro osu hodnot
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Red;
chart.Axes.VerticalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Tento kód upravuje vzhled vedlejších čar mřížky na ose hodnot.

## Krok 7: Definujte formát čísla osy hodnot

Upravte formát čísla pro osu hodnot.

```csharp
// Nastavení formátu čísla osy hodnot
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

Tento krok vám umožňuje formátovat čísla zobrazená na ose hodnot.

## Krok 8: Nastavte maximální a minimální hodnoty grafu

Definujte maximální a minimální hodnoty pro graf.

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

Zde určíte rozsah hodnot, které má osa grafu zobrazovat.

## Krok 9: Přizpůsobte vlastnosti textu osy hodnot

Můžete také přizpůsobit vlastnosti textu osy hodnot.

```csharp
// Nastavení vlastností textu osy hodnot
IChartPortionFormat txtVal = chart.Axes.VerticalAxis.TextFormat.PortionFormat;
txtVal.FontBold = NullableBool.True;
txtVal.FontHeight = 16;
txtVal.FontItalic = NullableBool.True;
txtVal.FillFormat.FillType = FillType.Solid;
txtVal.FillFormat.SolidFillColor.Color = Color.DarkGreen;
txtVal.LatinFont = new FontData("Times New Roman");
```

Tento kód umožňuje upravit styl písma a vzhled popisků osy hodnot.

## Krok 10: Přidejte název osy hodnoty

Pokud váš graf vyžaduje název pro osu hodnot, můžete jej přidat tímto krokem.

```csharp
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

V tomto kroku můžete nastavit název pro osu hodnot.

## Krok 11: Přizpůsobte hlavní čáry mřížky pro osu kategorie

Nyní se zaměřme na hlavní čáry mřížky pro osu kategorií.

```csharp
// Nastavení formátu hlavních čar mřížky pro osu kategorie
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes

.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;
```

Tento kód konfiguruje vzhled hlavních čar mřížky na ose kategorií.

## Krok 12: Upravte vedlejší čáry mřížky pro osu kategorie

Podobně jako u osy hodnot můžete přizpůsobit vedlejší čáry mřížky pro osu kategorií.

```csharp
// Nastavení formátu vedlejších čar mřížky pro osu kategorie
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;
```

Zde můžete upravit vzhled vedlejších čar mřížky na ose kategorie.

## Krok 13: Přizpůsobte vlastnosti textu osy kategorie

Upravte vlastnosti textu pro popisky os kategorií.

```csharp
// Nastavení vlastností textu osy kategorie
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.FillType = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

Tento kód umožňuje upravit styl písma a vzhled popisků os kategorií.

## Krok 14: Přidejte název osy kategorie

V případě potřeby můžete také přidat název na osu kategorie.

```csharp
// Nastavení názvu kategorie
chart.Axes.HorizontalAxis.HasTitle = true;
chart.Axes.HorizontalAxis.Title.AddTextFrameForOverriding("");

IPortion catTitle = chart.Axes.HorizontalAxis.Title.TextFrameForOverriding.Paragraphs[0].Portions[0];
catTitle.Text = "Sample Category";
catTitle.PortionFormat.FillFormat.FillType = FillType.Solid;
catTitle.PortionFormat.FillFormat.SolidFillColor.Color = Color.Gray;
catTitle.PortionFormat.FontHeight = 20;
catTitle.PortionFormat.FontBold = NullableBool.True;
catTitle.PortionFormat.FontItalic = NullableBool.True;
```

V tomto kroku můžete nastavit název pro osu kategorií.

## Krok 15: Další přizpůsobení

Můžete prozkoumat další přizpůsobení, jako jsou legendy, zadní stěna grafu, podlaha a barvy plochy grafu. Tato přizpůsobení vám umožní zlepšit vizuální přitažlivost vašeho grafu.

```csharp
// Další přizpůsobení (volitelné)

// Nastavení vlastností textu legend
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Nastavit legendy grafu bez překrývání grafu
chart.Legend.Overlay = true;

// Vynesení první série na sekundární osu hodnot (v případě potřeby)
// Chart.ChartData.Series[0].PlotOnSecondAxis = true;

// Nastavení barvy zadní stěny grafu
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

// Nastavení barvy podlahy grafu
chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

//Nastavení barvy oblasti plotru
chart.PlotArea.Format.Fill.FillType = FillType.Solid;
chart.PlotArea.Format.Fill.SolidFillColor.Color = Color.LightCyan;

// Uložte prezentaci
pres.Save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

Tato další přizpůsobení jsou volitelná a lze je použít na základě vašich konkrétních požadavků na návrh grafu.

## Závěr

tomto podrobném průvodci jsme prozkoumali pokročilé přizpůsobení grafu pomocí Aspose.Slides pro .NET. Naučili jste se, jak vytvořit prezentaci, přidat graf a doladit jeho vzhled, včetně čar mřížky, popisků os a dalších vizuálních prvků. S výkonnými možnostmi přizpůsobení, které poskytuje Aspose.Slides, můžete vytvářet grafy, které efektivně zprostředkují vaše data a zaujmou vaše publikum.

 Pokud máte nějaké dotazy nebo se při práci s Aspose.Slides pro .NET setkáte s nějakými problémy, neváhejte prozkoumat dokumentaci[tady](https://reference.aspose.com/slides/net/) nebo vyhledejte pomoc v Aspose.Slides[Fórum](https://forum.aspose.com/).

## Nejčastější dotazy

### Jaké verze .NET jsou podporovány Aspose.Slides pro .NET?
Aspose.Slides for .NET podporuje různé verze .NET, včetně .NET Framework a .NET Core. Úplný seznam podporovaných verzí naleznete v dokumentaci.

### Mohu pomocí Aspose.Slides for .NET vytvářet grafy ze zdrojů dat, jako jsou soubory aplikace Excel?
Ano, Aspose.Slides for .NET vám umožňuje vytvářet grafy z externích zdrojů dat, jako jsou tabulky aplikace Excel. Podrobné příklady si můžete prohlédnout v dokumentaci.

### Jak mohu do řady grafů přidat vlastní štítky dat?
 Chcete-li k řadě grafů přidat vlastní štítky dat, můžete získat přístup k`DataLabels` vlastnost série a upravte štítky podle potřeby. Ukázky kódu a příklady naleznete v dokumentaci.

### Je možné exportovat graf do různých formátů souborů, jako je PDF nebo obrázkové formáty?
Ano, Aspose.Slides for .NET poskytuje možnosti exportu prezentace s grafy do různých formátů, včetně PDF a obrazových formátů. Knihovnu můžete použít k uložení své práce v požadovaném výstupním formátu.

### Kde najdu další návody a příklady pro Aspose.Slides pro .NET?
 Na Aspose.Slides můžete najít nepřeberné množství výukových programů, příkladů kódu a dokumentace[webová stránka](https://reference.aspose.com/slides/net/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
