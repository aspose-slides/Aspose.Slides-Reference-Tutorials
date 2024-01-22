---
title: Upravit data grafu v externím sešitu v Java Slides
linktitle: Upravit data grafu v externím sešitu v Java Slides
second_title: Aspose.Slides Java PowerPoint Processing API
description: Naučte se upravovat data grafu v externím sešitu pomocí Aspose.Slides for Java. Průvodce krok za krokem se zdrojovým kódem.
type: docs
weight: 17
url: /cs/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/
---

## Úvod do úprav dat grafu v externím sešitu v Java Slides

této příručce si ukážeme, jak upravit data grafu v externím sešitu pomocí Aspose.Slides for Java. Dozvíte se, jak programově upravit data grafu v prezentaci PowerPoint. Ujistěte se, že máte v projektu nainstalovanou a nakonfigurovanou knihovnu Aspose.Slides pro Javu.

## Předpoklady

- Aspose.Slides pro Javu
- Vývojové prostředí Java

## Krok 1: Načtěte prezentaci

 Nejprve musíme načíst prezentaci PowerPoint, která obsahuje graf, jehož data chceme upravit. Nahradit`"Your Document Directory"` se skutečnou cestou k souboru vaší prezentace.

```java
// Cesta k adresáři dokumentů.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Krok 2: Přístup k grafu

Po načtení prezentace potřebujeme získat přístup k grafu v prezentaci. V tomto příkladu předpokládáme, že graf je na prvním snímku a je prvním obrazcem na tomto snímku.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Krok 3: Upravte data grafu

Nyní upravme data grafu. Zaměříme se na změnu konkrétního datového bodu v grafu. V tomto příkladu nastavíme hodnotu prvního datového bodu v první řadě na 100. Tuto hodnotu můžete upravit podle potřeby.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Krok 4: Uložte prezentaci

Po provedení nezbytných změn v datech grafu uložte upravenou prezentaci do nového souboru. Můžete zadat cestu a formát výstupního souboru podle svých požadavků.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Krok 5: Vyčištění

Nezapomeňte zlikvidovat objekt prezentace, abyste uvolnili jakékoli zdroje.

```java
if (pres != null) pres.dispose();
```

Nyní jste úspěšně upravili data grafu v externím sešitu v rámci prezentace PowerPoint pomocí Aspose.Slides for Java. Tento kód můžete přizpůsobit svým specifickým potřebám a integrovat jej do svých aplikací Java.

## Kompletní zdrojový kód

```java
        // Věnujte pozornost tomu, že cesta k externímu sešitu se v prezentaci téměř neukládá
        // takže před spuštěním příkladu zkopírujte soubor externalWorkbook.xlsx z adresáře Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\
        // Cesta k adresáři dokumentů.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save(RunExamples.getOutPath() + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Závěr

tomto komplexním průvodci jsme prozkoumali, jak upravit data grafu v externích sešitech v rámci prezentací PowerPoint pomocí Aspose.Slides for Java. Dodržováním podrobných pokynů a příkladů zdrojového kódu jste získali znalosti a dovednosti, jak snadno programově upravovat data grafu.

## FAQ

### Jak určím jiný graf nebo snímek?

 Chcete-li získat přístup k jinému grafu nebo snímku, upravte příslušný index v souboru`getSlides().get_Item()` a`getShapes().get_Item()` metody. Pamatujte, že indexování začíná od 0.

### Mohu upravovat data ve více grafech v rámci jedné prezentace?

Ano, můžete upravit data ve více grafech v rámci stejné prezentace opakováním kroků úpravy dat grafu pro každý graf.

### Co když chci upravit data v externím sešitu v jiném formátu?

Pomocí příslušných tříd a metod Aspose.Cells pro čtení a zápis dat v tomto formátu můžete upravit kód tak, aby zpracovával různé formáty externích sešitů.

### Jak mohu automatizovat tento proces pro více prezentací?

Můžete vytvořit smyčku pro zpracování více prezentací, načíst každou z nich, provést požadované změny a uložit upravené prezentace jednu po druhé.