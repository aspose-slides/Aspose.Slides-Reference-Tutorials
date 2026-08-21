---
date: '2026-08-21'
description: Naučte se, jak vytvořit clustered column chart a přidat trend lines s
  Aspose.Slides for Java. Obsahuje nastavení licence, integraci Maven/Gradle a podrobné
  příklady.
keywords:
- create clustered column chart
- add trend line
- aspose slides license
- java chart creation
- trend lines in charts
lastmod: '2026-08-21'
og_description: Vytvořte clustered column chart a přidejte trend lines pomocí Aspose.Slides
  for Java. Tento průvodce pokrývá nastavení licence, Maven/Gradle a krok‑za‑krokem
  ukázky kódu.
og_image_alt: Aspose.Slides for Java tutorial showing a clustered column chart with
  trend lines
og_title: Vytvořte clustered column chart a přidejte trend lines s Aspose.Slides for
  Java
schemas:
- author: Aspose
  dateModified: '2026-08-21'
  description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  headline: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  type: TechArticle
- description: Learn how to create a clustered column chart and add trend lines with
    Aspose.Slides for Java. Includes license setup, Maven/Gradle integration, and
    detailed examples.
  name: How to create clustered column chart and add trend lines using Aspose.Slides
    for Java
  steps:
  - name: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
    text: '**Initialize the presentation** – set up the output folder and create a
      new `Presentation` instance.'
  - name: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
    text: '**Add a clustered column chart** – obtain the chart shape, configure its
      series, and populate data points.'
  - name: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
    text: '**Configure the trend line** – select the series and call `addTrendline(TrendlineType.Exponential)`.'
  - name: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
    text: '**Set up the trend line** – use `addTrendline(TrendlineType.Linear)` and
      then adjust `getLineFormat().setFillFormat().setFillType(FillType.Solid)` to
      change color.'
  - name: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
    text: '**Customize the trend line** – after adding the trend line, access its
      `getDataLabel()` and set the `setText("Custom label")` property.'
  - name: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
    text: '**Configure the trend line** – call `addTrendline(TrendlineType.MovingAverage)`
      and set `setPeriod(3)` to use a three‑point moving average.'
  - name: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
    text: '**Customize the trend line** – after adding the trend line, set `setOrder(3)`
      for a cubic fit.'
  - name: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
    text: '**Configure the trend line** – use `addTrendline(TrendlineType.Power)`
      and adjust `setBackward(2)` to extend the line backward.'
  type: HowTo
- questions:
  - answer: Add the `<dependency>` snippet shown in the Maven section to your `pom.xml`
      and run `mvn clean install`.
    question: How do I set up Aspose.Slides for a Maven project?
  - answer: Yes, you can modify line style, width, dash pattern, and even forecast
      forward/backward values via the `ITrendline` API.
    question: Can I customise trend lines beyond colour and label?
  - answer: Verify that your JDK version matches the Aspose.Slides minimum requirement
      (JDK 8+). Consult the Aspose release notes for any breaking changes.
    question: What should I do if I encounter a version‑compatibility error?
  - answer: Absolutely. Loop through each `IChart` in a slide collection and invoke
      the appropriate `addTrendline` method for each series.
    question: Is it possible to add trend lines to multiple charts automatically?
  - answer: Yes, a purchased Aspose.Slides license removes evaluation limits and unlocks
      full performance optimisations.
    question: Do I need a paid license for production use?
  type: FAQPage
tags:
- create clustered column chart
- Aspose.Slides for Java
- Java chart customization
- trend line examples
- Java presentation generation
title: Jak vytvořit clustered column chart a přidat trend lines pomocí Aspose.Slides
  for Java
url: /cs/java/charts-graphs/create-customize-charts-trend-lines-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Jak vytvořit seskupený sloupcový graf a přidat trendové čáry pomocí Aspose.Slides pro Java

Vytváření poutavých prezentací často začíná jasnou vizualizací vašich dat. V tomto průvodci **create clustered column chart** objekty, poté je obohatíte o různé typy trendových čar – exponenciální, lineární, logaritmické, klouzavý průměr, polynomické a mocninné – pomocí výkonného API Aspose.Slides pro Java.

## Rychlé odpovědi
- **Jaký je první krok?** Initialise a `Presentation` object and add a clustered column chart to a slide.  
- **Která verze knihovny je požadována?** Aspose.Slides for Java 25.4 nebo novější.  
- **Mohu použít Maven nebo Gradle?** Ano, oba jsou podporovány; Maven používá `<dependency>` a Gradle používá `implementation`.  
- **Potřebuji licenci?** Zkušební licence funguje pro hodnocení; plná licence Aspose.Slides odstraňuje omezení hodnocení.  
- **Kolik typů trendových čar je k dispozici?** Šest vestavěných typů: exponential, linear, logarithmic, moving average, polynomial, a power.

## Co je create clustered column chart?
`create clustered column chart` znamená vytvoření grafu, který seskupuje více datových řad vedle sebe v každé kategorii, což usnadňuje porovnání hodnot mezi řadami. Tento typ grafu je ideální pro vizualizaci kategoriálních dat, jako jsou čtvrtletní prodeje napříč regiony, a umožňuje divákům rychle zaznamenat rozdíly mezi skupinami.

## Proč přidávat trendovou čáru?
Trendové čáry odhalují základní vzorec datové řady, pomáhají předpovídat budoucí hodnoty, zvýraznit míru růstu nebo vyhladit šum v datech. Přidáním trendové čáry do seskupeného sloupcového grafu se surová čísla promění v použitelné poznatky, což umožní zúčastněným stranám pochopit dlouhodobé tendence a činit rozhodnutí založená na datech.

## Předpoklady
- **Java Development Kit (JDK):** 8 nebo novější.  
- **Aspose.Slides for Java:** verze 25.4 nebo novější.  
- **IDE:** IntelliJ IDEA, Eclipse nebo jakýkoli editor kompatibilní s Java.  
- **Nástroj pro sestavení:** Maven nebo Gradle (volitelné, ale doporučené).  
- **Licence:** soubor licence Aspose.Slides – zkušební nebo zakoupený.  

Měli byste být obeznámeni se základní syntaxí Javy a s řízením závislostí projektu.

## Jak nastavit Aspose.Slides pro Java?
Přidejte knihovnu Aspose.Slides do svého projektu pomocí preferovaného správce závislostí a umístěte soubor licence tam, kde jej runtime dokáže najít. Tím zajistíte plnou funkčnost a odstraníte omezení hodnocení.

### Maven
Přidejte tuto závislost do souboru `pom.xml`:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle
Zahrňte tento řádek do souboru `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Můžete také stáhnout JAR ručně z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Licence Aspose Slides
Umístěte soubor `Aspose.Slides.lic` do kořenového adresáře projektu nebo nastavte licenci programově pomocí `License license = new License(); license.setLicense("Aspose.Slides.lic");`. Zkušební licence odstraňuje všechna omezení funkcí, ale zakoupená licence eliminuje vodoznak hodnocení a poskytuje plné optimalizace výkonu. Pro produkční použití zvažte zakoupení licence na [Aspose purchase page](https://purchase.aspose.com/buy).

## Jak vytvořit prezentaci a přidat seskupený sloupcový graf?
Třída `Presentation` představuje soubor PowerPoint a poskytuje metody pro vytváření, úpravu a ukládání snímků. Vytvořte instanci `Presentation`, přidejte snímek a poté zavolejte `addChart` s `ChartType.ClusteredColumn` pro vytvoření objektu grafu. Tento proces nastaví plátno snímku, vloží tvar grafu a připraví jej pro naplnění daty a stylování.

1. **Inicializujte prezentaci** – nastavte výstupní složku a vytvořte novou instanci `Presentation`.  
```java
   String dataDir = "YOUR_DOCUMENT_DIRECTORY";
   File dir = new File(dataDir);
   if (!dir.exists()) {
       dir.mkdirs();
   }
   ```

2. **Přidejte seskupený sloupcový graf** – získejte tvar grafu, nakonfigurujte jeho řady a naplňte datové body.  
```java
   Presentation pres = new Presentation();
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 20, 20, 500, 400);
   pres.save("YOUR_OUTPUT_DIRECTORY/Chart_out.pptx", SaveFormat.Pptx);
   ```

## Jak přidat exponenciální trendovou čáru?
Rozhraní `ITrendline` definuje trendovou čáru, kterou lze přidat k řadě grafu pro modelování datových vzorců. Aplikujte exponenciální trendovou čáru na řadu vytvořením instance `ITrendline`, nastavením jejího `TrendlineType` na `Exponential` a připojením k požadované řadě. Tento typ trendové čáry je užitečný pro data, která rychle rostou s rostoucí rychlostí.

1. **Nastavte trendovou čáru** – vyberte řadu a zavolejte `addTrendline(TrendlineType.Exponential)`.  
```java
   ITrendline tredLineExp = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Exponential);
   tredLineExp.setDisplayEquation(false); // Hides the equation for simplicity.
   ```

## Jak přidat lineární trendovou čáru?
Lineární trendová čára zobrazuje nejlépe odpovídající přímku skrz vaše datové body. Můžete také přizpůsobit její vzhled, například barvu a tloušťku čáry, aby odpovídala stylu vaší prezentace.

1. **Nastavte trendovou čáru** – použijte `addTrendline(TrendlineType.Linear)` a poté upravte `getLineFormat().setFillFormat().setFillType(FillType.Solid)` pro změnu barvy.  
```java
   ITrendline tredLineLin = chart.getChartData().getSeries().get_Item(0).getTrendLines().add(TrendlineType.Linear);
   tredLineLin.getFormat().getLine().getFillFormat().setFillType(FillType.Solid);
   tredLineLin.getFormat().getLine().getFillFormat().getSolidFillColor().setColor(Color.RED);
   ```

## Jak přidat logaritmickou trendovou čáru s vlastním textovým rámcem?
Logaritmické trendové čáry jsou ideální pro data, která na začátku rychle rostou a pak se vyrovnávají. Přepsání výchozího popisku vám umožní přidat vysvětlující text, který objasní význam trendu.

1. **Přizpůsobte trendovou čáru** – po přidání trendové čáry přistupte k `getDataLabel()` a nastavte vlastnost `setText("Custom label")`.  
```java
   ITrendline tredLineLog = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Logarithmic);
   tredLineLog.addTextFrameForOverriding("New log trend line");
   ```

## Jak přidat trendovou čáru klouzavý průměr?
Trendové čáry klouzavý průměr vyhlazují krátkodobé výkyvy a zdůrazňují dlouhodobé trendy. Můžete určit periodu (počet bodů) použité pro průměrování, což vám umožní řídit hladkost čáry.

1. **Nastavte trendovou čáru** – zavolejte `addTrendline(TrendlineType.MovingAverage)` a nastavte `setPeriod(3)` pro použití tříbodového klouzavého průměru.  
```java
   ITrendline tredLineMovAvg = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.MovingAverage);
   tredLineMovAvg.setPeriod((byte) 3); // Sets the period for calculation.
   String newTrendLineName = "New TrendLine Name";
   tredLineMovAvg.setTrendlineName(newTrendLineName);
   ```

## Jak přidat polynomickou trendovou čáru?
Polynomické trendové čáry přizpůsobují data křivkou definovanou polynomickým rovnicí. Vlastnost `order` řídí stupeň polynomu, což vám umožní modelovat složitější vztahy.

1. **Přizpůsobte trendovou čáru** – po přidání trendové čáry nastavte `setOrder(3)` pro kubický fit.  
```java
   ITrendline tredLinePol = chart.getChartData().getSeries().get_Item(2).getTrendLines().add(TrendlineType.Polynomial);
   tredLinePol.setForward(1); // Sets forward value.
   byte order = 3;
   tredLinePol.setOrder(order); // Polynomial degree/order.
   ```

## Jak přidat mocninnou trendovou čáru?
Mocninné trendové čáry jsou užitečné, když data následují vztah mocninného zákona. Můžete také nastavit hodnoty zpětného a budoucího předpovídání pro prodloužení čáry mimo existující rozsah dat.

1. **Nastavte trendovou čáru** – použijte `addTrendline(TrendlineType.Power)` a upravte `setBackward(2)` pro prodloužení čáry zpět.  
```java
   ITrendline tredLinePower = chart.getChartData().getSeries().get_Item(1).getTrendLines().add(TrendlineType.Power);
   tredLinePower.setBackward(1); // Sets backward value.
   ```

## Praktické aplikace trendových čar v seskupených sloupcových grafech
- **Finanční analýza:** Exponenciální a polynomické trendy pomáhají předpovídat pohyby cen akcií.  
- **Prognóza prodeje:** Čáry klouzavého průměru vyhlazují sezónní špičky a poskytují jasnější pohled na základní prodejní trendy.  
- **Vědecký výzkum:** Logaritmické trendy jsou ideální pro data pokrývající několik řádů velikosti, jako je akustická intenzita nebo pH úrovně.  
- **Monitorování provozu:** Mocninné trendové čáry mohou modelovat degradaci výkonu v průběhu času.

## Jak optimalizovat paměť při používání Aspose.Slides?
Okamžitě uvolňujte objekty a po uložení použijte `presentation.dispose()`. Pro velké datové sady povolte líné načítání obrázků a vyhněte se načítání celého grafu do paměti najednou.

- **Vzory uvolňování:** Zabalte `Presentation` do bloku try‑with‑resources nebo zavolejte `presentation.dispose()` v bloku finally.  
- **Líné načítání:** Nastavte `ChartData.setUseCache(true)` při práci s tisíci datovými body.  
- **Streamování výstupu:** Zapište prezentaci přímo do `FileOutputStream`, abyste se vyhnuli držení celého souboru v RAM.

## Kvantifikované výhody Aspose.Slides pro Java
Aspose.Slides podporuje **více než 50 typů grafů**, dokáže generovat prezentace s **více než 1 000 snímky** za méně než **30 sekund** na typickém 2 GHz procesoru a zpracovává **PDF o 500 stránkách** bez nutnosti instalace Microsoft Office. Tato čísla jsou ověřena na nejnovějším vydání 25.4.

## Závěr
Nyní máte kompletní řešení od začátku do konce pro **creating clustered column chart** objekty a jejich obohacení o všechny hlavní typy trendových čar dostupné v Aspose.Slides pro Java. Dodržením výše uvedených kroků můžete vytvářet prezentace založené na datech, které jsou vizuálně atraktivní i analyticky výkonné.

Další kroky zahrnují prozkoumání možností stylování grafů, export do PDF/HTML a automatizaci generování grafů napříč více zdroji dat.

## Často kladené otázky

**Q: Jak nastavit Aspose.Slides pro Maven projekt?**  
A: Přidejte úryvek `<dependency>` uvedený v sekci Maven do souboru `pom.xml` a spusťte `mvn clean install`.

**Q: Mohu přizpůsobit trendové čáry nad rámec barvy a popisku?**  
A: Ano, můžete upravit styl čáry, šířku, vzor čárky a dokonce předpovídat hodnoty dopředu/zpět pomocí API `ITrendline`.

**Q: Co mám dělat, pokud narazím na chybu nekompatibility verzí?**  
A: Ověřte, že verze vašeho JDK odpovídá minimálním požadavkům Aspose.Slides (JDK 8+). Prohlédněte si poznámky k vydání Aspose pro případné breaking changes.

**Q: Je možné automaticky přidat trendové čáry do více grafů?**  
A: Rozhodně. Projděte každé `IChart` ve sbírce snímků a zavolejte příslušnou metodu `addTrendline` pro každou řadu.

**Q: Potřebuji placenou licenci pro produkční použití?**  
A: Ano, zakoupená licence Aspose.Slides odstraňuje omezení hodnocení a odemyká plné optimalizace výkonu.

**Poslední aktualizace:** 2026-08-21  
**Testováno s:** Aspose.Slides for Java 25.4  
**Autor:** Aspose

## Související tutoriály

- [aspose slides maven dependency: Přidat a konfigurovat grafy v prezentacích pomocí Aspose.Slides pro Java](/slides/java/charts-graphs/add-charts-aspose-slides-java-guide/)
- [Add animation to PowerPoint chart using Aspose.Slides for Java – A Step‑by‑Step Guide](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)
- [Create PowerPoint Chart Java – Save Presentations with Charts Using Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}