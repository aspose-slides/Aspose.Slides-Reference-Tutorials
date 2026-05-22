---
date: '2026-03-20'
description: Naučte se, jak přidat seskupený sloupcový graf do prezentace PowerPoint,
  přizpůsobit graf v PowerPointu a vložit graf datové řady pomocí Aspose.Slides pro
  Java.
keywords:
- Grouped Column Chart
- Aspose.Slides for Java
- PowerPoint Presentation
title: Jak přidat seskupený sloupcový graf do PowerPointu pomocí Aspose.Slides pro
  Java
url: /cs/java/charts-graphs/create-grouped-column-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak přidat seskupený sloupcový graf v PowerPointu pomocí Aspose.Slides pro Java

## Úvod

Když potřebujete **přidat seskupený sloupcový graf** do PowerPoint prezentace, jasná vizualizace může proměnit surová čísla v okamžitě pochopitelný příběh. Provádět to ručně v PowerPointu může být časově náročné, zejména když musíte programově generovat mnoho snímků. **Aspose.Slides for Java** odstraňuje tuto překážku – umožňuje vám vytvořit, přizpůsobit PowerPoint graf a vložit datové řady grafu pomocí několika řádků kódu.

V tomto tutoriálu se naučíte, jak:
- Inicializovat novou PowerPoint prezentaci pomocí Aspose.Slides for Java.
- **Přidat graf do snímku** a nakonfigurovat jej jako seskupený sloupcový graf.
- **Vytvořit seskupený sloupcový graf** definováním úrovní seskupení pro kategorie.
- **Vložit datové řady do grafu** tak, aby vaše data byla zobrazena správně.
- Uložit hotovou prezentaci jako soubor PPTX.

Ujistěte se, že máte vše potřebné, než se ponoříme do kódu.

## Rychlé odpovědi
- **Jaká je hlavní třída?** `Presentation` z `com.aspose.slides`.
- **Jaký typ grafu se používá?** `ChartType.ClusteredColumn`.
- **Potřebuji licenci pro testování?** Bezplatná zkušební verze funguje, ale licence odstraňuje omezení hodnocení.
- **Jaká verze Javy je podporována?** JDK 16 nebo novější (příklad používá JDK 16).
- **Jak spustit ukázku?** Přidejte Maven/Gradle závislost, zkompilujte a spusťte metodu `main`.

## Co je „přidat seskupený sloupcový graf“?

*Sesku­pený sloupcový graf* (také nazývaný *skupinový sloupcový graf*) zobrazuje více datových řad vedle sebe pro každou kategorii, což usnadňuje porovnání hodnot mezi skupinami. V PowerPointu je tento typ grafu ideální pro čtvrtletní prodeje, výsledky průzkumů nebo jakýkoli scénář, kde potřebujete kontrastovat několik datových sad v rámci jedné kategorie.

## Proč použít Aspose.Slides k přidání seskupeného sloupcového grafu?

- **Plná automatizace** – generujte desítky snímků bez ruční práce.
- **Detailní přizpůsobení** – ovládejte barvy, popisky, úrovně seskupení a další.
- **Cross‑platform** – funguje na jakémkoli OS, který podporuje Javu.
- **Není vyžadována instalace Office** – generujte soubory PPTX na serverech nebo v CI pipelinech.

## Požadavky

- **Aspose.Slides for Java** knihovna (doporučena nejnovější verze).
- JDK 16 nebo novější.
- Nástroj pro sestavení Maven nebo Gradle (nebo můžete JAR přidat ručně).
- IDE nebo textový editor pro spuštění Java kódu.

## Nastavení Aspose.Slides pro Java

Přidejte knihovnu do svého projektu pomocí jednoho z následujících skriptů pro sestavení.

**Maven**

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativně můžete přímo stáhnout nejnovější verzi z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence

Před nasazením do produkce získáte licenci:
- **Bezplatná zkušební verze** – prozkoumejte všechny funkce bez nákupu.
- **Dočasná licence** – vyzkoušejte rozšířené možnosti na krátkou dobu.
- **Plná licence** – odemkne neomezené používání. Získejte ji na [stránce nákupu Aspose](https://purchase.aspose.com/buy).

## Průvodce implementací

Provedeme vás každým krokem a vysvětlíme **jak přidat graf** a **přizpůsobit PowerPoint graf**.

### Inicializace prezentace

Nejprve vytvořte nový objekt `Presentation` a získejte výchozí snímek.

```java
import com.aspose.slides.*;

// Feature: Initialize Presentation
Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```

### Přidání grafu do snímku

Nyní **přidáme graf do snímku** pomocí typu `ClusteredColumn` a vymažeme veškerá výchozí data.

```java
// Feature: Add Chart to Slide
IChart ch = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.ClusteredColumn, 100, 100, 600, 450);
ch.getChartData().getSeries().clear();
ch.getChartData().getCategories().clear();
```

### Příprava sešitu s daty grafu

Graf ukládá svá data do interního sešitu. Vymažeme jej, abychom začali s čistým stavem.

```java
// Feature: Prepare Chart Data Workbook
IChartDataWorkbook fact = ch.getChartData().getChartDataWorkbook();
fact.clear(0);
int defaultWorksheetIndex = 0;
```

### Přidání kategorií s úrovněmi seskupení

Seskupování kategorií vytváří efekt **skupinového sloupcového grafu**. Každá kategorie může patřit do logické skupiny.

```java
// Feature: Add Categories with Grouping Levels
IChartCategory category = ch.getChartData().getCategories().add(
    fact.getCell(0, "c2", "A"));
category.getGroupingLevels().setGroupingItem(1, "Group1");

category = ch.getChartData().getCategories().add(fact.getCell(0, "c3", "B"));
// Repeat for other categories
```

### Přidání datových řad do grafu

Zde **vkládáme položky datových řad do grafu**, které budou vizualizovány jako samostatné sloupce.

```java
// Feature: Add Data Series to Chart
IChartSeries series = ch.getChartData().getSeries().add(
    fact.getCell(0, "D1", "Series 1"), ChartType.ClusteredColumn);
series.getDataPoints().addDataPointForBarSeries(fact.getCell(defaultWorksheetIndex, "D2", 10));
// Continue adding data points
```

### Uložení prezentace s grafem

Nakonec zapíšeme soubor PPTX na disk.

```java
// Feature: Save Presentation with Chart
pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```

## Praktické aplikace

- **Obchodní zprávy** – porovnejte čtvrtletní výnosy napříč regiony.
- **Akademický výzkum** – zobrazte experimentální výsledky seskupené podle podmínek testu.
- **Projektové řízení** – vizualizujte míru dokončení úkolů pro více týmů na jednom snímku.

## Úvahy o výkonu

- **Správa paměti** – uvolněte velké sešity po použití.
- **Dávkové operace** – vyhněte se aktualizaci grafu uvnitř úzkých smyček; nejprve shromážděte data a pak je aplikujte.
- **Vestavěné optimalizace** – Aspose.Slides poskytuje metody jako `Presentation.optimize()` pro velké soubory.

## Časté úskalí a tipy

- **Úskalí:** Zapomenutí vymazat existující řady/kategorie může vést k duplicitním datům.  
  **Tip:** Vždy zavolejte `clear()` před naplněním nových dat.  

- **Úskalí:** Použití špatné adresy buňky (např. `"c2"` místo `"C2"`).  
  **Tip:** Odkazy na buňky jsou necitlivé na velikost písmen, ale pro čitelnost je udržujte konzistentní.  

- **Tip:** Použijte `setGroupingItem` k vytvoření smysluplných štítků skupin; automaticky se zobrazí v legendě grafu.

## Často kladené otázky

**Q1: Jak mohu přidat více řad do mého grafu?**  
A1: Opakovaně volajte `ch.getChartData().getSeries().add()`, přičemž každé řadě přiřadíte jedinečný název a datové body.

**Q2: Jaké jsou některé běžné problémy s grafy Aspose.Slides?**  
A2: Problémy často vznikají z nesouladu datových rozsahů nebo chybějících buněk sešitu. Ověřte, že každá kategorie a datový bod má odpovídající buňku.

**Q3: Mohu použít Aspose.Slides s jinými programovacími jazyky?**  
A3: Ano, Aspose poskytuje ekvivalentní knihovny pro .NET, C++, Python a další.

**Q4: Jak aktualizuji existující graf v prezentaci?**  
A4: Načtěte prezentaci, najděte graf pomocí `slide.getShapes().get_Item(index)`, a poté upravte jeho řady nebo formátování podle potřeby.

**Q5: Existují omezení typů grafů v Aspose.Slides?**  
A5: Knihovna podporuje širokou škálu typů grafů, ale vždy zkontrolujte nejnovější dokumentaci pro případ nově přidaných nebo zastaralých typů.

## Zdroje

- **Documentation**: [Aspose.Slides Reference](https://reference.aspose.com/slides/java/)
- **Download**: [Latest Releases](https://releases.aspose.com/slides/java/)
- **Purchase**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)
- **Free Trial**: [Start Your Free Trial](https://releases.aspose.com/slides/java/)
- **Temporary License**: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- **Support Forum**: [Aspose Support](https://forum.aspose.com/c/slides/11)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**Poslední aktualizace:** 2026-03-20  
**Testováno s:** Aspose.Slides for Java 25.4 (JDK 16)  
**Autor:** Aspose