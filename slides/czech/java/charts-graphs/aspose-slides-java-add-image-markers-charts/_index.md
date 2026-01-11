---
date: '2026-01-11'
description: Naučte se, jak používat Aspose Slides pro Javu, přidávat obrázkové značky
  do grafů a konfigurovat Mavenovou závislost Aspose Slides pro vlastní vizuály grafů.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Jak používat Aspose Slides Java: Přidat obrázkové značky do grafů'
url: /cs/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak používat Aspose Slides pro Java: Přidání obrázkových značek do grafů

## Úvod
Vytváření vizuálně atraktivních prezentací je klíčové pro efektivní komunikaci a grafy jsou mocným nástrojem, jak stručně předat složitá data. Když se ptáte **jak použít Aspose**, aby vaše grafy vynikly, odpovědí jsou vlastní obrázkové značky. Standardní značky mohou působit genericky, ale s Aspose.Slides pro Java je můžete nahradit libovolným obrázkem — každý datový bod tak bude okamžitě rozpoznatelný.

V tomto tutoriálu projdeme celý proces přidání obrázkových značek do čárového grafu, od nastavení **Aspose Slides Maven závislosti** až po načtení obrázků a jejich aplikaci na datové body. Na konci budete jistě ovládat **jak přidat značky**, **jak přidat obrázky do řady grafu** a získáte připravený ukázkový kód.

**Co se naučíte**
- Jak nastavit Aspose.Slides pro Java (včetně Maven/Gradle)
- Vytvoření základní prezentace a grafu
- Přidání obrázkových značek k datovým bodům grafu
- Konfiguraci velikosti a stylu značek pro optimální vizualizaci

Připravení posunout své grafy na vyšší úroveň? Pojďme nejprve projít předpoklady, než začneme!

### Rychlé odpovědi
- **Jaký je hlavní cíl?** Přidat vlastní obrázkové značky k datovým bodům grafu.  
- **Která knihovna je vyžadována?** Aspose.Slides pro Java (Maven/Gradle).  
- **Potřebuji licenci?** Dočasná licence stačí pro hodnocení; plná licence je nutná pro produkci.  
- **Jaká verze Javy je podporována?** JDK 16 nebo novější.  
- **Mohu použít libovolný formát obrázku?** Ano — PNG, JPEG, BMP atd., pokud je soubor přístupný.

### Předpoklady
Pro sledování tohoto tutoriálu potřebujete:
1. **Aspose.Slides pro Java knihovnu** — získáte ji přes Maven, Gradle nebo přímým stažením.  
2. **Vývojové prostředí Javy** — nainstalované JDK 16 nebo novější.  
3. **Základní znalosti programování v Javě** — znalost syntaxe a konceptů Javy vám usnadní práci.

## Co je Aspose Slides Maven závislost?
Maven závislost stáhne správné binární soubory pro vaši verzi Javy. Přidáním do souboru `pom.xml` zajistíte, že knihovna bude k dispozici během kompilace i běhu.

### Instalace přes Maven
Přidejte následující závislost do souboru `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalace přes Gradle
Vložte tento řádek do souboru `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Alternativně můžete stáhnout nejnovější verzi z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### Kroky pro získání licence
- **Bezplatná zkušební verze** — začněte s dočasnou licencí a prozkoumejte funkce.  
- **Dočasná licence** — odemkne pokročilé možnosti během testování.  
- **Koupě** — získejte plnou licenci pro komerční projekty.

## Základní inicializace a nastavení
Nejprve vytvořte objekt `Presentation`. Tento objekt představuje celý soubor PowerPoint a bude obsahovat náš graf.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Průvodce implementací
Níže najdete krok‑za‑krokem návod, jak přidat obrázkové značky do grafu. Každý blok kódu je doprovázen vysvětlením, abyste pochopili **proč** je daný řádek důležitý.

### Krok 1: Vytvoření nové prezentace s grafem
Přidáme čárový graf s výchozími značkami na první snímek.

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Initialize the Presentation object
        Presentation presentation = new Presentation();

        // Get the first slide from the collection
        ISlide slide = presentation.getSlides().get_Item(0);

        // Add a default line chart with markers to the slide
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Krok 2: Přístup a konfigurace dat grafu
Vymažeme výchozí řady a přidáme vlastní řadu, připravíme list pro vlastní datové body.

```java
import com.aspose.slides.*;

public class ManageChartData {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();

        // Clear existing series and add a new one
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Krok 3: Přidání obrázkových značek k datovým bodům grafu  
Ukážeme **jak přidat značky** pomocí obrázků. Nahraďte zástupné cesty skutečnou polohou vašich obrázků.

```java
import com.aspose.slides.*;

public class AddImageMarkers {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Add data points with images as markers
        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 2, 1, (double) 2.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 3, 1, (double) 3.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 4, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx2);
    }
}
```

### Krok 4: Nastavení velikosti značky a uložení prezentace  
Upravíme styl značky pro lepší viditelnost a zapíšeme finální soubor PPTX.

```java
import com.aspose.slides.*;

public class ConfigureAndSavePresentation {
    public static void main(String[] args) throws IOException {
        Presentation presentation = new Presentation();
        ISlide slide = presentation.getSlides().get_Item(0);

        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );

        int defaultWorksheetIndex = 0;
        IChartDataWorkbook fact = chart.getChartData().getChartDataWorkbook();
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );

        // Load and add images as markers (example using placeholder paths)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        // Adjust marker style for the whole series
        series.setMarkerStyleType(MarkerStyleType.Circle);
        series.setMarkerSize(10);

        // Save the presentation
        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Časté problémy a řešení
- **FileNotFoundException** — Ověřte, že cesty k obrázkům (`YOUR_DOCUMENT_DIRECTORY/...`) jsou správné a soubory existují.  
- **LicenseException** — Ujistěte se, že před voláním jakéhokoli API v produkci máte nastavenou platnou Aspose licenci.  
- **Značka není viditelná** — Zvyšte hodnotu `setMarkerSize` nebo použijte obrázky s vyšším rozlišením pro jasnější zobrazení.

## Často kladené otázky

**Q: Mohu místo JPEG použít PNG obrázky pro značky?**  
A: Ano, libovolný formát podporovaný Aspose.Slides (PNG, JPEG, BMP, GIF) funguje jako značka.

**Q: Potřebuji licenci pro Maven/Gradle balíčky?**  
A: Dočasná licence stačí pro vývoj a testování; plná licence je vyžadována pro komerční distribuci.

**Q: Lze přidat různé obrázky ke každému datovému bodu ve stejné řadě?**  
A: Rozhodně. V příkladu `AddImageMarkers` střídáme dva obrázky, ale můžete načíst unikátní obrázek pro každý bod.

**Q: Jak `aspose slides maven dependency` ovlivňuje velikost projektu?**  
A: Maven balíček obsahuje jen potřebné binární soubory pro zvolenou verzi JDK, takže velikost zůstává rozumná. Pokud je velikost kritická, můžete použít verzi **no‑dependencies**.

**Q: Jaké verze Javy jsou podporovány?**  
A: Aspose.Slides pro Java podporuje JDK 8 až JDK 21. Příklad používá JDK 16, ale můžete upravit klasifikátor podle potřeby.

## Závěr
Po přečtení tohoto návodu víte **jak používat Aspose** k obohacení grafů o vlastní obrázkové značky, jak nastavit **Aspose Slides Maven závislost** a jak **přidat obrázky do řady grafu** pro profesionální vzhled. Experimentujte s různými ikonami, velikostmi a typy grafů a vytvořte prezentace, které skutečně vyniknou.

---

**Poslední aktualizace:** 2026-01-11  
**Testováno s:** Aspose.Slides pro Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}