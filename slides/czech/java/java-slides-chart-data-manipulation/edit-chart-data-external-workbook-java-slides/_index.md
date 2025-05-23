---
"description": "Naučte se, jak upravovat data grafu v externím sešitu pomocí Aspose.Slides pro Javu. Podrobný návod se zdrojovým kódem."
"linktitle": "Úprava dat grafu v externím sešitu v aplikaci Java Slides"
"second_title": "API pro zpracování PowerPointu v Javě Aspose.Slides"
"title": "Úprava dat grafu v externím sešitu v aplikaci Java Slides"
"url": "/cs/java/chart-data-manipulation/edit-chart-data-external-workbook-java-slides/"
"weight": 17
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}

# Úprava dat grafu v externím sešitu v aplikaci Java Slides


## Úvod do úpravy dat grafu v externím sešitu v Javě (prezentace)

V této příručce si ukážeme, jak upravovat data grafu v externím sešitu pomocí knihovny Aspose.Slides pro Javu. Naučíte se, jak programově upravovat data grafu v prezentaci PowerPoint. Ujistěte se, že máte ve svém projektu nainstalovanou a nakonfigurovanou knihovnu Aspose.Slides pro Javu.

## Předpoklady

- Aspose.Slides pro Javu
- Vývojové prostředí v Javě

## Krok 1: Načtení prezentace

Nejprve musíme načíst prezentaci PowerPointu, která obsahuje graf, jehož data chceme upravit. Nahraďte `"Your Document Directory"` se skutečnou cestou k souboru prezentace.

```java
// Cesta k adresáři s dokumenty.
String dataDir = "Your Document Directory";
Presentation pres = new Presentation(dataDir + "presentation.pptx");
```

## Krok 2: Přístup k grafu

Jakmile je prezentace načtena, potřebujeme přistupovat k grafu v rámci prezentace. V tomto příkladu předpokládáme, že graf je na prvním snímku a je prvním tvarem na tomto snímku.

```java
IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
```

## Krok 3: Úprava dat grafu

Nyní upravme data grafu. Zaměříme se na změnu konkrétního datového bodu v grafu. V tomto příkladu jsme nastavili hodnotu prvního datového bodu v první sérii na 100. Tuto hodnotu můžete dle potřeby upravit.

```java
ChartData chartData = (ChartData) chart.getChartData();
chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
```

## Krok 4: Uložte prezentaci

Po provedení potřebných změn v datech grafu uložte upravenou prezentaci do nového souboru. Cestu k výstupnímu souboru a formát můžete zadat podle svých požadavků.

```java
pres.save("output.pptx", SaveFormat.Pptx);
```

## Krok 5: Úklid

Nezapomeňte zlikvidovat prezentační objekt, abyste uvolnili veškeré prostředky.

```java
if (pres != null) pres.dispose();
```

Nyní jste úspěšně upravili data grafu v externím sešitu v rámci vaší prezentace v PowerPointu pomocí Aspose.Slides pro Javu. Tento kód si můžete přizpůsobit svým specifickým potřebám a integrovat ho do svých aplikací v Javě.

## Kompletní zdrojový kód

```java
        // Věnujte pozornost tomu, že cesta k externímu sešitu se v prezentaci téměř neukládá.
        // Před spuštěním příkladu prosím zkopírujte soubor externalWorkbook.xlsx z adresáře Data/Chart D:\Aspose.Slides\Aspose.Slides-for-.NET-master\Examples\Data\Charts\
        // Cesta k adresáři s dokumenty.
        String dataDir = "Your Document Directory";
        Presentation pres = new Presentation(dataDir + "presentation.pptx");
        try
        {
            IChart chart = (IChart) pres.getSlides().get_Item(0).getShapes().get_Item(0);
            ChartData chartData = (ChartData) chart.getChartData();
            chartData.getSeries().get_Item(0).getDataPoints().get_Item(0).getValue().getAsCell().setValue(100);
            pres.save("Your Output Directory" + "presentation_out.pptx", SaveFormat.Pptx);
        }
        finally
        {
            if (pres != null) pres.dispose();
        }
```
## Závěr

V této komplexní příručce jsme prozkoumali, jak upravovat data grafů v externích sešitech v rámci prezentací PowerPointu pomocí Aspose.Slides pro Javu. Dodržováním podrobných pokynů a příkladů zdrojového kódu jste získali znalosti a dovednosti pro snadnou programovou úpravu dat grafů.

## Často kladené otázky

### Jak mohu určit jiný graf nebo snímek?

Chcete-li zobrazit jiný graf nebo snímek, upravte příslušný index v `getSlides().get_Item()` a `getShapes().get_Item()` metody. Nezapomeňte, že indexování začíná od 0.

### Mohu upravovat data ve více grafech v rámci jedné prezentace?

Ano, data ve více grafech v rámci jedné prezentace můžete upravovat opakováním kroků úpravy dat grafu pro každý graf.

### Co když chci upravit data v externím sešitu s jiným formátem?

Kód můžete upravit pro zpracování různých formátů externích sešitů pomocí příslušných tříd a metod Aspose.Cells pro čtení a zápis dat v tomto formátu.

### Jak mohu tento proces automatizovat pro více prezentací?

Můžete vytvořit smyčku pro zpracování více prezentací, načíst každou z nich, provést požadované změny a uložit upravené prezentace jednu po druhé.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}