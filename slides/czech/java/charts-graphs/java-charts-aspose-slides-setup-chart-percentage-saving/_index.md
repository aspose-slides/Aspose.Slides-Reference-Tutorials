---
"date": "2025-04-17"
"description": "Naučte se, jak vytvářet, upravovat a ukládat grafy s procentuálními popisky v prezentacích v Javě pomocí Aspose.Slides. Zlepšete si své prezentační dovednosti ještě dnes!"
"title": "Vytvářejte a upravujte grafy v prezentacích v Javě pomocí Aspose.Slides"
"url": "/cs/java/charts-graphs/java-charts-aspose-slides-setup-chart-percentage-saving/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvářejte a upravujte grafy v prezentacích v Javě pomocí Aspose.Slides

## Zavedení
Vytváření poutavých prezentací často zahrnuje více než jen text; vyžaduje dynamické grafy, které efektivně sdělují informace. Pokud chcete vylepšit své prezentace v Javě sofistikovanými funkcemi grafů pomocí Aspose.Slides, tento tutoriál je pro vás. Provedeme vás vytvořením prezentace, přidáváním a konfigurací grafů, výpočtem součtů, zobrazením procentuálních popisků a uložením vaší práce – to vše v několika snadných krocích.

**Co se naučíte:**
- Jak vytvářet a upravovat prezentace s grafy pomocí Aspose.Slides pro Javu
- Výpočet součtů kategorií v grafech
- Zobrazování dat jako procentuálních popisků v grafech
- Ukládání prezentací s vylepšenými funkcemi grafů

Pojďme se ponořit do předpokladů, které potřebujete, než začnete.

## Předpoklady
Abyste mohli postupovat podle tohoto tutoriálu, ujistěte se, že máte následující:

- **Vývojová sada pro Javu (JDK)**Verze 8 nebo vyšší.
- **IDE**Například IntelliJ IDEA, Eclipse nebo jakékoli IDE podporované Javou.
- **Aspose.Slides pro knihovnu Java**: Toto je klíčové pro práci s funkcemi prezentace.

### Požadované knihovny a verze
Budete potřebovat Aspose.Slides pro Javu. Zde je návod, jak ho zahrnout do vašeho projektu:

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

Případně si můžete nejnovější verzi stáhnout přímo z [Aspose.Slides pro verze Java](https://releases.aspose.com/slides/java/).

### Nastavení prostředí
Ujistěte se, že vaše vývojové prostředí je nakonfigurováno pro použití JDK 8 nebo novějšího a že vaše IDE je nastaveno pro správu závislostí pomocí Mavenu nebo Gradle.

**Získání licence:**
- **Bezplatná zkušební verze**: Přístup k základním funkcím pro účely testování.
- **Dočasná licence**Otestujte pokročilé funkce bez omezení vyhodnocování.
- **Nákup**Pro dlouhodobé komerční využití zvažte zakoupení licence.

## Nastavení Aspose.Slides pro Javu
Začněte nastavením knihovny Aspose.Slides ve vašem projektu Java. Zde je návod, jak ji inicializovat a nakonfigurovat:

1. Přidejte závislost pomocí Mavenu nebo Gradle, jak je znázorněno výše.
2. Importujte potřebné balíčky Aspose.Slides:
   ```java
   import com.aspose.slides.*;
   ```

3. Inicializovat nový `Presentation` instance:
   ```java
   Presentation presentation = new Presentation();
   ```

Toto nastavení vám umožní začít programově vytvářet prezentace.

## Průvodce implementací

### Vytvářejte a upravujte grafy ve své prezentaci

#### Přehled
Vytvoření grafu zahrnuje inicializaci prezentace, přístup ke snímkům a přidání grafu se specifickými atributy, jako je typ, umístění a velikost.

**Kroky:**
1. **Vytvořit instanci prezentace**Začněte vytvořením instance `Presentation` třída.
2. **Přístupový snímek**Načíst první snímek pomocí `get_Item(0)`.
3. **Přidat graf**Použití `addChart()` přidat skládaný sloupcový graf na zadaných souřadnicích s definovanými rozměry.

```java
// Funkce: Vytvořte prezentaci s grafem
import com.aspose.slides.*;

try {
    Presentation presentation = new Presentation();
    ISlide slide = presentation.getSlides().get_Item(0);
    
    IChart chart = slide.getShapes().addChart(
        ChartType.StackedColumn,
        20, 20, 400, 400
    );
} finally {
    if (presentation != null) presentation.dispose();
}
```

### Výpočet součtů pro kategorie

#### Přehled
Výpočet součtů kategorií zahrnuje iteraci každou řadou v grafu za účelem shrnutí hodnot pro každou kategorii.

**Kroky:**
1. **Inicializace pole**Vytvořte pole pro uchovávání celkových hodnot.
2. **Iterovat kategoriemi a sériemi**Použijte vnořené smyčky k shromažďování součtů pro každou kategorii ze všech řad.

```java
// Funkce: Výpočet součtů pro kategorie v grafu
import com.aspose.slides.*;

public void calculateCategoryTotals(IChart chart, double[] total_for_Cat) {
    for (int k = 0; k < chart.getChartData().getCategories().size(); k++) {
        IChartCategory cat = chart.getChartData().getCategories().get_Item(k);
        total_for_Cat[k] = 0;

        for (int i = 0; i < chart.getChartData().getSeries().size(); i++) {
            double value = (double) (
                chart.getChartData().getSeries().get_Item(i).
                    getDataPoints().get_Item(k).
                    getValue().getData());
            total_for_Cat[k] += value;
        }
    }
}
```

### Zobrazení dat jako procentuálních popisků v grafu

#### Přehled
Tato funkce se zaměřuje na konfiguraci popisků dat pro zobrazení hodnot v procentech, což zajišťuje přehlednost vizualizace.

**Kroky:**
1. **Konfigurace popisků sérií**Nastavení vlastností popisku, jako je velikost písma a viditelnost legendy.
2. **Výpočet procent**Vypočítejte procento pro každý datový bod na základě celkové hodnoty kategorie.
3. **Nastavit text popisku**: Naformátujte popisky tak, aby zobrazovaly procenta se dvěma desetinnými místy.

```java
// Funkce: Zobrazení dat jako procentuálních popisků v grafu
import com.aspose.slides.*;

public void displayPercentageLabels(IChart chart, double[] total_for_Cat) {
    for (int x = 0; x < chart.getChartData().getSeries().size(); x++) {
        IChartSeries series = chart.getChartData().getSeries().get_Item(x);
        
        series.getLabels().getDefaultDataLabelFormat().setShowLegendKey(false);

        for (int j = 0; j < series.getDataPoints().size(); j++) {
            IDataLabel lbl = series.getDataPoints().get_Item(j).getLabel();
            double dataPontPercent = (double) (
                series.getDataPoints().get_Item(j).
                    getValue().getData()) / total_for_Cat[j] * 100;

            IPortion port = new Portion();
            port.setText(String.format("{0:F2} %%", dataPontPercent));
            port.getPortionFormat().setFontHeight(8f);
            
            lbl.getTextFrameForOverriding().setText("");
            IParagraph para = lbl.getTextFrameForOverriding().getParagraphs().get_Item(0);
            para.getPortions().add(port);

            lbl.getDataLabelFormat().setShowSeriesName(false);
            lbl.getDataLabelFormat().setShowPercentage(false);
            lbl.getDataLabelFormat().setShowLegendKey(false);
            lbl.getDataLabelFormat().setShowCategoryName(false);
            lbl.getDataLabelFormat().setShowBubbleSize(false);
        }
    }
}
```

### Uložit prezentaci s grafem

#### Přehled
Nakonec uložte prezentaci do zadané cesty ve formátu PPTX.

**Kroky:**
1. **Uložit metodu**Použijte `save()` metoda na `Presentation` instance.
2. **Likvidace zdrojů**Zajistěte uvolnění zdrojů po uložení.

```java
// Funkce: Uložení prezentace s grafem
import com.aspose.slides.*;

public void savePresentation(Presentation presentation, String outputPath) {
    try {
        presentation.save(outputPath + "DisplayPercentageAsLabels_out.pptx", SaveFormat.Pptx);
    } finally {
        if (presentation != null) presentation.dispose();
    }
}
```

## Praktické aplikace

1. **Finanční výkaznictví**: Použijte grafy k zobrazení procentuálního růstu tržeb napříč odděleními.
2. **Analýza prodejních dat**Vizualizace prodejních dat podle regionu s procentuálními popisky pro jasnější přehled.
3. **Vzdělávací prezentace**Vylepšete akademické prezentace vizuálními statistikami.
4. **Marketingové kampaně**Zobrazujte metriky výkonu kampaně jako poutavé vizuální prvky.
5. **Schůzky o obchodní strategii**Používejte grafy k prezentaci složitých dat v diskusích o strategickém plánování.

## Úvahy o výkonu
- **Správa paměti**: Zlikvidujte `Presentation` objekty okamžitě uvolnit zdroje.
- **Optimalizace načítání grafů**Pokud je to možné, načtěte do paměti pouze nezbytné prvky grafu.
- **Dávkové zpracování**Při zpracování více prezentací zvažte jejich dávkové zpracování, abyste efektivně řídili spotřebu zdrojů.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}