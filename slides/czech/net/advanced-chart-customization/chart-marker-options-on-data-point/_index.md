---
title: Použití možností značky grafu na datovém bodu v Aspose.Slides .NET
linktitle: Možnosti značek grafu na datovém bodu
second_title: Aspose.Slides .NET PowerPoint Processing API
description: Naučte se, jak vylepšit své PowerPointové grafy pomocí Aspose.Slides pro .NET. Přizpůsobte značky datových bodů pomocí obrázků. Vytvářejte poutavé prezentace.
type: docs
weight: 11
url: /cs/net/advanced-chart-customization/chart-marker-options-on-data-point/
---

Při práci s prezentacemi a vizualizací dat nabízí Aspose.Slides for .NET širokou škálu výkonných funkcí pro vytváření, přizpůsobení a manipulaci s grafy. V tomto tutoriálu prozkoumáme, jak používat možnosti značek grafu na datových bodech k vylepšení prezentací grafů. Tento podrobný průvodce vás provede celým procesem, počínaje předpoklady a importem jmenných prostorů až po rozdělení každého příkladu do několika kroků.

## Předpoklady

Než se pustíme do používání možností značek grafu na datových bodech, ujistěte se, že máte splněny následující předpoklady:

-  Aspose.Slides for .NET: Ujistěte se, že máte nainstalovaný Aspose.Slides for .NET. Můžete si jej stáhnout z[webová stránka](https://releases.aspose.com/slides/net/).

- Ukázková prezentace: Pro tento tutoriál použijeme ukázkovou prezentaci s názvem "Test.pptx." Tuto prezentaci byste měli mít v adresáři dokumentů.

Nyní začněme importem potřebných jmenných prostorů.

## Importovat jmenné prostory

```csharp
﻿using Aspose.Slides;
using Aspose.Slides.Charts;
using Aspose.Slides.Export;
```

Importovali jsme požadované jmenné prostory a inicializovali naši prezentaci. Nyní přistoupíme k použití možností značek grafu na datových bodech.

## Krok 1: Vytvoření výchozího grafu

```csharp

// Cesta k adresáři dokumentů.
string dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "Test.pptx");

ISlide slide = pres.Slides[0];

//Vytvoření výchozího grafu
IChart chart = slide.Shapes.AddChart(ChartType.LineWithMarkers, 0, 0, 400, 400);
```

Vytvoříme výchozí graf typu „LineWithMarkers“ na snímku na určeném místě a velikosti.

## Krok 2: Získání výchozího indexu datového listu grafu

```csharp
// Získání výchozího indexu listu dat grafu
int defaultWorksheetIndex = 0;
```

Zde získáme index výchozího listu dat grafu.

## Krok 3: Získání listu dat grafu

```csharp
// Získání listu dat grafu
IChartDataWorkbook fact = chart.ChartData.ChartDataWorkbook;
```

Načteme sešit dat grafu pro práci s daty grafu.

## Krok 4: Úprava řady grafů

```csharp
// Smazat ukázkovou sérii
chart.ChartData.Series.Clear();

// Přidat novou sérii
chart.ChartData.Series.Add(fact.GetCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.Type);
```

V tomto kroku odstraníme všechny existující demo série a přidáme do grafu novou sérii s názvem „Série 1“.

## Krok 5: Nastavení obrazové výplně pro datové body

```csharp
// Nastavte obrázek pro značky
System.Drawing.Image img1 = (System.Drawing.Image)new Bitmap(dataDir + "aspose-logo.jpg");
IPPImage imgx1 = pres.Images.AddImage(img1);

System.Drawing.Image img2 = (System.Drawing.Image)new Bitmap(dataDir + "Tulips.jpg");
IPPImage imgx2 = pres.Images.AddImage(img2);

// Vezměte první sérii grafů
IChartSeries series = chart.ChartData.Series[0];

// Přidejte nové datové body s výplní obrázku
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

Nastavili jsme obrázkové značky pro datové body, což vám umožní přizpůsobit, jak se každý datový bod zobrazí v grafu.

## Krok 6: Změna velikosti značky řady grafů

```csharp
// Změna velikosti značky řady grafů
series.Marker.Size = 15;
```

Zde upravíme velikost značky řady grafů, aby byla vizuálně přitažlivá.

## Krok 7: Uložení prezentace

```csharp
pres.Save(dataDir + "AsposeScatterChart.pptx", SaveFormat.Pptx);
```

Nakonec prezentaci uložíme s novým nastavením grafu.

## Závěr

Aspose.Slides for .NET vám umožňuje vytvářet úžasné prezentace grafů s různými možnostmi přizpůsobení. V tomto kurzu jsme se zaměřili na použití možností značek grafu na datových bodech, abychom zlepšili vizuální reprezentaci vašich dat. S Aspose.Slides pro .NET můžete své prezentace posunout na další úroveň, díky čemuž budou poutavější a informativnější.

Pokud máte nějaké dotazy nebo potřebujete pomoc s Aspose.Slides pro .NET, neváhejte navštívit[Dokumentace Aspose.Slides](https://reference.aspose.com/slides/net/) nebo se obrátit na[Aspose komunita](https://forum.aspose.com/) pro podporu.

## Často kladené otázky (FAQ)

### Mohu použít vlastní obrázky jako značky pro datové body v Aspose.Slides pro .NET?
Ano, můžete použít vlastní obrázky jako značky pro datové body v Aspose.Slides pro .NET, jak je ukázáno v tomto tutoriálu.

### Jak mohu změnit typ grafu v Aspose.Slides pro .NET?
 Typ grafu můžete změnit zadáním jiného`ChartType` při vytváření grafu, například „Sloupec“, „Koláč“ nebo „Plocha“.

### Je Aspose.Slides for .NET kompatibilní s nejnovějšími verzemi PowerPointu?
Aspose.Slides for .NET je navržen pro práci s různými formáty aplikace PowerPoint a je pravidelně aktualizován, aby byla zachována kompatibilita s nejnovějšími verzemi aplikace PowerPoint.

### Kde najdu další návody a zdroje pro Aspose.Slides pro .NET?
 Můžete prozkoumat další výukové programy a zdroje v[Dokumentace Aspose.Slides](https://reference.aspose.com/slides/net/).

### Je k dispozici zkušební verze Aspose.Slides pro .NET?
 Ano, můžete vyzkoušet Aspose.Slides for .NET stažením bezplatné zkušební verze z[tady](https://releases.aspose.com/).