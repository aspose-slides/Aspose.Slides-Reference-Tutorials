---
"date": "2025-04-17"
"description": "Naučte se, jak vytvářet a upravovat dynamické burzovní grafy v PowerPointu pomocí Aspose.Slides pro Javu. Tato příručka se zabývá inicializací prezentací, přidáváním datových řad, formátováním grafů a ukládáním souborů."
"title": "Vytváření dynamických burzovních grafů v PowerPointu s Aspose.Slides pro Javu"
"url": "/cs/java/charts-graphs/dynamic-stock-charts-powerpoint-aspose-slides-java/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Vytváření dynamických burzovních grafů v PowerPointu s Aspose.Slides pro Javu

## Zavedení

Vylepšete své prezentace v PowerPointu začleněním dynamických akciových grafů. Ať už jste finanční analytik, obchodní profesionál nebo pedagog, který potřebuje efektivně vizualizovat trendy v datech, tento tutoriál vás provede vytvářením a úpravou akciových grafů pomocí Aspose.Slides pro Javu. Po čtení tohoto průvodce budete schopni načítat existující soubory PowerPointu, přidávat podrobné akciové grafy s vlastními sériemi a kategoriemi, krásně je formátovat a ukládat vylepšené prezentace.

**Co se naučíte:**
- Inicializace prezentace v Javě pomocí Aspose.Slides
- Přidání a přizpůsobení burzovních grafů
- Vymazat datové řady a kategorie
- Vložení nových datových bodů pro komplexní analýzu
- Efektivní formátování čar a sloupců grafu
- Uložit aktualizovanou prezentaci

Jste připraveni vytvářet vizuálně poutavé prezentace? Pojďme na to!

## Předpoklady

Než začneme, ujistěte se, že máte následující:

- **Vývojová sada pro Javu (JDK)**Ujistěte se, že je ve vašem systému nainstalováno JDK.
- **IDE**Pro psaní a spouštění kódu v Javě použijte libovolné IDE, jako je IntelliJ IDEA nebo Eclipse.
- **Aspose.Slides pro knihovnu Java**Tento tutoriál vyžaduje verzi 25.4 Aspose.Slides pro Javu.

### Nastavení Aspose.Slides pro Javu

#### Znalec
Chcete-li integrovat Aspose.Slides do svého projektu pomocí Mavenu, přidejte do svého souboru následující závislost `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle
Pro uživatele Gradle, zahrňte toto do svého `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Přímé stažení
Nebo si stáhněte nejnovější JAR soubor z [Aspose.Slides pro verze Java](https://releases.aspose.com/slides/java/).

**Získání licence**Můžete začít s bezplatnou zkušební verzí nebo požádat o dočasnou licenci. Pro delší používání zvažte zakoupení plné licence.

## Průvodce implementací

Pojďme si rozebrat každou funkci krok za krokem.

### Inicializovat prezentaci
#### Přehled
Začněte načtením existujícího souboru PowerPointu, abyste jej připravili na úpravy.

#### Podrobný průvodce
1. **Import knihovny**:
   
   ```java
   import com.aspose.slides.Presentation;
   ```

2. **Načíst soubor s prezentací**:
   
   ```java
   String documentDirectory = "YOUR_DOCUMENT_DIRECTORY";
   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       // Připraveno k provádění operací na 'pres'
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Přidat burzovní graf na snímek
#### Přehled
Tento krok zahrnuje přidání burzovního grafu na první snímek prezentace.

3. **Přidat graf**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.ChartType;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Vymazat existující datové řady a kategorie v grafu
#### Přehled
Odeberte z grafu všechny existující datové řady nebo kategorie a začněte znovu.

4. **Vymazat data**:
   
   ```java
   import com.aspose.slides.IChart;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       chart.getChartData().getSeries().clear();
       chart.getChartData().getCategories().clear();
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Přidání kategorií k datům grafu
#### Přehled
Přidejte vlastní kategorie pro lepší segmentaci a pochopení dat.

5. **Vložit kategorie**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();
       
       // Přidat kategorie
       chart.getChartData().getCategories().add(wb.getCell(0, 1, 0, "A"));
       chart.getChartData().getCategories().add(wb.getCell(0, 2, 0, "B"));
       chart.getChartData().getCategories().add(wb.getCell(0, 3, 0, "C"));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Přidat datovou řadu do grafu
#### Přehled
Pro komplexní analýzu integrujte různé datové řady, jako například otevírací, nejvyšší, nejnižší a uzavírací.

6. **Přidat datovou řadu**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Přidat série pro „Otevřeno“, „Vysoké“, „Nízké“ a „Zavřít“
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 1, "Open"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 2, "High"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 3, "Low"), chart.getType());
       chart.getChartData().getSeries().add(wb.getCell(0, 0, 4, "Close"), chart.getType());
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Přidání datových bodů do série
#### Přehled
Pro přesné znázornění naplňte každou sérii specifickými datovými body.

7. **Vložit datové body**:
   
   ```java
   import com.aspose.slides.IChart;
   import com.aspose.slides.IChartDataWorkbook;

   Presentation pres = new Presentation(documentDirectory + "/Test.pptx");
   try {
       IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
           ChartType.OpenHighLowClose, 50, 50, 600, 400, false);
       IChartDataWorkbook wb = chart.getChartData().getChartDataWorkbook();

       // Přidání datových bodů do série „Otevřít“
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 1, 72));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 1, 25));
       chart.getChartData().getSeries().get_Item(0).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 1, 38));

       // Přidat datové body do série „Vysoká“
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 2, 172));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 2, 57));
       chart.getChartData().getSeries().get_Item(1).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 2, 57));

       // Přidání datových bodů do řady „Nízká“
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 3, 12));
       chart.getChartData().getSeries().get_Item(2).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 3, 13));

       // Přidat datové body do série „Uzavření“
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 1, 4, 25));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 2, 4, 38));
       chart.getChartData().getSeries().get_Item(3).getDataPoints().addDataPointForStockCategory(wb.getCell(0, 3, 4, 50));
   } finally {
       if (pres != null) pres.dispose();
   }
   ```

### Formátování čar s horní a dolní hranicí a vzestupných/dolních sloupců
#### Přehled
Pro lepší vizualizaci si můžete přizpůsobit vzhled čar s horní a dolní hranicí a ukazatelů nahoru/dolů.

8. **Formátování čar s horní a dolní hranicí**:
   
   ```java
   import com.aspose.slides.FillType;
   import java.awt.Color;

   // Formátování čar s horní a dolní hranicí pro sérii „Uzavření“
   LineFormat highLowLine = chart.getChartData().getSeriesGroups().get_Item(0).getHiLowLinesFormat();
   highLowLine.getFillFormat().setFillType(FillType.Solid);
   highLowLine.getFillFormat().getSolidFillColor().setColor(Color.GRAY);
   ```

9. **Zobrazit nahoru/dolů ukazatele**:
   
   ```java
   // Zobrazit sloupce nahoru/dolů pro skupinu sérií burzovních grafů
   chart.getChartData().getSeriesGroups().get_Item(0).setHasUpDownBars(true);
   ```

### Přizpůsobení popisků dat na řádcích s nejvyšší a nejnižší hodnotou
#### Přehled
Přidejte a naformátujte popisky dat pro zobrazení hodnot na úsecích s nejvyšší a nejnižší hodnotou.

10. **Zobrazit hodnoty na ukazatelích nahoru/dolů**:
    
    ```java
    // Zobrazit hodnoty na nahoru/dolů pro každou sérii ve skupině grafů
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getLabels().getDefaultDataLabelFormat().setShowValue(true);
    }
    ```

### Nastavení barvy výplně dolních pruhů
#### Přehled
Nastavte vlastní barvu výplně pro horní/dolní pruhy pro vylepšení vizuálního rozlišení.

11. **Změna barev nahoru/dolů**:
    
    ```java
    // Změna barev nahoru/dolů pro každou sérii ve skupině grafů
    for (IChartSeries ser : chart.getChartData().getSeries()) {
        ser.getFormat().getFill().setFillType(FillType.Solid);
        if (ser == chart.getChartData().getSeries().get_Item(0)) { // Série „Otevřeno“
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.CYAN); // Tyčinky nahoru v azurové barvě
        } else if (ser == chart.getChartData().getSeries().get_Item(1)) { // Série „Vysoká“
            ser.getFormat().getFill().getSolidFillColor().setColor(Color.DARKSEAGREEN); // Svislé tyče v tmavě mořské zelené barvě
        }
    }
    ```

### Uložte soubor PowerPointu
#### Přehled
Uložte změny do nového souboru PowerPointu.

12. **Uložit prezentaci**:
    
    ```java
    pres.save("Add_Stock_Chart.pptx", com.aspose.slides.SaveFormat.Pptx);
    ```

## Závěr

Gratulujeme! Úspěšně jste vytvořili a upravili dynamické akciové grafy v PowerPointu pomocí Aspose.Slides pro Javu. Tento proces vylepšuje vaše prezentace vizuálně atraktivními vizualizacemi dat, což vám umožní efektivně sdělovat finanční informace. Pokud máte zájem o další úpravy nebo prozkoumání jiných typů grafů, zvažte ponoření se do komplexního [Dokumentace k Aspose.Slides](https://docs.aspose.com/slides/java/).

## Další četba a reference
- Dokumentace k Aspose.Slides pro Javu: Prozkoumejte podrobné návody k používání různých funkcí Aspose.Slides.
- Přehled nástrojů pro tvorbu grafů v PowerPointu: Seznamte se s různými nástroji pro tvorbu grafů dostupnými v aplikaci Microsoft PowerPoint.
- Nejlepší postupy pro vizualizaci dat: Naučte se, jak efektivně prezentovat data vizuálně.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}