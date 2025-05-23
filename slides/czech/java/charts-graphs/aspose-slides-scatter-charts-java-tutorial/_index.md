---
"date": "2025-04-17"
"description": "Naučte se, jak vytvářet dynamické bodové grafy pomocí Aspose.Slides pro Javu. Vylepšete své prezentace pomocí přizpůsobitelných funkcí grafů."
"title": "Vytvářejte a upravujte bodové grafy v Javě pomocí Aspose.Slides"
"url": "/cs/java/charts-graphs/aspose-slides-scatter-charts-java-tutorial/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvářejte a upravujte bodové grafy v Javě pomocí Aspose.Slides

Vylepšete své prezentace přidáním dynamických bodových grafů pomocí Javy s Aspose.Slides. Tento komplexní tutoriál vás provede nastavením adresářů, inicializací prezentací, vytvářením bodových grafů, správou dat grafů, přizpůsobením typů řad a značek a uložením vaší práce – to vše s lehkostí.

**Co se naučíte:**
- Nastavení adresáře pro ukládání souborů prezentací
- Inicializace a manipulace s prezentacemi pomocí Aspose.Slides
- Vytváření bodových grafů na snímcích
- Správa a přidávání dat do grafických řad
- Přizpůsobení typů a značek řad grafů
- Uložení prezentace s úpravami

Začněme tím, že se ujistíme, že máte potřebné předpoklady.

## Předpoklady

Abyste mohli postupovat podle tohoto tutoriálu, ujistěte se, že máte:
- **Aspose.Slides pro Javu**Je vyžadována verze 25.4 nebo novější.
- **Vývojová sada pro Javu (JDK)**Je vyžadován JDK 8 nebo vyšší.
- Základní znalost programování v Javě a znalost sestavovacích nástrojů Maven nebo Gradle.

## Nastavení Aspose.Slides pro Javu

Než začneme s kódováním, integrujte Aspose.Slides do svého projektu pomocí jedné z následujících metod:

### Znalec
Zahrňte tuto závislost do svého `pom.xml` soubor:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Přidejte tento řádek do svého `build.gradle` soubor:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Nebo si stáhněte nejnovější verzi Aspose.Slides pro Javu z [Aspose Releases](https://releases.aspose.com/slides/java/).

#### Získání licence
- **Bezplatná zkušební verze**Začněte s 30denní bezplatnou zkušební verzí a prozkoumejte funkce.
- **Dočasná licence**Získejte dočasnou licenci pro prodloužené testování.
- **Nákup**Zakupte si licenci pro plný přístup a podporu.

Nyní inicializujte Aspose.Slides ve vaší Java aplikaci přidáním potřebných importů, jak je znázorněno níže.

## Průvodce implementací

### Nastavení adresáře
Nejprve se ujistěte, že existuje adresář pro ukládání souborů prezentací. Tímto krokem zabráníte chybám během ukládání souborů.

#### Vytvoření adresáře, pokud neexistuje
```java
import java.io.File;

String dataDir = "YOUR_DOCUMENT_DIRECTORY";
boolean isExists = new File(dataDir).exists();
if (!isExists) {
    // Vytvořte adresář
    new File(dataDir).mkdirs();
}
```
Tento úryvek kódu kontroluje zadaný adresář a pokud neexistuje, vytvoří ho. Používá `File.exists()` ověřit přítomnost a `File.mkdirs()` k vytvoření adresářů.

### Inicializace prezentace

Dále inicializujte objekt prezentace, kam přidáte bodový graf.

#### Inicializace prezentace
```java
import com.aspose.slides.Presentation;

Presentation pres = new Presentation();
ISlide slide = pres.getSlides().get_Item(0);
```
Zde, `new Presentation()` vytvoří prázdnou prezentaci. Pro přímou práci s prvním snímkem přistupujeme k němu.

### Vytvoření grafu
Dalším krokem je vytvoření bodového grafu na našem inicializovaném snímku.

#### Přidání bodového grafu na snímek
```java
import com.aspose.slides.IChart;
import com.aspose.slides.ChartType;

IChart chart = slide.getShapes().addChart(ChartType.ScatterWithSmoothLines, 0, 0, 400, 400);
```
Tento úryvek kódu přidá na první snímek bodový graf s hladkými čarami. Parametry definují polohu a velikost grafu.

### Správa dat grafů
Nyní se pojďme postarat o správu dat v grafu vymazáním všech existujících řad a přidáním nových.

#### Správa řady grafů
```java
import com.aspose.slides.IChartDataWorkbook;
import com.aspose.slides.IChartSeries;

int defaultWorksheetIndex = 0;
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
chart.getChartData().getSeries().clear();

// Přidání nové série do grafu
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), chart.getType());
chart.getChartData().getSeries().add(fact.getCell(defaultWorksheetIndex, 1, 3, "Series 2"), chart.getType());
```
Tato část vymaže stávající data a přidá do našeho bodového grafu dvě nové řady.

### Přidání datových bodů pro rozptylovou řadu
Pro vizualizaci našich dat přidáváme body do každé řady v bodovém grafu.

#### Přidat datové body
```java
import com.aspose.slides.DataPointImpl;

IChartSeries series = chart.getChartData().getSeries().get_Item(0);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 1, 1), fact.getCell(defaultWorksheetIndex, 2, 2, 3));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 1, 2), fact.getCell(defaultWorksheetIndex, 3, 2, 10));
```
Používáme `addDataPointForScatterSeries()` pro připojení datových bodů k naší první sérii. Parametry definují hodnoty X a Y.

### Typ série a modifikace značky
Vzhled grafu si můžete přizpůsobit změnou typu a stylu značek v každé sérii.

#### Přizpůsobit sérii
```java
import com.aspose.slides.MarkerStyleType;

series.setType(ChartType.ScatterWithStraightLinesAndMarkers);
series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Star);

// Úprava druhé série
series = chart.getChartData().getSeries().get_Item(1);
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 2, 3, 5), fact.getCell(defaultWorksheetIndex, 2, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 3, 3, 3), fact.getCell(defaultWorksheetIndex, 3, 4, 1));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 4, 3, 2), fact.getCell(defaultWorksheetIndex, 4, 4, 2));
series.getDataPoints().addDataPointForScatterSeries(fact.getCell(defaultWorksheetIndex, 5, 3, 5), fact.getCell(defaultWorksheetIndex, 5, 4, 1));

series.getMarker().setSize(10);
series.getMarker().setSymbol(MarkerStyleType.Circle);
```
Tyto změny upravují typ série tak, aby používal rovné čáry a značky. Také nastavujeme velikost značek a symbol pro vizuální rozlišení.

### Ukládání prezentace
Nakonec uložte prezentaci se všemi provedenými úpravami.

#### Uložte si prezentaci
```java
import com.aspose.slides.SaveFormat;

pres.save("YOUR_OUTPUT_DIRECTORY/AsposeChart_out.pptx", SaveFormat.Pptx);
```
Použití `SaveFormat.Pptx` a zadejte formát PowerPointu pro uložení souboru. Tento krok je klíčový pro zachování všech změn.

## Praktické aplikace
Zde jsou některé případy použití z reálného světa:
1. **Finanční analýza**: Použijte bodové grafy k zobrazení trendů akcií v čase.
2. **Vědecký výzkum**Reprezentují experimentální datové body pro analýzu.
3. **Řízení projektů**Vizualizace alokace zdrojů a metrik průběhu.

Integrace Aspose.Slides do vašeho systému vám umožňuje automatizovat generování reportů, což zvyšuje produktivitu a přesnost.

## Úvahy o výkonu
Pro optimální výkon:
- Spravujte využití paměti odstraněním prezentací po uložení.
- Pro velké datové sady používejte efektivní datové struktury.
- Minimalizujte operace náročné na zdroje v rámci smyček.

Osvědčené postupy zajišťují hladký chod i při složitých manipulacích s grafy.

## Závěr
V tomto tutoriálu jste se naučili nastavovat adresáře, inicializovat prezentace Aspose.Slides, vytvářet a upravovat bodové grafy, spravovat data řad, upravovat značky a ukládat svou práci. Chcete-li dále prozkoumat možnosti Aspose.Slides, zvažte ponoření se do pokročilejších funkcí, jako je animace a přechody mezi snímky.

**Další kroky**Experimentujte s různými typy grafů nebo integrujte tyto techniky do většího projektu v Javě.

## Často kladené otázky

### Jak změním barvu značek?
Chcete-li změnit barvu značky, použijte `series.getMarker().getFillFormat().setFillColor(ColorObject)`, kde `ColorObject` je vaše požadovaná barva.

### Mohu do bodového grafu přidat více než dvě řady?
Ano, můžete přidat libovolný počet řad opakováním procesu přidávání nových řad a datových bodů.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}