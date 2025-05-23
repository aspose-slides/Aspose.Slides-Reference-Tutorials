---
"description": "Naučte se, jak nastavit režimy rozvržení pro snímky v Javě pomocí Aspose.Slides. V tomto podrobném návodu se zdrojovým kódem si můžete přizpůsobit umístění a velikost grafu."
"linktitle": "Nastavení režimu rozvržení v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení režimu rozvržení v Java Slides"
"url": "/cs/java/data-manipulation/set-layout-mode-java-slides/"
"weight": 23
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení režimu rozvržení v Java Slides


## Úvod do nastavení režimu rozvržení v Javě Slides

tomto tutoriálu se naučíme, jak nastavit režim rozvržení grafu v Javě pomocí Aspose.Slides pro Javu. Režim rozvržení určuje umístění a velikost grafu v rámci snímku.

## Předpoklady

Než začneme, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Vytvořte prezentaci

Nejprve musíme vytvořit novou prezentaci.

```java
String dataDir = "Your Document Directory";
Presentation presentation = new Presentation();
```

## Krok 2: Přidání snímku a grafu

Dále přidáme snímek a k němu graf. V tomto příkladu vytvoříme seskupený sloupcový graf.

```java
ISlide slide = presentation.getSlides().get_Item(0);
IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 20, 100, 600, 400);
```

## Krok 3: Nastavení rozvržení grafu

Nyní nastavme rozvržení grafu. Upravíme pozici a velikost grafu na snímku pomocí `setX`, `setY`, `setWidth`, `setHeight` metody. Dále nastavíme `LayoutTargetType` pro určení režimu rozvržení.

```java
chart.getPlotArea().setX(0.2f);
chart.getPlotArea().setY(0.2f);
chart.getPlotArea().setWidth(0.7f);
chart.getPlotArea().setHeight(0.7f);
chart.getPlotArea().setLayoutTargetType(LayoutTargetType.Inner);
```

tomto příkladu jsme nastavili cílový typ rozvržení grafu na „Vnitřní“, což znamená, že bude umístěn a zvětšen vzhledem k vnitřní oblasti snímku.

## Krok 4: Uložte prezentaci

Nakonec uložme prezentaci s nastavením rozvržení grafu.

```java
presentation.save(dataDir + "SetLayoutMode_outer.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro nastavení režimu rozvržení v Javě Slides

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

V tomto tutoriálu jsme se naučili, jak nastavit režim rozvržení grafu v Javě pomocí Aspose.Slides pro Javu. Polohu a velikost grafu si můžete přizpůsobit podle svých specifických požadavků úpravou hodnot v `setX`, `setY`, `setWidth`, `setHeight`a `setLayoutTargetType` metody. To vám dává kontrolu nad umístěním grafů v rámci snímků.

## Často kladené otázky

### Jak změním režim rozvržení grafu v Aspose.Slides pro Javu?

Chcete-li změnit režim rozvržení grafu v Aspose.Slides pro Javu, můžete použít `setLayoutTargetType` metodu v oblasti grafu. Můžete ji nastavit na jednu z možností `LayoutTargetType.Inner` nebo `LayoutTargetType.Outer` závislosti na požadovaném rozvržení.

### Mohu si přizpůsobit umístění a velikost grafu na snímku?

Ano, polohu a velikost grafu na snímku můžete přizpůsobit pomocí `setX`, `setY`, `setWidth`a `setHeight` metody v oblasti vykreslování grafu. Upravte tyto hodnoty tak, aby graf byl umístěn a měl velikost podle vašich požadavků.

### Kde najdu více informací o Aspose.Slides pro Javu?

Více informací o Aspose.Slides pro Javu naleznete v [dokumentace](https://reference.aspose.com/slides/java/)Obsahuje podrobné reference API a příklady, které vám pomohou efektivně pracovat se snímky a grafy v Javě.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}