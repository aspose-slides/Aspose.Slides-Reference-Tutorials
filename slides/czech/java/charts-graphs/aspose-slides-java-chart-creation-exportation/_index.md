---
date: '2026-02-09'
description: Naučte se, jak vytvořit graf a exportovat jej do Excelu pomocí Aspose.Slides
  pro Javu. Ovládněte vizualizaci dat, obchodní prezentační snímky a generování sešitu.
keywords:
- Aspose.Slides Java
- creating charts in Java
- exporting chart data with Aspose
title: Jak vytvořit graf pomocí Aspose.Slides Java
url: /cs/java/charts-graphs/aspose-slides-java-chart-creation-exportation/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak vytvořit graf pomocí Aspose.Slides for Java

**Ovládněte techniky vizualizace dat s Aspose.Slides for Java**

V dnešním prostředí řízeném daty je programové *jak vytvořit graf* dovednost, která dokáže proměnit surová čísla v poutavé vizuální příběhy. Ať už vytváříte prezentaci obchodní zprávy nebo interaktivní analytický dashboard, Aspose.Slides for Java vám poskytuje možnost generovat, přizpůsobovat a exportovat grafy přímo z kódu. V tomto tutoriálu se naučíte, jak vytvořit objekty grafu, exportovat data grafu do Excelu a propojit grafy s externími sešity pro bezproblémovou správu dat.

## Rychlé odpovědi
- **Jaká knihovna je potřeba?** Aspose.Slides for Java (v25.4+).  
- **Mohu exportovat data grafu do Excelu?** Ano – použijte `readWorkbookStream()` a zapište bajty do souboru *.xlsx*.  
- **Jaká verze Javy je vyžadována?** JDK 16 nebo vyšší.  
- **Potřebuji licenci?** Bezplatná zkušební licence stačí pro hodnocení; pro produkci je vyžadována trvalá licence.  
- **Jaký typ grafu je předveden?** Koláčový graf, ale stejný postup funguje i pro sloupcové, čárové a další typy grafů.

## Co je Aspose.Slides for Java?
Aspose.Slides for Java je čistě Java API, které umožňuje vývojářům vytvářet, upravovat a konvertovat PowerPoint prezentace bez Microsoft Office. Podporuje kompletní škálu typů grafů, vazbu dat a exportní možnosti, což z něj činí ideální řešení pro projekty **data visualization java**.

## Proč použít Aspose.Slides k vytvoření grafu a exportu grafu do Excelu?
- **Žádná instalace Office** – funguje na jakémkoli serveru nebo cloudovém prostředí.  
- **Bohatá knihovna grafů** – desítky typů grafů a plná kontrola stylování.  
- **Přímý export do Excelu** – generuje externí sešit pro následnou analýzu.  
- **Výkonnostně orientované** – nízká spotřeba paměti a rychlé zpracování velkých prezentací.

## Předpoklady
Než se pustíme dál, ujistěte se, že máte následující:

### Požadované knihovny a verze
- **Aspose.Slides for Java** verze 25.4 nebo novější

### Požadavky na nastavení prostředí
- Java Development Kit (JDK) 16 nebo vyšší  
- IDE jako IntelliJ IDEA nebo Eclipse (nebo jakýkoli textový editor, který preferujete)

### Předpoklady znalostí
- Základní programovací dovednosti v Javě  
- Znalost nástrojů pro sestavení Maven nebo Gradle

## Nastavení Aspose.Slides for Java
Přidejte knihovnu do svého projektu pomocí vašeho oblíbeného systému sestavení.

**Maven**
```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

**Gradle**
```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

Alternativně můžete [stáhnout nejnovější verzi přímo](https://releases.aspose.com/slides/java/).

### Kroky získání licence
Aspose.Slides nabízí bezplatnou zkušební licenci pro vyzkoušení všech funkcí. Můžete také požádat o dočasnou licenci nebo si zakoupit licenci pro delší používání. Postupujte podle těchto kroků:

1. Navštivte [stránku nákupu Aspose](https://purchase.aspose.com/buy) a získejte licenci.  
2. Pro bezplatnou zkušební verzi stáhněte z [Releases](https://releases.aspose.com/slides/java/).  
3. Požádejte o dočasnou licenci [zde](https://purchase.aspose.com/temporary-license/).

Jakmile máte soubor licence, inicializujte jej ve své Java aplikaci:

```java
com.aspose.slides.License license = new com.aspose.slides.License();
license.setLicense("path/to/your/license/file.lic");
```

## Průvodce krok za krokem

### Jak vytvořit graf – Načtení prezentace
Načtení existujícího souboru PowerPoint je prvním krokem, než můžete přidávat nebo upravovat grafy.

```java
import com.aspose.slides.Presentation;

public class Feature1 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        // Load an existing presentation
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        
        // Clean up resources
        if (pres != null) pres.dispose();
    }
}
```

**Vysvětlení:**  
- `Presentation` představuje soubor PowerPoint.  
- Vždy zavolejte `dispose()`, aby se uvolnily nativní zdroje.

### Jak vytvořit graf – Přidání koláčového grafu do snímku
Nyní vložíme koláčový graf, který je ideální pro zobrazování proporčních dat.

```java
import com.aspose.slides.ChartType;
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature2 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Add a Pie chart at position (50, 50) with width 400 and height 600
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                ChartType.Pie, 50, 50, 400, 600);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Vysvětlení:**  
- `addChart` vloží graf na první snímek.  
- Parametry definují typ grafu, pozici X/Y a velikost.

### Jak exportovat graf do Excelu – Export dat grafu
Exportování dat grafu umožňuje analytikům pracovat s čísly v Excelu, což poskytuje hlubší vhled.

```java
import com.aspose.slides.IChart;
import java.io.File;
import java.io.FileOutputStream;
import java.io.IOException;
import java.io.FileNotFoundException;
import com.aspose.slides.Presentation;

public class Feature3 {
    public static void main(String[] args) {
        // Set the path to your document directory and output directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            File file = new File(externalWbPath);
            if (file.exists()) file.delete();
            
            // Export chart data to an Excel stream
            byte[] workbookData = chart.getChartData().readWorkbookStream();
            FileOutputStream outputStream = new FileOutputStream(file);
            outputStream.write(workbookData);
            outputStream.close();
        } catch (FileNotFoundException e) {
            e.printStackTrace();
        } catch (IOException e) {
            e.printStackTrace();
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Vysvětlení:**  
- `readWorkbookStream()` získá podkladový Excel sešit grafu jako pole bajtů.  
- Pole bajtů je zapsáno do `externalWorkbook1.xlsx`, čímž získáte připravený Excel soubor.

### Jak vytvořit graf – Nastavení externího sešitu pro dynamická data
Propojení grafu s externím sešitem vám umožní aktualizovat graf pouhým úpravou souboru Excel.

```java
import com.aspose.slides.IChart;
import com.aspose.slides.Presentation;

public class Feature4 {
    public static void main(String[] args) {
        // Set the path to your document directory
        String dataDir = "YOUR_DOCUMENT_DIRECTORY";
        
        Presentation pres = new Presentation(dataDir + "/presentation.pptx");
        try {
            // Access the first slide's chart
            IChart chart = pres.getSlides().get_Item(0).getShapes().addChart(
                com.aspose.slides.ChartType.Pie, 50, 50, 400, 600);
            
            // Define and set the path for the external workbook
            String externalWbPath = dataDir + "/externalWorkbook1.xlsx";
            chart.getChartData().setExternalWorkbook(externalWbPath);
        } finally {
            if (pres != null) pres.dispose();
        }
    }
}
```

**Vysvětlení:**  
- `setExternalWorkbook` sváže graf se zadaným Excel souborem, což umožňuje živé aktualizace dat bez nutnosti přestavovat snímek.

## Praktické aplikace
Aspose.Slides nabízí univerzální řešení pro různé reálné scénáře:

1. **Obchodní zprávy – snímky:** Automaticky generujte čtvrtletní výkonnostní grafy z vašich datových kanálů.  
2. **Akademické prezentace:** Převádějte výzkumná data na přehledné vizualizace bez ručního vytváření grafů.  
3. **Finanční analýza:** Exportujte data grafu do Excelu pro auditory k ověření čísel.  
4. **Marketingová analytika:** Vizualizujte metriky kampaní a sdílejte editovatelné sešity se zainteresovanými stranami.

## Časté problémy a řešení
- **`FileNotFoundException`** – Ověřte, že `dataDir` ukazuje na existující složku a že výstupní cesta je zapisovatelná.  
- **Úniky paměti** – Vždy zavolejte `pres.dispose()` v bloku `finally`, aby se uvolnily nativní zdroje.  
- **Graf se nezobrazuje** – Ujistěte se, že index snímku (`get_Item(0)`) odpovídá skutečně existujícímu snímku.

## Často kladené otázky

**Q: Mohu použít jiný typ grafu (např. Bar, Line) se stejným kódem?**  
A: Ano. Nahraďte `ChartType.Pie` libovolnou jinou hodnotou výčtu `ChartType`, například `ChartType.Bar` nebo `ChartType.Line`.

**Q: Je možné aktualizovat externí sešit po vytvoření grafu?**  
A: Rozhodně. Přímo upravte soubor Excel; propojený graf odrazí změny při dalším otevření prezentace.

**Q: Potřebuji samostatnou licenci pro funkci exportu do Excelu?**  
A: Ne. Funkce exportu do Excelu je součástí standardní licence Aspose.Slides for Java.

**Q: Jaké verze Javy jsou podporovány?**  
A: Aspose.Slides for Java podporuje JDK 16 a novější; starší verze mohou fungovat, ale nejsou oficiálně testovány.

**Q: Jak mohu vložit vygenerovaný Excel sešit do souboru PPTX?**  
A: Použijte `chart.getChartData().setExternalWorkbook(null)` pro vložení sešitu, nebo ponechte externí odkaz pro dynamické aktualizace.

---

**Poslední aktualizace:** 2026-02-09  
**Testováno s:** Aspose.Slides for Java 25.4 (jdk16 classifier)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}