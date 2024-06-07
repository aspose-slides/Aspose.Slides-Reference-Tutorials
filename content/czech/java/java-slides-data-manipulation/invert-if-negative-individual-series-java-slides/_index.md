---
title: Invert If Negative pro jednotlivé řady v Java Slides
linktitle: Invert If Negative pro jednotlivé řady v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se používat funkci Invert If Negative v Aspose.Slides for Java k vylepšení vizuálů grafů v prezentacích PowerPoint.
type: docs
weight: 11
url: /cs/java/data-manipulation/invert-if-negative-individual-series-java-slides/
---

## Úvod do Invert If Negative pro jednotlivé řady v Java Slides

Aspose.Slides for Java poskytuje výkonné nástroje pro práci s prezentacemi a jednou zajímavou funkcí je možnost ovládat, jak se datové řady zobrazují v grafech. V tomto článku prozkoumáme, jak používat funkci „Invert If Negative“ pro jednotlivé série v Java Slides. Tato funkce vám umožňuje vizuálně rozlišovat negativní datové body v grafu, díky čemuž jsou vaše prezentace informativnější a poutavější.

## Předpoklady

Než se ponoříme do kódu, ujistěte se, že máte splněny následující předpoklady:

- Java Development Kit (JDK) nainstalovaný ve vašem systému.
-  Aspose.Slides pro knihovnu Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Nastavení vašeho projektu

Chcete-li začít, vytvořte nový projekt Java ve vašem preferovaném integrovaném vývojovém prostředí (IDE). Jakmile je váš projekt nastaven, podle následujících kroků implementujte funkci „Invert If Negative“ pro jednotlivé série v Java Slides.

## Krok 1: Zahrňte knihovnu Aspose.Slides

Nejprve musíte do projektu zahrnout knihovnu Aspose.Slides. Můžete to udělat přidáním souboru JAR knihovny do cesty třídy vašeho projektu. Tento krok zajistí, že budete mít přístup ke všem potřebným třídám a metodám pro práci s PowerPointovými prezentacemi.

```java
import com.aspose.slides.*;
```

## Krok 2: Vytvořte prezentaci

 Nyní vytvoříme novou PowerPoint prezentaci pomocí Aspose.Slides. Adresář, kam chcete prezentaci uložit, můžete definovat pomocí`dataDir` variabilní.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 3: Přidejte graf

V tomto kroku do prezentace přidáme graf. Jako příklad použijeme seskupený sloupcový graf. Můžete si vybrat různé typy grafů na základě vašich požadavků.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## Krok 4: Konfigurace datové řady grafu

Dále nakonfigurujeme datové řady grafu. Abychom demonstrovali funkci „Invert If Negative“, vytvoříme vzorovou datovou sadu s kladnými i zápornými hodnotami.

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// Přidávání datových bodů do řady
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## Krok 5: Použijte „Invert If Negative“

Nyní použijeme funkci „Invert If Negative“ na jeden z datových bodů. To vizuálně invertuje barvu konkrétního datového bodu, když je negativní.

```java
series.get_Item(0).setInvertIfNegative(false); // Ve výchozím nastavení neinvertovat
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // Invertujte barvu pro třetí datový bod
```

## Krok 6: Uložte prezentaci

Nakonec prezentaci uložte do určeného adresáře.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro Invert If Negative pro jednotlivé série v Java Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak používat funkci „Invert If Negative“ pro jednotlivé série v Java Slides pomocí Aspose.Slides for Java. Tato funkce vám umožňuje zvýraznit negativní datové body v grafech, díky čemuž budou vaše prezentace vizuálně přitažlivější a informativnější.

## FAQ

### Jaký je účel funkce „Invert If Negative“ v Aspose.Slides for Java?

Funkce "Invert If Negative" v Aspose.Slides for Java umožňuje vizuálně rozlišovat negativní datové body v grafech. Zvýrazněním konkrétních datových bodů pomáhá učinit vaše prezentace informativnější a poutavější.

### Jak mohu zahrnout knihovnu Aspose.Slides do svého projektu Java?

Chcete-li do svého projektu Java zahrnout knihovnu Aspose.Slides, musíte přidat soubor JAR knihovny do cesty třídy vašeho projektu. To vám umožní přístup ke všem nezbytným třídám a metodám pro práci s prezentacemi PowerPoint.

### Mohu s funkcí „Invert If Negative“ používat různé typy grafů?

Ano, s funkcí „Invert If Negative“ můžete používat různé typy grafů. V tomto kurzu jsme jako příklad použili seskupený sloupcový graf, ale tuto funkci můžete použít na různé typy grafů na základě vašich požadavků.

### Je možné upravit vzhled obrácených datových bodů?

Ano, vzhled inverzních datových bodů si můžete přizpůsobit. Aspose.Slides for Java poskytuje možnosti pro ovládání barvy a stylu datových bodů, když jsou invertovány kvůli nastavení "Invert If Negative".

### Kde mohu získat přístup k dokumentaci Aspose.Slides for Java?

 Dokumentaci k Aspose.Slides for Java můžete získat na adrese[tady](https://reference.aspose.com/slides/java/).