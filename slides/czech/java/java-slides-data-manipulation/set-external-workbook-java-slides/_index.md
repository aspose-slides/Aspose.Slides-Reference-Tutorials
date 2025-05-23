---
"description": "Naučte se, jak nastavit externí sešity v Java Slides pomocí Aspose.Slides pro Javu. Vytvářejte dynamické prezentace s integrací dat z Excelu."
"linktitle": "Nastavení externího sešitu v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení externího sešitu v Java Slides"
"url": "/cs/java/data-manipulation/set-external-workbook-java-slides/"
"weight": 19
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení externího sešitu v Java Slides


## Úvod do nastavení externího sešitu v aplikaci Java Slides

tomto tutoriálu se podíváme na to, jak nastavit externí sešit v Java Slides pomocí Aspose.Slides. Naučíte se, jak vytvořit prezentaci v PowerPointu s grafem, který odkazuje na data z externího sešitu aplikace Excel. Po dokončení této příručky budete mít jasnou představu o tom, jak integrovat externí data do vašich prezentací v Java Slides.

## Předpoklady

Než se pustíme do implementace, ujistěte se, že máte splněny následující předpoklady:

- Na vašem systému nainstalovaná sada pro vývoj Java (JDK).
- Do vašeho projektu byla přidána knihovna Aspose.Slides pro Javu.
- Sešit aplikace Excel s daty, na která chcete odkazovat ve své prezentaci.

## Krok 1: Vytvořte novou prezentaci

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

Začneme vytvořením nové prezentace v PowerPointu pomocí Aspose.Slides.

## Krok 2: Přidání grafu

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
```

Dále do prezentace vložíme koláčový graf. Typ a umístění grafu si můžete dle potřeby přizpůsobit.

## Krok 3: Přístup k externímu sešitu

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
```

Pro přístup k externímu sešitu používáme `setExternalWorkbook` metodu a zadejte cestu k sešitu aplikace Excel obsahujícímu data.

## Krok 4: Propojení dat grafu

```java
chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
```

Graf propojíme s daty z externího sešitu zadáním odkazů na buňky pro řady a kategorie.

## Krok 5: Uložte prezentaci

```java
pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
```

Nakonec uložíme prezentaci s odkazem na externí sešit jako soubor PowerPointu.

## Kompletní zdrojový kód pro sadu externího sešitu v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, false);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook(dataDir + "externalWorkbook.xlsx");
	chartData.getSeries().add(chartData.getChartDataWorkbook().getCell(0, "B1"), ChartType.Pie);
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B2"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B3"));
	chartData.getSeries().get_Item(0).getDataPoints().addDataPointForPieSeries(chartData.getChartDataWorkbook().getCell(0, "B4"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A2"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A3"));
	chartData.getCategories().add(chartData.getChartDataWorkbook().getCell(0, "A4"));
	pres.save(dataDir + "Presentation_with_externalWorkbook.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

V tomto tutoriálu jsme se naučili, jak nastavit externí sešit v Java Slides pomocí Aspose.Slides. Nyní můžete vytvářet prezentace, které dynamicky odkazují na data ze sešitů aplikace Excel, což zvyšuje flexibilitu a interaktivitu vašich slidů.

## Často kladené otázky

### Jak nainstaluji Aspose.Slides pro Javu?

Knihovnu Aspose.Slides pro Javu lze nainstalovat přidáním knihovny do vašeho projektu v Javě. Knihovnu si můžete stáhnout z webových stránek Aspose a postupovat podle pokynů k instalaci uvedených v dokumentaci.

### Mohu používat různé typy grafů s externími sešity?

Ano, můžete použít různé typy grafů podporované službou Aspose.Slides a propojit je s daty z externích sešitů. Postup se může mírně lišit v závislosti na zvoleném typu grafu.

### Co když se změní datová struktura mého externího sešitu?

Pokud se struktura dat externího sešitu změní, může být nutné aktualizovat odkazy na buňky v kódu Java, aby data v grafu zůstala přesná.

### Je Aspose.Slides kompatibilní s nejnovějšími verzemi Javy?

Aspose.Slides pro Javu je pravidelně aktualizován, aby byla zajištěna kompatibilita s nejnovějšími verzemi Javy. Pro optimální výkon a kompatibilitu nezapomeňte kontrolovat aktualizace a používat nejnovější verzi knihovny.

### Mohu přidat více grafů odkazujících na stejný externí sešit?

Ano, do prezentace můžete přidat více grafů, které odkazují na stejný externí sešit. Jednoduše opakujte kroky popsané v tomto tutoriálu pro každý graf, který chcete vytvořit.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}