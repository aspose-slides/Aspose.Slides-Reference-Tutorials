---
"date": "2025-04-15"
"description": "Naučte se, jak vylepšit své prezentace pomocí bodových grafů pomocí Aspose.Slides pro .NET. Postupujte podle tohoto komplexního průvodce a efektivně vytvářejte a upravujte grafy."
"title": "Přidání bodových grafů do prezentací pomocí Aspose.Slides .NET – Podrobný návod"
"url": "/cs/net/charts-graphs/aspose-slides-net-scatter-charts-presentation-guide/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Přidání bodových grafů do prezentací pomocí Aspose.Slides .NET: Podrobný návod

## Zavedení
Chcete vylepšit své prezentace snadnou integrací bodových grafů? Díky síle Aspose.Slides pro .NET se vytváření a úprava grafů stává hračkou. Tento tutoriál vás provede přidáváním bodových grafů do vašich snímků pomocí Aspose.Slides pro .NET. Zvládnutím těchto technik budete prezentovat data efektivněji a vytvářet vizuálně poutavé prezentace.

**Co se naučíte:**
- Nastavení Aspose.Slides pro .NET ve vašem projektu
- Vytvoření nové prezentace a přístup k jejímu prvnímu snímku
- Přidání bodových grafů s hladkými čarami do snímků
- Vymazání stávajících řad a přidání nových do grafů
- Úprava datových bodů a stylů značek pro vylepšenou vizualizaci
- Uložení prezentace do zadaného adresáře

Začněme tím, že si projdeme předpoklady.

## Předpoklady
Před implementací Aspose.Slides pro .NET se ujistěte, že máte následující:
- **Knihovna Aspose.Slides pro .NET**Verze 23.7 nebo novější.
- **Vývojové prostředí**Visual Studio 2019 nebo novější s .NET Framework 4.6.1+ nebo .NET Core/5+.
- **Základní znalost C#**Znalost objektově orientovaného programování v jazyce C#.

## Nastavení Aspose.Slides pro .NET
Abyste mohli začít používat Aspose.Slides, musíte si do projektu nainstalovat knihovnu. Postupujte takto:

**Použití .NET CLI:**
```bash
dotnet add package Aspose.Slides
```

**Použití konzole Správce balíčků:**
```powershell
Install-Package Aspose.Slides
```

**Uživatelské rozhraní Správce balíčků NuGet:**
- Vyhledejte „Aspose.Slides“ a nainstalujte nejnovější verzi.

### Získání licence
Můžete začít s bezplatnou zkušební verzí nebo požádat o dočasnou licenci, abyste si mohli vyzkoušet všechny funkce. Chcete-li si licenci zakoupit, postupujte takto:
1. Návštěva [Zakoupit Aspose.Slides](https://purchase.aspose.com/buy) koupit plnou licenci.
2. Pro dočasnou licenci navštivte [Stránka s dočasnou licencí](https://purchase.aspose.com/temporary-license/).

Jakmile získáte licenční soubor, přidejte jej do svého projektu pomocí:
```csharp
Aspose.Slides.License license = new Aspose.Slides.License();
license.SetLicense("Aspose.Slides.lic");
```

## Průvodce implementací
Implementaci rozdělíme do logických sekcí na základě funkcí.

### Vytvořit prezentaci a přidat snímek
Tato část ukazuje, jak vytvořit prezentaci a zobrazit její první snímek.

#### Přehled
Začněte vytvořením instance `Presentation` třída, která představuje váš soubor PowerPoint. Přístup k snímkům je pomocí tohoto objektového modelu přímočarý.

#### Kroky implementace
**Krok 1: Inicializace prezentace**
```csharp
using Aspose.Slides;

// Vytvořte novou prezentaci
t Presentation pres = new Presentation();
```
Tento kód inicializuje nový prezentační dokument.

**Krok 2: Přístup k prvnímu snímku**
```csharp
// Přístup k prvnímu snímku v prezentaci
ISlide slide = pres.Slides[0];
```
Zde, `pres.Slides[0]` přistupuje k úplně prvnímu snímku. 

### Přidání bodového grafu na snímek
Nyní si do prezentace přidejme bodový graf.

#### Přehled
Přidávání grafů vám může pomoci vizuálně reprezentovat data v prezentacích. Aspose.Slides usnadňuje začlenění různých typů grafů, včetně bodových grafů.

#### Kroky implementace
**Krok 1: Vytvoření a přidání bodového grafu**
```csharp
using Aspose.Slides.Charts;

// Vytvořte a přidejte výchozí bodový graf s hladkými čarami
IChart chart = slide.Shapes.AddChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Tento úryvek přidá bodový graf na zadané pozici a velikosti.

### Vymazat a přidat řadu do dat grafu
#### Přehled
Možná budete muset graf upravit vymazáním stávajících řad a přidáním nových. Tato část se zabývá touto funkcí.

#### Kroky implementace
**Krok 1: Přístup k sešitu s daty grafů**
```csharp
int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;

// Vymazat všechny již existující série
chart.ChartData.Series.Clear();
```
Tento kód vymaže existující data a začne znovu s novou sérií.

**Krok 2: Přidání nové série**
```csharp
// Přidat novou sérii s názvem „Série 1“
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);

// Přidat další sérii s názvem „Série 2“
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.Type);
```
Tyto kroky přidají do grafu dvě nové řady.

### Úprava datových bodů a stylu značky první série
#### Přehled
Pro lepší vizualizaci bodových grafů si můžete přizpůsobit datové body a styly značek.

#### Kroky implementace
**Krok 1: Přístup k datovým bodům a jejich přidání**
```csharp
IChartSeries series = chart.ChartData.Series[0];

// Sečtěte datové body (1, 3) a (2, 10)
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, 1), fact.GetCell(defaultWorksheetIndex, 2, 2, 3));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, 2), fact.GetCell(defaultWorksheetIndex, 3, 2, 10));
```
**Krok 2: Úprava stylu značky**
```csharp
// Změna typu série a úprava stylu značky
series.Type = ChartType.ScatterWithStraightLinesAndMarkers;
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Star;
```
### Úprava datových bodů a stylu značek druhé série
#### Přehled
Podobně si upravte druhou sérii tak, aby odpovídala vašim potřebám při prezentaci.

#### Kroky implementace
**Krok 1: Přístup k více datovým bodům a jejich přidání**
```csharp
// Přístup k druhé sérii grafů
series = chart.ChartData.Series[1];

// Přidat více datových bodů
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 2, 3, 5), fact.GetCell(defaultWorksheetIndex, 2, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 3, 3, 3), fact.GetCell(defaultWorksheetIndex, 3, 4, 1));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 4, 3, 2), fact.GetCell(defaultWorksheetIndex, 4, 4, 2));
series.DataPoints.AddDataPointForScatterSeries(fact.GetCell(defaultWorksheetIndex, 5, 3, 5), fact.GetCell(defaultWorksheetIndex, 5, 4, 1));
```
**Krok 2: Úprava stylu značky**
```csharp
// Změna velikosti a symbolu značky pro druhou sérii
series.Marker.Size = 10;
series.Marker.Symbol = MarkerStyleType.Circle;
```
### Uložit prezentaci
Nakonec uložte prezentaci do určeného adresáře.

#### Kroky implementace
**Krok 1: Definování adresáře**
Ujistěte se, že výstupní adresář existuje. Pokud ne, vytvořte jej:
```csharp
using Aspose.Slides.Export;
using System.IO;

string YOUR_DOCUMENT_DIRECTORY = "YOUR_DOCUMENT_DIRECTORY";
bool isExists = Directory.Exists(YOUR_DOCUMENT_DIRECTORY);
if (!isExists) 
    Directory.CreateDirectory(YOUR_DOCUMENT_DIRECTORY);

// Uložit prezentaci
pres.Save(YOUR_DOCUMENT_DIRECTORY + "\AsposeChart_out.pptx", SaveFormat.Pptx);
```
Tento kód uloží soubor prezentace do zadaného umístění.

## Závěr
Nyní jste úspěšně přidali bodové grafy do svých prezentací pomocí Aspose.Slides pro .NET. Pokračujte v prozkoumávání dalších funkcí a úprav dostupných v knihovně, abyste si vylepšili dovednosti v oblasti vizualizace dat.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}