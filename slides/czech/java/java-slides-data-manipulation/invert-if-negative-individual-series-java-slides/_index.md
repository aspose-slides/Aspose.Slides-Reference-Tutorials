---
"description": "Naučte se, jak používat funkci Invertovat, pokud je záporné v Aspose.Slides pro Javu k vylepšení vizuální stránky grafů v prezentacích PowerPointu."
"linktitle": "Invertovat, pokud je záporné pro jednotlivé série v Javě Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Invertovat, pokud je záporné pro jednotlivé série v Javě Slides"
"url": "/cs/java/data-manipulation/invert-if-negative-individual-series-java-slides/"
"weight": 11
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Invertovat, pokud je záporné pro jednotlivé série v Javě Slides


## Úvod do inverze negativního kritéria pro jednotlivé řady v Javě Slides

Aspose.Slides pro Javu poskytuje výkonné nástroje pro práci s prezentacemi a jednou zajímavou funkcí je možnost ovládat, jak se datové řady zobrazují v grafech. V tomto článku se podíváme na to, jak používat funkci „Invertovat, pokud je záporné“ pro jednotlivé řady v Java Slides. Tato funkce umožňuje vizuálně rozlišit záporné datové body v grafu, díky čemuž jsou vaše prezentace informativnější a poutavější.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte splněny následující předpoklady:

- Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
- Knihovna Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

## Nastavení projektu

Chcete-li začít, vytvořte nový projekt Java ve vámi preferovaném integrovaném vývojovém prostředí (IDE). Jakmile je projekt nastaven, postupujte podle těchto kroků a implementujte funkci „Invertovat, pokud je záporné“ pro jednotlivé série v Java Slides.

## Krok 1: Přidání knihovny Aspose.Slides

Nejprve je třeba do projektu zahrnout knihovnu Aspose.Slides. Toho dosáhnete přidáním souboru JAR knihovny do cesty ke třídám projektu. Tento krok vám zajistí přístup ke všem potřebným třídám a metodám pro práci s prezentacemi v PowerPointu.

```java
import com.aspose.slides.*;
```

## Krok 2: Vytvořte prezentaci

Nyní si vytvořme novou prezentaci v PowerPointu pomocí Aspose.Slides. Adresář, kam chcete prezentaci uložit, můžete definovat pomocí `dataDir` proměnná.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 3: Přidání grafu

V tomto kroku přidáme do prezentace graf. Jako příklad použijeme shlukový sloupcový graf. Můžete si vybrat různé typy grafů podle vašich požadavků.

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
```

## Krok 4: Konfigurace datové řady grafu

Dále nakonfigurujeme datovou řadu grafu. Pro demonstraci funkce „Invertovat, pokud je záporné“, vytvoříme ukázkovou datovou sadu s kladnými i zápornými hodnotami.

```java
IChartSeriesCollection series = chart.getChartData().getSeries();
chart.getChartData().getSeries().clear();

// Přidání datových bodů do řady
series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
```

## Krok 5: Použijte funkci „Invertovat, pokud je záporná“

Nyní na jeden z datových bodů aplikujeme funkci „Invertovat, pokud je záporná“. Tato funkce vizuálně invertuje barvu daného datového bodu, když je záporný.

```java
series.get_Item(0).setInvertIfNegative(false); // Ve výchozím nastavení neinvertovat
series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true); // Invertovat barvu pro třetí datový bod
```

## Krok 6: Uložte prezentaci

Nakonec uložte prezentaci do vámi určeného adresáře.

```java
pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro invertování negativního kódu pro jednotlivé série v Javě Slides

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 50, 50, 600, 400, true);
	IChartSeriesCollection series = chart.getChartData().getSeries();
	chart.getChartData().getSeries().clear();
	series.add(chart.getChartData().getChartDataWorkbook().getCell(0, "B1"), chart.getType());
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B2", -5));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B3", 3));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B4", -2));
	series.get_Item(0).getDataPoints().addDataPointForBarSeries(chart.getChartData().getChartDataWorkbook().getCell(0, "B5", 1));
	series.get_Item(0).setInvertIfNegative(false);
	series.get_Item(0).getDataPoints().get_Item(2).setInvertIfNegative(true);
	pres.save(dataDir + "InvertIfNegativeForIndividualSeries.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak používat funkci „Invertovat, pokud je záporné“ pro jednotlivé série v Java Slides pomocí Aspose.Slides pro Javu. Tato funkce umožňuje zvýraznit záporné datové body v grafech, čímž se vaše prezentace stanou vizuálně přitažlivějšími a informativnějšími.

## Často kladené otázky

### Jaký je účel funkce „Invertovat, pokud je záporné“ v Aspose.Slides pro Javu?

Funkce „Invertovat, pokud je záporná“ v Aspose.Slides pro Javu umožňuje vizuálně rozlišit záporné datové body v grafech. Pomáhá zvýšit informativnost a poutavost vašich prezentací zvýrazněním konkrétních datových bodů.

### Jak mohu do svého projektu v Javě zahrnout knihovnu Aspose.Slides?

Chcete-li do svého projektu v Javě zahrnout knihovnu Aspose.Slides, je nutné přidat soubor JAR knihovny do cesty tříd projektu. To vám umožní přístup ke všem potřebným třídám a metodám pro práci s prezentacemi v PowerPointu.

### Mohu s funkcí „Invertovat, pokud je hodnota záporná“ používat různé typy grafů?

Ano, s funkcí „Invertovat, pokud je záporné“ můžete použít různé typy grafů. V tomto tutoriálu jsme jako příklad použili klastrovaný sloupcový graf, ale tuto funkci můžete podle svých požadavků použít na různé typy grafů.

### Je možné přizpůsobit vzhled invertovaných datových bodů?

Ano, vzhled invertovaných datových bodů si můžete přizpůsobit. Aspose.Slides pro Javu nabízí možnosti pro ovládání barvy a stylu datových bodů, když jsou invertovány, a to díky nastavení „Invertovat, pokud je záporné“.

### Kde mohu získat přístup k dokumentaci k Aspose.Slides pro Javu?

Dokumentaci k Aspose.Slides pro Javu naleznete na adrese [zde](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}