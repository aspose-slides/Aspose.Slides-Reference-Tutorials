---
"description": "Naučte se, jak vytvářet úžasné grafy s Aspose.Slides pro .NET. Posuňte svou vizualizaci dat na vyšší úroveň s naším podrobným návodem."
"linktitle": "Entity grafu a formátování"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Vytváření krásných grafů s Aspose.Slides pro .NET"
"url": "/cs/net/advanced-chart-customization/chart-entities/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Vytváření krásných grafů s Aspose.Slides pro .NET


V dnešním světě založeném na datech je efektivní vizualizace dat klíčem k předávání informací vašemu publiku. Aspose.Slides pro .NET je výkonná knihovna, která vám umožňuje vytvářet úžasné prezentace a snímky, včetně poutavých grafů. V tomto tutoriálu vás provedeme procesem vytváření krásných grafů pomocí Aspose.Slides pro .NET. Každý příklad rozdělíme do několika kroků, abyste pochopili a implementovali entity grafů a formátování. Tak pojďme na to!

## Předpoklady

Než se pustíme do vytváření krásných grafů s Aspose.Slides pro .NET, je třeba se ujistit, že máte splněny následující předpoklady:

1. Aspose.Slides pro .NET: Ujistěte se, že máte nainstalovanou knihovnu Aspose.Slides pro .NET. Můžete si ji stáhnout z [webové stránky](https://releases.aspose.com/slides/net/).

2. Vývojové prostředí: Měli byste mít funkční vývojové prostředí s Visual Studiem nebo jiným IDE, které podporuje vývoj v .NET.

3. Základní znalost C#: Znalost programování v C# je pro tento tutoriál nezbytná.

Nyní, když máme splněny všechny předpoklady, pojďme k tvorbě krásných grafů pomocí Aspose.Slides pro .NET.

## Importovat jmenné prostory

Nejprve je třeba importovat potřebné jmenné prostory pro práci s Aspose.Slides pro .NET:

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
// Cesta k adresáři s dokumenty.
string dataDir = "Your Document Directory";

// Vytvořte adresář, pokud ještě neexistuje.
bool IsExists = System.IO.Directory.Exists(dataDir);
if (!IsExists)
    System.IO.Directory.CreateDirectory(dataDir);

// Vytváření instance prezentace
Presentation pres = new Presentation();
```

## Krok 2: Otevření prvního snímku

Přejděme k prvnímu snímku v prezentaci, kam umístíme náš graf.

```csharp
// Přístup k prvnímu snímku
ISlide slide = pres.Slides[0];
```

## Krok 3: Přidání vzorového grafu

Nyní přidáme na náš snímek ukázkový graf. V tomto příkladu vytvoříme spojnicový graf se značkami.

```csharp
// Přidání ukázkového grafu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Krok 4: Nastavení názvu grafu

Dáme našemu grafu název, díky kterému bude informativnější a vizuálně atraktivnější.

```csharp
// Název grafu nastavení
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

## Krok 5: Úprava čar mřížky svislé osy

V tomto kroku upravíme čáry mřížky svislé osy, aby byl náš graf vizuálně atraktivnější.

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

// Nastavení formátu čísel osy hodnot
chart.Axes.VerticalAxis.IsNumberFormatLinkedToSource = false;
chart.Axes.VerticalAxis.DisplayUnit = DisplayUnitType.Thousands;
chart.Axes.VerticalAxis.NumberFormat = "0.0%";
```

## Krok 6: Definování rozsahu svislé osy

V tomto kroku nastavíme maximální, minimální a jednotkové hodnoty pro svislou osu.

```csharp
// Maximální a minimální hodnoty v tabulce nastavení
chart.Axes.VerticalAxis.IsAutomaticMajorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMaxValue = false;
chart.Axes.VerticalAxis.IsAutomaticMinorUnit = false;
chart.Axes.VerticalAxis.IsAutomaticMinValue = false;

chart.Axes.VerticalAxis.MaxValue = 15f;
chart.Axes.VerticalAxis.MinValue = -2f;
chart.Axes.VerticalAxis.MinorUnit = 0.5f;
chart.Axes.VerticalAxis.MajorUnit = 2.0f;
```

## Krok 7: Úprava textu na svislé ose

Nyní upravíme vzhled textu na svislé ose.

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

## Krok 8: Úprava čar mřížky vodorovné osy

Nyní si upravme čáry mřížky pro vodorovnou osu.

```csharp
// Nastavení formátu hlavních čar mřížky pro osu kategorií
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Green;
chart.Axes.HorizontalAxis.MajorGridLinesFormat.Line.Width = 5;

// Nastavení formátu vedlejších čar mřížky pro osu kategorií
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.FillType = FillType.Solid;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.FillFormat.SolidFillColor.Color = Color.Yellow;
chart.Axes.HorizontalAxis.MinorGridLinesFormat.Line.Width = 3;

// Nastavení vlastností textu osy kategorií
IChartPortionFormat txtCat = chart.Axes.HorizontalAxis.TextFormat.PortionFormat;
txtCat.FontBold = NullableBool.True;
txtCat.FontHeight = 16;
txtCat.FontItalic = NullableBool.True;
txtCat.FillFormat.Fill

Type = FillType.Solid;
txtCat.FillFormat.SolidFillColor.Color = Color.Blue;
txtCat.LatinFont = new FontData("Arial");
```

## Krok 9: Úprava popisků vodorovných os

V tomto kroku upravíme polohu a natočení popisků vodorovných os.

```csharp
// Nastavení pozice popisku osy kategorií
chart.Axes.HorizontalAxis.TickLabelPosition = TickLabelPositionType.Low;

// Nastavení úhlu natočení popisku osy kategorie
chart.Axes.HorizontalAxis.TickLabelRotationAngle = 45;
```

## Krok 10: Úprava legend

Vylepšeme legendy v našem grafu pro lepší čitelnost.

```csharp
// Nastavení vlastností textu legendy
IChartPortionFormat txtleg = chart.Legend.TextFormat.PortionFormat;
txtleg.FontBold = NullableBool.True;
txtleg.FontHeight = 16;
txtleg.FontItalic = NullableBool.True;
txtleg.FillFormat.FillType = FillType.Solid;
txtleg.FillFormat.SolidFillColor.Color = Color.DarkRed;

// Nastavit zobrazení legend grafu bez překrývání grafů
chart.Legend.Overlay = true;
```

## Krok 11: Úprava pozadí grafu

Přizpůsobíme barvy pozadí grafu, zadní stěny a podlahy.

```csharp
// Barva zadní stěny tabulky nastavení
chart.BackWall.Thickness = 1;
chart.BackWall.Format.Fill.FillType = FillType.Solid;
chart.BackWall.Format.Fill.SolidFillColor.Color = Color.Orange;

chart.Floor.Format.Fill.FillType = FillType.Solid;
chart.Floor.Format.Fill.SolidFillColor.Color = Color.Red;

// Nastavení barvy oblasti grafu
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

Vytváření krásných a informativních grafů ve vašich prezentacích je nyní s Aspose.Slides pro .NET snazší než kdy dříve. V tomto tutoriálu jsme se zabývali základními kroky pro přizpůsobení různých aspektů grafu, aby byl vizuálně přitažlivý a informativní. S těmito technikami můžete vytvářet úžasné grafy, které efektivně sdělí vaše data vašemu publiku.

Začněte experimentovat s Aspose.Slides pro .NET a posuňte vizualizaci dat na další úroveň!

## Často kladené otázky

### 1. Co je Aspose.Slides pro .NET?

Aspose.Slides pro .NET je výkonná knihovna, která umožňuje vývojářům v .NET vytvářet, manipulovat s prezentacemi v Microsoft PowerPointu a převádět je. Nabízí širokou škálu funkcí pro práci se snímky, tvary, grafy a dalšími prvky.

### 2. Kde si mohu stáhnout Aspose.Slides pro .NET?

Aspose.Slides pro .NET si můžete stáhnout z webových stránek [zde](https://releases.aspose.com/slides/net/).

### 3. Je k dispozici bezplatná zkušební verze Aspose.Slides pro .NET?

Ano, můžete získat bezplatnou zkušební verzi Aspose.Slides pro .NET od [zde](https://releases.aspose.com/).

### 4. Jak mohu získat dočasnou licenci pro Aspose.Slides pro .NET?

Pokud potřebujete dočasnou licenci, můžete si ji pořídit od [tento odkaz](https://purchase.aspose.com/temporary-license/).

### 5. Existuje komunita nebo fórum podpory pro Aspose.Slides pro .NET?

Ano, najdete komunitu a fórum podpory Aspose.Slides. [zde](https://forum.aspose.com/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}