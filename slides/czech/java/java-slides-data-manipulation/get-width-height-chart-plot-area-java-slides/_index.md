---
"description": "Naučte se, jak načíst rozměry plochy grafu v Java Slides pomocí Aspose.Slides pro Javu. Zlepšete si své dovednosti v automatizaci PowerPointu."
"linktitle": "Získejte šířku a výšku z oblasti grafu v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Získejte šířku a výšku z oblasti grafu v Java Slides"
"url": "/cs/java/data-manipulation/get-width-height-chart-plot-area-java-slides/"
"weight": 21
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Získejte šířku a výšku z oblasti grafu v Java Slides


## Zavedení

Grafy jsou účinným způsobem vizualizace dat v prezentacích PowerPointu. Někdy můžete potřebovat znát rozměry oblasti grafu z různých důvodů, například pro změnu velikosti nebo umístění prvků v grafu. Tato příručka vám ukáže, jak získat šířku a výšku oblasti grafu pomocí Javy a Aspose.Slides pro Javu.

## Předpoklady

Než se pustíme do kódu, ujistěte se, že máte ve svém projektu v Javě nainstalovanou a nastavenou knihovnu Aspose.Slides for Java. Knihovnu si můžete stáhnout z webových stránek Aspose. [zde](https://releases.aspose.com/slides/java/).

## Krok 1: Nastavení prostředí

Ujistěte se, že máte do svého projektu v Javě přidánu knihovnu Aspose.Slides pro Javu. Můžete to provést zahrnutím knihovny do závislostí projektu nebo ručním přidáním souboru JAR.

## Krok 2: Vytvoření prezentace v PowerPointu

Začněme vytvořením prezentace v PowerPointu a přidáním snímku do ní. Ten bude sloužit jako kontejner pro náš graf.

```java
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
```

Nahradit `"Your Document Directory"` cestou k adresáři s dokumenty.

## Krok 3: Přidání grafu

Nyní přidáme na snímek klastrovaný sloupcový graf. Také ověříme rozvržení grafu.

```java
Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
chart.validateChartLayout();
```

Tento kód vytvoří klastrovaný sloupcový graf na pozici (100, 100) s dimenzemi (500, 350).

## Krok 4: Získání rozměrů plochy grafu

Pro načtení šířky a výšky vykreslované oblasti grafu můžeme použít následující kód:

```java
double x = chart.getPlotArea().getActualX();
double y = chart.getPlotArea().getActualY();
double w = chart.getPlotArea().getActualWidth();
double h = chart.getPlotArea().getActualHeight();
```

Nyní proměnné `x`, `y`, `w`a `h` obsahují příslušné hodnoty pro souřadnici X, souřadnici Y, šířku a výšku oblasti grafu.

## Krok 5: Uložení prezentace

Nakonec prezentaci s grafem uložte.

```java
pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
```

Nezapomeňte vyměnit `"Chart_out.pptx"` s požadovaným názvem výstupního souboru.

## Kompletní zdrojový kód pro získání šířky a výšky z oblasti grafu v Java Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "test.Pptx");
try
{
	Chart chart = (Chart) pres.getSlides().get_Item(0).getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 500, 350);
	chart.validateChartLayout();
	double x = chart.getPlotArea().getActualX();
	double y = chart.getPlotArea().getActualY();
	double w = chart.getPlotArea().getActualWidth();
	double h = chart.getPlotArea().getActualHeight();
	// Uložit prezentaci s grafem
	pres.save(dataDir + "Chart_out.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

tomto článku jsme se zabývali tím, jak získat šířku a výšku oblasti grafu v aplikaci Java Slides pomocí rozhraní Aspose.Slides for Java API. Tyto informace mohou být cenné, když potřebujete dynamicky upravovat rozvržení grafů v prezentacích PowerPointu.

## Často kladené otázky

### Jak mohu změnit typ grafu na jiný než shlukovaný sloupcový graf?

Typ grafu můžete změnit nahrazením `ChartType.ClusteredColumn` s požadovaným výčtem typů grafů, například `ChartType.Line` nebo `ChartType.Pie`.

### Mohu upravit další vlastnosti grafu?

Ano, různé vlastnosti grafu, jako jsou data, popisky a formátování, můžete upravit pomocí rozhraní Aspose.Slides pro Java API. Další podrobnosti naleznete v dokumentaci.

### Je Aspose.Slides pro Javu vhodný pro profesionální automatizaci PowerPointu?

Ano, Aspose.Slides pro Javu je výkonná knihovna pro automatizaci úloh PowerPointu v aplikacích Java. Poskytuje komplexní funkce pro práci s prezentacemi, snímky, tvary, grafy a dalšími prvky.

### Jak se mohu dozvědět více o Aspose.Slides pro Javu?

Rozsáhlou dokumentaci a příklady naleznete na stránce s dokumentací k Aspose.Slides pro Javu. [zde](https://reference.aspose.com/slides/java/).


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}