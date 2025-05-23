---
"description": "Naučte se, jak nastavit externí sešity a aktualizovat data grafů v Java Slides pomocí Aspose.Slides pro Javu. Zlepšete si své dovednosti automatizace PowerPointu."
"linktitle": "Nastavení externího sešitu s aktualizací dat grafu v Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Nastavení externího sešitu s aktualizací dat grafu v Java Slides"
"url": "/cs/java/data-manipulation/set-external-workbook-update-chart-data-java-slides/"
"weight": 20
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Nastavení externího sešitu s aktualizací dat grafu v Java Slides


## Úvod do nastavení externího sešitu s aktualizací dat grafu v Javě Slides

tomto komplexním průvodci vás provedeme procesem nastavení externího sešitu s aktualizovanými daty grafu v Java Slides pomocí rozhraní Aspose.Slides for Java API. Tato výkonná knihovna umožňuje programově manipulovat s prezentacemi PowerPointu, což usnadňuje automatizaci úkolů, jako je aktualizace dat grafu z externího zdroje. Na konci tohoto tutoriálu budete mít jasnou představu o tom, jak tohoto úkolu dosáhnout, a to pomocí podrobných pokynů a doprovodného kódu Java.

## Předpoklady

Než se pustíme do implementace, ujistěte se, že máte splněny následující předpoklady:

1. Aspose.Slides pro Javu: Měli byste mít nainstalovanou knihovnu Aspose.Slides pro Javu. Můžete si ji stáhnout z [zde](https://releases.aspose.com/slides/java/).

2. Vývojové prostředí Java: Ujistěte se, že máte ve svém systému nastavené vývojové prostředí Java.

## Krok 1: Vytvořte novou prezentaci

Pro začátek si vytvořme novou prezentaci v PowerPointu pomocí Aspose.Slides pro Javu. Zde je kód v Javě, který to udělá:

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
```

## Krok 2: Přidání grafu

Nyní si do naší prezentace přidejme graf. V tomto příkladu vytvoříme koláčový graf:

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
```

## Krok 3: Nastavení externího sešitu

Zde nastavíme externí sešit jako zdroj dat pro náš graf. Musíte zadat URL adresu externího sešitu, i když prozatím neexistuje:

```java
IChartData chartData = chart.getChartData();
chartData.setExternalWorkbook("http://cesta/neexistuje", false);
```

## Krok 4: Uložte prezentaci

Nakonec uložte prezentaci s aktualizovanými daty grafu:

```java
pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
```

## Kompletní zdrojový kód pro sadu externího sešitu s aktualizací dat grafu v Javě Slides

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation();
try
{
	IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(ChartType.Pie, 50, 50, 400, 600, true);
	IChartData chartData = chart.getChartData();
	chartData.setExternalWorkbook("http://cesta/neexistuje", false);
	pres.save(dataDir + "SetExternalWorkbookWithUpdateChartData.pptx", SaveFormat.Pptx);
}
finally
{
	if (pres != null) pres.dispose();
}
```

## Závěr

Gratulujeme! Naučili jste se, jak v aplikaci Java Slides nastavit externí sešit s aktualizovanými daty grafu pomocí nástroje Aspose.Slides pro Javu. To může být neuvěřitelně užitečné pro dynamickou aktualizaci grafů v prezentacích PowerPoint z externích zdrojů dat.

## Často kladené otázky

### Jak mohu aktualizovat data externího sešitu pro graf?

Chcete-li aktualizovat data externího sešitu pro graf, stačí upravit data v externím sešitu na zadané adrese URL. Při příštím otevření prezentace Aspose.Slides for Java načte aktualizovaná data z externího sešitu a graf odpovídajícím způsobem aktualizuje.

### Mohu použít lokální soubor jako externí sešit?

Ano, jako externí sešit můžete použít lokální soubor, ale místo adresy URL zadejte cestu k souboru. Ujistěte se však, že cesta k souboru je správná a přístupná z vaší aplikace Java.

### Existují nějaká omezení pro používání externích sešitů s Aspose.Slides pro Javu?

když je používání externích sešitů výkonnou funkcí, mějte na paměti, že dostupnost dat externího sešitu závisí na jejich přístupnosti na zadané adrese URL nebo cestě k souboru. Abyste předešli problémům s načítáním dat, ujistěte se, že je externí zdroj dat při otevření prezentace k dispozici.

### Mohu si po nastavení externího sešitu přizpůsobit vzhled grafu?

Ano, vzhled grafu, včetně jeho názvu, popisků, barev a dalších prvků, si můžete přizpůsobit, a to i po nastavení externího sešitu. Aspose.Slides pro Javu nabízí rozsáhlé možnosti formátování grafů, které vyhoví vašim potřebám.

### Kde najdu další dokumentaci a zdroje pro Aspose.Slides pro Javu?

Podrobnou dokumentaci a další zdroje naleznete v dokumentaci k Aspose.Slides pro Javu na adrese [zde](https://reference.aspose.com/slides/java/).

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}