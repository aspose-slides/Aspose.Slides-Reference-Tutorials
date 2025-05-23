---
"description": "Vytvořte prstencové grafy s vlastními velikostmi otvorů v Java Slides pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem pro přizpůsobení grafu."
"linktitle": "Díra v prstencovém grafu v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Díra v prstencovém grafu v Javě Slides"
"url": "/cs/java/chart-elements/doughnut-chart-hole-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Díra v prstencovém grafu v Javě Slides


## Úvod do prstencového grafu s dírou v Javě Slides

V tomto tutoriálu vás provedeme vytvořením prstencového grafu s otvorem pomocí Aspose.Slides pro Javu. Tento podrobný návod vás provede celým procesem s příklady zdrojového kódu.

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Můžete si ji stáhnout z [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/).

## Krok 1: Importujte požadované knihovny

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;
import com.aspose.slides.SaveFormat;
```

## Krok 2: Inicializace prezentace

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";

// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
```

## Krok 3: Vytvořte prstencový graf

```java
try {
    // Vytvořte prstencový graf na prvním snímku
    IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
    
    // Nastavení velikosti otvoru v prstencovém grafu (v procentech)
    chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
    
    // Uložit prezentaci na disk
    presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
} finally {
    // Zlikvidujte prezentační objekt
    if (presentation != null) presentation.dispose();
}
```

## Krok 4: Spusťte kód

Spusťte kód Java v IDE nebo textovém editoru a vytvořte prstencový graf se zadanou velikostí otvoru. Nezapomeňte nahradit `"Your Document Directory"` se skutečnou cestou, kam chcete prezentaci uložit.

## Kompletní zdrojový kód pro otvor v prstencovém grafu v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření instance třídy Presentation
Presentation presentation = new Presentation();
try
{
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Doughnut, 50, 50, 400, 400);
	chart.getChartData().getSeriesGroups().get_Item(0).setDoughnutHoleSize((byte) 90);
	// Zapsat prezentaci na disk
	presentation.save(dataDir + "DoughnutHoleSize_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto tutoriálu jste se naučili, jak vytvořit prstencový graf s otvorem pomocí Aspose.Slides pro Javu. Velikost otvoru si můžete přizpůsobit úpravou `setDoughnutHoleSize` parametr metody.

## Často kladené otázky

### Jak mohu změnit barvu segmentů grafu?

Chcete-li změnit barvu segmentů grafu, můžete použít `setDataPointsInLegend` metoda na `IChart` objekt a nastavte požadovanou barvu pro každý datový bod.

### Mohu přidat popisky k segmentům prstencového grafu?

Ano, k segmentům prstencového grafu můžete přidat popisky pomocí `setDataPointsLabelValue` metoda na `IChart` objekt.

### Je možné přidat k grafu název?

Jistě! Název grafu můžete přidat pomocí `setTitle` metoda na `IChart` objektu a zadáním požadovaného textu titulku.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}