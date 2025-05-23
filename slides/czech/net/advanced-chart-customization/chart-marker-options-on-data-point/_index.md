---
"description": "Naučte se, jak vylepšit grafy v PowerPointu pomocí Aspose.Slides pro .NET. Přizpůsobte si značky datových bodů pomocí obrázků. Vytvářejte poutavé prezentace."
"linktitle": "Možnosti značek grafu u datového bodu"
"second_title": "Rozhraní API pro zpracování PowerPointu v .NET od Aspose.Slides"
"title": "Použití možností značek grafu na datovém bodě v Aspose.Slides .NET"
"url": "/cs/net/advanced-chart-customization/chart-marker-options-on-data-point/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Použití možností značek grafu na datovém bodě v Aspose.Slides .NET


Při práci s prezentacemi a vizualizací dat nabízí Aspose.Slides pro .NET širokou škálu výkonných funkcí pro vytváření, úpravy a manipulaci s grafy. V tomto tutoriálu se podíváme na to, jak pomocí možností značek grafu na datových bodech vylepšit prezentace grafů. Tato podrobná příručka vás provede celým procesem, počínaje předpoklady a importem jmenných prostorů až po rozdělení každého příkladu do několika kroků.

## Předpoklady

Než se pustíme do používání možností značek grafu na datových bodech, ujistěte se, že máte splněny následující předpoklady:

- Aspose.Slides pro .NET: Ujistěte se, že máte nainstalovaný Aspose.Slides pro .NET. Můžete si ho stáhnout z [webové stránky](https://releases.aspose.com/slides/net/).

- Ukázková prezentace: V tomto tutoriálu použijeme ukázkovou prezentaci s názvem „Test.pptx“. Tuto prezentaci byste měli mít ve svém adresáři dokumentů.

Nyní začněme importem potřebných jmenných prostorů.

## Importovat jmenné prostory

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Importovali jsme požadované jmenné prostory a inicializovali naši prezentaci. Nyní se pustíme do použití možností značek grafu na datových bodech.

## Krok 1: Vytvoření výchozího grafu

```csharp

// Cesta k adresáři s dokumenty.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

// Vytvoření výchozího grafu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Na snímku na zadaném místě a velikosti vytvoříme výchozí graf typu „LineWithMarkers“.

## Krok 2: Získání výchozího indexu pracovního listu s daty grafu

```csharp
// Získání výchozího indexu listu s daty grafu
int defaultWorksheetIndex = 0;
```

Zde získáme index výchozího listu s daty grafu.

## Krok 3: Získání pracovního listu s daty grafu

```csharp
// Získání pracovního listu s daty grafu
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Pro práci s daty grafu načteme sešit s daty grafu.

## Krok 4: Úprava série grafů

```csharp
// Smazat demo sérii
chart.ChartData.Series.Clear();

// Přidat novou sérii
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

V tomto kroku odstraníme všechny existující demo série a do grafu přidáme novou sérii s názvem „Série 1“.

## Krok 5: Nastavení výplně obrázku pro datové body

```csharp
// Nastavte obrázek pro značky
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Vezměte si první sérii grafů
IChartSeries series = chart.ChartData.Series[0];

// Přidání nových datových bodů s obrázkovou výplní
IChartDataPoint point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 1, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 2, 1, (double)2.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 3, 1, (double)3.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx1;

point = series.DataPoints.AddDataPointForLineSeries(fact.GetCell(defaultWorksheetIndex, 4, 1, (double)4.5));
point.Marker.Format.Fill.FillType = FillType.Picture;
point.Marker.Format.Fill.PictureFillFormat.Picture.Image = imgx2;
```

Pro datové body jsme nastavili obrázkové značky, což vám umožňuje přizpůsobit, jak se každý datový bod zobrazuje v grafu.

## Krok 6: Změna velikosti značky řady grafů

```csharp
// Změna velikosti značky řady grafů
series.Marker.Size = 15;
```

Zde upravíme velikost značky řady grafu, aby byla vizuálně přitažlivá.

## Krok 7: Uložení prezentace

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Nakonec uložíme prezentaci s novým nastavením grafu.

## Závěr

Aspose.Slides pro .NET vám umožňuje vytvářet úžasné grafické prezentace s různými možnostmi přizpůsobení. V tomto tutoriálu jsme se zaměřili na použití možností značek grafu na datových bodech pro vylepšení vizuální reprezentace vašich dat. S Aspose.Slides pro .NET můžete své prezentace posunout na další úroveň a učinit je poutavějšími a informativnějšími.

Pokud máte jakékoli dotazy nebo potřebujete pomoc s Aspose.Slides pro .NET, neváhejte navštívit [Dokumentace k Aspose.Slides](https://reference.aspose.com/slides/net/) nebo se obraťte na [Komunita Aspose](https://forum.aspose.com/) pro podporu.

## Často kladené otázky (FAQ)

### Mohu v Aspose.Slides pro .NET použít vlastní obrázky jako značky pro datové body?
Ano, v Aspose.Slides pro .NET můžete použít vlastní obrázky jako značky pro datové body, jak je ukázáno v tomto tutoriálu.

### Jak mohu změnit typ grafu v Aspose.Slides pro .NET?
Typ grafu můžete změnit zadáním jiného `ChartType` při vytváření grafu, například „Sloupcový“, „Výsečový“ nebo „Plošný“.

### Je Aspose.Slides pro .NET kompatibilní s nejnovějšími verzemi PowerPointu?
Aspose.Slides pro .NET je navržen pro práci s různými formáty PowerPointu a je pravidelně aktualizován, aby byl zachován kompatibilita s nejnovějšími verzemi PowerPointu.

### Kde najdu další návody a zdroje pro Aspose.Slides pro .NET?
Další návody a zdroje si můžete prohlédnout v [Dokumentace k Aspose.Slides](https://reference.aspose.com/slides/net/).

### Je k dispozici zkušební verze Aspose.Slides pro .NET?
Ano, Aspose.Slides pro .NET si můžete vyzkoušet stažením bezplatné zkušební verze z [zde](https://releases.aspose.com/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}