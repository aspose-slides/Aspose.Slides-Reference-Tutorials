---
"description": "Naučte se, jak nastavit data grafu z excelového sešitu v Java Slides pomocí Aspose.Slides. Podrobný návod s příklady kódu pro dynamické prezentace."
"linktitle": "Nastavení dat grafu ze sešitu v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení dat grafu ze sešitu v Java Slides"
"url": "/cs/java/data-manipulation/set-chart-data-from-workbook-java-slides/"
"weight": 15
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení dat grafu ze sešitu v Java Slides


## Úvod do nastavení dat grafu ze sešitu v Javě - Slides

Aspose.Slides pro Javu je výkonná knihovna, která umožňuje vývojářům programově pracovat s prezentacemi v PowerPointu. Poskytuje rozsáhlé funkce pro vytváření, manipulaci a správu snímků v PowerPointu. Jedním z běžných požadavků při práci s prezentacemi je dynamické nastavování dat grafu z externího zdroje dat, například ze sešitu aplikace Excel. V tomto tutoriálu si ukážeme, jak toho dosáhnout pomocí Javy.

## Předpoklady

Než se pustíme do implementace, ujistěte se, že máte splněny následující předpoklady:

- Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
- Do vašeho projektu byla přidána knihovna Aspose.Slides pro Javu.
- Sešit aplikace Excel s daty, která chcete použít pro graf.

## Krok 1: Vytvořte prezentaci

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Začneme vytvořením nové prezentace v PowerPointu pomocí Aspose.Slides pro Javu.

## Krok 2: Přidání grafu

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Dále přidáme graf do jednoho ze snímků v prezentaci. V tomto příkladu přidáváme koláčový graf, ale můžete si vybrat typ grafu, který vyhovuje vašim potřebám.

## Krok 3: Vymazání dat grafu

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

Z grafu vymažeme veškerá existující data, abychom jej připravili na nová data ze sešitu aplikace Excel.

## Krok 4: Načtení sešitu aplikace Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

Načteme sešit aplikace Excel, který obsahuje data, která chceme použít pro graf. Nahraďte `"book1.xlsx"` s cestou k vašemu souboru Excel.

## Krok 5: Zápis datového proudu sešitu do grafu

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Data z excelového sešitu převedeme do streamu a zapíšeme je do dat grafu.

## Krok 6: Nastavení rozsahu dat grafu

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Z excelového sešitu určíme rozsah buněk, které se mají použít jako data pro graf. Upravte rozsah podle potřeby pro vaše data.

## Krok 7: Úprava série grafů

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Různé vlastnosti grafové série si můžete přizpůsobit svým požadavkům. V tomto příkladu povolujeme pro grafovou sérii různé barvy.

## Krok 8: Uložte prezentaci

```java
pres.save(outPath, SaveFormat.Pptx);
```

Nakonec uložíme prezentaci s aktualizovanými daty grafu do zadané výstupní cesty.

## Kompletní zdrojový kód pro nastavení dat grafu ze sešitu v Javě Slides

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
try {
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
	chart.getChartData().getChartDataWorkbook().clear(0);
	Workbook workbook = null;
	try {
		workbook = new Workbook("Your Document Directory";
	} catch (Exception ex) {
		System.out.println(ex);
	}
	ByteArrayOutputStream mem = new ByteArrayOutputStream();
	workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
	mem.flush();
	chart.getChartData().writeWorkbookStream(mem.toByteArray());
	chart.getChartData().setRange("Sheet2!$A$1:$B$3");
	IChartSeries series = chart.getChartData().getSeries().get_Item(0);
	series.getParentSeriesGroup().setColorVaried(true);
	pres.save(outPath, SaveFormat.Pptx);
} catch(Exception e) {
} finally {
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak nastavit data grafu z excelového sešitu v Java Slides pomocí knihovny Aspose.Slides pro Javu. Pomocí podrobného návodu a poskytnutých příkladů zdrojového kódu můžete snadno integrovat dynamická data grafu do svých prezentací v PowerPointu.

## Často kladené otázky

### Jak si mohu přizpůsobit vzhled grafu v prezentaci?

Vzhled grafu si můžete přizpůsobit úpravou vlastností, jako jsou barvy, písma, popisky a další. Podrobné informace o možnostech přizpůsobení grafu naleznete v dokumentaci k Aspose.Slides pro Javu.

### Mohu pro graf použít data z jiného souboru aplikace Excel?

Ano, data z libovolného souboru aplikace Excel můžete použít zadáním správné cesty k souboru při načítání sešitu v kódu.

### Jaké další typy grafů mohu vytvořit pomocí Aspose.Slides pro Javu?

Aspose.Slides pro Javu podporuje různé typy grafů, včetně sloupcových grafů, spojnicových grafů, bodových grafů a dalších. Můžete si vybrat typ grafu, který nejlépe vyhovuje vašim potřebám reprezentace dat.

### Je možné dynamicky aktualizovat data grafu v běžící prezentaci?

Ano, data grafu v prezentaci můžete dynamicky aktualizovat úpravou podkladového sešitu a následnou aktualizací dat grafu.

### Kde najdu další příklady a zdroje pro práci s Aspose.Slides pro Javu?

Další příklady a zdroje si můžete prohlédnout na [Webové stránky Aspose](https://www.aspose.com/)Dokumentace k Aspose.Slides pro Javu navíc poskytuje komplexní pokyny k práci s knihovnou.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}