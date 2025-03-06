---
title: Přidat vlastní chybu v Java Slides
linktitle: Přidat vlastní chybu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Přečtěte si, jak přidat vlastní chybové úsečky do grafů aplikace PowerPoint v aplikaci Java Slides pomocí Aspose.Slides. Podrobný průvodce se zdrojovým kódem pro přesnou vizualizaci dat.
weight: 11
url: /cs/java/chart-data-manipulation/add-custom-error-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidat vlastní chybu v Java Slides


## Úvod do přidávání vlastních chybových pruhů do snímků Java pomocí Aspose.Slides

V tomto tutoriálu se naučíte, jak přidat vlastní chybové úsečky do grafu v prezentaci PowerPoint pomocí Aspose.Slides for Java. Chybové úsečky jsou užitečné pro zobrazení variability nebo nejistoty v datových bodech v grafu.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Knihovna Aspose.Slides for Java nainstalovaná a nakonfigurovaná ve vašem projektu.
- Nastaveno vývojové prostředí Java.

## Krok 1: Vytvořte prázdnou prezentaci

Nejprve vytvořte prázdnou prezentaci v PowerPointu.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytváření prázdné prezentace
Presentation presentation = new Presentation();
```

## Krok 2: Přidejte bublinový graf

Dále do prezentace přidáme bublinový graf.

```java
// Vytvoření bublinového grafu
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Krok 3: Přidejte vlastní chybové úsečky

Nyní do řady grafů přidáme vlastní chybové úsečky.

```java
// Přidání vlastních chybových pruhů a nastavení jejich formátu
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Krok 4: Nastavte data chybových pruhů

V tomto kroku přistoupíme k datovým bodům řady grafů a nastavíme hodnoty vlastních chybových pruhů pro každý bod.

```java
// Přístup k datovým bodům řady grafů a nastavení hodnot chybových pruhů pro jednotlivé body
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Nastavení chybových pruhů pro body sérií grafu
for (int i = 0; i < points.size(); i++)
{
    points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
    points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
}
```

## Krok 5: Uložte prezentaci

Nakonec uložte prezentaci s vlastními chybovými úsečkami.

```java
// Ukládání prezentace
presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
```

A je to! Úspěšně jste přidali vlastní chybové úsečky do grafu v prezentaci aplikace PowerPoint pomocí Aspose.Slides for Java.

## Kompletní zdrojový kód pro přidání vlastní chyby v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytváření prázdné prezentace
Presentation presentation = new Presentation();
try
{
	// Vytvoření bublinového grafu
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Přidání vlastních chybových pruhů a nastavení jejich formátu
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Přístup k datovým bodům řady grafů a nastavení hodnot chybových pruhů pro jednotlivé body
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Nastavení chybových pruhů pro body sérií grafu
	for (int i = 0; i < points.size(); i++)
	{
		points.get_Item(i).getErrorBarsCustomValues().getXMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getXPlus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYMinus().setAsLiteralDouble(i + 1);
		points.get_Item(i).getErrorBarsCustomValues().getYPlus().setAsLiteralDouble(i + 1);
	}
	// Ukládání prezentace
	presentation.save(dataDir + "ErrorBarsCustomValues_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto komplexním tutoriálu jste se naučili, jak vylepšit své prezentace v PowerPointu přidáním vlastních chybových pruhů do grafů pomocí Aspose.Slides for Java. Chybové úsečky poskytují cenné informace o variabilitě a nejistotě dat, díky čemuž jsou vaše grafy informativnější a vizuálně přitažlivější.

## FAQ

### Jak přizpůsobím vzhled chybových pruhů?

 Vzhled chybových pruhů můžete upravit úpravou vlastností souboru`IErrorBarsFormat` objekt, jako je styl čáry, barva čáry a šířka chybového pruhu.

### Mohu přidat chybové úsečky do jiných typů grafů?

Ano, do různých typů grafů podporovaných Aspose.Slides for Java můžete přidat chybové úsečky, včetně sloupcových grafů, spojnicových grafů a bodových grafů.

### Jak nastavím různé hodnoty chybového sloupce pro každý datový bod?

Můžete procházet datové body a pro každý bod nastavit vlastní hodnoty chybových pruhů, jak je znázorněno v kódu výše.

### Je možné skrýt chybové úsečky pro konkrétní datové body?

 Ano, viditelnost chybových pruhů pro jednotlivé datové body můžete ovládat nastavením`setVisible` vlastnictvím`IErrorBarsFormat` objekt.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
