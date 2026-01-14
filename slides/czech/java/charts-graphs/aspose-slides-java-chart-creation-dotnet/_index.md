---
date: '2026-01-14'
description: Naučte se, jak přidat seskupený sloupcový graf a vložit jej do snímku
  v .NET prezentacích pomocí Aspose.Slides pro Java. Postupujte podle tohoto krok‑za‑krokem
  průvodce s kompletními ukázkami kódu.
keywords:
- Aspose.Slides for Java
- .NET presentations
- charts in .NET
title: Přidat seskupený sloupcový graf do .NET prezentací Aspose.Slides Java
url: /cs/java/charts-graphs/aspose-slides-java-chart-creation-dotnet/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytváření grafů v .NET prezentacích pomocí Aspose.Slides pro Java
## Úvod
Vytváření poutavých prezentací často zahrnuje integraci vizuálních datových reprezentací, jako jsou grafy, které zvyšují porozumění a zapojení publika. Pokud jste vývojář, který chce do svých .NET prezentací pomocí Aspose.Slides pro Java přidat dynamické, přizpůsobitelné grafy, tento tutoriál je určen právě pro vás. Prozkoumáme, jak můžete inicializovat prezentace, přidávat různé typy grafů, spravovat data grafu a efektivně formátovat data řad.

**Co se naučíte:**
- Jak nastavit a používat Aspose.Slides pro Java ve vašem .NET prostředí.
- Inicializace nové prezentace pomocí Aspose.Slides.
- Přidávání a přizpůsobení grafů v slidech.
- Správa sešitů s daty grafu.
- Formátování dat řad, zejména zacházení s negativními hodnotami.

Přechod do sekce požadavků zajistí, že budete připraveni snadno sledovat postup.

## Rychlé odpovědi
- **Jaký je hlavní cíl?** Přidat seskupený sloupcový graf do .NET slidu.
- **Která knihovna je vyžadována?** Aspose.Slides pro Java (v25.4+).
- **Mohu ji použít v .NET projektu?** Ano – Java knihovna funguje přes most Java‑to‑.NET.
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je vyžadována komerční licence.
- **Jak dlouho trvá implementace?** Přibližně 10‑15 minut pro základní graf.

## Co je seskupený sloupcový graf?
Seskupený sloupcový graf zobrazuje více datových řad vedle sebe pro každou kategorii, což usnadňuje porovnání hodnot mezi skupinami. Tento vizuál je ideální pro obchodní dashboardy, výkonnostní zprávy a jakýkoli scénář, kde potřebujete kontrastovat několik metrik.

## Proč přidat graf do slidu pomocí Aspose.Slides pro Java?
Použití Aspose.Slides vám umožní generovat, upravovat a ukládat prezentace bez nainstalovaného Microsoft PowerPointu. Poskytuje plnou kontrolu nad typy grafů, daty a stylováním, což znamená, že můžete automatizovat generování reportů přímo z vašich .NET aplikací.

## Požadavky
Než se pustíte do vytváření grafů pomocí Aspose.Slides pro Java, shrňme, co potřebujete:

### Požadované knihovny a verze
- **Aspose.Slides pro Java**: Verze 25.4 nebo novější.

### Požadavky na nastavení prostředí
- Vývojové prostředí podporující .NET aplikace.
- Základní pochopení konceptů programování v Javě.

### Předpoklady znalostí
- Znalost vytváření prezentací v kontextu .NET aplikací.
- Porozumění závislostem Javy a jejich správě (Maven/Gradle).

## Nastavení Aspose.Slides pro Java
Abyste mohli začít používat Aspose.Slides, musíte jej zahrnout jako závislost do svého projektu. Zde je návod, jak to provést:

### Maven
Přidejte následující závislost do souboru `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Zahrňte toto do souboru `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Alternativně můžete stáhnout nejnovější verzi z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Kroky získání licence
- **Free Trial**: Začněte s dočasnou licencí pro prozkoumání funkcí.
- **Purchase**: Zvažte zakoupení licence pro rozsáhlé používání.

#### Základní inicializace a nastavení
Zde je, jak inicializovat Aspose.Slides ve vašem kódu:
```java
import com.aspose.slides.Presentation;
// Initialize a new Presentation object
Presentation pres = new Presentation();
try {
    // Your logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
Toto nastavení zajišťuje efektivní správu prostředků.

## Průvodce implementací
Provedeme vás implementací funkcí krok za krokem.

### Inicializace prezentace
**Přehled:** Vytvoření instance prezentace připraví podmínky pro všechny následné operace. Tato funkce ukazuje, jak začít od nuly pomocí Aspose.Slides.

#### Krok 1: Import potřebných balíčků
```java
import com.aspose.slides.Presentation;
```

#### Krok 2: Vytvoření nového objektu Presentation
Zde je, jak to provést:
```java
Presentation pres = new Presentation();
try {
    // Your code logic here...
} finally {
    if (pres != null) pres.dispose(); // Ensures resources are freed
}
```
*Tím se zajistí, že objekt prezentace je po použití řádně uvolněn, což zabraňuje únikům paměti.*

### Přidání grafu do slidu
**Přehled:** Přidání grafu do vašeho slidu může učinit vizualizaci dat efektivnější a poutavější.

#### Krok 1: Import potřebných balíčků
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.ISlide;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
```

#### Krok 2: Inicializace prezentace a přidání grafu
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    // Additional logic for chart customization...
} finally {
    if (pres != null) pres.dispose();
}
```
*Zde přidáváme seskupený sloupcový graf na první slide na zadaných souřadnicích a rozměrech.*

### Správa sešitu s daty grafu
**Přehled:** Efektivní správa sešitu s daty vašeho grafu vám umožní plynule manipulovat s řadami a kategoriemi.

#### Krok 1: Import potřebných balíčků
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.IChartDataWorkbook;
```

#### Krok 2: Přístup a vymazání sešitu s daty
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing data
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Your customization logic here...
} finally {
    if (pres != null) pres.dispose();
}
```
*Vymazání sešitu je klíčové pro zahájení s čistým štítem při přidávání nových řad a kategorií.*

### Přidání řad a kategorií do grafu
**Přehled:** Tato funkce ukazuje, jak můžete přidávat smysluplné datové body spravováním řad a kategorií.

#### Krok 1: Přidání řad a kategorií
```java
Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Clear existing series and categories
    chart.getChartData().getSeries().clear();
    chart.getChartData().getCategories().clear();

    // Add new series and categories
    chart.getChartData().getSeries().add(workBook.getCell(0, 0, 1, "Series 1"), chart.getType());
    chart.getChartData().getCategories().add(workBook.getCell(0, 1, 0, "Category 1"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 2, 0, "Category 2"));
    chart.getChartData().getCategories().add(workBook.getCell(0, 3, 0, "Category 3"));

    // Further customization logic...
} finally {
    if (pres != null) pres.dispose();
}
```
*Přidání řad a kategorií umožňuje organizovanější prezentaci dat.*

### Naplnění dat řad a formátování
**Přehled:** Naplňte svůj graf datovými body a formátujte vzhled pro zvýšení čitelnosti, zejména při práci s negativními hodnotami.

#### Krok 1: Naplnění dat řad
```java
import com.aspose.slides.Presentation;
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;
import com.aspose.slides.Color;
import com.aspose.slides.FillType;
import com.aspose.slides.SaveFormat;

Presentation pres = new Presentation();
try {
    ISlide slide = pres.getSlides().get_Item(0);
    IChart chart = slide.getShapes().addChart(ChartType.ClusteredColumn, 100, 100, 400, 300);

    IChartDataWorkbook workBook = chart.getChartData().getChartDataWorkbook();

    // Add series and categories (reuse previous logic)
    
    IChartSeries series = chart.getChartData().getSeries().get_Item(0);
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 1, 1, -20));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 2, 1, 30));
    series.getDataPoints().addDataPointForBarSeries(workBook.getCell(0, 3, 1, 10));

    // Format series for negative values
    series.getFormat().getFill().setFillType(FillType.Solid);
    series.getFormat().getLine().getFillFormat().setFillType(FillType.NoFill);
    
    Color positiveColor = Color.GREEN;
    Color negativeColor = Color.RED;
    for (IDataPoint dataPoint : series.getDataPoints()) {
        if (((Number)dataPoint.getValue()).doubleValue() < 0) {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(negativeColor);
        } else {
            dataPoint.getFormat().getFill().setFillType(FillType.Solid);
            dataPoint.getFormat().getFill().getSolidFillColor().setColor(positiveColor);
        }
    }

    // Save the presentation
    pres.save("output.pptx", SaveFormat.Pptx);
} finally {
    if (pres != null) pres.dispose();
}
```
*Tato sekce ukazuje, jak naplnit data a aplikovat barevné formátování pro lepší vizualizaci.*

## Časté problémy a řešení
- **Memory leaks:** Vždy zavolejte `dispose()` na objektu `Presentation` v bloku `finally`.
- **Incorrect chart type:** Ujistěte se, že používáte `ChartType.ClusteredColumn`, když chcete seskupený sloupcový graf; jiné typy vytvoří odlišné vizuální výsledky.
- **Negative value colors not applied:** Ověřte, že hodnota `IDataPoint` je před porovnáním správně přetypována na `Number`.

## Často kladené otázky

**Q: Mohu použít Aspose.Slides pro Java v čistém .NET projektu bez Javy?**  
A: Ano. Knihovna funguje přes most Java‑to‑.NET, což vám umožní volat Java API z .NET jazyků.

**Q: Podporuje bezplatná zkušební verze vytváření grafů?**  
A: Zkušební verze obsahuje plnou funkčnost grafů, ale vygenerované soubory obsahují malé hodnotící vodoznak.

**Q: Které verze .NET jsou kompatibilní?**  
A: Jakákoli verze .NET, která může interoperovat s Java 16+, včetně .NET Framework 4.6+, .NET Core 3.1+ a .NET 5/6/7.

**Q: Jak zvládnout velké prezentace s mnoha grafy?**  
A: Opakovaně používejte stejnou instanci `IChartDataWorkbook`, kde je to možné, a každou `Presentation` rychle uvolněte, aby se uvolnila paměť.

**Q: Je možné exportovat graf jako obrázek?**  
A: Ano. Použijte metody `chart.getImage()` nebo `chart.exportChartImage()` k získání PNG/JPEG reprezentací.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-01-14  
**Testováno s:** Aspose.Slides pro Java 25.4  
**Autor:** Aspose