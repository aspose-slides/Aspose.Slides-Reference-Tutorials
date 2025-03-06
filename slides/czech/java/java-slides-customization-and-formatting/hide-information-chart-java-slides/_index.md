---
title: Skrýt informace z grafu v Java Slides
linktitle: Skrýt informace z grafu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se skrýt prvky grafu v Java Slides pomocí Aspose.Slides pro Java. Přizpůsobte si prezentace tak, aby byly přehledné a estetické, pomocí podrobných pokynů a zdrojového kódu.
weight: 13
url: /cs/java/customization-and-formatting/hide-information-chart-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod ke skrytí informací z grafu v Java Slides

V tomto tutoriálu prozkoumáme, jak skrýt různé prvky z grafu v Java Slides pomocí Aspose.Slides for Java API. Tento kód můžete použít k přizpůsobení grafů podle potřeby pro vaše prezentace.

## Krok 1: Nastavení prostředí

 Než začneme, ujistěte se, že máte do projektu přidánu knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 2: Vytvořte novou prezentaci

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 3: Přidání grafu do snímku

Na snímek přidáme spojnicový graf se značkami a poté skryjeme různé prvky grafu.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Krok 4: Skryjte nadpis grafu

Název grafu můžete skrýt následovně:

```java
chart.setTitle(false);
```

## Krok 5: Skrýt osu hodnot

Chcete-li skrýt osu hodnot (svislou osu), použijte následující kód:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Krok 6: Skryjte osu kategorie

Chcete-li skrýt osu kategorie (horizontální osu), použijte tento kód:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Krok 7: Skryjte legendu

Legendu grafu můžete skrýt takto:

```java
chart.setLegend(false);
```

## Krok 8: Skryjte hlavní čáry mřížky

Chcete-li skrýt hlavní čáry mřížky vodorovné osy, můžete použít následující kód:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Krok 9: Odeberte sérii

Pokud chcete z grafu odstranit všechny řady, můžete použít smyčku takto:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Krok 10: Přizpůsobte řadu grafů

Řady grafů můžete přizpůsobit podle potřeby. V tomto příkladu změníme styl značky, polohu popisku dat, velikost značky, barvu čáry a styl čárky:

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getMarker().setSymbol(MarkerStyleType.Circle);
series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
series.getMarker().setSize(15);
series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
```

## Krok 11: Uložte prezentaci

Nakonec prezentaci uložte do souboru:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

A je to! Úspěšně jste skryli různé prvky z grafu v Java Slides pomocí Aspose.Slides for Java. Své grafy a prezentace můžete dále upravovat podle svých specifických požadavků.

## Kompletní zdrojový kód pro skrytí informací z grafu v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Skrytí názvu grafu
	chart.setTitle(false);
	///Hiding Hodnoty osy
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Kategorie Viditelnost osy
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Skrytí legendy
	chart.setLegend(false);
	//Skrytí MajorGridLines
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
	for (int i = 0; i < chart.getChartData().getSeries().size(); i++)
	{
		chart.getChartData().getSeries().removeAt(i);
	}
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getMarker().setSymbol(MarkerStyleType.Circle);
	series.getLabels().getDefaultDataLabelFormat().setShowValue(true);
	series.getLabels().getDefaultDataLabelFormat().setPosition(LegendDataLabelPosition.Top);
	series.getMarker().setSize(15);
	//Nastavení barvy čáry řady
	series.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	series.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(new Color(PresetColor.Purple));
	series.getFormat().getLine().setDashStyle(LineDashStyle.Solid);
	pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```
## Závěr

V tomto podrobném průvodci jsme prozkoumali, jak skrýt různé prvky z grafu v Java Slides pomocí Aspose.Slides for Java API. To může být neuvěřitelně užitečné, když potřebujete upravit své grafy pro prezentace a učinit je vizuálně přitažlivějšími nebo přizpůsobenými vašim konkrétním potřebám.

## FAQ

### Jak dále přizpůsobím vzhled prvků grafu?

Můžete přizpůsobit různé vlastnosti prvků grafu, jako je barva čáry, barva výplně, styl značek a další, přístupem k odpovídajícím vlastnostem řady grafů, značek, štítků a formátu.

### Mohu skrýt konkrétní datové body v grafu?

Ano, konkrétní datové body můžete skrýt manipulací s daty v řadě grafů. Datové body můžete odebrat nebo nastavit jejich hodnoty na null, abyste je skryli.

### Jak mohu do grafu přidat další řady?

 Další řady můžete do grafu přidat pomocí`IChartData.getSeries().add` a specifikaci datových bodů pro novou řadu.

### Je možné dynamicky změnit typ grafu?

Ano, typ grafu můžete dynamicky změnit vytvořením nového grafu požadovaného typu a zkopírováním dat ze starého grafu do nového.

### Jak mohu programově změnit název grafu a popisky osy?

Můžete nastavit nadpis a popisky grafu a os přístupem k jejich příslušným vlastnostem a nastavením požadovaného textu a formátování.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
