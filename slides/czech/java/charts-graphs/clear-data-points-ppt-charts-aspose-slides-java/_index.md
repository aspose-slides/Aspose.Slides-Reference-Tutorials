---
date: '2026-08-27'
description: Naučte se, jak vymazat data points v charts v PowerPoint pomocí Aspose.Slides
  for Java. Tento step‑by‑step tutorial ukazuje, jak programově vymazat hodnoty chart,
  osvědčené postupy a efektivní správu series.
keywords:
- how to clear chart
- programmatically clear chart
- remove chart data points
- Aspose.Slides Java chart manipulation
- PowerPoint chart automation
lastmod: '2026-08-27'
og_description: Naučte se, jak vymazat data points v chart v PowerPoint pomocí Aspose.Slides
  for Java. Postupujte podle step‑by‑step instructions pro programové efektivní resetování
  charts.
og_image_alt: Code example showing how to clear chart data points in a PowerPoint
  presentation using Aspose.Slides for Java
og_title: Jak vymazat data points v chart v PowerPoint s Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-27'
  description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  headline: 'How to clear data points in PowerPoint charts using Aspose.Slides for
    Java: a comprehensive guide'
  type: TechArticle
- description: Learn how to clear chart data points in PowerPoint using Aspose.Slides
    for Java. This step‑by‑step tutorial shows how to programmatically clear chart
    values, best practices, and efficient series handling.
  name: 'How to clear data points in PowerPoint charts using Aspose.Slides for Java:
    a comprehensive guide'
  steps:
  - name: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
    text: '**Load the presentation** – create a `Presentation` instance pointing to
      your source file.'
  - name: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
    text: '**Access the slide and chart** – retrieve the slide (usually index 0) and
      cast the first shape to `IChart`.'
  - name: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
    text: '**Iterate through the target series** – select the series you want to clear
      (e.g., `chart.getChartData().getSeries().get_Item(0)`) and loop over its data
      points, setting both X and Y cell values to `null`.'
  - name: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
    text: '**Save the modified presentation** – write the changes to a new file or
      overwrite the original.'
  - name: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
    text: '**Data refresh pipelines** – replace stale numbers with fresh analytics
      without rebuilding the chart layout.'
  - name: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
    text: '**Template distribution** – provide PowerPoint templates that contain empty
      charts ready for user input.'
  - name: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
    text: '**Dynamic dashboards** – generate nightly presentations that pull data
      from APIs, clearing old values first.'
  - name: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
    text: '**Automated reporting jobs** – integrate the clearing logic into CI/CD
      pipelines for automated report generation.'
  type: HowTo
- questions:
  - answer: A free trial license is sufficient for development and testing. A commercial
      license is required for production deployments.
    question: Do I need a license for development builds?
  - answer: Yes, the library fully supports modern PPTX features, including advanced
      chart types and SmartArt.
    question: Does Aspose.Slides for Java support PowerPoint 2016/2019 features?
  - answer: Absolutely – just reference the series that belongs to the secondary axis
      and set its data points to `null` as described above.
    question: Can I clear data points in a chart that uses a secondary axis?
  - answer: Yes. Call `dataPoint.getYValue().setValue(null)` and leave the X cell
      untouched.
    question: Is it possible to clear only Y values while keeping X labels?
  - answer: Wrap the clearing code in a loop that iterates over a directory of PPTX
      files, applying the same logic to each file.
    question: How can I automate this for multiple presentations?
  type: FAQPage
tags:
- clear chart
- Aspose.Slides
- Java chart manipulation
- PowerPoint automation
- chart data points
title: 'Jak vymazat data points v charts PowerPoint pomocí Aspose.Slides for Java:
  komplexní průvodce'
url: /cs/java/charts-graphs/clear-data-points-ppt-charts-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vymazat datové body v grafech PowerPointu pomocí Aspose.Slides pro Java

## Úvod

V mnoha reportovacích řetězcích potřebujete **resetovat graf** bez nutnosti znovu vytvářet jeho rozvržení. Ať už aktualizujete dashboard, distribuujete šablonu nebo automatizujete noční reporty, znalost **jak vymazat datové body grafu** šetří čas a snižuje chyby. Tento tutoriál vám ukáže, jak pomocí **Aspose.Slides pro Java** programově vymazat konkrétní body nebo celou sérii, přičemž zachová vizuální styl.

**Co se naučíte**
- Jak Aspose.Slides umožňuje manipulovat s grafy PowerPointu z Javy.  
- Krok‑za‑krokem instrukce pro vymazání datových bodů v sérii grafu.  
- Tipy pro výkon a licencování.

## Rychlé odpovědi
- **Jaká knihovna je vyžadována?** Aspose.Slides pro Java (v25.4+).  
- **Která metoda skutečně vymaže datový bod?** Nastavení hodnot buněk X a Y na `null`.  
- **Potřebuji licenci pro produkci?** Ano – komerční licence odstraňuje omezení zkušební verze.  
- **Je podporována Java 16?** Rozhodně; knihovna funguje s JDK 16 a novějšími.  
- **Mohu cílit jen na jednu sérii?** Ano – iterujte konkrétní sérii, kterou chcete vymazat.

## Co je Aspose.Slides pro Java?

Aspose.Slides pro Java je plnohodnotné API, které umožňuje vytvářet, upravovat a konvertovat soubory PowerPointu bez Microsoft Office. Podporuje více než 70 typů grafů, více než 150 formátů souborů a dokáže zpracovat prezentace až do velikosti 500 MB, aniž by načítalo celý soubor do paměti.

## Proč vymazat datové body v grafu?

Vymazání datových bodů v grafu vám umožní zachovat stávající rozvržení grafu – jako jsou barvy, legendy, nastavení os a značky – a zároveň nahradit podkladové číselné hodnoty. Tento přístup je užitečný, když potřebujete aktualizovat graf novými daty, poskytnout šablonu s prázdnými zástupci nebo generovat dynamické dashboardy, které se často mění, aniž byste museli znovu stavět vizuální design.

- Aktualizace grafu novým datasetem při zachování barev, legend a nastavení os.  
- Distribuce šablony, která obsahuje prázdné grafy připravené k zadání uživatelem.  
- Vytváření dynamických dashboardů, kde se data často mění.

## Jak vymazat datové body v grafu v PowerPointu pomocí Aspose.Slides pro Java

Načtěte prezentaci, najděte graf a nastavte buňky X a Y každého datového bodu na `null`. Tím se odstraní číselné hodnoty, ale série, značky a formátování zůstanou nedotčeny. Celý proces obvykle trvá méně než sekundu pro standardní 10‑snímkovou PPTX.

### Přímá odpověď
Pro vymazání datových bodů v grafu otevřete PPTX pomocí `new Presentation("input.pptx")`, získejte cílový objekt `IChart`, projděte požadovanou `IChartSeries` a zavolejte `dataPoint.getXValue().setValue(null)` a `dataPoint.getYValue().setValue(null)` pro každý bod. Nakonec uložte prezentaci pomocí `pres.save("output.pptx", SaveFormat.Pptx)`. Tento přístup programově vymaže data a zachová vizuální design grafu.

### Definiční kotvy
- `Presentation` je hlavní objekt Aspose.Slides, který představuje soubor PowerPointu v paměti.  
- `IChart` je rozhraní poskytující přístup k sériím, osám a formátování grafu.  
- `IChartSeries` představuje jednu sérii v grafu a obsahuje kolekci objektů `IDataPoint`.  
- `IDataPoint` uchovává jednotlivé hodnoty X a Y pro bod v grafu.

### Krok za krokem implementace

1. **Načtěte prezentaci** – vytvořte instanci `Presentation`, která ukazuje na váš zdrojový soubor.  
   ```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

2. **Přístup k snímku a grafu** – získejte snímek (obvykle index 0) a přetypujte první tvar na `IChart`.  
   ```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

3. **Iterujte cílovou sérii** – vyberte sérii, kterou chcete vymazat (např. `chart.getChartData().getSeries().get_Item(0)`) a projděte její datové body, přičemž nastavíte buňky X i Y na `null`.  
   ```java
import com.aspose.slides.*;

public class ChartManipulation {
    public static void main(String[] args) {
        Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
        try {
            // Your code here
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

4. **Uložte upravenou prezentaci** – zapište změny do nového souboru nebo přepište původní.  
   ```java
   Presentation pres = new Presentation("YOUR_DOCUMENT_DIRECTORY/TestChart.pptx");
   ```

## Nastavení Aspose.Slides pro Java

### Instalace pomocí Maven

```java
   ISlide sl = pres.getSlides().get_Item(0);
   IChart chart = (IChart) sl.getShapes().get_Item(0);
   ```

### Instalace pomocí Gradle

```java
   for (IChartDataPoint dataPoint : chart.getChartData().getSeries().get_Item(0).getDataPoints()) {
       dataPoint.getXValue().getAsCell().setValue(null);
       dataPoint.getYValue().getAsCell().setValue(null);
   }
   ```

### Přímé stažení

Alternativně si stáhněte nejnovější verzi z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

### Získání licence

Pro použití Aspose.Slides nad rámec omezení zkušební verze:
- Získejte **bezplatnou zkušební** licenci.  
- Požádejte o **dočasnou licenci** pro hodnocení.  
- Zakupte **komerční licenci** pro produkční nasazení.

#### Základní inicializace a nastavení

```java
   pres.save("YOUR_DOCUMENT_DIRECTORY/UpdatedTestChart.pptx", SaveFormat.Pptx);
   ```

## Praktické aplikace

Vymazání datových bodů v grafu je užitečné v mnoha reálných scénářích:

1. **Datové refresh pipeline** – nahraďte zastaralá čísla čerstvými analytickými údaji bez nutnosti přestavovat rozvržení grafu.  
2. **Distribuce šablon** – poskytujte PowerPoint šablony, které obsahují prázdné grafy připravené k zadání uživatelem.  
3. **Dynamické dashboardy** – generujte noční prezentace, které čerpají data z API, přičemž nejprve vymažou staré hodnoty.  
4. **Automatizované reportovací úlohy** – integrujte logiku vymazání do CI/CD pipeline pro automatické generování reportů.

## Úvahy o výkonu

- **Uvolňujte objekty**: Po uložení zavolejte `pres.dispose()` pro uvolnění nativních zdrojů.  
- **Dávkové zpracování**: Znovu použijte jedinou instanci `License` napříč mnoha soubory, aby se minimalizovalo zatížení.  
- **Ladění JVM**: Zvyšte velikost haldy (`-Xmx2g` nebo vyšší) při zpracování prezentací větších než 200 MB.  
- **Paměťově úsporný režim**: Aspose.Slides dokáže streamovat velké PPTX soubory, což umožňuje zpracování až 10 000 snímků bez úplného načtení do paměti.

## Často kladené otázky

**Q: Potřebuji licenci pro vývojové sestavy?**  
A: Pro vývoj a testování stačí bezplatná zkušební licence. Pro produkční nasazení je vyžadována komerční licence.

**Q: Podporuje Aspose.Slides pro Java funkce PowerPoint 2016/2019?**  
A: Ano, knihovna plně podporuje moderní PPTX funkce, včetně pokročilých typů grafů a SmartArt.

**Q: Mohu vymazat datové body v grafu, který používá sekundární osu?**  
A: Rozhodně – stačí odkazovat na sérii patřící k sekundární ose a nastavit její datové body na `null`, jak je popsáno výše.

**Q: Je možné vymazat jen Y hodnoty a zachovat X popisky?**  
A: Ano. Zavolejte `dataPoint.getYValue().setValue(null)` a nechte buňku X nedotčenu.

**Q: Jak mohu automatizovat tento proces pro více prezentací?**  
A: Zabalte kód pro vymazání do smyčky, která iteruje přes adresář PPTX souborů a aplikuje stejnou logiku na každý soubor.

## Zdroje

- [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)
- [Download Aspose.Slides for Java](https://releases.aspose.com/slides/java/)
- [Purchase a License](https://purchase.aspose.com/buy)
- [Free Trial Version](https://releases.aspose.com/slides/java/)
- [Temporary License Application](https://purchase.aspose.com/temporary-license/)
- [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

S těmito zdroji jste připraveni začít vymazávat datové body v grafech ve vašich Java aplikacích. Šťastné programování!

---

**Poslední aktualizace:** 2026-08-27  
**Testováno s:** Aspose.Slides pro Java 25.4 (JDK 16)  
**Autor:** Aspose

## Související tutoriály

- [How to Edit PowerPoint Chart Data Using Aspose.Slides for Java: A Comprehensive Guide](/slides/java/charts-graphs/edit-ppt-chart-data-aspose-slides-java/)
- [How to Add Chart to PowerPoint Using Aspose.Slides for Java: A Step‑By‑Step Guide](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Clear Specific Chart Series Data Points Data in Java Slides](/slides/java/java-slides-chart-data-manipulation/clear-specific-chart-series-data-points-java-slides/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}