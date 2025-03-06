---
title: Přidejte barvu k datovým bodům v Java Slides
linktitle: Přidejte barvu k datovým bodům v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak přidat barvu do datových bodů ve snímcích Java pomocí Aspose.Slides for Java.
weight: 10
url: /cs/java/chart-data-manipulation/add-color-data-points-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Přidejte barvu k datovým bodům v Java Slides


## Úvod do přidávání barvy do datových bodů v Java Slides

V tomto tutoriálu si ukážeme, jak přidat barvu do datových bodů na snímcích Java pomocí Aspose.Slides for Java. Tento podrobný průvodce obsahuje příklady zdrojového kódu, které vám pomohou dosáhnout tohoto úkolu.

## Předpoklady

Než začnete, ujistěte se, že máte splněny následující předpoklady:

- Vývojové prostředí Java
- Aspose.Slides pro knihovnu Java

## Krok 1: Vytvořte novou prezentaci

Nejprve vytvoříme novou prezentaci pomocí Aspose.Slides for Java. Tato prezentace bude sloužit jako kontejner pro náš graf.

```java
Presentation pres = new Presentation();
```

## Krok 2: Přidejte Sunburst Chart

Nyní do prezentace přidáme graf Sunburst. Určíme typ, umístění a velikost grafu.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Sunburst, 100, 100, 450, 400);
```

## Krok 3: Přístup k datovým bodům

 Abychom mohli upravit datové body v grafu, potřebujeme přístup k`IChartDataPointCollection` objekt.

```java
IChartDataPointCollection dataPoints = chart.getChartData().getSeries().get_Item(0).getDataPoints();
```

## Krok 4: Přizpůsobte datové body

V tomto kroku přizpůsobíme konkrétní datové body. Zde měníme barvu datových bodů a konfigurujeme nastavení štítků.

```java
// Přizpůsobit datový bod 0
IDataLabel branch1Label = dataPoints.get_Item(0).getDataPointLevels().get_Item(2).getLabel();
branch1Label.getDataLabelFormat().setShowCategoryName(false);
branch1Label.getDataLabelFormat().setShowSeriesName(true);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().setFillType(FillType.Solid);
branch1Label.getDataLabelFormat().getTextFormat().getPortionFormat().getFillFormat().getSolidFillColor().setColor(java.awt.Color.YELLOW);

// Přizpůsobte datový bod 9
IFormat steam4Format = dataPoints.get_Item(9).getFormat();
steam4Format.getFill().setFillType(FillType.Solid);
steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());
```

## Krok 5: Uložte prezentaci

Nakonec uložte prezentaci s přizpůsobeným grafem.

```java
pres.save("Your Output Directory/AddColorToDataPoints.pptx", SaveFormat.Pptx);
```

A je to! Úspěšně jste přidali barvu ke konkrétním datovým bodům na snímku Java pomocí Aspose.Slides for Java.

## Kompletní zdrojový kód pro přidání barvy do datových bodů v Java Slides

```java
Presentation pres = new Presentation();
try
{
	// Cesta k adresáři dokumentů.
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
	steam4Format.getFill().getSolidFillColor().setColor(com.aspose.cells.Color.fromArgb(0, 176, 240, 255).d());//DĚLAT
	pres.save(dataDir + "AddColorToDataPoints.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jste se naučili, jak přidat barvu do datových bodů na snímcích Java pomocí Aspose.Slides for Java. Své grafy a prezentace můžete dále upravovat podle svých specifických požadavků.

## FAQ

### Jak mohu změnit barvu jiných datových bodů?

Chcete-li změnit barvu ostatních datových bodů, můžete postupovat podobným způsobem, jak je uvedeno v kroku 4. Otevřete datový bod, který chcete upravit, a upravte jeho nastavení barev a štítků.

### Mohu přizpůsobit další aspekty grafu?

 Ano, můžete přizpůsobit různé aspekty grafu, včetně písem, štítků, nadpisů a dalších. Odkazovat na[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/) pro podrobné možnosti přizpůsobení.

### Kde najdu další příklady a dokumentaci?

 Další příklady a podrobnou dokumentaci k používání Aspose.Slides pro Javu naleznete na[Dokumentace Aspose.Slides](https://reference.aspose.com/slides/java/) webová stránka.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
