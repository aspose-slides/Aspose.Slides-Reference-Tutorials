---
"date": "2025-04-17"
"description": "Naučte se, jak v Javě vytvářet spojnicové grafy se značkami pomocí Aspose.Slides. Tento tutoriál se zabývá vytvářením grafů, sčítáním řad a efektivním ukládáním prezentací."
"title": "Vytvořte spojnicové grafy s výchozími značkami pomocí Aspose.Slides pro Javu"
"url": "/cs/java/charts-graphs/create-line-charts-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytvořte spojnicové grafy s výchozími značkami pomocí Aspose.Slides pro Javu
## Zavedení
Vytváření vizuálně poutavých a informativních grafů je nezbytné pro prezentace, reporty a dashboardy. Automatizace tohoto procesu ve vývoji softwaru šetří čas a zajišťuje konzistenci napříč dokumenty. Tento tutoriál ukazuje, jak vytvářet spojnicové grafy se značkami pomocí Aspose.Slides pro Javu.
**Aspose.Slides pro Javu** je výkonná knihovna, která umožňuje vývojářům programově manipulovat s prezentacemi v PowerPointu bez nutnosti instalace Microsoft Office. Zjednodušuje úkoly, jako je vytváření, úprava a export snímků, což z ní činí nezbytný nástroj pro automatizované generování dokumentů.
**Co se naučíte:**
- Jak inicializovat Aspose.Slides pro Javu
- Kroky k vytvoření spojnicového grafu se značkami
- Přidávání řad a kategorií do grafů
- Konfigurace legend grafu
- Ukládání prezentace
Jste připraveni se do toho pustit? Nejdříve se ujistěte, že máte vše připravené!
## Předpoklady
Než začneme, ujistěte se, že je vaše vývojové prostředí připravené:
1. **Knihovny a závislosti:**
   - Knihovna Aspose.Slides pro Javu (doporučena verze 25.4)
   - Vývojářská sada Java (JDK) verze 16 nebo vyšší
2. **Nastavení prostředí:**
   - Vaše IDE by mělo podporovat nástroje pro sestavování Maven nebo Gradle.
   - V případě potřeby se ujistěte, že máte platný licenční soubor.
3. **Předpoklady znalostí:**
   - Základní znalost programování v Javě
   - Znalost tvorby projektů pomocí Mavenu nebo Gradle
S tímto hotovým si pojďme nastavit Aspose.Slides pro váš projekt!
## Nastavení Aspose.Slides pro Javu
Chcete-li používat Aspose.Slides pro Javu, musíte jej zahrnout jako závislost ve vašem projektu. Nastavení se bude mírně lišit v závislosti na tom, zda používáte Maven nebo Gradle.
### Znalec
Přidejte do svého `pom.xml` soubor:
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```
### Gradle
Zahrňte toto do svého `build.gradle` soubor:
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```
### Přímé stažení
Případně si můžete stáhnout nejnovější verzi z [Aspose.Slides pro verze Java](https://releases.aspose.com/slides/java/).
**Kroky pro získání licence:**
- Pro bezplatnou zkušební verzi navštivte [stránka s bezplatnou zkušební verzí](https://releases.aspose.com/slides/java/).
- Chcete-li získat dočasnou licenci, přejděte na [stránka s dočasnou licencí](https://purchase.aspose.com/temporary-license/).
- Zakupte si plnou licenci prostřednictvím jejich [nákupní portál](https://purchase.aspose.com/buy).
**Základní inicializace:**
Zde je návod, jak inicializovat Aspose.Slides ve vaší aplikaci Java:
```java
import com.aspose.slides.Presentation;
// Inicializace nového prezentačního objektu
Presentation pres = new Presentation();
```
A teď se pojďme pustit do tvorby grafů!
## Průvodce implementací
### Funkce 1: Vytvoření grafu s výchozími značkami
Tato část ukazuje, jak vytvořit spojnicový graf vybavený značkami. Tato funkce je nezbytná pro efektivní vizualizaci datových trendů.
#### Přidání spojnicového grafu
Chcete-li přidat spojnicový graf se značkami:
```java
import com.aspose.slides.*;
// Přístup k prvnímu snímku
ISlide slide = pres.getSlides().get_Item(0);
// Přidat spojnicový graf se značkami na snímek na pozici (10, 10) o velikosti (400, 400)
IChart chart = slide.getShapes().addChart(
    ChartType.LineWithMarkers, 10, 10, 400, 400);
```
#### Vymazání sérií a kategorií
Pro nový začátek:
```java
// Vyčistěte stávající série a kategorie a zajistěte tak čistý seznam
chart.getChartData().getSeries().clear();
chart.getChartData().getCategories().clear();
// Získejte datový sešit grafu pro další manipulaci
IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
```
### Funkce 2: Přidání sérií a kategorií
Přidávání řad a kategorií je klíčové pro naplnění grafů smysluplnými daty.
#### Vytvoření nové série
Chcete-li přidat novou sérii s názvem „Série 1“:
```java
// Přidat do grafu novou řadu
chart.getChartData().getSeries().add(fact.getCell(0, 0, 1, "Series 1"), chart.getType());
// Přístup k první sérii pro naplnění dat
IChartSeries series = chart.getChartData().getSeries().get_Item(0);
```
#### Naplňování kategorií a datových bodů
Přidání kategorií a odpovídajících datových bodů:
```java
// Přidejte názvy kategorií a jejich příslušné datové body
chart.getChartData().getCategories().add(fact.getCell(0, 1, 0, "C1"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 1, 24));

chart.getChartData().getCategories().add(fact.getCell(0, 2, 0, "C2"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 1, 23));

chart.getChartData().getCategories().add(fact.getCell(0, 3, 0, "C3"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 1, -10));

// Elegantní zpracování nulových datových bodů
chart.getChartData().getCategories().add(fact.getCell(0, 4, 0, "C4"));
series.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 1, null));
```
### Funkce 3: Přidání druhé série a naplnění datových bodů
Přidání dalších řad dodá vašim grafům větší hloubku.
#### Vytvoření a naplnění druhé série
Chcete-li přidat „Sérii 2“:
```java
// Přidat další sérii s názvem „Série 2“
chart.getChartData().getSeries().add(fact.getCell(0, 0, 2, "Series 2"), chart.getType());

// Přístup k druhé sérii pro naplnění dat
IChartSeries series2 = chart.getChartData().getSeries().get_Item(1);

// Přidat datové body pro „Sérii 2“
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 1, 2, 30));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 2, 2, 10));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 3, 2, 60));
series2.getDataPoints().addDataPointForLineSeries(fact.getCell(0, 4, 2, 40));
```
### Funkce 4: Konfigurace legendy grafu
Konfigurace legendy zlepšuje čitelnost grafu.
#### Úprava nastavení legendy
Konfigurace:
```java
// Povolte legendu a nastavte ji tak, aby se nezobrazovala přes datové body
chart.setLegend(true);
chart.getLegend().setOverlay(false);
```
### Funkce 5: Uložení prezentace
Jakmile je graf připravený, uložte prezentaci do souboru.
```java
try {
    // Uložit upravenou prezentaci do zadaného adresáře
    pres.save("YOUR_DOCUMENT_DIRECTORY/DefaultMarkersInChart.pptx");
} finally {
    if (pres != null) pres.dispose();
}
```
## Praktické aplikace
1. **Obchodní reporting:**
   - Používejte grafy ve finančních výkazech k zobrazení trendů v čase.
2. **Analýza dat:**
   - Vizualizujte datové vzorce a korelace během fází analýzy.
3. **Vzdělávací materiály:**
   - Vytvářejte informativní slajdy pro akademické přednášky nebo prezentace.
4. **Řízení projektu:**
   - Vylepšete časové osy projektů pomocí vizuálních prvků grafu.
5. **Marketingové prezentace:**
   - Efektivně prezentujte trendy prodeje a výsledky kampaní pomocí grafů.
## Závěr
Naučili jste se, jak v Javě vytvářet spojnicové grafy se značkami pomocí Aspose.Slides, přidávat řady a kategorie, konfigurovat legendy a ukládat prezentace. Tyto dovednosti jsou cenné pro vytváření dynamického vizuálního obsahu v různých profesionálních aplikacích.
Chcete-li se dozvědět více o funkcích Aspose.Slides nebo vyhledat podporu komunity, navštivte jejich [oficiální dokumentace](https://docs.aspose.com/slides/java/) nebo se připojte k fórům jako Stack Overflow.
Šťastné kódování!

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}