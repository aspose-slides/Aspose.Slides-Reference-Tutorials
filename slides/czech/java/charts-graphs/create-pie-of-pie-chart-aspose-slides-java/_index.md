---
"date": "2025-04-17"
"description": "Naučte se, jak vytvořit a přizpůsobit koláčový graf pomocí Aspose.Slides pro Javu. Tato příručka se zabývá nastavením, implementací a praktickými aplikacemi."
"title": "Vytvořte koláčový graf v Javě s Aspose.Slides – Komplexní průvodce"
"url": "/cs/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvořte koláčový graf v Javě pomocí Aspose.Slides: Komplexní průvodce

## Grafy a tabulky

### Zavedení

Ve vizualizaci dat představují koláčové grafy intuitivní způsob, jak reprezentovat proporce v rámci datové sady. Při práci se složitými datovými sadami, kde jsou některé segmenty výrazně menší než jiné, se však tradiční koláčové grafy mohou stát nepřehlednými a obtížně interpretovatelnými. Koláčové grafy tento problém řeší rozdělením malých segmentů do sekundárního grafu, což zlepšuje čitelnost.

tomto tutoriálu se naučíte, jak vytvořit a manipulovat s koláčovým grafem pomocí Aspose.Slides pro Javu. Probereme nastavení prostředí, vytvoření grafu, přizpůsobení vlastností, jako jsou popisky dat a pozice rozdělení, a uložení prezentace ve formátu PPTX. Na konci budete mít tyto funkce zvládnuté s praktickými aplikacemi a tipy pro zvýšení výkonu.

**Co se naučíte:**
- Nastavení Aspose.Slides pro Javu
- Vytvoření koláčového grafu
- Úpravy vlastností grafu, jako jsou popisky dat a konfigurace rozdělení
- Uložení prezentace na disk

Jste připraveni začít? Nejprve se podívejme na předpoklady!

## Předpoklady

Před vytvořením našeho koláčového grafu se ujistěte, že máte:

### Požadované knihovny, verze a závislosti:
- **Aspose.Slides pro Javu**Nezbytné pro programovou správu prezentací v PowerPointu.

### Požadavky na nastavení prostředí:
- Na vašem počítači nainstalovaná sada pro vývojáře Java (JDK). Doporučujeme používat JDK 16 nebo novější.
- Integrované vývojové prostředí (IDE), jako je IntelliJ IDEA, Eclipse nebo NetBeans.

### Předpoklady znalostí:
- Základní znalost programování v Javě
- Znalost Mavenu nebo Gradle pro správu závislostí

## Nastavení Aspose.Slides pro Javu

### Informace o instalaci:

**Znalec:**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

**Přímé stažení**Nejnovější verzi si můžete stáhnout z [Aspose.Slides pro verze Java](https://releases.aspose.com/slides/java/).

### Kroky pro získání licence:
- **Bezplatná zkušební verze**Začněte s 30denní zkušební verzí a prozkoumejte všechny funkce.
- **Dočasná licence**Požádejte o dočasnou licenci pro prodloužené zkušební období.
- **Nákup**Pokud Aspose.Slides splňuje vaše potřeby, zvažte zakoupení licence.

### Základní inicializace a nastavení

Jakmile máte knihovnu v projektu nastavenou, inicializujte ji vytvořením instance knihovny `Presentation` třída:

```java
Presentation presentation = new Presentation();
```

Tímto si připravíte půdu pro přidávání různých grafů do vašich snímků. Dále se přesuneme k implementaci našeho koláčového grafu.

## Průvodce implementací

### Vytvoření „koláčového“ grafu

#### Přehled
Začneme vytvořením instance `Presentation` a na první snímek přidejte koláčový graf. Tento graf efektivně vizualizuje data oddělením menších segmentů do sekundárního koláčového grafu, což zlepšuje čitelnost.

#### Krok 1: Vytvoření instance třídy Presentation
```java
// Vytvořte novou prezentaci
ePresentation presentation = new Presentation();
```
Tento kód inicializuje vaši prezentaci, kam přidáme naše grafy.

#### Krok 2: Přidání grafu „Výsečkový graf“ na první snímek
```java
// Přidat koláčový graf na první snímek na pozici (50, 50) o velikosti (500x400)
eIChart chart = presentation.getSlides().get_Item(0).getShapes().addChart(
    ChartType.PieOfPie, 50, 50, 500, 400);
```
Zde určujeme typ grafu (`PieOfPie`) a jeho polohu a rozměry na snímku.

#### Krok 3: Nastavení popisků dat pro zobrazení hodnot pro řadu
```java
// Konfigurace popisků dat pro zobrazení hodnot
echart.getChartData().getSeries().get_Item(0)
    .getLabels()
    .getDefaultDataLabelFormat()
    .setShowValue(true);
```
Tento krok zajišťuje, že každý segment našeho koláčového grafu zobrazuje odpovídající hodnotu, což usnadňuje rychlou interpretaci dat.

#### Krok 4: Konfigurace velikosti druhého koláče a rozdělení podle procent
```java
// Nastavení velikosti sekundárního koláče
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setSecondPieSize(149);

// Rozdělte koláč procenty
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitBy(PieSplitType.ByPercentage);

// Nastavení rozdělené pozice
echart.getChartData().getSeries().get_Item(0)
    .getParentSeriesGroup()
    .setPieSplitPosition(53);
```
Tato konfigurace vám umožňují přizpůsobit způsob rozdělení grafu a zobrazení menších segmentů, což zlepšuje přehlednost pro diváky.

#### Krok 5: Uložení prezentace na disk ve formátu PPTX
```java
// Definovat výstupní adresář
eString outputDir = "YOUR_OUTPUT_DIRECTORY";

// Uložte prezentaci\epresentation.save(outputDir + "/SecondPlotOptionsforCharts_out.pptx\

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}