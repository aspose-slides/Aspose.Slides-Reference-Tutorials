---
date: '2026-08-21'
description: Naučte se, jak vytvořit box plot v Javě pomocí Aspose.Slides, přidat
  graf do snímku a vygenerovat box‑and‑whisker graf v PowerPointu. Ideální pro vývojáře
  Java.
keywords:
- create box plot java
- java add chart slide
- Aspose.Slides for Java
lastmod: '2026-08-21'
og_description: Naučte se, jak vytvořit box plot v Javě pomocí Aspose.Slides, přidat
  graf do snímku a vygenerovat box‑and‑whisker graf v PowerPointu. Ideální pro vývojáře
  Java.
og_image_alt: 'Developer guide: create box plot java with Aspose.Slides in PowerPoint'
og_title: Jak vytvořit box plot v Javě pomocí Aspose.Slides pro PowerPoint
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  headline: How to create box plot java with Aspose.Slides for PowerPoint
  type: TechArticle
- description: Learn how to create box plot java using Aspose.Slides, add chart to
    slide, and generate a box‑and‑whisker chart in PowerPoint. Ideal for Java developers.
  name: How to create box plot java with Aspose.Slides for PowerPoint
  steps:
  - name: create or open a presentation
    text: 'First, open an existing PPTX or start a new one: > **Pro tip:** If the
      file doesn’t exist, Aspose.Slides will automatically create a new blank presentation.'
  - name: add a box‑and‑whisker chart to the slide
    text: 'Place the chart where you need it by specifying the position and size (in
      points):'
  - name: clear existing data
    text: 'Before feeding new data, wipe any placeholder categories or series:'
  - name: configure categories
    text: 'Add the categories (X‑axis labels) that will appear under each box: > **Note:**
      Adjust the label text to match your data domain (e.g., “Q1”, “Product A”).'
  - name: create and customize the series
    text: 'Now create a series, set visual options, and feed the numeric data points:
      You can replace the `int[] data` array with values read from a database, CSV
      file, or any other source.'
  - name: save the presentation
    text: 'Persist the changes to a new PPTX file:'
  - name: clean up resources
    text: 'Always dispose of the `Presentation` object to free native resources:'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java.
    question: What library creates a box plot in Java?
  - answer: '`ChartType.BoxAndWhisker`.'
    question: Which chart type is used?
  - answer: A free trial works for evaluation; a commercial license is required for
      production.
    question: Do I need a license?
  - answer: Yes – repeat the series‑creation block for each data set.
    question: Can I add multiple series?
  - answer: PowerPoint PPTX (`SaveFormat.Pptx`).
    question: What format is the final file?
  type: FAQPage
tags:
- box plot java
- Aspose.Slides
- PowerPoint chart Java
- box-and-whisker
- Java data visualization
title: Jak vytvořit box plot v Javě pomocí Aspose.Slides pro PowerPoint
url: /cs/java/charts-graphs/create-box-and-whisker-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit krabicový diagram v Javě pomocí Aspose.Slides pro PowerPoint

V tomto průvodci **vytvoříte krabicový diagram v Javě** pomocí Aspose.Slides a poté vložíte graf přímo do snímku PowerPointu. Programatické generování krabicových a vousatých grafů vám umožní převést surová statistická data na přehledné vizuální informace, aniž byste opustili svůj Java kód. Pokud potřebujete automatizovat reportování v PowerPointu, Aspose.Slides pro Java poskytuje spolehlivé a výkonné API.

## Co se naučíte

- Nastavení prostředí pro Aspose.Slides pro Java
- Kroky k **přidání grafu do snímku** a generování krabicového grafu v PowerPointu pomocí Javy
- Nejlepší postupy pro optimalizaci výkonu při práci s Aspose.Slides
- Reálné aplikace krabicových a vousatých grafů

## Rychlé odpovědi
- **Která knihovna vytváří krabicový diagram v Javě?** Aspose.Slides pro Java.  
- **Jaký typ grafu se používá?** `ChartType.BoxAndWhisker`.  
- **Potřebuji licenci?** Bezplatná zkušební verze funguje pro hodnocení; pro produkci je vyžadována komerční licence.  
- **Mohu přidat více řad?** Ano – opakujte blok pro vytvoření řady pro každý datový soubor.  
- **Jaký je formát konečného souboru?** PowerPoint PPTX (`SaveFormat.Pptx`).  

## Co je krabicový diagram a proč jej použít v Javě?

Krabicový a vousatý graf (často nazývaný *box plot*) vizualizuje rozdělení dat – medián, kvartily a odlehlé hodnoty – v kompaktní formě. V Javě vám programatické generování tohoto grafu umožní vložit statistické poznatky přímo do PowerPointových prezentací, čímž eliminuje ruční tvorbu grafů. Je zvláště užitečný pro porovnání rozdělení napříč více kategoriemi, jako jsou výsledky testů ve třídách nebo prodejní čísla v regionech. Generováním grafu v Javě jej můžete integrovat do automatizovaných reportovacích pipeline, což zajišťuje, že nejnovější data jsou vždy odrážena ve vašich prezentacích.

## Proč přidat graf do snímku pomocí Aspose.Slides?

Aspose.Slides abstrahuje nízkoúrovňové detaily OpenXML a poskytuje plynulé API pro vytváření, stylizaci a export grafů. To vám umožní automatizovat generování reportů, zajistit konzistentní branding a integrovat grafy do širších Java workflow. Knihovna také podporuje možnosti stylování jako barvy, písma a značky, což vám umožní sladit graf s firemní identitou. Navíc se stará o složité úkoly jako vazba dat a aktualizace grafu bez nutnosti instalace Microsoft Office.

## Jak v Javě přidat graf na snímek s Aspose.Slides?

Načtěte nebo vytvořte `Presentation`, vložte `Chart` typu `BoxAndWhisker`, naplňte data a soubor uložte – vše během několika řádků Javy. API se postará o rozvržení, škálování a vykreslování, takže nemusíte manipulovat s XML sami. Můžete také programově nastavit názvy grafu a popisky os, aby poskytovaly kontext pro diváky.

## Požadavky

- **Java Development Kit (JDK)**: JDK 8 nebo vyšší.  
- **Aspose.Slides pro Java knihovna**: Vyžadována pro manipulaci s PowerPointem.  
- **IDE**: IntelliJ IDEA, Eclipse nebo jakýkoli editor kompatibilní s Javou.

## Nastavení Aspose.Slides pro Java

Přidejte knihovnu jako Maven, Gradle nebo ruční závislost.

### Maven

Přidejte následující závislost do svého `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle

Ve svém `build.gradle` zahrňte:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení

Alternativně stáhněte nejnovější verzi z [vydání Aspose.Slides pro Java](https://releases.aspose.com/slides/java/).

#### Získání licence

- **Bezplatná zkušební verze** – prozkoumejte funkce bez nákladů.  
- **Dočasná licence** – použijte pro krátkodobé hodnocení.  
- **Koupě** – odemkněte plnou funkčnost pro produkční úlohy.

Pro inicializaci Aspose.Slides se ujistěte, že je JAR na classpath a nastavte licenční soubor podle dokumentace.

## Průvodce implementací

Níže je podrobný průvodce krok za krokem. Každý blok je vysvětlen před úryvkem, abyste přesně věděli, co dělá.

### Co je třída `Presentation`?

Třída `Presentation` je centrální objekt v Aspose.Slides, který představuje celý PowerPoint soubor v paměti. Poskytuje přístup ke snímkům, grafům, tvarům a dalším prvkům, umožňuje vytvářet, upravovat a ukládat prezentace programově. Pomocí této třídy můžete přidávat nové snímky, vkládat obrázky a měnit pořadí snímků jednoduchými voláními API.

### Krok 1: vytvořit nebo otevřít prezentaci

Nejprve otevřete existující PPTX nebo začněte novou:

```java
Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/test.pptx");
```

> **Tip:** Pokud soubor neexistuje, Aspose.Slides automaticky vytvoří novou prázdnou prezentaci.

### Krok 2: přidat krabicový a vousatý graf do snímku

Umístěte graf tam, kde jej potřebujete, zadáním pozice a velikosti (v bodech):

```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.BoxAndWhisker, 50, 50, 500, 400);
```

### Krok 3: vymazat existující data

Před vložením nových dat odstraňte veškeré placeholder kategorie nebo řady:

```java
chart.getChartData().getCategories().clear();
chart.getChartData().getSeries().clear();

IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
wb.clear(0); // Clears content starting from cell "A1"
```

### Krok 4: nakonfigurovat kategorie

Přidejte kategorie (popisky os X), které se objeví pod každou krabičkou:

```java
for (int i = 1; i <= 6; i++) {
    chart.getChartData().getCategories()
        .add(wb.getCell(0, "A" + i, "Category 1"));
}
```

> **Poznámka:** Přizpůsobte text popisků tak, aby odpovídal vašemu datovému doménu (např. „Q1“, „Produkt A“).

### Krok 5: vytvořit a přizpůsobit řadu

Nyní vytvořte řadu, nastavte vizuální možnosti a vložte číselné datové body:

```java
IChartSeries series = chart.getChartData().getSeries().add(ChartType.BoxAndWhisker);
series.setQuartileMethod(QuartileMethodType.Exclusive); // Set quartile method to Exclusive
series.setShowMeanLine(true); // Display mean line
series.setShowMeanMarkers(true); // Show markers for mean values
series.setShowInnerPoints(true); // Display inner points on the chart
series.setShowOutlierPoints(true); // Show outlier points on the chart

int[] data = {15, 41, 16, 10, 23, 16}; // Sample data points
for (int i = 0; i < data.length; i++) {
    series.getDataPoints().addDataPointForBoxAndWhiskerSeries(
        wb.getCell(0, "B" + (i + 1), data[i]));
}
```

Můžete nahradit pole `int[] data` hodnotami načtenými z databáze, CSV souboru nebo jiného zdroje.

### Krok 6: uložit prezentaci

Uložte změny do nového PPTX souboru:

```java
pres.save("YOUR_OUTPUT_DIRECTORY/BoxAndWhisker.pptx", SaveFormat.Pptx);
```

### Krok 7: uvolnit prostředky

Vždy uvolněte objekt `Presentation`, aby se uvolnily nativní zdroje:

```java
finally {
    if (pres != null) pres.dispose();
}
```

## Praktické aplikace

Krabicové a vousaté grafy jsou neocenitelné ve statistické analýze a prezentaci dat. Zde je několik scénářů, kde vynikají:

1. **Finanční analýza** – vizualizovat rozdělení příjmů napříč regiony.  
2. **Kontrola kvality** – odhalit odlehlé hodnoty ve výrobních měřeních.  
3. **Akademický výzkum** – zobrazit variabilitu experimentálních výsledků.  
4. **Marketingový výzkum** – porovnat výkonnost produktů napříč demografickými skupinami.

Vkládáním těchto grafů přímo do PowerPointových prezentací umožníte zainteresovaným stranám rychle pochopit složitá data na první pohled.

## Úvahy o výkonu

Aspose.Slides dokáže zpracovat prezentace s **500+ snímky** a grafy s **100 000+ datovými body**, přičemž spotřeba paměti zůstává pod 200 MB na typickém serveru. Pro zůstání v těchto mezích:

- **Správa paměti** – rychle uvolňovat objekty `Presentation`.  
- **Zpracování dat** – načítejte jen potřebná data; vyhněte se přímému vkládání obrovských datových sad do sešitu grafu.  
- **Líné načítání** – při generování mnoha snímků vytvářejte grafy jen pro ty, které budou zobrazeny.

## Časté problémy a řešení

| Problém | Příčina | Řešení |
|-------|-------|----------|
| **Graf je prázdný** | Buňky dat nejsou správně naplněny | Ověřte, že `wb.getCell` odkazuje na správný řádek/sloupec a že hodnota není `null`. |
| **Outliery nejsou zobrazeny** | `setShowOutlierPoints` nastaveno na `false` | Ujistěte se, že je voláno `series.setShowOutlierPoints(true)`. |
| **Únik paměti** | Prezentace není uvolněna | Vždy obalte použití do `try/finally` a zavolejte `dispose()`. |
| **Nesprávné kvartily** | Použití výchozí metody `Inclusive` | Přepněte na `Exclusive` pomocí `setQuartileMethod(QuartileMethodType.Exclusive)`. |

## Často kladené otázky

**Q1: Co je krabicový a vousatý graf?**  
Krabicový a vousatý graf, také známý jako box plot, zobrazuje rozdělení dat na základě pěti souhrnných statistik: minimum, první kvartil, medián, třetí kvartil a maximum, plus případné odlehlé hodnoty.

**Q2: Mohu přizpůsobit vzhled krabicového a vousatého grafu?**  
Ano. Aspose.Slides vám umožní měnit barvy, styly čar, tvary značek a přidávat popisky dat prostřednictvím formátovacího API grafu.

**Q3: Je možné v jednom grafu zpracovat více řad?**  
Rozhodně. Opakujte blok pro vytvoření řady pro každý datový soubor, který chcete vizualizovat.

**Q4: Jak vyřešit problémy s nesprávným zobrazováním dat?**  
Ujistěte se, že jsou data správně zapsána do buněk sešitu a že jsou povoleny viditelnostní vlastnosti jako `setShowMeanLine`.

**Q5: Kde mohu získat podporu, pokud narazím na problémy?**  
Navštivte [Aspose.Slides forum](https://forum.aspose.com/c/slides/11) pro komunitní pomoc nebo konzultujte oficiální dokumentaci.

**Q6: Podporuje Aspose.Slides jiné typy grafů?**  
Ano, podporuje více než 50 typů grafů – včetně čárových, sloupcových, koláčových, rozptylových, radarových a trychtýřových – takže si můžete vybrat nejlepší vizualizaci pro svá data.

**Q7: Mohu generovat grafy v prostředí serveru bez UI?**  
Knihovna funguje plně v serverových scénářích; není vyžadována žádná UI ani instalace Microsoft Office.

## Zdroje

- **Dokumentace**: Prozkoumejte podrobné reference API na [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Stáhnout**: Přístup na stránku vydání Aspose.Slides [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)  
- **Nákup**: Kupte licenci pro odemknutí všech funkcí [Aspose Purchase](https://purchase.aspose.com/buy)  
- **Bezplatná zkušební verze a dočasná licence**: Začněte s bezplatnou zkušební verzí nebo požádejte o dočasnou licenci [Aspose.Slides releases page](https://releases.aspose.com/slides/java/)

Postupováním podle tohoto průvodce jste nyní připraveni programově generovat přehledné krabicové a vousaté grafy ve svých Java aplikacích a vkládat je přímo do PowerPointových prezentací. Šťastné programování!

---

**Poslední aktualizace:** 2026-08-21  
**Testováno s:** Aspose.Slides 25.4 (JDK 16 classifier)  
**Autor:** Aspose

## Související tutoriály

- [Jak přidat graf do PowerPointu pomocí Aspose.Slides pro Java: krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java: vytvořit graf v PowerPointu pomocí Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Přidat animaci do grafu PowerPointu pomocí Aspose.Slides pro Java – krok za krokem](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}