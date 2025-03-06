---
title: Legenda velikosti písma v Java Slides
linktitle: Legenda velikosti písma v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vylepšete prezentace v PowerPointu pomocí Aspose.Slides pro Java. V našem podrobném průvodci se dozvíte, jak přizpůsobit velikosti písma legendy a další.
weight: 13
url: /cs/java/chart-elements/font-size-legend-java-slides/
---

{< blocks/products/pf/main-wrap-class >}
{< blocks/products/pf/main-container >}
{< blocks/products/pf/tutorial-page-section >}


## Úvod do legendy velikosti písma v Java Slides

V tomto tutoriálu se naučíte, jak upravit velikost písma legendy na snímku aplikace PowerPoint pomocí Aspose.Slides for Java. K dosažení tohoto úkolu poskytneme podrobné pokyny a zdrojový kód.

## Předpoklady

 Než začnete, ujistěte se, že máte v projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Inicializujte prezentaci

Nejprve importujte potřebné třídy a inicializujte prezentaci PowerPoint.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

 Nahradit`"Your Document Directory"` se skutečnou cestou k souboru PowerPoint.

## Krok 2: Přidejte graf

Dále na snímek přidáme graf a nastavíme velikost písma legendy.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

 V tomto kódu vytvoříme na prvním snímku seskupený sloupcový graf a nastavíme velikost písma textu legendy na 20 bodů. Můžete upravit`setFontHeight`hodnotu pro změnu velikosti písma podle potřeby.

## Krok 3: Přizpůsobte hodnoty os

Nyní přizpůsobme hodnoty svislé osy grafu.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Zde nastavíme minimální a maximální hodnoty pro vertikální osu. Hodnoty můžete upravit podle svých požadavků na data.

## Krok 4: Uložte prezentaci

Nakonec upravenou prezentaci uložte do nového souboru.

```java
    pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
    if (pres != null) pres.dispose();
}
```

Tento kód uloží upravenou prezentaci jako "output.pptx" do zadaného adresáře.

## Kompletní zdrojový kód pro legendu velikosti písma v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
	chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMinValue(-5);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(10);
	pres.save(dataDir + "output.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

Úspěšně jste přizpůsobili velikost písma legendy na snímku Java PowerPoint pomocí Aspose.Slides for Java. Můžete dále prozkoumat možnosti Aspose.Slides a vytvářet interaktivní a vizuálně přitažlivé prezentace.

## FAQ

### Jak změním velikost písma textu legendy v grafu?

Chcete-li změnit velikost písma textu legendy v grafu, můžete použít následující kód:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

 V tomto kódu vytvoříme graf a nastavíme velikost písma textu legendy na 20 bodů. Můžete upravit`setFontHeight` hodnotu pro změnu velikosti písma.

### Mohu upravit další vlastnosti legendy v grafu?

Ano, pomocí Aspose.Slides můžete upravit různé vlastnosti legendy v grafu. Mezi běžné vlastnosti, které můžete přizpůsobit, patří formátování textu, pozice, viditelnost a další. Chcete-li například změnit polohu legendy, můžete použít:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Tento kód nastavuje legendu tak, aby se zobrazovala ve spodní části grafu. Další možnosti přizpůsobení naleznete v dokumentaci Aspose.Slides.

### Jak nastavím minimální a maximální hodnoty pro svislou osu v grafu?

Chcete-li nastavit minimální a maximální hodnoty pro svislou osu v grafu, můžete použít následující kód:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Zde zakážeme automatické škálování os a určíme minimální a maximální hodnoty pro vertikální osu. Upravte hodnoty podle potřeby pro data grafu.

### Kde najdu další informace a dokumentaci k Aspose.Slides?

 Komplexní dokumentaci a reference API pro Aspose.Slides for Java můžete najít na webu dokumentace Aspose. Návštěva[tady](https://reference.aspose.com/slides/java/) pro podrobné informace o používání knihovny.
{< /blocks/products/pf/tutorial-page-section >}

{< /blocks/products/pf/main-container >}
{< /blocks/products/pf/main-wrap-class >}

{< blocks/products/products-backtop-button >}
