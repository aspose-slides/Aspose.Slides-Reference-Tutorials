---
"description": "Naučte se, jak přidat barvu k datovým bodům v slidech v Javě pomocí Aspose.Slides pro Javu."
"linktitle": "Přidání barvy k datovým bodům v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidání barvy k datovým bodům v Javě Slides"
"url": "/cs/java/chart-data-manipulation/add-color-data-points-java-slides/"
"weight": 10
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidání barvy k datovým bodům v Javě Slides


## Úvod do přidávání barev k datovým bodům v Javě Slides

V tomto tutoriálu si ukážeme, jak přidat barvu k datovým bodům v Javě pomocí Aspose.Slides pro Javu. Tato podrobná příručka obsahuje příklady zdrojového kódu, které vám s tímto úkolem pomohou.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

- Vývojové prostředí v Javě
- Aspose.Slides pro knihovnu Java

## Krok 1: Vytvořte novou prezentaci

Nejprve si vytvoříme novou prezentaci pomocí Aspose.Slides pro Javu. Tato prezentace bude sloužit jako kontejner pro náš graf.

```java
Presentation pres = new Presentation();
```

## Krok 2: Přidání slunečního grafu

Nyní přidáme do prezentace graf Sunburst. Určíme typ grafu, umístění a velikost.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Krok 3: Přístup k datovým bodům

Pro úpravu datových bodů v grafu potřebujeme přístup k `IChartDataPointCollection` objekt.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Krok 4: Úprava datových bodů

V tomto kroku si upravíme konkrétní datové body. Zde změníme barvu datových bodů a nakonfigurujeme nastavení popisků.

```java
// Přizpůsobit datový bod 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Přizpůsobení datového bodu 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Krok 5: Uložte prezentaci

Nakonec uložte prezentaci s upraveným grafem.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

To je vše! Úspěšně jste přidali barvu k určitým datovým bodům na snímku v Javě pomocí Aspose.Slides pro Javu.

## Kompletní zdrojový kód pro přidání barvy k datovým bodům v Javě Slides

```java
Presentation pres = new Presentation();
try
{
	// Cesta k adresáři s dokumenty.
	String dataDir = "Your Document Directory";
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
	IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
	dataPoints.get_Item(3).getDataPointLevels().get_Item(0).getLabel().getDataLabelFormat().setShowValue(true);
	IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
	branch1Label.getDataLabelFormat().setShowCategoryName(false);
	branch1Label.getDataLabelFormat().setShowSeriesName(true);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
	branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);
	IFormat steam4Format = dataPoints.get_Item(9).getFormat();
	steam4Format.getFill().setFillType(FillType.Solid);
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//ÚKOL
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jste se naučili, jak přidat barvu k datovým bodům v Javě pomocí Aspose.Slides pro Javu. Grafy a prezentace si můžete dále přizpůsobit podle svých specifických požadavků.

## Často kladené otázky

### Jak mohu změnit barvu jiných datových bodů?

Chcete-li změnit barvu jiných datových bodů, můžete použít podobný postup, jaký je znázorněn v kroku 4. Přejděte k datovému bodu, který chcete přizpůsobit, a upravte jeho barvu a nastavení popisku.

### Mohu si přizpůsobit další aspekty grafu?

Ano, můžete si přizpůsobit různé aspekty grafu, včetně písem, popisků, nadpisů a dalších. Viz [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/) pro detailní možnosti přizpůsobení.

### Kde najdu další příklady a dokumentaci?

Další příklady a podrobnou dokumentaci k používání Aspose.Slides pro Javu naleznete na [Dokumentace k Aspose.Slides](https://reference.aspose.com/slides/java/) webové stránky.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}