---
title: Nastavte režim rozvržení v aplikaci Java Slides
linktitle: Nastavte režim rozvržení v aplikaci Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit režimy rozvržení pro snímky Java pomocí Aspose.Slides. Přizpůsobte si umístění a velikost grafu v tomto podrobném průvodci se zdrojovým kódem.
weight: 23
url: /cs/java/data-manipulation/set-layout-mode-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Nastavte režim rozvržení v aplikaci Java Slides


## Úvod do nastavení režimu rozvržení v Java Slides

V tomto tutoriálu se naučíme, jak nastavit režim rozvržení pro graf v Java slides pomocí Aspose.Slides for Java. Režim rozložení určuje umístění a velikost grafu na snímku.

## Předpoklady

 Než začneme, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z[tady](https://releases.aspose.com/slides/java/).

## Krok 1: Vytvořte prezentaci

Nejprve musíme vytvořit novou prezentaci.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Krok 2: Přidejte snímek a graf

Dále k němu přidáme snímek a graf. V tomto příkladu vytvoříme seskupený sloupcový graf.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Krok 3: Nastavte rozložení grafu

 Nyní nastavíme rozložení grafu. Pozici a velikost grafu v rámci snímku upravíme pomocí`setX`, `setY`, `setWidth`, `setHeight` metody. Navíc nastavíme`LayoutTargetType` k určení režimu rozvržení.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

V tomto příkladu jsme nastavili graf tak, aby měl cílový typ rozvržení "Vnitřní", což znamená, že bude umístěn a velikostně vzhledem k vnitřní oblasti snímku.

## Krok 4: Uložte prezentaci

Nakonec uložíme prezentaci s nastavením rozložení grafu.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro nastavení režimu rozvržení v Java Slides

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
try
{
	ISlide slide = presentation.getSlides().get_Item(0);
	IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
	chart.getPlotArea().setX(0.2f);
	chart.getPlotArea().setY(0.2f);
	chart.getPlotArea().setWidth(0.7f);
	chart.getPlotArea().setHeight(0.7f);
	chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
	presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

 V tomto tutoriálu jsme se naučili, jak nastavit režim rozvržení pro graf na snímcích Java pomocí Aspose.Slides for Java. Pozici a velikost grafu můžete upravit podle svých konkrétních požadavků úpravou hodnot v`setX`, `setY`, `setWidth`, `setHeight` , a`setLayoutTargetType`metody. To vám dává kontrolu nad umístěním grafů na snímcích.

## FAQ

### Jak změním režim rozložení pro graf v Aspose.Slides pro Java?

 Chcete-li změnit režim rozložení pro graf v Aspose.Slides pro Java, můžete použít`setLayoutTargetType` metoda na ploše grafu. Můžete jej nastavit na obojí`LayoutTargetType.Inner` nebo`LayoutTargetType.Outer` v závislosti na požadovaném rozložení.

### Mohu upravit polohu a velikost grafu na snímku?

 Ano, polohu a velikost grafu na snímku můžete upravit pomocí`setX`, `setY`, `setWidth` , a`setHeight` metody na ploše grafu. Upravte tyto hodnoty tak, aby umístění a velikost grafu odpovídaly vašim požadavkům.

### Kde najdu více informací o Aspose.Slides for Java?

 Více informací o Aspose.Slides for Java naleznete v[dokumentace](https://reference.aspose.com/slides/java/). Obsahuje podrobné odkazy a příklady rozhraní API, které vám pomohou efektivně pracovat se snímky a grafy v Javě.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
