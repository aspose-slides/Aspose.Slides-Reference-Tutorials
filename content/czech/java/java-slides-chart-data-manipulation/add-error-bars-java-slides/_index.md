---
title: Přidejte chybové úsečky do snímků Java
linktitle: Přidejte chybové úsečky do snímků Java
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak přidat chybové úsečky do grafů PowerPoint v Javě pomocí Aspose.Slides. Podrobný průvodce se zdrojovým kódem pro přizpůsobení chybových pruhů.
type: docs
weight: 13
url: /cs/java/chart-data-manipulation/add-error-bars-java-slides/
---

## Úvod do přidávání chybových úseček v Java Slides pomocí Aspose.Slides

V tomto tutoriálu si ukážeme, jak přidat chybové úsečky do grafu na snímku aplikace PowerPoint pomocí Aspose.Slides for Java. Chybové úsečky poskytují cenné informace o variabilitě nebo nejistotě datových bodů v grafu. Vytvoříme bublinový graf a přidáme do něj chybové úsečky. Začněme!

## Předpoklady

 Než začnete, ujistěte se, že máte v projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z[Aspose webové stránky](https://downloads.aspose.com/slides/java).

## Krok 1: Vytvořte prázdnou prezentaci

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytváření prázdné prezentace
Presentation presentation = new Presentation();
```

tomto kroku vytvoříme prázdnou prezentaci, kam přidáme náš graf s chybovými úsečkami.

## Krok 2: Vytvořte bublinový graf

```java
// Vytvoření bublinového grafu
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Zde vytvoříme bublinový graf a určíme jeho polohu a rozměry na snímku.

## Krok 3: Přidání chybových pruhů a nastavení formátu

```java
// Přidání chybových pruhů a nastavení jeho formátu
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

V tomto kroku přidáme do grafu chybové úsečky a nastavíme jejich formát. Chybové úsečky můžete přizpůsobit změnou hodnot, typů a dalších vlastností.

- `errBarX` představuje chybové úsečky podél osy X.
- `errBarY` představuje chybové úsečky podél osy Y.
- Zviditelníme chybové úsečky X i Y.
- `setValueType` určuje typ hodnoty pro chybové úsečky (např. Fixed nebo Percentage).
- `setValue` nastavuje hodnotu pro chybové úsečky.
- `setType` definuje typ chybových pruhů (např. Plus nebo Minus).
-  Šířku čar chybového pruhu nastavíme pomocí`getFormat().getLine().setWidth(2)`.
- `setEndCap` určuje, zda se mají na chybové úsečky zahrnout koncovky.

## Krok 4: Uložte prezentaci

```java
// Ukládání prezentace
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Nakonec prezentaci s přidanými chybovými úsečkami uložíme na určené místo.

je to! Úspěšně jste přidali chybové úsečky do grafu na snímku aplikace PowerPoint pomocí Aspose.Slides for Java.

## Kompletní zdrojový kód pro přidání chybových pruhů do snímků Java

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytváření prázdné prezentace
Presentation presentation = new Presentation();
try
{
	// Vytvoření bublinového grafu
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Přidání chybových pruhů a nastavení jeho formátu
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Ukládání prezentace
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak vylepšit vaše prezentace PowerPoint přidáním chybových pruhů do grafů pomocí Aspose.Slides pro Java. Chybové úsečky poskytují cenné informace o variabilitě a nejistotách dat, díky čemuž jsou vaše prezentace informativnější a vizuálně přitažlivější.

## FAQ

### Jak mohu dále upravit vzhled chybových pruhů?

Chybové úsečky můžete přizpůsobit úpravou jejich vlastností, jako je styl čáry, barva a šířka, jak je ukázáno v kroku 3.

### Mohu přidat chybové úsečky do různých typů grafů?

Ano, do různých typů grafů podporovaných Aspose.Slides for Java můžete přidat chybové úsečky. Jednoduše vytvořte požadovaný typ grafu a postupujte podle stejných kroků přizpůsobení chybového pruhu.

### Jak mohu upravit polohu a velikost grafu na snímku?

Polohu a rozměry grafu můžete ovládat úpravou parametrů v`addChart` způsob, jak je ukázáno v kroku 2.

### Kde najdu více informací o Aspose.Slides for Java?

 Můžete odkazovat na[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/) pro podrobné informace o používání knihovny.