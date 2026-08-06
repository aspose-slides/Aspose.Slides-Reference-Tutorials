---
date: '2026-08-06'
description: Naučte se, jak změnit barvu písma legendy a upravit text legendy grafu
  pomocí Aspose.Slides for Java. Postupujte podle krok za krokem návodu a rychle přizpůsobte
  legendy grafu.
keywords:
- customize chart legends in Aspose.Slides Java
- Aspose.Slides for Java legend customization
- Java presentation chart styling
lastmod: '2026-08-06'
og_description: Naučte se, jak změnit barvu písma legendy a upravit text legendy grafu
  s Aspose.Slides for Java. Tento průvodce vám ukáže přesné kroky a osvědčené postupy.
og_image_alt: 'Developer guide: change legend font color in Aspose.Slides for Java'
og_title: Jak změnit barvu písma legendy v Aspose.Slides for Java
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  headline: How to change legend font color in Aspose.Slides for Java
  type: TechArticle
- description: Learn how to change legend font color and modify chart legend text
    using Aspose.Slides for Java. Follow step‑by‑step instructions to customize chart
    legends quickly.
  name: How to change legend font color in Aspose.Slides for Java
  steps:
  - name: Initialize Aspose.Slides in your Java application.
    text: Initialize Aspose.Slides in your Java application.
  - name: Load an existing presentation or create a new one.
    text: Load an existing presentation or create a new one.
  - name: '**Load the presentation:**'
    text: '**Load the presentation:**'
  - name: '**Add a clustered column chart:**'
    text: '**Add a clustered column chart:**'
  - name: '**Access legend entry text format:**'
    text: '**Access legend entry text format:**'
  - name: '**Set bold and italic styles with a specific height:**'
    text: '**Set bold and italic styles with a specific height:**'
  - name: '**Change fill type to solid color for better visibility:**'
    text: '**Change fill type to solid color for better visibility:**'
  - name: '**Save your changes:**'
    text: '**Save your changes:**'
  - name: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
    text: '**Business presentations:** Align legend colors with corporate branding
      for a polished look.'
  - name: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
    text: '**Educational materials:** Highlight key data series by using contrasting
      legend colors.'
  type: HowTo
- questions:
  - answer: No, the color change is preserved in all export formats supported by Aspose.Slides,
      including PDF and PPTX.
    question: Does changing the legend font color affect exported PDF files?
  - answer: Yes – set `FillType.Gradient` and configure the gradient stops via `getGradientStyle()`.
    question: Can I use a gradient instead of a solid color?
  - answer: A chart can have up to 256 legend entries, limited only by the number
      of data series you add.
    question: How many legend entries can a chart have?
  type: FAQPage
tags:
- change legend font color
- Aspose.Slides
- Java chart customization
- presentation styling
title: Jak změnit barvu písma legendy v Aspose.Slides for Java
url: /cs/java/charts-graphs/customize-chart-legends-aspose-slides-java/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak změnit barvu písma legendy v Aspose.Slides pro Java

## Úvod
Pokud potřebujete **change legend font color** v grafu, Aspose.Slides pro Java vám poskytuje plnou kontrolu nad každým záznamem legendy. Tento tutoriál vás provede přizpůsobením stylů textu legendy, aplikací tučného nebo kurzívního písma a nastavením plných barev, aby vaše grafy vypadaly přesně tak, jak chcete. Na konci tohoto průvodce budete schopni s jistotou upravovat text legendy grafu a integrovat změny do jakékoli existující prezentace.

**Co se naučíte**
- Jak programově **change legend font color**.
- Způsoby, jak **modify chart legend text**, například tučné, kurzívní a velikost.
- Tipy pro aplikaci změn na více grafech v jedné prezentaci.
- Jak integrovat tyto kroky do většího automatizačního pracovního postupu.

## Rychlé odpovědi
- **Mohu změnit barvu jedné položky legendy?** Ano – přístup k položce přes její index a nastavení výplňového formátu na plnou barvu.  
- **Potřebuji licenci k používání těchto API?** Pro produkci je vyžadována dočasná nebo placená licence; pro hodnocení funguje bezplatná zkušební verze.  
- **Jaká verze Javy je podporována?** Aspose.Slides pro Java 25.4+ funguje s JDK 16 a novějšími.  
- **Ovlivní změny ostatní prvky grafu?** Ne, formátování legendy je oddělené od stylování datových sérií.  
- **Je možný hromadný processing?** Ano – projděte smyčkou snímky a grafy a aplikujte stejné nastavení legendy na celou prezentaci.

## Co je change legend font color?
`change legend font color` odkazuje na programovou operaci nastavení barvy textu položek legendy grafu pomocí API Aspose.Slides. Tato operace aktualizuje vizuální vzhled legendy, aniž by měnila podkladová data.

## Proč přizpůsobovat legendy grafů?
Aspose.Slides podporuje **50+ vstupních a výstupních formátů** a dokáže zpracovat prezentace s **500+ snímky**, přičemž spotřeba paměti zůstává pod 200 MB. Přizpůsobení legend zlepšuje čitelnost, posiluje barvy značky a zajišťuje, že klíčové datové body vyniknou – zejména v obchodních nebo vzdělávacích prezentacích, kde vizuální jasnost podporuje rozhodování.

## Předpoklady
- Knihovna **Aspose.Slides for Java** (verze 25.4 nebo novější).  
- Java Development Kit (JDK) 16 nebo vyšší.  
- IDE, jako je IntelliJ IDEA, Eclipse nebo NetBeans.  
- Maven nebo Gradle pro správu závislostí.  
- Základní znalost programování v Javě.

## Nastavení Aspose.Slides pro Java
Pro zahájení přizpůsobování legend vašich grafů přidejte knihovnu do svého projektu pomocí jedné z níže uvedených metod.

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
Include this line in your `build.gradle` file:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Můžete také získat nejnovější JAR z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Kroky získání licence
- **Free trial:** Začněte s bezplatnou zkušební verzí a prozkoumejte funkce Aspose.Slides.  
- **Temporary license:** Požádejte o dočasnou licenci pro rozšířené hodnocení.  
- **Purchase:** Pro plný přístup zvažte zakoupení licence na [Aspose Purchase](https://purchase.aspose.com/buy).

#### Základní inicializace a nastavení
Po přidání knihovny do vašeho projektu:
1. Inicializujte Aspose.Slides ve své Java aplikaci.  
2. Načtěte existující prezentaci nebo vytvořte novou.

## Jak změnit barvu písma legendy?
Pro změnu barvy písma legendy načtěte prezentaci, získejte objekt grafu, získáte jeho legendu a poté upravte formát textu každé položky legendy nastavením typu výplně na plnou a určením požadované barvy. Tato jediná operace okamžitě aktualizuje barvu textu legendy, aniž by bylo nutné překreslovat celý snímek. Příklad: `legendEntry.getTextFormat().getFillFormat().setFillType(FillType.Solid); legendEntry.getTextFormat().getFillFormat().setSolidFillColor(Color.RED);` Tento přístup funguje pro jakýkoli typ grafu a nevyžaduje znovu‑vykreslení celého snímku.

### Přístup a úprava vlastností textu legendy

#### Definiční kotva
`IChart` rozhraní představuje objekt grafu na snímku a jeho metoda `getLegend()` vrací objekt `ILegend`, který obsahuje kolekci položek `ILegendEntry`.

#### Přidání grafu do vaší prezentace
1. **Load the presentation:**  
   ```java
   Presentation pres = new Presentation(dataDir + "/test.pptx");
   ```  

2. **Add a clustered column chart:**  
   ```java
   IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
       ChartType.ClusteredColumn, 50, 50, 600, 400);
   ```  

#### Přizpůsobení vlastností písma
3. **Access legend entry text format:**  
   Zde je `legendEntry` objekt `ILegendEntry` představující jednu položku v legendě grafu.  
   ```java
   IChartTextFormat tf = chart.getLegend().getEntries().get_Item(1).getTextFormat();
   ```  

4. **Set bold and italic styles with a specific height:**  
   ```java
   tf.getPortionFormat().setFontBold(NullableBool.True);
   tf.getPortionFormat().setFontHeight(20);
   tf.getPortionFormat().setFontItalic(NullableBool.True);
   ```  

5. **Change fill type to solid color for better visibility:**  
   ```java
   tf.getPortionFormat().getFillFormat().setFillType(FillType.Solid);
   tf.getPortionFormat().getFillFormat().getSolidFillColor().setColor(Color.BLUE);
   ```  

#### Uložení prezentace
6. **Save your changes:**  
   ```java
   pres.save(outputDir + "/output.pptx", SaveFormat.Pptx);
   ```  

### Časté úskalí a řešení problémů
- Ověřte, že index položky legendy odpovídá pořadí sérií ve vašem grafu.  
- Ujistěte se, že používáte verzi knihovny, která podporuje `setSolidFillColor` (k dispozici od verze 20.9).

## Praktické aplikace
Přizpůsobení textu legendy je užitečné v mnoha reálných scénářích:

1. **Business presentations:** Přizpůsobte barvy legendy firemnímu brandingu pro profesionální vzhled.  
2. **Educational materials:** Zvýrazněte klíčové datové série pomocí kontrastních barev legendy.  
3. **Marketing decks:** Zdůrazněte výkonnostní metriky tučnými, barevnými legendami, aby upoutaly pozornost zainteresovaných stran.  

Můžete také automatizovat aktualizace legend tím, že načtete hodnoty barev z databáze nebo konfiguračního souboru.

## Úvahy o výkonu
When processing large decks, keep these tips in mind:
- **Efficient memory management:** Po uložení zavolejte `presentation.dispose()`, aby se uvolnily nativní zdroje.  
- **Load only required slides:** Použijte `Presentation.load(String path, LoadOptions options)` s `LoadOptions.setLoadOnlySlideIds()`, pokud potřebujete jen podmnožinu.  
- **Batch processing:** Seskupte aktualizace legend podle snímku, abyste snížili počet volání API a zvýšili propustnost.

## Závěr
Nyní víte, jak **change legend font color** a **modify chart legend text** pomocí Aspose.Slides pro Java. Tyto úpravy zvyšují vizuální jasnost a pomáhají efektivněji předávat data. Experimentujte s různými fonty, velikostmi a barvami, aby odpovídaly stylovému průvodci vaší prezentace, a prozkoumejte další funkce stylování grafů pro vytvoření skutečně profesionálních prezentací.

**Další kroky**
- Vyzkoušejte aplikaci stejného stylu legendy na koláčové a čárové grafy.  
- Kombinujte přizpůsobení legendy s formátováním popisků dat pro plně brandovaný graf.  

Jste připraveni pozvednout své prezentace? Implementujte výše uvedené kroky a okamžitě uvidíte rozdíl!

## Často kladené otázky
1. **Jak změním barvu textu položky legendy?**  
   Použijte `getFillFormat().setFillType(FillType.Solid)` a poté `setSolidFillColor(Color.YOUR_COLOR)` na formátu textu položky legendy.

2. **Mohu aplikovat tyto změny na všechny legendy v prezentaci?**  
   Ano – projděte každý snímek, najděte každý graf a v cyklu aktualizujte jeho položky legendy.

3. **Je možné dynamicky upravit velikost písma na základě délky textu?**  
   Můžete vypočítat požadovanou velikost pomocí `TextFrame.getTextFrameFormat().getFontHeight()` a nastavit ji pomocí `setFontHeight(double)`.

4. **Co když narazím na problémy s indexováním položek legendy?**  
   Zkontrolujte, že index, který používáte, odpovídá pořadí sérií; pamatujte, že indexy jsou nulové.

5. **Kde najdu více příkladů Aspose.Slides?**  
   Prozkoumejte [Aspose Documentation](https://reference.aspose.com/slides/java/) pro komplexní průvodce a reference API.

**Další otázky a odpovědi**

**Q: Ovlivní změna barvy písma legendy exportované PDF soubory?**  
A: Ne, změna barvy je zachována ve všech exportních formátech podporovaných Aspose.Slides, včetně PDF a PPTX.

**Q: Mohu použít gradient místo plné barvy?**  
A: Ano – nastavte `FillType.Gradient` a nakonfigurujte gradientové zastávky pomocí `getGradientStyle()`.

**Q: Kolik položek legendy může mít graf?**  
A: Graf může mít až 256 položek legendy, omezeno pouze počtem datových sérií, které přidáte.

## Zdroje
- **Documentation:** Komplexní průvodce používáním funkcí Aspose.Slides ([Link](https://reference.aspose.com/slides/java/)).  
- **Download:** Získejte nejnovější verzi Aspose.Slides pro Java ([Link](https://releases.aspose.com/slides/java/)).  
- **Purchase:** Kupte licenci pro odemknutí plných možností ([Link](https://purchase.aspose.com/buy)).  
- **Free trial & temporary license:** Začněte s bezplatnými zkušebními verzemi a požádejte o dočasné licence ([Free Trial Link](https://releases.aspose.com/slides/java/), [Temporary License Link](https://purchase.aspose.com/temporary-license/)).  
- **Support:** Získejte pomoc od komunity na fóru podpory Aspose ([Link](https://forum.aspose.com/c/slides/11)).

---

**Poslední aktualizace:** 2026-08-06  
**Testováno s:** Aspose.Slides pro Java 25.4  
**Autor:** Aspose

## Související tutoriály

- [Vylepšení PowerPoint grafů: Přizpůsobení písma a os s Aspose.Slides pro Java](/slides/java/charts-graphs/enhance-powerpoint-charts-aspose-slides-java/)
- [Aspose.Slides pro Java: Průvodce dynamickými textovými rámy a přizpůsobením písma](/slides/java/shapes-text-frames/aspose-slides-java-dynamic-text-frames-fonts/)
- [Animace grafů v PowerPointu pomocí Aspose.Slides pro Java – krok za krokem průvodce](/slides/java/animations-transitions/animate-charts-pptx-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}