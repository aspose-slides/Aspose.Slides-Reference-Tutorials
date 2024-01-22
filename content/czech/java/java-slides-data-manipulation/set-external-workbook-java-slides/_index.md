---
title: Nastavte externí sešit v Java Slides
linktitle: Nastavte externí sešit v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit externí sešity v Java Slides pomocí Aspose.Slides for Java. Vytvářejte dynamické prezentace s integrací dat aplikace Excel.
type: docs
weight: 19
url: /cs/java/data-manipulation/set-external-workbook-java-slides/
---

## Úvod k nastavení externího sešitu v Java Slides

tomto tutoriálu prozkoumáme, jak nastavit externí sešit v Java Slides pomocí Aspose.Slides. Dozvíte se, jak vytvořit prezentaci v PowerPointu s grafem, který odkazuje na data z externího excelového sešitu. Na konci této příručky budete mít jasno v tom, jak integrovat externí data do vašich prezentací Java Slides.

## Předpoklady

Než se pustíme do implementace, ujistěte se, že máte následující předpoklady:

- Java Development Kit (JDK) nainstalovaný ve vašem systému.
- Do vašeho projektu byla přidána knihovna Aspose.Slides for Java.
- Excelový sešit s daty, na která chcete v prezentaci odkazovat.

## Krok 1: Vytvořte novou prezentaci

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Začneme vytvořením nové PowerPointové prezentace pomocí Aspose.Slides.

## Krok 2: Přidejte graf

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Dále do prezentace vložíme výsečový graf. Podle potřeby můžete upravit typ a pozici grafu.

## Krok 3: Přístup k externímu sešitu

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

 Pro přístup k externímu sešitu používáme`setExternalWorkbook` a zadejte cestu k excelovému sešitu obsahujícímu data.

## Krok 4: Svažte data grafu

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Graf svážeme s daty z externího sešitu zadáním odkazů na buňky pro řady a kategorie.

## Krok 5: Uložte prezentaci

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Nakonec uložíme prezentaci s odkazem na externí sešit jako soubor PowerPoint.

## Kompletní zdrojový kód pro sadu externích sešitů v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak nastavit externí sešit v Java Slides pomocí Aspose.Slides. Nyní můžete vytvářet prezentace, které dynamicky odkazují na data z excelových sešitů, čímž se zvyšuje flexibilita a interaktivita vašich snímků.

## FAQ

### Jak nainstaluji Aspose.Slides for Java?

Aspose.Slides for Java lze nainstalovat přidáním knihovny do vašeho projektu Java. Knihovnu si můžete stáhnout z webu Aspose a postupujte podle pokynů k instalaci uvedených v dokumentaci.

### Mohu používat různé typy grafů s externími sešity?

Ano, můžete použít různé typy grafů podporované Aspose.Slides a svázat je s daty z externích sešitů. Proces se může mírně lišit v závislosti na zvoleném typu grafu.

### Co když se změní datová struktura mého externího sešitu?

Pokud se změní struktura dat vašeho externího sešitu, možná budete muset aktualizovat odkazy na buňky v kódu Java, abyste zajistili, že data grafu zůstanou přesná.

### Je Aspose.Slides kompatibilní s nejnovějšími verzemi Java?

Aspose.Slides for Java je pravidelně aktualizován, aby byla zajištěna kompatibilita s nejnovějšími verzemi Java. Nezapomeňte zkontrolovat aktualizace a používat nejnovější verzi knihovny pro optimální výkon a kompatibilitu.

### Mohu přidat více grafů odkazujících na stejný externí sešit?

Ano, do prezentace můžete přidat více grafů, přičemž všechny odkazují na stejný externí sešit. Jednoduše opakujte kroky popsané v tomto kurzu pro každý graf, který chcete vytvořit.