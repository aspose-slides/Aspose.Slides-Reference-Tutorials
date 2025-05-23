---
"description": "Naučte se vytvářet a upravovat grafy v Java Slides pomocí Aspose.Slides. Vylepšete své prezentace pomocí výkonných grafů."
"linktitle": "Entity grafu v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Entity grafu v Javě Slides"
"url": "/cs/java/data-manipulation/chart-entities-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Entity grafu v Javě Slides


## Úvod do entit grafů v Javě – Slidy

Grafy jsou výkonné nástroje pro vizualizaci dat v prezentacích. Ať už vytváříte obchodní zprávy, akademické prezentace nebo jakoukoli jinou formu obsahu, grafy pomáhají efektivně sdělovat informace. Aspose.Slides pro Javu poskytuje robustní funkce pro práci s grafy, což z něj dělá skvělou volbu pro vývojáře v Javě.

## Předpoklady

Než se ponoříme do světa grafických entit, ujistěte se, že máte splněny následující předpoklady:

- Nainstalovaná vývojářská sada Java (JDK)
- Knihovna Aspose.Slides pro Javu byla stažena a přidána do vašeho projektu
- Základní znalost programování v Javě

Nyní se pojďme pustit do vytváření a úpravy grafů pomocí Aspose.Slides pro Javu.

## Krok 1: Vytvoření prezentace

Prvním krokem je vytvoření nové prezentace, do které přidáte graf. Zde je úryvek kódu pro vytvoření prezentace:

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidání grafu

Jakmile máte prezentaci připravenou, je čas přidat graf. V tomto příkladu přidáme jednoduchý spojnicový graf se značkami. Zde je návod, jak to udělat:

```java
// Přístup k prvnímu snímku
ISlide slide = pres.getSlides().get_Item(0);

// Přidání ukázkového grafu
IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
```

## Krok 3: Úprava názvu grafu

Dobře definovaný graf by měl mít název. Nastavme název našeho grafu:

```java
// Název grafu nastavení
chart.setTitle(true);
chart.getChartTitle().addTextFrameForOverriding("");
IPortion chartTitle = chart.getChartTitle().getTextFrameForOverriding().getParagraphs().get_Item(0).getPortions().get_Item(0);
chartTitle.setText("Sample Chart");
```

## Krok 4: Formátování mřížkových čar

Hlavní a vedlejší čáry mřížky grafu můžete formátovat. Nastavme formátování čar mřížky svislé osy:

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

## Krok 5: Úprava osy hodnot

Máte kontrolu nad formátem čísel, maximálními a minimálními hodnotami osy hodnot. Zde je návod, jak si ji přizpůsobit:

```java
// Nastavení formátu čísel osy hodnot
chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");

// Maximální a minimální hodnoty v tabulce nastavení
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

Aby byl graf informativnější, můžete k ose hodnot přidat název:

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
// Nastavení formátu hlavních čar mřížky pro osu kategorií
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);

// Nastavení formátu vedlejších čar mřížky pro osu kategorií
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
```

## Krok 8: Přidání legend

Legendy pomáhají vysvětlit datové řady v grafu. Pojďme si legendy přizpůsobit:

```java
// Nastavení vlastností textu legendy
IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
txtleg.setFontBold(NullableBool.True);
txtleg.setFontHeight(16);
txtleg.setFontItalic(NullableBool.True);
txtleg.getFillFormat().setFillType(FillType.Solid);
txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);

// Nastavit zobrazení legend grafu bez překrývání grafů
chart.getLegend().setOverlay(true);
```

## Krok 9: Uložení prezentace

Nakonec uložte prezentaci s grafem:

```java
pres.save(dataDir + "FormattedChart_out.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro entity grafů v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvořte adresář, pokud ještě neexistuje.
boolean IsExists = new File(dataDir).exists();
if (!IsExists)
	new File(dataDir).mkdirs();
// Vytváření instance prezentace // Vytváření instance prezentace
Presentation pres = new Presentation();
try
{
	// Přístup k prvnímu snímku
	ISlide slide = pres.getSlides().get_Item(0);
	// Přidání ukázkového grafu
	IChart chart = slide.getShapes().addChart(ChartType.LineWithMarkers, 50, 50, 500, 400);
	// Název grafu nastavení
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
	// Nastavení formátu čísel osy hodnot
	chart.getAxes().getVerticalAxis().setNumberFormatLinkedToSource(false);
	chart.getAxes().getVerticalAxis().setDisplayUnit(DisplayUnitType.Thousands);
	chart.getAxes().getVerticalAxis().setNumberFormat("0.0%");
	// Maximální a minimální hodnoty v tabulce nastavení
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
	// Nastavení formátu čáry osy hodnot: Nyní zastaralé
	// chart.getAxes().getVerticalAxis().aVerticalAxis.l.AxisLine.setWidth(10);
	// chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().setFillType(FillType.Solid);
	// Chart.getAxes().getVerticalAxis().AxisLine.getFillFormat().getSolidFillColor().Color = Color.Red;
	// Nastavení formátu hlavních čar mřížky pro osu kategorií
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.GREEN);
	chart.getAxes().getHorizontalAxis().getMajorGridLinesFormat().getLine().setWidth(5);
	// Nastavení formátu vedlejších čar mřížky pro osu kategorií
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().setFillType(FillType.Solid);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.YELLOW);
	chart.getAxes().getHorizontalAxis().getMinorGridLinesFormat().getLine().setWidth(3);
	// Nastavení vlastností textu osy kategorií
	IChartPortionFormat txtCat = chart.getAxes().getHorizontalAxis().getTextFormat().getPortionFormat();
	txtCat.setFontBold(NullableBool.True);
	txtCat.setFontHeight(16);
	txtCat.setFontItalic(NullableBool.True);
	txtCat.getFillFormat().setFillType(FillType.Solid);
	txtCat.getFillFormat().getSolidFillColor().setColor(Color.BLUE);
	txtCat.setLatinFont(new FontData("Arial"));
	// Název kategorie nastavení
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
	// Nastavení úhlu natočení osy kategorie
	chart.getAxes().getHorizontalAxis().setTickLabelRotationAngle(45);
	// Nastavení vlastností textu legendy
	IChartPortionFormat txtleg = chart.getLegend().getTextFormat().getPortionFormat();
	txtleg.setFontBold(NullableBool.True);
	txtleg.setFontHeight(16);
	txtleg.setFontItalic(NullableBool.True);
	txtleg.getFillFormat().setFillType(FillType.Solid);
	txtleg.getFillFormat().getSolidFillColor().setColor(Color.RED);
	// Nastavit zobrazení legend grafu bez překrývání grafů
	chart.getLegend().setOverlay(true);
	// Vykreslení první řady na sekundární ose hodnot
	// Chart.getChartData().getSeries().get_Item(0).PlotOnSecondAxis = true;
	// Barva zadní stěny tabulky nastavení
	chart.getBackWall().setThickness(1);
	chart.getBackWall().getFormat().getFill().setFillType(FillType.Solid);
	chart.getBackWall().getFormat().getFill().getSolidFillColor().setColor(Color.ORANGE);
	chart.getFloor().getFormat().getFill().setFillType(FillType.Solid);
	chart.getFloor().getFormat().getFill().getSolidFillColor().getColor();
	// Nastavení barvy oblasti grafu
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

V tomto článku jsme prozkoumali svět grafů v Java Slides pomocí Aspose.Slides pro Javu. Naučili jste se, jak vytvářet, upravovat a manipulovat s grafy pro vylepšení vašich prezentací. Grafy nejenže zvyšují vizuální přitažlivost dat, ale také pomáhají publiku snáze porozumět složitým informacím.

## Často kladené otázky

### Jak změním typ grafu?

Chcete-li změnit typ grafu, použijte `chart.setType()` metodu a zadejte požadovaný typ grafu.

### Mohu do grafu přidat více datových řad?

Ano, do grafu můžete přidat více datových řad pomocí `chart.getChartData().getSeries().addSeries()` metoda.

### Jak si mohu přizpůsobit barvy grafu?

Barvy grafu můžete přizpůsobit nastavením formátu výplně pro různé prvky grafu, jako jsou čáry mřížky, název a legendy.

### Mohu vytvářet 3D grafy?

Ano, Aspose.Slides pro Javu podporuje vytváření 3D grafů. Můžete nastavit `ChartType` na typ 3D grafu a vytvořit ho.

### Je Aspose.Slides pro Javu kompatibilní s nejnovějšími verzemi Javy?

Ano, Aspose.Slides pro Javu je pravidelně aktualizován, aby podporoval nejnovější verze Javy a poskytuje kompatibilitu v široké škále prostředí Java.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}