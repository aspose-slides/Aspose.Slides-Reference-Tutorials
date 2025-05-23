---
"description": "Vylepšete prezentace v PowerPointu pomocí Aspose.Slides pro Javu. V našem podrobném návodu se naučíte, jak přizpůsobit velikosti písma legendy a další."
"linktitle": "Legenda velikosti písma v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Legenda velikosti písma v Java Slides"
"url": "/cs/java/chart-elements/font-size-legend-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Legenda velikosti písma v Java Slides


## Úvod do legendy velikosti písma v Javě Slides

tomto tutoriálu se naučíte, jak přizpůsobit velikost písma legendy na snímku v PowerPointu pomocí Aspose.Slides pro Javu. Poskytneme podrobné pokyny a zdrojový kód pro dosažení tohoto úkolu.

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Inicializace prezentace

Nejprve importujte potřebné třídy a inicializujte prezentaci v PowerPointu.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.pptx");
```

Nahradit `"Your Document Directory"` se skutečnou cestou k vašemu souboru PowerPointu.

## Krok 2: Přidání grafu

Dále přidáme na snímek graf a nastavíme velikost písma legendy.

```java
try
{
    IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
    chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
}
```

V tomto kódu vytvoříme na prvním snímku klastrovaný sloupcový graf a nastavíme velikost písma textu legendy na 20 bodů. Velikost můžete upravit `setFontHeight` hodnota pro změnu velikosti písma podle potřeby.

## Krok 3: Úprava hodnot os

Nyní si upravme hodnoty svislé osy grafu.

```java
    chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
    chart.getAxes().getVerticalAxis().setMinValue(-5);
    chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
    chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Zde nastavujeme minimální a maximální hodnoty pro svislou osu. Hodnoty můžete upravit podle vašich datových požadavků.

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

Tento kód uloží upravenou prezentaci jako „output.pptx“ do zadaného adresáře.

## Kompletní zdrojový kód pro legendu velikosti písma v Java Slides

```java
// Cesta k adresáři s dokumenty.
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

Úspěšně jste upravili velikost písma legendy ve snímku v PowerPointu v Javě pomocí nástroje Aspose.Slides pro Javu. Můžete dále prozkoumat možnosti nástroje Aspose.Slides a vytvářet interaktivní a vizuálně poutavé prezentace.

## Často kladené otázky

### Jak změním velikost písma textu legendy v grafu?

Chcete-li změnit velikost písma textu legendy v grafu, můžete použít následující kód:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400);
chart.getLegend().getTextFormat().getPortionFormat().setFontHeight(20);
```

tomto kódu vytvoříme graf a nastavíme velikost písma textu legendy na 20 bodů. Velikost můžete upravit `setFontHeight` hodnota pro změnu velikosti písma.

### Mohu si přizpůsobit další vlastnosti legendy v grafu?

Ano, pomocí Aspose.Slides můžete přizpůsobit různé vlastnosti legendy v grafu. Mezi běžné vlastnosti, které můžete přizpůsobit, patří formátování textu, pozice, viditelnost a další. Například pro změnu pozice legendy můžete použít:

```java
chart.getLegend().setPosition(LegendPosition.Bottom);
```

Tento kód nastaví legendu tak, aby se zobrazovala ve spodní části grafu. Další možnosti přizpůsobení naleznete v dokumentaci k Aspose.Slides.

### Jak nastavím minimální a maximální hodnoty pro svislou osu v grafu?

Chcete-li nastavit minimální a maximální hodnoty pro svislou osu v grafu, můžete použít následující kód:

```java
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMinValue(-5);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(10);
```

Zde vypneme automatické škálování os a zadáme minimální a maximální hodnoty pro svislou osu. Upravte hodnoty podle potřeby pro data grafu.

### Kde najdu více informací a dokumentace k Aspose.Slides?

Komplexní dokumentaci a reference API pro Aspose.Slides pro Javu naleznete na webových stránkách dokumentace Aspose. Navštivte [zde](https://reference.aspose.com/slides/java/) pro podrobné informace o používání knihovny.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}