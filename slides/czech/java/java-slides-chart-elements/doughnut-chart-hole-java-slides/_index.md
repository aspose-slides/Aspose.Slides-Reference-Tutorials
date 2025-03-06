---
title: Díra prstencového grafu v Java Slides
linktitle: Díra prstencového grafu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Vytvářejte prstencové grafy s vlastními velikostmi děr v Java Slides pomocí Aspose.Slides for Java. Podrobný průvodce se zdrojovým kódem pro přizpůsobení grafu.
weight: 11
url: /cs/java/chart-elements/doughnut-chart-hole-java-slides/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}


## Úvod do prstencového grafu s dírou v Java Slides

V tomto tutoriálu vás provedeme vytvořením prstencového grafu s dírou pomocí Aspose.Slides for Java. Tento průvodce vás krok za krokem provede celým procesem s příklady zdrojového kódu.

## Předpoklady

 Než začnete, ujistěte se, že máte v projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[Aspose.Slides pro dokumentaci Java](https://reference.aspose.com/slides/java/).

## Krok 1: Importujte požadované knihovny

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Krok 2: Inicializujte prezentaci

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";

// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
```

## Krok 3: Vytvořte prstencový graf

```java
try {
    // Na prvním snímku vytvořte prstencový graf
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Nastavte velikost otvoru v prstencovém grafu (v procentech)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Uložte prezentaci na disk
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Zlikvidujte předmět prezentace
    if (presentation != null) presentation.dispose();
}
```

## Krok 4: Spusťte kód

 Spusťte kód Java ve svém IDE nebo textovém editoru a vytvořte prstencový graf se zadanou velikostí díry. Nezapomeňte vyměnit`"Your Document Directory"` se skutečnou cestou, kam chcete prezentaci uložit.

## Kompletní zdrojový kód pro kruhový graf Díra v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
// Vytvořte instanci třídy Presentation
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Zápis prezentace na disk
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

 V tomto tutoriálu jste se naučili, jak vytvořit prstencový graf s dírou pomocí Aspose.Slides pro Java. Velikost otvoru můžete upravit úpravou`setDoughnutHoleSize` parametr metody.

## FAQ

### Jak mohu změnit barvu segmentů grafu?

 Chcete-li změnit barvu segmentů grafu, můžete použít`setDataPointsInLegend` metoda na`IChart` objekt a nastavte požadovanou barvu pro každý datový bod.

### Mohu přidat štítky do segmentů prstencového grafu?

 Ano, k segmentům prstencového grafu můžete přidat štítky pomocí`setDataPointsLabelValue` metoda na`IChart` objekt.

### Je možné do grafu přidat název?

 Rozhodně! Do grafu můžete přidat název pomocí`setTitle` metoda na`IChart` objekt a poskytnutí požadovaného textu nadpisu.
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
