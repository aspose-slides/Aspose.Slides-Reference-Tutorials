---
title: Graf entit v Java Slides
linktitle: Graf entit v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se vytvářet a přizpůsobovat grafy Java Slides pomocí Aspose.Slides. Vylepšete své prezentace pomocí výkonných entit grafů.
type: docs
weight: 13
url: /cs/java/data-manipulation/chart-entities-java-slides/
---

## Úvod do grafových entit v Java Slides

Grafy jsou mocné nástroje pro vizualizaci dat v prezentacích. Ať už vytváříte obchodní zprávy, akademické prezentace nebo jakoukoli jinou formu obsahu, grafy pomáhají efektivně předávat informace. Aspose.Slides for Java poskytuje robustní funkce pro práci s grafy, díky čemuž je vhodnou volbou pro vývojáře Java.

## Předpoklady

Než se ponoříme do světa entit grafu, ujistěte se, že máte splněny následující předpoklady:

- Java Development Kit (JDK) nainstalován
- Knihovna Aspose.Slides for Java byla stažena a přidána do vašeho projektu
- Základní znalost programování v Javě

Nyní začněme s vytvářením a přizpůsobením grafů pomocí Aspose.Slides pro Java.

## Krok 1: Vytvoření prezentace

Prvním krokem je vytvoření nové prezentace, do které přidáte svůj graf. Zde je úryvek kódu pro vytvoření prezentace:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidání grafu

Jakmile budete mít svou prezentaci připravenou, je čas přidat graf. V tomto příkladu přidáme jednoduchý spojnicový graf se značkami. Můžete to udělat takto:

```java
// Přístup k prvnímu snímku
ISlide slide = pres.getSlides().get_Item(0);

// Přidání vzorového grafu
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Krok 3: Přizpůsobení názvu grafu

Dobře definovaný graf by měl mít název. Nastavíme název pro náš graf:

```java
// Nastavení názvu grafu
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Krok 4: Formátování čar mřížky

Můžete formátovat hlavní a vedlejší čáry mřížky grafu. Nastavíme nějaké formátování pro čáry mřížky svislé osy:

```java
// Nastavení formátu hlavních čar mřížky pro osu hodnot
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);

// Nastavení formátu vedlejších čar mřížky pro osu hodnot
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Krok 5: Přizpůsobení osy hodnot

Máte kontrolu nad formátem čísel, maximálními a minimálními hodnotami osy hodnot. Postup přizpůsobení:

```java
// Nastavení formátu čísla osy hodnot
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Nastavovací tabulka maximální, minimální hodnoty
chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
chart.getAxes().getVerticalAxis().setMaxValue(15f);
chart.getAxes().getVerticalAxis().setMinValue(-2f);
chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
```

## Krok 6: Přidání názvu osy hodnot

Chcete-li, aby byl graf informativnější, můžete k ose hodnot přidat název:

```java
// Nastavení názvu osy hodnot
chart.getAxes().getVerticalAxis().setTitle(true);
chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
valtitle.setText("Primary Axis");
```

## Krok 7: Formátování osy kategorií

Osu kategorií, která obvykle představuje kategorie dat, lze také přizpůsobit:

```java
// Nastavení formátu hlavních čar mřížky pro osu kategorie
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

//Nastavení formátu vedlejších čar mřížky pro osu kategorie
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Krok 8: Přidání legend

Legendy pomáhají vysvětlit datové řady ve vašem grafu. Pojďme přizpůsobit legendy:

```java
// Nastavení vlastností textu legend
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Nastavit legendy grafu bez překrývání grafu
chart.getLegend().setOverlay(true);
```

## Krok 9: Uložení prezentace

Nakonec uložte prezentaci s grafem:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro entity grafu v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě není přítomen.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Okamžitá prezentace// Okamžitá prezentace
Presentation pres = new Presentation();
try
{
	// Přístup k prvnímu snímku
	ISlide slide = pres.getSlides().get_Item(0);
	// Přidání vzorového grafu
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Nastavení názvu grafu
	chart.setTitle(true);
	chart.getChartTitle().addTextFrameForOverriding("");
	IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	chartTitle.setText("Sample Chart");
	chartTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	chartTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	chartTitle.getPortionFormat().setFontHeight(20);
	chartTitle.getPortionFormat().setFontBold(NullableBool.True);
	chartTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Nastavení formátu hlavních čar mřížky pro osu hodnot
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	chart.getAxes().getVerticalAxis().getMajorGridLinesFormat().getLine().setDashStyle(LineDashStyle.DashDot);
	// Nastavení formátu vedlejších čar mřížky pro osu hodnot
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
	chart.getAxes().getVerticalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Nastavení formátu čísla osy hodnot
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Nastavovací tabulka maximální, minimální hodnoty
	chart.getAxes().getVerticalAxis().setAutomaticMajorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMaxValue(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinorUnit(false);
	chart.getAxes().getVerticalAxis().setAutomaticMinValue(false);
	chart.getAxes().getVerticalAxis().setMaxValue(15f);
	chart.getAxes().getVerticalAxis().setMinValue(-2f);
	chart.getAxes().getVerticalAxis().setMinorUnit(0.5f);
	chart.getAxes().getVerticalAxis().setMajorUnit(2.0f);
	// Nastavení vlastností textu osy hodnot
	IChartPortionFormat txtVal = chart.getAxes().getVerticalAxis().getTextFormat().getPortionFormat();
	txtVal.setFontBold(NullableBool.True);
	txtVal.setFontHeight(16);
	txtVal.setFontItalic(NullableBool.True);
	txtVal.getFillFormat().setFillType(FillType.Solid);
	txtVal.getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	txtVal.setLatinFont(new FontData("Times New Roman"));
	// Nastavení názvu osy hodnot
	chart.getAxes().getVerticalAxis().setTitle(true);
	chart.getAxes().getVerticalAxis().getTitle().addTextFrameForOverriding("");
	IPortion valtitle = chart.getAxes().getVerticalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	valtitle.setText("Primary Axis");
	valtitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	valtitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	valtitle.getPortionFormat().setFontHeight(20);
	valtitle.getPortionFormat().setFontBold(NullableBool.True);
	valtitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Formát čáry osy hodnot: Nyní Obselete
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Nastavení formátu hlavních čar mřížky pro osu kategorie
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	//Nastavení formátu vedlejších čar mřížky pro osu kategorie
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Nastavení vlastností textu osy kategorie
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Nastavení názvu kategorie
	chart.getAxes().getHorizontalAxis().setTitle(true);
	chart.getAxes().getHorizontalAxis().getTitle().addTextFrameForOverriding("");
	IPortion catTitle = chart.getAxes().getHorizontalAxis().getTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
	catTitle.setText("Sample Category");
	catTitle.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	catTitle.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.GRAY);
	catTitle.getPortionFormat().setFontHeight(20);
	catTitle.getPortionFormat().setFontBold(NullableBool.True);
	catTitle.getPortionFormat().setFontItalic(NullableBool.True);
	// Nastavení polohy štítku osy kategorie
	chart.getAxes().getHorizontalAxis().setTickLabelPosition(TickLabelPositionType.Low);
	// Nastavení úhlu natočení osového štítku kategorie
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Nastavení vlastností textu legend
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Nastavit legendy grafu bez překrývání grafu
	chart.getLegend().setOverlay(true);
	// Vynesení první série na sekundární osu hodnot
	//Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Nastavení barvy zadní stěny grafu
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Nastavení barvy oblasti plotru
	chart.getPlotArea().getFormat().getFill().setFillType(FillType.Solid);
	chart.getPlotArea().getFormat().getFill().getSolidFillColor().setColor(new Color(PresetColor.LightCyan));
	// Uložit prezentaci
	pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto článku jsme prozkoumali svět entit grafu v Java Slides pomocí Aspose.Slides pro Java. Naučili jste se vytvářet, přizpůsobovat a manipulovat s grafy, abyste vylepšili své prezentace. Grafy nejen činí vaše data vizuálně přitažlivými, ale také pomáhají vašemu publiku snadněji porozumět komplexním informacím.

## FAQ

### Jak změním typ grafu?

 Chcete-li změnit typ grafu, použijte`chart.setType()` a zadejte požadovaný typ grafu.

### Mohu do grafu přidat více datových řad?

 Ano, do grafu můžete přidat více datových řad pomocí`chart.getChartData().getSeries().addSeries()` metoda.

### Jak přizpůsobím barvy grafu?

Barvy grafu můžete přizpůsobit nastavením formátu výplně pro různé prvky grafu, jako jsou čáry mřížky, nadpis a legendy.

### Mohu vytvořit 3D grafy?

 Ano, Aspose.Slides for Java podporuje tvorbu 3D grafů. Můžete nastavit`ChartType` na typ 3D grafu, abyste jej vytvořili.

### Je Aspose.Slides for Java kompatibilní s nejnovějšími verzemi Java?

Ano, Aspose.Slides for Java je pravidelně aktualizován, aby podporoval nejnovější verze Java a poskytuje kompatibilitu v celé řadě prostředí Java.