---
title: Nastavení dat grafu ze sešitu v Java Slides
linktitle: Nastavení dat grafu ze sešitu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit data grafu z excelového sešitu v Java Slides pomocí Aspose.Slides. Podrobný průvodce s příklady kódu pro dynamické prezentace.
type: docs
weight: 15
url: /cs/java/data-manipulation/set-chart-data-from-workbook-java-slides/
---

## Úvod k nastavení dat grafu ze sešitu v Java Slides

Aspose.Slides for Java je výkonná knihovna, která umožňuje vývojářům pracovat s prezentacemi v PowerPointu programově. Poskytuje rozsáhlé funkce pro vytváření, manipulaci a správu snímků aplikace PowerPoint. Jedním z běžných požadavků při práci s prezentacemi je dynamické nastavení dat grafu z externího zdroje dat, jako je sešit aplikace Excel. V tomto tutoriálu si ukážeme, jak toho dosáhnout pomocí Javy.

## Předpoklady

Než se pustíme do implementace, ujistěte se, že máte následující předpoklady:

- Java Development Kit (JDK) nainstalovaný ve vašem systému.
- Do vašeho projektu byla přidána knihovna Aspose.Slides for Java.
- Excelový sešit s daty, která chcete použít pro graf.

## Krok 1: Vytvořte prezentaci

```java
String outPath = "Your Output Directory" + "response2.pptx";
Presentation pres = new Presentation();
```

Začneme vytvořením nové PowerPointové prezentace pomocí Aspose.Slides for Java.

## Krok 2: Přidejte graf

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 500, 400);
```

Dále přidáme graf na jeden ze snímků v prezentaci. V tomto příkladu přidáváme výsečový graf, ale můžete si vybrat typ grafu, který vyhovuje vašim potřebám.

## Krok 3: Vymažte data grafu

```java
chart.getChartData().getChartDataWorkbook().clear(0);
```

grafu vymažeme všechna existující data, abychom je připravili na nová data z excelového sešitu.

## Krok 4: Načtěte sešit aplikace Excel

```java
Workbook workbook = new Workbook("Your Document Directory";
```

 Načteme sešit Excel, který obsahuje data, která chceme použít pro graf. Nahradit`"book1.xlsx"` s cestou k souboru Excel.

## Krok 5: Zapište datový proud sešitu do dat grafu

```java
ByteArrayOutputStream mem = new ByteArrayOutputStream();
workbook.save(mem, com.aspose.cells.SaveFormat.XLSX);
mem.flush();
chart.getChartData().writeWorkbookStream(mem.toByteArray());
```

Data sešitu Excel převedeme na stream a zapíšeme je do dat grafu.

## Krok 6: Nastavte rozsah dat grafu

```java
chart.getChartData().setRange("Sheet2!$A$1:$B$3");
```

Určujeme rozsah buněk z excelového sešitu, které mají být použity jako data pro graf. Upravte rozsah podle potřeby pro vaše data.

## Krok 7: Přizpůsobte řadu grafů

```java
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getParentSeriesGroup().setColorVaried(true);
```

Různé vlastnosti sérií grafů můžete přizpůsobit svým požadavkům. V tomto příkladu povolíme různé barvy pro řadu grafů.

## Krok 8: Uložte prezentaci

```java
pres.save(outPath, SaveFormat.Pptx);
```

Nakonec prezentaci s aktualizovanými daty grafu uložíme do zadané výstupní cesty.

## Kompletní zdrojový kód pro nastavení dat grafu ze sešitu v Java Slides

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

tomto tutoriálu jsme se naučili, jak nastavit data grafu z excelového sešitu v Java Slides pomocí knihovny Aspose.Slides for Java. Podle podrobného průvodce a pomocí poskytnutých příkladů zdrojového kódu můžete snadno integrovat data dynamických grafů do svých prezentací PowerPoint.

## FAQ

### Jak mohu přizpůsobit vzhled grafu v mé prezentaci?

Vzhled grafu můžete upravit úpravou vlastností, jako jsou barvy, písma, štítky a další. Podrobné informace o možnostech přizpůsobení grafu naleznete v dokumentaci Aspose.Slides for Java.

### Mohu pro graf použít data z jiného souboru Excel?

Ano, můžete použít data z libovolného souboru Excel zadáním správné cesty k souboru při načítání sešitu v kódu.

### Jaké další typy grafů mohu vytvořit pomocí Aspose.Slides for Java?

Aspose.Slides for Java podporuje různé typy grafů, včetně sloupcových grafů, spojnicových grafů, bodových grafů a dalších. Můžete si vybrat typ grafu, který nejlépe vyhovuje vašim potřebám reprezentace dat.

### Je možné dynamicky aktualizovat data grafu v běžící prezentaci?

Ano, data grafu můžete dynamicky aktualizovat v prezentaci úpravou podkladového sešitu a následným obnovením dat grafu.

### Kde najdu další příklady a zdroje pro práci s Aspose.Slides for Java?

 Další příklady a zdroje můžete prozkoumat na[Aspose webové stránky](https://www.aspose.com/). Dokumentace Aspose.Slides for Java navíc poskytuje komplexní pokyny pro práci s knihovnou.