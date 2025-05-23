---
"description": "Naučte se, jak skrýt prvky grafu v Java Slides pomocí Aspose.Slides pro Javu. Přizpůsobte si prezentace pro přehlednost a estetiku pomocí podrobných pokynů a zdrojového kódu."
"linktitle": "Skrýt informace z grafu v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Skrýt informace z grafu v Javě Slides"
"url": "/cs/java/customization-and-formatting/hide-information-chart-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Skrýt informace z grafu v Javě Slides


## Úvod do skrytí informací z grafu v Javě Slides

tomto tutoriálu se podíváme na to, jak skrýt různé prvky z grafu v Java Slides pomocí Aspose.Slides for Java API. Tento kód můžete použít k přizpůsobení grafů podle potřeby pro vaše prezentace.

## Krok 1: Nastavení prostředí

Než začneme, ujistěte se, že máte do projektu přidánu knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 2: Vytvořte novou prezentaci

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 3: Přidání grafu na snímek

Na snímek přidáme spojnicový graf se značkami a poté skryjeme různé prvky grafu.

```java
ISlide slide = pres.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
```

## Krok 4: Skrýt název grafu

Název grafu můžete skrýt takto:

```java
chart.setTitle(false);
```

## Krok 5: Skrýt osu hodnot

Chcete-li skrýt osu hodnot (svislou osu), použijte následující kód:

```java
chart.getAxes().getVerticalAxis().setVisible(false);
```

## Krok 6: Skrýt osu kategorií

Chcete-li skrýt osu kategorií (vodorovnou osu), použijte tento kód:

```java
chart.getAxes().getHorizontalAxis().setVisible(false);
```

## Krok 7: Skrýt legendu

Legendu grafu můžete skrýt takto:

```java
chart.setLegend(false);
```

## Krok 8: Skrýt hlavní čáry mřížky

Chcete-li skrýt hlavní čáry mřížky vodorovné osy, můžete použít následující kód:

```java
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
```

## Krok 9: Odebrání série

Pokud chcete z grafu odstranit všechny série, můžete použít smyčku podobnou této:

```java
for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
    chart.getChartData().getSeries().removeAt(i);
}
```

## Krok 10: Úprava série grafů

Sérii grafů si můžete dle potřeby přizpůsobit. V tomto příkladu změníme styl značky, umístění popisku dat, velikost značky, barvu čáry a styl čárkování:

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

Nakonec uložte prezentaci do souboru:

```java
pres.save(dataDir + "HideInformationFromChart.pptx", SaveFormat.Pptx);
```

To je vše! Pomocí Aspose.Slides pro Javu jste úspěšně skryli různé prvky z grafu v Java Slides. Grafy a prezentace si můžete dále přizpůsobit podle svých specifických požadavků.

## Kompletní zdrojový kód pro skrytí informací z grafu v Java Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	ISlide slide = pres.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 140, 118, 320, 370);
	//Skrytí názvu grafu
	chart.setTitle(false);
	///Skrytí osy hodnot
	chart.getAxes().getVerticalAxis().setVisible(false);
	//Viditelnost osy kategorie
	chart.getAxes().getHorizontalAxis().setVisible(false);
	//Skrytí legendy
	chart.setLegend(false);
	//Skrytí hlavních čar mřížky
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
	//Nastavení barvy čáry série
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

tomto podrobném návodu jsme prozkoumali, jak skrýt různé prvky z grafu v aplikaci Java Slides pomocí rozhraní Aspose.Slides for Java API. To může být neuvěřitelně užitečné, když potřebujete přizpůsobit grafy pro prezentace a učinit je vizuálně přitažlivějšími nebo přizpůsobenými vašim specifickým potřebám.

## Často kladené otázky

### Jak mohu dále přizpůsobit vzhled prvků grafu?

Různé vlastnosti prvků grafu, jako je barva čáry, barva výplně, styl značky a další, můžete přizpůsobit přístupem k odpovídajícím vlastnostem řady grafů, značek, popisků a formátu.

### Mohu v grafu skrýt konkrétní datové body?

Ano, konkrétní datové body můžete skrýt manipulací s daty v grafu. Datové body můžete odebrat nebo nastavit jejich hodnotu na null, abyste je skryli.

### Jak mohu do grafu přidat další série?

Do grafu můžete přidat další série pomocí `IChartData.getSeries().add` metodu a určení datových bodů pro novou řadu.

### Je možné dynamicky měnit typ grafu?

Ano, typ grafu můžete dynamicky změnit vytvořením nového grafu požadovaného typu a zkopírováním dat ze starého grafu do nového.

### Jak mohu programově změnit název a popisky os grafu?

Název a popisky grafu a os můžete nastavit tak, že otevřete jejich příslušné vlastnosti a nastavíte požadovaný text a formátování.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}