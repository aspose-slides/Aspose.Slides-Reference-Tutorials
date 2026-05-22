---
date: '2026-03-23'
description: Naučte se, jak používat Aspose.Slides pro Javu k vytváření čárových grafů
  se značkami, přidat druhou sérii a zpracovávat nulová data v prezentacích PowerPoint.
keywords:
- Aspose.Slides for Java
- line charts with markers in Java
- creating presentations programmatically
title: 'Jak používat Aspose.Slides pro Javu: Vytvořte čárové grafy s výchozími značkami'
url: /cs/java/charts-graphs/create-line-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvoření čárových grafů s výchozími značkami pomocí Aspose.Slides pro Java

## Úvod
Pokud se ptáte, **jak používat Aspose** k automatizaci tvorby PowerPoint, jste na správném místě. V tomto tutoriálu si projdeme vytvoření **čárového grafu se značkami**, přidání druhé řady a zpracování nulových dat — vše pomocí Aspose.Slides pro Java. Na konci budete mít připravený úryvek kódu, který vygeneruje profesionálně vypadající graf, aniž byste museli ručně otevírat PowerPoint.

### Rychlé odpovědi
- **Jaká knihovna potřebuji?** Aspose.Slides pro Java (doporučena nejnovější verze)  
- **Mohu přidat druhou řadu?** Ano – API vám umožní snadno přidat více řad.  
- **Jak jsou zpracovány nulové datové body?** Použijte `null` v hodnotě buňky; graf bod přeskočí.  
- **Potřebuji Maven?** Maven nebo Gradle fungují; viz sekce *aspose slides maven* níže.  
- **Je licence vyžadována?** Bezplatná zkušební verze funguje pro vývoj; pro produkci je potřeba komerční licence.

## Jak použít Aspose.Slides pro Java k vytvoření čárových grafů
Vytváření grafů programově vám ušetří hodiny ručního formátování a zaručuje konzistenci napříč prezentacemi. Ať už budujete funkci **create powerpoint chart** v nástroji pro reportování nebo generujete sady snímků za běhu, Aspose.Slides vám dává plnou kontrolu z Java kódu.

## Požadavky
Předtím, než začneme, ujistěte se, že je vaše vývojové prostředí připravené:

1. **Knihovny a závislosti**
   - Knihovna Aspose.Slides pro Java (doporučena verze 25.4) – pokrývá scénář *aspose slides maven*.
   - Java Development Kit (JDK) verze 16 nebo vyšší.
2. **Nastavení prostředí**
   - IDE s podporou Maven nebo Gradle.
   - Platný soubor licence Aspose, pokud plánujete spouštět kód mimo zkušební verzi.
3. **Předpoklady znalostí**
   - Základy programování v Javě.
   - Znalost souborů pro sestavení Maven nebo Gradle.

## Nastavení Aspose.Slides pro Java
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
Vložte toto do souboru `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Přímé stažení
Alternativně můžete stáhnout nejnovější verzi z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

**Kroky pro získání licence:**
- Pro bezplatnou zkušební verzi navštivte [free trial page](https://releases.aspose.com/slides/java/).
- Pro získání dočasné licence přejděte na [temporary license page](https://purchase.aspose.com/temporary-license/).
- Zakupte plnou licenci přes jejich [purchase portal](https://purchase.aspose.com/buy).

**Základní inicializace:**
Zde je, jak můžete inicializovat Aspose.Slides ve vaší Java aplikaci:
```java
import com.aspose.slides.Presentation;
// Initialize a new presentation object
Presentation pres = new Presentation();
```

Nyní přejděme k vytváření grafů!

## Průvodce implementací
### Funkce 1: Vytvoření grafu s výchozími značkami
V této sekci se ukazuje, jak vytvořit **čárový graf se značkami**, což je ideální pro zvýraznění jednotlivých datových bodů na trendové linii.

#### Přidání čárového grafu
Pro přidání čárového grafu se značkami:
```java
import com.aspose.slides.*;
// Access the first slide
ISlide slide = pres.getSlides().get_Item(0);
// Add a line chart with markers to the slide at position (10, 10) with size (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```

#### Vymazání řad a kategorií
Pro začátek od nuly:
```java
// Clear existing series and categories to ensure a clean slate
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Obtain the chart's data workbook for further manipulation
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```

### Funkce 2: Přidání řad a kategorií
Přidání řad a kategorií je klíčové pro naplnění vašich grafů smysluplnými daty.

#### Vytvoření nové řady
Pro přidání nové řady s názvem "Series 1":
```java
// Add a new series to the chart
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Access the first series for data population
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```

#### Naplnění kategorií a datových bodů
Pro přidání kategorií a odpovídajících datových bodů:
```java
// Add category names and their respective data points
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Handling null data points gracefully
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```

### Funkce 3: Přidání druhé řady a naplnění datových bodů
Přidání dalších řad poskytuje větší hloubku vaší vizuální analýze.

#### Vytvoření a naplnění druhé řady
Pro přidání "Series 2":
```java
// Add another series named 'Series 2'
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Access the second series for data population
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Add data points for 'Series 2'
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```

### Funkce 4: Konfigurace legendy grafu
Konfigurace legendy zvyšuje čitelnost grafu, zejména když **přidáte druhou řadu**.

#### Úprava nastavení legendy
Pro konfiguraci:
```java
// Enable the legend and set it not to overlay on data points
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```

### Funkce 5: Uložení prezentace
Jakmile je váš graf připraven, budete chtít **create powerpoint chart** soubory, které lze sdílet nebo dále upravovat.

```java
try {
    // Save the modified presentation to a specified directory
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```

## Praktické aplikace
1. **Obchodní reportování:** Použijte čárový graf se značkami k ilustraci finančních trendů během čtvrtletí.  
2. **Analýza dat:** Vizualizujte experimentální data, kde každá značka zvýrazňuje měřicí bod.  
3. **Vzdělávací materiály:** Vytvořte přednáškové snímky, které ukazují krok za krokem změny v procesu.  
4. **Projektové řízení:** Sledujte milníky na časové ose s odlišnými značkami pro klíčová data.  
5. **Marketingové prezentace:** Zobrazte špičky výkonnosti kampaně s jasnými značkami.

## Časté problémy a řešení
- **Nulové datové body způsobují chyby:** Předávejte `null` jako hodnotu buňky (jak je ukázáno) – Aspose jednoduše bod vynechá.  
- **Graf se zobrazuje bez značek:** Ujistěte se, že používáte `ChartType.LineWithMarkers` místo `ChartType.Line`.  
- **Legenda překrývá data:** Nastavte `chart.getLegend().setOverlay(false)`, aby legenda byla oddělena.  

## Často kladené otázky
**Q: Mohu tento přístup použít k generování grafů ve webové službě?**  
A: Rozhodně. Knihovna funguje v jakémkoli Java prostředí, včetně server‑side aplikací.

**Q: Potřebuji licenci pro vývojové sestavení?**  
A: Bezplatná zkušební verze funguje pro vývoj a testování. Pro produkční použití je vyžadována komerční licence.

**Q: Jak Aspose zachází s velkými datovými sadami?**  
A: API efektivně streamuje data; přesto udržujte počet datových bodů na rozumné úrovni, aby nedocházelo k velkým velikostem souborů.

**Q: Existuje podpora pro jiné typy grafů?**  
A: Ano – Aspose.Slides podporuje sloupcové, koláčové, rozptylové a mnoho dalších typů grafů.

**Q: Mohu přizpůsobit tvary a barvy značek?**  
A: Můžete upravit formát značky pomocí vlastnosti `Marker` u každého datového bodu.

## Závěr
Nyní víte **jak používat Aspose** k vytvoření čárového grafu s výchozími značkami, přidání druhé řady, zpracování nulových dat a uložení výsledku jako soubor PowerPoint. Tyto techniky vám umožní automatizovat tvorbu reportů, zlepšit vyprávění dat a udržet konzistentní prezentace.

Pro podrobnější informace prozkoumejte [oficiální dokumentaci](https://docs.aspose.com/slides/java/) nebo se připojte ke komunitním fórům jako Stack Overflow.

---

**Poslední aktualizace:** 2026-03-23  
**Testováno s:** Aspose.Slides pro Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}