---
"description": "Naučte se, jak přidat vlastní chybové úsečky do grafů PowerPointu v Java Slides pomocí Aspose.Slides. Podrobný návod se zdrojovým kódem pro přesnou vizualizaci dat."
"linktitle": "Přidat vlastní chybu do Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidat vlastní chybu do Java Slides"
"url": "/cs/java/chart-data-manipulation/add-custom-error-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidat vlastní chybu do Java Slides


## Úvod do přidávání vlastních chybových úseček do prezentací v Javě pomocí Aspose.Slides

V tomto tutoriálu se naučíte, jak přidat vlastní chybové úsečky do grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Javu. Chybové úsečky jsou užitečné pro zobrazení variability nebo nejistoty v datových bodech v grafu.

## Předpoklady

Než začnete, ujistěte se, že máte následující:

- Knihovna Aspose.Slides pro Javu je nainstalována a nakonfigurována ve vašem projektu.
- Nastavení vývojového prostředí v Javě.

## Krok 1: Vytvořte prázdnou prezentaci

Nejprve si vytvořte prázdnou prezentaci v PowerPointu.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření prázdné prezentace
Presentation presentation = new Presentation();
```

## Krok 2: Přidání bublinového grafu

Dále do prezentace přidáme bublinový graf.

```java
// Vytvoření bublinového grafu
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

## Krok 3: Přidání vlastních chybových úseček

Nyní přidejme do série grafů vlastní chybové úsečky.

```java
// Přidání vlastních chybových úseček a nastavení jejich formátu
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Custom);
errBarY.setValueType(ErrorBarValueType.Custom);
```

## Krok 4: Nastavení dat chybových úseček

tomto kroku přistupujeme k datovým bodům řady grafů a nastavíme pro každý bod vlastní hodnoty chybových úseček.

```java
// Přístup k datovým bodům řady grafů a nastavení hodnot chybových úseček pro jednotlivé body
IChartDataPointCollection points = series.getDataPoints();
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);

// Nastavení chybových úseček pro body řady grafů
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

To je vše! Úspěšně jste přidali vlastní chybové úsečky do grafu v prezentaci PowerPoint pomocí Aspose.Slides pro Javu.

## Kompletní zdrojový kód pro přidání vlastní chyby v Java Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření prázdné prezentace
Presentation presentation = new Presentation();
try
{
	// Vytvoření bublinového grafu
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Přidání vlastních chybových úseček a nastavení jejich formátu
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	IErrorBarsFormat errBarX = series.getErrorBarsXFormat();
	IErrorBarsFormat errBarY = series.getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Custom);
	errBarY.setValueType(ErrorBarValueType.Custom);
	// Přístup k datovým bodům řady grafů a nastavení hodnot chybových úseček pro jednotlivé body
	IChartDataPointCollection points = series.getDataPoints();
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForXMinusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYPlusValues(DataSourceType.DoubleLiterals);
	points.getDataSourceTypeForErrorBarsCustomValues().setDataSourceTypeForYMinusValues(DataSourceType.DoubleLiterals);
	// Nastavení chybových úseček pro body řady grafů
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

tomto komplexním tutoriálu jste se naučili, jak vylepšit své prezentace v PowerPointu přidáním vlastních chybových úseček do grafů pomocí Aspose.Slides pro Javu. Chybové úsečky poskytují cenné informace o variabilitě a nejistotě dat, díky čemuž jsou vaše grafy informativnější a vizuálně atraktivnější.

## Často kladené otázky

### Jak si přizpůsobím vzhled chybových úseček?

Vzhled chybových úseček si můžete přizpůsobit úpravou vlastností `IErrorBarsFormat` objektu, jako je styl čáry, barva čáry a šířka chybového úsečky.

### Mohu přidat chybové úsečky do jiných typů grafů?

Ano, chybové úsečky můžete přidat do různých typů grafů podporovaných službou Aspose.Slides pro Javu, včetně sloupcových grafů, spojnicových grafů a bodových grafů.

### Jak nastavím různé hodnoty chybové úsečky pro každý datový bod?

Můžete procházet datové body a nastavit vlastní hodnoty chybového úsečky pro každý bod, jak je znázorněno ve výše uvedeném kódu.

### Je možné skrýt chybové úsečky pro konkrétní datové body?

Ano, viditelnost chybových úseček pro jednotlivé datové body můžete ovládat nastavením `setVisible` majetek `IErrorBarsFormat` objekt.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}