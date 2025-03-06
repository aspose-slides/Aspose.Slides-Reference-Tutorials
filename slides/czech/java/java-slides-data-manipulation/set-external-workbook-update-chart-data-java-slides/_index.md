---
title: Nastavte externí sešit s aktualizací dat grafu v Java Slides
linktitle: Nastavte externí sešit s aktualizací dat grafu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se, jak nastavit externí sešity a aktualizovat data grafu v aplikaci Java Slides pomocí Aspose.Slides for Java. Vylepšete své dovednosti v automatizaci aplikace PowerPoint.
type: docs
weight: 20
url: /cs/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/
---

## Úvod k nastavení externího sešitu s aktualizací dat grafu v Java Slides

tomto komplexním průvodci vás provedeme procesem nastavení externího sešitu s aktualizovanými daty grafu v aplikaci Java Slides pomocí Aspose.Slides for Java API. Tato výkonná knihovna vám umožňuje programově manipulovat s prezentacemi PowerPoint, což usnadňuje automatizaci úloh, jako je aktualizace dat grafu z externího zdroje. Na konci tohoto tutoriálu budete mít jasnou představu o tom, jak tohoto úkolu dosáhnout pomocí podrobných pokynů a doprovodného kódu Java.

## Předpoklady

Než se pustíme do implementace, ujistěte se, že máte splněny následující předpoklady:

1.  Aspose.Slides for Java: Měli byste mít nainstalovanou knihovnu Aspose.Slides for Java. Můžete si jej stáhnout z[tady](https://releases.aspose.com/slides/java/).

2. Vývojové prostředí Java: Ujistěte se, že máte ve svém systému nastavené vývojové prostředí Java.

## Krok 1: Vytvořte novou prezentaci

Chcete-li začít, vytvořte novou prezentaci PowerPoint pomocí Aspose.Slides pro Java. Zde je kód Java, jak to udělat:

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidejte graf

Nyní do naší prezentace přidáme graf. V tomto příkladu vytvoříme výsečový graf:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Krok 3: Nastavte externí sešit

Zde nastavíme externí sešit jako zdroj dat pro náš graf. Musíte zadat adresu URL externího sešitu, i když zatím neexistuje:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://cesta/neexistuje/existuje", nepravda);
```

## Krok 4: Uložte prezentaci

Nakonec uložte prezentaci s aktualizovanými daty grafu:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro sadu externího sešitu s aktualizací dat grafu v Java Slides

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://cesta/neexistuje/existuje", nepravda);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

Gratulujeme! Naučili jste se, jak nastavit externí sešit s aktualizovanými daty grafu v Java Slides pomocí Aspose.Slides for Java. To může být neuvěřitelně užitečné pro dynamickou aktualizaci grafů v prezentacích PowerPoint z externích zdrojů dat.

## FAQ

### Jak mohu aktualizovat data externího sešitu pro graf?

Chcete-li aktualizovat data externího sešitu pro graf, stačí upravit data v externím sešitu na zadané adrese URL. Při příštím otevření prezentace Aspose.Slides for Java načte aktualizovaná data z externího sešitu a podle toho aktualizuje graf.

### Mohu jako externí sešit použít místní soubor?

Ano, můžete použít místní soubor jako externí sešit zadáním cesty k souboru namísto adresy URL. Jen se ujistěte, že cesta k souboru je správná a dostupná z vaší Java aplikace.

### Existují nějaká omezení pro používání externích sešitů s Aspose.Slides for Java?

I když je používání externích sešitů výkonnou funkcí, mějte na paměti, že dostupnost dat externího sešitu závisí na jejich dostupnosti na poskytnuté adrese URL nebo cestě k souboru. Ujistěte se, že při otevření prezentace je k dispozici externí zdroj dat, abyste předešli problémům s načítáním dat.

### Mohu upravit vzhled grafu po nastavení externího sešitu?

Ano, vzhled grafu, včetně jeho názvu, štítků, barev a dalších, můžete přizpůsobit i po nastavení externího sešitu. Aspose.Slides for Java poskytuje rozsáhlé možnosti formátování grafů, aby vyhovovaly vašim potřebám.

### Kde najdu další dokumentaci a zdroje pro Aspose.Slides for Java?

 Podrobnou dokumentaci a další zdroje naleznete v dokumentaci Aspose.Slides for Java na adrese[tady](https://reference.aspose.com/slides/java/).