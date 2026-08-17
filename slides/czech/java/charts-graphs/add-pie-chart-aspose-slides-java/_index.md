---
date: '2026-05-29'
description: Naučte se, jak vytvořit pie chart pomocí Aspose.Slides Maven, přidat
  pie chart java do snímku a přizpůsobit data grafu. Podrobný návod krok za krokem
  s nastavením Maven a reálnými příklady.
keywords:
- create pie chart aspose
- add pie chart java
- add chart slide
- aspose slides maven example
schemas:
- author: Aspose
  dateModified: '2026-05-29'
  description: Learn how to create pie chart aspose using Aspose.Slides Maven, add
    pie chart java to a slide, and customize chart data. Step‑by‑step guide with Maven
    setup and real‑world examples.
  headline: Create Pie Chart Aspose – Add a Chart to a Presentation with Maven
  type: TechArticle
- questions:
  - answer: Use the Maven or Gradle dependency shown above, or download the library
      from the releases page.
    question: How do I install Aspose.Slides for Java?
  - answer: JDK 16 or later; the library runs on any platform that supports Java.
    question: What are the system requirements for Aspose.Slides?
  - answer: Yes, Aspose.Slides supports bar, line, scatter, radar, and more than 20
      chart types.
    question: Can I add other chart types besides pie charts?
  - answer: Dispose of objects promptly, limit high‑resolution images, and reuse chart
      templates to keep memory usage low.
    question: How should I handle large presentations efficiently?
  - answer: Visit the [Aspose documentation](https://reference.aspose.com/slides/java/)
      for a complete API reference.
    question: Where can I find more details about Aspose.Slides features?
  type: FAQPage
title: Vytvořit Pie Chart Aspose – Přidat Chart do prezentace pomocí Maven
url: /cs/java/charts-graphs/add-pie-chart-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak přidat koláčový graf do prezentace pomocí Aspose.Slides Java

## Úvod
V tomto průvodci **vytvoříte koláčový graf aspose** pomocí Aspose.Slides Maven a uvidíte, jak jej vložit do snímku PowerPoint. Vytváření vizuálně atraktivních prezentací je klíčové pro efektivní předávání informací, zejména když hraje datová vizualizace zásadní roli. Pokud chcete tento proces automatizovat pomocí **aspose slides maven**, jste na správném místě. Provedeme vás přidáním grafu do snímku — konkrétně koláčového grafu — a jeho přizpůsobením pro reálné scénáře.

### Co se naučíte
- Jak inicializovat objekt prezentace v Javě.  
- Kroky k **přidání koláčového grafu java** na první snímek prezentace.  
- Přístup k sešitu s daty grafu a výpis listů v něm.  

Ponořme se do toho, jak můžete využít Aspose.Slides Java k vylepšení svých prezentací pomocí dynamických grafů!

## Rychlé odpovědi
- **Jaká knihovna přidává grafy přes Maven?** aspose slides maven  
- **Jaký typ grafu je předveden?** Pie chart (add chart to slide)  
- **Minimální požadovaná verze Javy?** JDK 16 nebo novější  
- **Potřebuji licenci pro testování?** Free trial funguje; pro produkci je licence potřeba  
- **Kde najdu Maven závislost?** In the setup section below  

## Co je Aspose Slides Maven?
Aspose.Slides pro Java je výkonné API, které umožňuje vývojářům programově vytvářet, upravovat a renderovat soubory PowerPoint. Maven balíček (`aspose-slides`) zjednodušuje správu závislostí, což vám umožní soustředit se na tvorbu a přizpůsobení snímků — například přidání koláčového grafu — bez nutnosti řešit nízkoúrovňové zpracování souborů.

## Proč použít Aspose.Slides Maven k přidání grafu do snímku?
Použití Aspose.Slides Maven vám umožní generovat grafy přímo z Java kódu bez ruční úpravy PowerPointu. Poskytuje úplnou programovou kontrolu nad typy grafů, zdroji dat a stylováním, což zajišťuje konzistentní značku a přesnost. Maven artefakt také spravuje všechny potřebné závislosti, zjednodušuje sestavení a umožňuje bezproblémovou integraci do CI/CD pipeline.

## Požadavky
- **Aspose.Slides pro Java** verze 25.4 nebo novější (Maven/Gradle).  
- JDK 16+ nainstalováno.  
- IDE (IntelliJ IDEA, Eclipse, atd.).  
- Základní znalost Javy a povědomí o Maven nebo Gradle.

## Nastavení Aspose.Slides pro Java
Nejprve zahrňte Aspose.Slides do svého projektu pomocí Maven nebo Gradle.

**Maven:**  
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
</dependency>
```
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle:**  
```groovy
implementation 'com.aspose:aspose-slides:25.4'
```
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativně můžete [stáhnout nejnovější verzi](https://releases.aspose.com/slides/java/) přímo z webu Aspose.

### Získání licence
Aspose.Slides pro Java nabízí bezplatnou zkušební verzi s dočasnou licencí pro testování. Pro neomezené používání v produkci zakupte licenci prostřednictvím [stránky nákupu](https://purchase.aspose.com/buy).

## Průvodce implementací
Níže rozdělujeme řešení do dvou funkcí: přidání koláčového grafu a přístup k jeho datovému sešitu.

### Funkce 1: Vytvoření prezentace a přidání grafu
#### Přehled
Tato část ukazuje, jak vytvořit novou prezentaci a **přidat koláčový graf** na první snímek.

#### Jak vytvořit koláčový graf aspose?
Načtěte třídu `Presentation`, přidejte graf typu `ChartType.Pie` a soubor uložte. Celá operace vyžaduje pouze tři volání API a běží za méně než sekundu pro typickou prezentaci s 10 snímky, což je ideální pro automatizovanou generaci reportů.

#### Krok za krokem

**Krok 1: Inicializace nového objektu Presentation**  
`Presentation` třída je hlavní objekt Aspose.Slides, který v paměti představuje soubor PowerPoint.  
```java
Presentation pres = new Presentation();
```
*Vytváří instanci `Presentation`, která bude obsahovat všechny snímky.*

**Krok 2: Přidání koláčového grafu**  
`ChartType.Pie` říká Aspose, aby vykreslil koláčový graf.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
    ChartType.Pie,
    50,
    50,
    400,
    500
);
```
*Umístí koláčový graf na souřadnice (50, 50) s šířkou 400 a výškou 500.*

**Krok 3: Uvolnění prostředků**  
Volání `dispose()` uvolní nativní prostředky a zabrání únikům paměti.  
```java
if (pres != null) pres.dispose();
```
*Uvolňuje nativní prostředky; vždy zavolejte `dispose()`, když jste hotovi.*

### Funkce 2: Přístup k datovému sešitu grafu a listům
#### Přehled
Naučte se, jak získat podkladový sešit, který ukládá data grafu, a iterovat přes jeho listy.

#### Jak získat přístup k datovému sešitu grafu?
Získejte `IChartDataWorkbook` z grafu a poté projděte jeho kolekci `Worksheets`. Tento sešit napodobuje soubor Excel, což vám umožní programově číst, upravovat nebo přidávat datové řady, které graf okamžitě zobrazí po aktualizaci během běhu bez restartu.

**Krok 1: (Znovupoužití) Inicializace nového objektu Presentation**  
*Stejné jako Funkce 1, Krok 1.*

**Krok 2: (Znovupoužití) Přidání koláčového grafu**  
*Stejné jako Funkce 1, Krok 2.*

**Krok 3: Získání datového sešitu grafu**  
`IChartDataWorkbook` je rozhraní, které poskytuje čtení/zápis přístup k internímu Excel‑podobnému sešitu grafu.  
```java
IChartDataWorkbook workbook = chart.getChartData().getChartDataWorkbook();
```
*Získává `IChartDataWorkbook` spojený s grafem.*

**Krok 4: Procházení listů**  
Objekty `Worksheet` představují jednotlivé listy uvnitř sešitu.  
```java
for (int i = 0; i < workbook.getWorksheets().size(); i++) {
    System.out.println(workbook.getWorksheets().get_Item(i).getName());
}
```
*Vypisuje název každého listu, což vám umožní ověřit strukturu dat.*

**Krok 5: Uvolnění prostředků**  
*Stejné jako Funkce 1, Krok 3.*

## Praktické aplikace
- **Data Reporting:** Automatické generování balíčků snímků s aktuálními metrikami pro business intelligence.  
- **Akademické prezentace:** Vizualizace výsledků výzkumu bez ruční tvorby grafů.  
- **Marketingový materiál:** Okamžité představení výkonu produktu nebo výsledků průzkumu.

## Úvahy o výkonu
- Aspose.Slides dokáže zpracovat **více než 50 vstupních a výstupních formátů** a zpracovat prezentace s stovkami stránek, aniž by načítal celý soubor do paměti.  
- Udržujte rozumný počet snímků a grafů; každý graf spotřebovává nativní paměť.  
- Vždy volejte `dispose()`, aby se prostředky rychle uvolnily.  
- Optimalizujte práci s daty sešitu — vyhněte se načítání obrovských datových sad do jednoho grafu.

## Závěr
Probrali jsme, jak **aspose slides maven** umožňuje **programově přidat graf do snímku** a jak pracovat s datovým sešitem grafu. S těmito stavebními bloky můžete automatizovat jakýkoli reportingový workflow, který vyžaduje profesionální výstup PowerPoint.

### Další kroky
- Prozkoumejte možnosti stylování grafu (barvy, legendy, datové popisky).  
- Připojte se k externím zdrojům dat (CSV, databáze) pro dynamické naplňování grafů.  
- Kombinujte více typů grafů v jedné prezentaci pro bohatší vyprávění.

## Často kladené otázky

**Q: Jak nainstaluji Aspose.Slides pro Java?**  
A: Použijte Maven nebo Gradle závislost uvedenou výše, nebo si stáhněte knihovnu ze stránky vydání.

**Q: Jaké jsou systémové požadavky pro Aspose.Slides?**  
A: JDK 16 nebo novější; knihovna běží na libovolné platformě, která podporuje Javu.

**Q: Mohu přidat jiné typy grafů kromě koláčových?**  
A: Ano, Aspose.Slides podporuje sloupcové, čárové, rozptylové, radarové a více než 20 typů grafů.

**Q: Jak efektivně zacházet s velkými prezentacemi?**  
A: Okamžitě uvolňujte objekty, omezte vysoké rozlišení obrázků a znovu používejte šablony grafů, aby byl nízký odběr paměti.

**Q: Kde najdu podrobnější informace o funkcích Aspose.Slides?**  
A: Navštivte [Aspose dokumentaci](https://reference.aspose.com/slides/java/) pro kompletní referenci API.

**Q: Je licence vyžadována pro komerční použití?**  
A: Pro produkci je vyžadována platná licence; pro vyhodnocení je k dispozici bezplatná zkušební verze.

**Q: Obsahuje Maven balíček všechny možnosti grafů?**  
A: Ano, Maven artefakt `aspose-slides` obsahuje kompletní grafický engine.

## Zdroje
- Dokumentace: [Aspose.Slides Java API Reference](https://reference.aspose.com/slides/java/)
- Stáhnout: [Latest Releases](https://releases.aspose.com/slides/java/)
- Nákup a zkušební verze: [Purchase Page](https://purchase.aspose.com/buy)
- Bezplatná zkušební verze: [Trial Downloads](https://releases.aspose.com/slides/java/)
- Dočasná licence: [Request a Temporary License](https://purchase.aspose.com/temporary-license/)
- Fórum podpory: [Aspose Community Forum](https://forum.aspose.com/c/slides/11)

---  

**Last Updated:** 2026-05-29  
**Tested With:** Aspose.Slides 25.4 for Java (jdk16)  
**Author:** Aspose

## Související tutoriály

- [Jak přizpůsobit barvy koláčového grafu v Javě pomocí Aspose.Slides – Kompletní průvodce](/slides/java/charts-graphs/aspose-slides-java-pie-charts-tutorial/)
- [Vytvoření grafu Pie of Pie v Javě s Aspose.Slides: Komplexní průvodce](/slides/java/charts-graphs/create-pie-of-pie-chart-aspose-slides-java/)
- [Animace grafů v PowerPointu pomocí Aspose.Slides pro Java – Průvodce krok za krokem](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}