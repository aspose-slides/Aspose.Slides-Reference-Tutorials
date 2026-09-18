---
date: '2026-09-17'
description: Naučte se, jak vytvořit bublinový graf v PowerPointu pomocí Aspose.Slides
  for Java. Tento průvodce vám ukáže, jak přidat graf do snímku, nastavit velikost
  bublin a efektivně uložit soubor PPTX.
keywords:
- create bubble chart powerpoint
- add chart to slide
- Aspose.Slides for Java tutorial
- bubble chart PowerPoint
- Java presentation automation
lastmod: '2026-09-17'
og_description: Naučte se, jak vytvořit bublinový graf v PowerPointu pomocí Aspose.Slides
  for Java. Tento tutoriál vysvětluje, jak přidat graf do snímku, upravit velikosti
  bublin a efektivně uložit prezentaci.
og_image_alt: 'Developer guide: create bubble chart powerpoint using Aspose.Slides
  for Java'
og_title: Vytvořte bublinový graf v PowerPointu pomocí Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-09-17'
  description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  headline: Create bubble chart powerpoint with Aspose.Slides for Java
  type: TechArticle
- description: Learn how to create bubble chart powerpoint using Aspose.Slides for
    Java. This guide shows you how to add chart to slide, configure bubble size, and
    save the PPTX efficiently.
  name: Create bubble chart powerpoint with Aspose.Slides for Java
  steps:
  - name: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
    text: '**Market analysis** – bubble size represents revenue while X/Y axes show
      growth and market share.'
  - name: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
    text: '**Performance metrics** – compare employee productivity (X), satisfaction
      (Y), and impact (size).'
  - name: '**Geographical data** – plot cities with population encoded in bubble size.'
    text: '**Geographical data** – plot cities with population encoded in bubble size.'
  - name: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
    text: '**Project management** – visualize timeline (X), cost (Y), and risk (size)
      on a single slide.'
  type: HowTo
- questions:
  - answer: Aspose.Slides for Java is a standalone library that lets you create, edit,
      and convert PowerPoint files without needing Microsoft Office.
    question: What is Aspose.Slides for Java?
  - answer: Add the Maven or Gradle dependency shown earlier, or drop the JAR into
      your classpath, then import `com.aspose.slides.*`.
    question: How do I integrate Aspose.Slides with my existing Java project?
  - answer: Yes, the library efficiently handles presentations up to **2 GB** and
      supports streaming to avoid loading the whole file into memory.
    question: Can I use Aspose.Slides for large presentations?
  - answer: Over **50 chart types** are supported, including bar, line, pie, radar,
      and waterfall charts.
    question: What chart types are available besides bubble charts?
  - answer: Absolutely. You can customize colors, fonts, borders, and data labels
      via the chart’s `ChartSeries` and `ChartTitle` objects.
    question: Is there built‑in support for styling chart elements?
  type: FAQPage
tags:
- create bubble chart
- Aspose.Slides
- Java charting
- PowerPoint automation
- slide graphics
title: Vytvořte bublinový graf v PowerPointu pomocí Aspose.Slides for Java
url: /cs/java/charts-graphs/create-bubble-charts-powerpoint-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Vytvořte bublinový graf PowerPoint s Aspose.Slides pro Java

## Úvod
Pokud potřebujete **vytvořit bublinový graf PowerPoint** prezentace programově, Aspose.Slides pro Java vám poskytuje čisté server‑side API, které funguje bez Microsoft Office. V tomto tutoriálu se naučíte, jak přidat graf na snímek, řídit velikosti bublin a uložit finální PPTX při efektivním řízení zdrojů. Kroky jsou rozděleny tak, abyste mohli kód zkopírovat‑vložit do jakéhokoli Java projektu a okamžitě vidět výsledky.

## Rychlé odpovědi
- **Jaká knihovna potřebuji?** Aspose.Slides for Java
- **Která verze Javy je vyžadována?** JDK 16 nebo vyšší
- **Jak přidám bublinový graf?** Zavolejte `addChart(ChartType.Bubble, …)` na snímek
- **Mohu změnit velikost bubliny?** Ano, pomocí `setBubbleSizeScale()`
- **Jak uložit soubor?** Použijte `pres.save("Result.pptx", SaveFormat.Pptx)`

## Co je vytvoření bublinového grafu PowerPoint?
Vytvoření bublinového grafu v PowerPointu znamená programově generovat graf, kde každý datový bod je reprezentován bublinou, jejíž X‑pozice, Y‑pozice a velikost kódují tři dimenze dat. Aspose.Slides pro Java zajišťuje vykreslování, takže nemusíte mít nainstalovaný PowerPoint.

## Proč používat Aspose.Slides pro Java?
Aspose.Slides podporuje **více než 50 typů grafů**, dokáže zpracovat prezentace až do **2 GB** bez načítání celého souboru do paměti a běží na libovolné platformě, která podporuje Java 16+. Tyto kvantifikované schopnosti z něj činí spolehlivou volbu pro podnikovou tvorbu reportů.

## Požadavky
- **Java Development Kit** 16 nebo novější nainstalovaný.
- **Aspose.Slides for Java** knihovna (přidejte pomocí Maven, Gradle nebo přímého stažení JAR).
- Základní znalost syntaxe Javy a objektově orientovaného programování.

## Nastavení Aspose.Slides pro Java
Pro zahájení používání Aspose.Slides zahrňte knihovnu do svého systému sestavení.

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
Zahrňte toto do svého `build.gradle`:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Můžete také získat nejnovější JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Získání licence
- **Free trial** – prozkoumejte všechny funkce zdarma.  
- **Temporary license** – rozšířené hodnocení pro větší projekty.  
- **Full license** – vyžadována pro nasazení do produkce.

### Základní inicializace a nastavení
Třída `Presentation` je vstupním bodem pro vytváření nebo načítání souborů PowerPoint.  
```java
// Initialize a new presentation
Presentation pres = new Presentation();
``` 
```java
import com.aspose.slides.Presentation;
```

## Průvodce implementací
Níže je podrobný krok‑za‑krokem průvodce vytvářením bublinového grafu a správou zdrojů.

## Jak vytvořit bublinový graf PowerPoint
V této sekci se naučíte přesné pořadí volání API potřebných k vygenerování bublinového grafu, nastavení jeho vizuálních vlastností a uložení výsledku jako soubor PPTX. Přístup funguje pro jakýkoli Java projekt, který zahrnuje Aspose.Slides a dodržuje osvědčené postupy správy zdrojů.

Načtěte prezentaci, přidejte bublinový graf, nakonfigurujte jeho vzhled a uložte soubor.

### Přímá odpověď
Vytvořte novou `Presentation`, zavolejte `addChart(ChartType.Bubble, …)` na požadovaném snímku, upravte měřítko velikosti bublin pomocí `setBubbleSizeScale(150)`, a poté uložte pomocí `pres.save("Result.pptx", SaveFormat.Pptx)`. Toto pořadí přidá plně funkční bublinový graf během několika řádků Javy.

- **`ChartType.Bubble`** představuje typ bublinového grafu.  
- **`addChart`** vloží nový graf zadaného typu na snímek.  
- **`setBubbleSizeScale`** upravuje celkovou velikost bublin v grafu.  
- **`SaveFormat.Pptx`** určuje formát souboru PPTX pro uložení.  

#### Implementace krok za krokem
**1. Inicializujte prezentaci** – vytvořte instanci objektu `Presentation`.  
```java
Presentation pres = new Presentation();
```

**2. Přidejte bublinový graf** – vložte graf na zvolené souřadnice.  
```java
IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
        ChartType.Bubble, 100, 100, 400, 300
);
```
- `ChartType.Bubble` říká Aspose.Slides, aby vytvořil bublinový graf.  
- Číselné parametry definují pozici X/Y a šířku/výšku v bodech.

**3. Nakonfigurujte měřítko velikosti bublin** – zvětšete bubliny pro lepší vizuální dopad.  
```java
chart.getChartData().getSeriesGroups().get_Item(0).setBubbleSizeScale(150);
```
- Nastavení měřítka na **150 %** způsobí, že každá bublina bude 1,5 × větší než výchozí.

**4. Uložte prezentaci** – zapište PPTX na disk.  
```java
pres.save("YOUR_OUTPUT_DIRECTORY/Result.pptx", SaveFormat.Pptx);
```

#### Tipy pro řešení problémů
- Ověřte oprávnění k zápisu do výstupní složky.  
- Potvrďte, že Aspose.Slides JAR odpovídá verzi JDK, kterou používáte.

## Jak efektivně spravovat zdroje PowerPointu
Efektivní správa zdrojů zabraňuje únikům paměti a udržuje nízkou zátěž JVM, zejména při zpracování velkých prezentací nebo běhu v serverovém prostředí. Postupujte podle níže uvedeného vzoru, abyste zajistili uvolnění nativních zdrojů i při výskytu výjimky.

Efektivní správa zdrojů zabraňuje únikům paměti, zejména při zpracování velkých prezentací.

### Přímá odpověď
Po dokončení práce s objektem `Presentation` vždy zavolejte `pres.dispose()` uvnitř bloku `try‑finally`; tím se uvolní nativní zdroje a JVM může rychle uvolnit paměť.

- **`pres.dispose()`** uvolňuje nativní zdroje použité prezentací.

**1. Vytvořte a upravte** – pracujte s prezentací podle potřeby.  
```java
Presentation pres = new Presentation();
```

**2. Uvolněte zdroje** – uvolněte paměť po dokončení zpracování.  
```java
if (pres != null) pres.dispose();
```

## Praktické aplikace
Bublinové grafy vynikají v situacích, kde je potřeba simultánně vizualizovat tři dimenze dat:

1. **Analýza trhu** – velikost bubliny představuje příjmy, zatímco osy X/Y ukazují růst a podíl na trhu.  
2. **Měřítka výkonnosti** – porovnejte produktivitu zaměstnanců (X), spokojenost (Y) a dopad (velikost).  
3. **Geografická data** – zobrazte města s populací zakódovanou ve velikosti bubliny.  
4. **Projektové řízení** – vizualizujte časovou osu (X), náklady (Y) a riziko (velikost) na jednom snímku.

## Úvahy o výkonu
- **Využití zdrojů** – uvolňujte prezentace okamžitě, aby byl nízký využití haldy.  
- **Správa paměti v Javě** – obalte práci s prezentací do `try‑finally`, aby bylo zajištěno uvolnění i při výjimkách.  
- **Zůstaňte aktuální** – upgradujte na nejnovější verzi Aspose.Slides, abyste získali výhody optimalizací výkonu a oprav chyb.

## Často kladené otázky

**Q: Co je Aspose.Slides pro Java?**  
A: Aspose.Slides pro Java je samostatná knihovna, která vám umožní vytvářet, upravovat a konvertovat soubory PowerPoint bez potřeby Microsoft Office.

**Q: Jak integrovat Aspose.Slides do mého existujícího Java projektu?**  
A: Přidejte Maven nebo Gradle závislost uvedenou dříve, nebo vložte JAR do classpath, poté importujte `com.aspose.slides.*`.

**Q: Mohu použít Aspose.Slides pro velké prezentace?**  
A: Ano, knihovna efektivně zpracovává prezentace až do **2 GB** a podporuje streamování, aby se zabránilo načítání celého souboru do paměti.

**Q: Jaké typy grafů jsou k dispozici kromě bublinových grafů?**  
A: Podporováno je více než **50 typů grafů**, včetně sloupcových, čárových, koláčových, radarových a vodopádových grafů.

**Q: Existuje vestavěná podpora pro stylování prvků grafu?**  
A: Rozhodně. Můžete přizpůsobit barvy, písma, okraje a popisky dat pomocí objektů `ChartSeries` a `ChartTitle` grafu.

## Zdroje
- **Dokumentace**: [Aspose.Slides Documentation](https://reference.aspose.com/slides/java/)  
- **Stáhnout**: [Aspose.Slides Releases](https://releases.aspose.com/slides/java/)  
- **Koupit**: [Buy Aspose.Slides](https://purchase.aspose.com/buy)  
- **Bezplatná zkušební verze**: [Start with a Free Trial](https://releases.aspose.com/slides/java/)  
- **Dočasná licence**: [Get a Temporary License](https://purchase.aspose.com/temporary-license/)  
- **Podpora**: [Aspose Support Forum](https://forum.aspose.com/c/slides/11)

---

**Poslední aktualizace:** 2026-09-17  
**Testováno s:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose

## Související tutoriály

- [Jak přidat graf do PowerPointu pomocí Aspose.Slides pro Java: Průvodce krok za krokem](/slides/java/charts-graphs/add-charts-powerpoint-aspose-slides-java-guide/)
- [Java vytvořit PowerPoint graf pomocí Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-chart-manipulation/)
- [Vytvořit PowerPoint graf v Javě – Uložit prezentace s grafy pomocí Aspose.Slides](/slides/java/charts-graphs/aspose-slides-java-save-presentations-charts/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}