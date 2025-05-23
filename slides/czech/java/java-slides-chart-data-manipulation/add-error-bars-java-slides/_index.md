---
"description": "Naučte se, jak přidat chybové úsečky do grafů PowerPointu v Javě pomocí Aspose.Slides. Podrobný návod se zdrojovým kódem pro přizpůsobení chybových úseček."
"linktitle": "Přidání chybových úseček do snímků v Javě"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Přidání chybových úseček do snímků v Javě"
"url": "/cs/java/chart-data-manipulation/add-error-bars-java-slides/"
"weight": 13
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Přidání chybových úseček do snímků v Javě


## Úvod do přidávání chybových úseček do prezentací v Javě pomocí Aspose.Slides

V tomto tutoriálu si ukážeme, jak přidat chybové úsečky do grafu na snímku v PowerPointu pomocí Aspose.Slides pro Javu. Chybové úsečky poskytují cenné informace o variabilitě nebo nejistotě datových bodů v grafu. Vytvoříme bublinový graf a přidáme do něj chybové úsečky. Začněme!

## Předpoklady

Než začnete, ujistěte se, že máte ve svém projektu Java nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z [Webové stránky Aspose](https://downloads.aspose.com/slides/java).

## Krok 1: Vytvořte prázdnou prezentaci

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření prázdné prezentace
Presentation presentation = new Presentation();
```

V tomto kroku vytvoříme prázdnou prezentaci, kam přidáme náš graf s chybovými úsečkami.

## Krok 2: Vytvořte bublinový graf

```java
// Vytvoření bublinového grafu
IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
```

Zde vytvoříme bublinový graf a určíme jeho polohu a rozměry na snímku.

## Krok 3: Přidání chybových úseček a nastavení formátu

```java
// Přidání chybových úseček a nastavení jejich formátu
IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
errBarX.setVisible(true);
errBarY.setVisible(true);
errBarX.setValueType(ErrorBarValueType.Fixed);
errBarX.setValue(0.1f);
errBarY.setValueType(ErrorBarValueType.Percentage);
errBarY.setValue(5);
errBarX.setType(ErrorBarType.Plus);
errBarY.getFormat().getLine().setWidth(2);
errBarX.setEndCap(true);
```

V tomto kroku přidáme do grafu chybové úsečky a nastavíme jejich formát. Chybové úsečky si můžete přizpůsobit změnou hodnot, typů a dalších vlastností.

- `errBarX` představuje chybové úsečky podél osy X.
- `errBarY` představuje chybové úsečky podél osy Y.
- Zviditelníme chybové úsečky X i Y.
- `setValueType` určuje typ hodnoty pro chybové úsečky (např. pevná nebo procentuální).
- `setValue` nastavuje hodnotu pro chybové úsečky.
- `setType` definuje typ chybových úseček (např. Plus nebo Mínus).
- Šířku čar chybových úseček nastavíme pomocí `getFormat().getLine().setWidth(2)`.
- `setEndCap` určuje, zda se mají na chybových úsečkách zahrnout koncové uzávěry.

## Krok 4: Uložte prezentaci

```java
// Ukládání prezentace
presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
```

Nakonec uložíme prezentaci s přidanými chybovými úsečkami na určené místo.

To je vše! Úspěšně jste přidali chybové úsečky do grafu na snímku aplikace PowerPoint pomocí Aspose.Slides pro Javu.

## Kompletní zdrojový kód pro přidání chybových úseček v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
// Vytvoření prázdné prezentace
Presentation presentation = new Presentation();
try
{
	// Vytvoření bublinového grafu
	IChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(ChartType.Bubble, 50, 50, 400, 300, true);
	// Přidání chybových úseček a nastavení jejich formátu
	IErrorBarsFormat errBarX = chart.getChartData().getSeries().get_Item(0).getErrorBarsXFormat();
	IErrorBarsFormat errBarY = chart.getChartData().getSeries().get_Item(0).getErrorBarsYFormat();
	errBarX.setVisible(true);
	errBarY.setVisible(true);
	errBarX.setValueType(ErrorBarValueType.Fixed);
	errBarX.setValue(0.1f);
	errBarY.setValueType(ErrorBarValueType.Percentage);
	errBarY.setValue(5);
	errBarX.setType(ErrorBarType.Plus);
	errBarY.getFormat().getLine().setWidth(2);
	errBarX.setEndCap(true);
	// Ukládání prezentace
	presentation.save(dataDir + "ErrorBars_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (presentation != null) presentation.dispose();
}
```

## Závěr

V tomto tutoriálu jsme prozkoumali, jak vylepšit vaše prezentace v PowerPointu přidáním chybových úseček do grafů pomocí Aspose.Slides pro Javu. Chybové úsečky poskytují cenné informace o variabilitě a nejistotách dat, díky čemuž jsou vaše prezentace informativnější a vizuálně atraktivnější.

## Často kladené otázky

### Jak mohu dále přizpůsobit vzhled chybových úseček?

Chybové úsečky můžete přizpůsobit úpravou jejich vlastností, jako je styl čáry, barva a šířka, jak je znázorněno v kroku 3.

### Mohu přidat chybové úsečky do různých typů grafů?

Ano, chybové úsečky můžete přidat do různých typů grafů podporovaných službou Aspose.Slides pro Javu. Jednoduše vytvořte požadovaný typ grafu a postupujte podle stejných kroků pro přizpůsobení chybových úseček.

### Jak mohu upravit polohu a velikost grafu na snímku?

Polohu a rozměry grafu můžete ovládat úpravou parametrů v `addChart` metodu, jak je znázorněno v kroku 2.

### Kde najdu více informací o Aspose.Slides pro Javu?

Můžete se odvolat na [Dokumentace k Aspose.Slides pro Javu](https://reference.aspose.com/slides/java/) pro podrobné informace o používání knihovny.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}