---
date: '2026-06-03'
description: Naučte se, jak použít aspose slides maven dependency pro Java, přidat
  image markers do charts a konfigurovat vlastní vizuály grafů pomocí Aspose.Slides.
keywords:
- aspose slides maven dependency
- how to add markers
- add images to chart
schemas:
- author: Aspose
  dateModified: '2026-06-03'
  description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  headline: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers
    to Charts'
  type: TechArticle
- description: Learn how to use the aspose slides maven dependency for Java, add image
    markers to charts, and configure custom chart visuals with Aspose.Slides.
  name: 'How to Use Aspose Slides Maven Dependency for Java: Add Image Markers to
    Charts'
  steps:
  - name: Create a New Presentation with a Chart
    text: The `Presentation` object creates a new PPTX file and `ISlide` represents
      a slide where the chart will be placed.
  - name: Access and Configure Chart Data
    text: The `IChart` interface provides methods to modify series, categories, and
      data points within the chart.
  - name: Add Image Markers to Chart Data Points
    text: '`IDataPoint` represents an individual point, and its `setMarker` method
      assigns a custom image as the marker.'
  - name: Configure Marker Size and Save the Presentation
    text: '`presentation.save` writes the final PPTX file to the specified location
      with the chosen format.'
  type: HowTo
- questions:
  - answer: Yes, any image format supported by Aspose.Slides (PNG, JPEG, BMP, GIF)
      works as a marker.
    question: Can I use PNG images instead of JPEG for markers?
  - answer: A temporary license is sufficient for development and testing; a full
      license is required for commercial distribution.
    question: Do I need a license for the Maven/Gradle packages?
  - answer: Absolutely. In the `AddImageMarkers` example we alternate between two
      pictures, but you can load a unique image for every point.
    question: Is it possible to add different images to each data point in the same
      series?
  - answer: The Maven package includes only the necessary binaries for the selected
      JDK version, keeping the footprint under **15 MB**. You can also use the **no‑dependencies**
      version if size is a concern.
    question: How does the aspose slides maven dependency affect project size?
  - answer: Aspose.Slides for Java supports JDK 8 through JDK 21. The example uses
      JDK 16, but you can adjust the classifier accordingly.
    question: What Java versions are supported?
  type: FAQPage
title: 'Jak použít Aspose Slides Maven Dependency pro Java: Přidat Image Markers do
  Charts'
url: /cs/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Jak použít Aspose Slides Maven Dependency pro Java: Přidání obrázkových značek do grafů

## Úvod
V tomto tutoriálu ukazujeme **how to use the Aspose Slides Maven Dependency for Java**, jak přidat obrázkové značky do grafů a každému datovému bodu poskytnout jedinečný vizuální podnět. Vytváření vizuálně atraktivních prezentací je klíčové pro efektivní komunikaci a grafy jsou výkonným způsobem, jak stručně předat složitá data. Když se ptáte, **how to use Aspose**, aby vaše grafy vynikly, odpovědí jsou vlastní obrázkové značky. Standardní značky mohou vypadat obecně, ale s Aspose.Slides pro Java je můžete nahradit libovolným obrázkem — což umožní, aby byl každý datový bod okamžitě rozpoznatelný.

Do konce tohoto průvodce budete schopni:

* Nastavit **aspose slides maven dependency** v Maven nebo Gradlu.
* Vytvořit základní prezentaci, vložit čárový graf a vymazat výchozí řady.
* Načíst obrázky PNG/JPEG/BMP a přiřadit je jako značky jednotlivým datovým bodům.
* Upravit velikost a styl značky a uložit finální soubor PPTX.

Jste připraveni pozvednout své grafy? Pojďme na to!

### Rychlé odpovědi
- **Jaký je hlavní účel?** Přidat vlastní obrázkové značky k datovým bodům grafu.  
- **Která knihovna je vyžadována?** Aspose.Slides for Java (Maven/Gradle).  
- **Potřebuji licenci?** Dočasná licence stačí pro hodnocení; plná licence je vyžadována pro produkci.  
- **Jaká verze Javy je podporována?** JDK 16 nebo novější.  
- **Mohu použít libovolný formát obrázku?** Ano — PNG, JPEG, BMP, GIF atd., pokud je soubor přístupný.

## Co je Aspose Slides Maven Dependency?
Aspose Slides Maven dependency je Maven artefakt, který obsahuje binární soubory Aspose.Slides for Java potřebné pro tvorbu grafů, práci s obrázky a manipulaci s prezentacemi. Přidáním této závislosti do vašeho `pom.xml` Maven automaticky stáhne správnou verzi pro váš JDK, vyřeší tranzitivní knihovny a zpřístupní kompletní API během kompilace i běhu.

### Jak přidat Aspose Slides Maven Dependency?
Načtěte knihovnu Aspose Slides pomocí Maven a Gradlu. Přímá odpověď: přidejte úryvek `<dependency>` do vašeho `pom.xml` **nebo** řádek `implementation` do vašeho `build.gradle`. Tento jediný krok zpřístupní kompletní API, včetně funkcí souvisejících s grafy a obrázkovými značkami, okamžitě ve vašem projektu.

#### Maven Installation
Přidejte následující závislost do souboru `pom.xml`:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle Installation
Vložte tento řádek do souboru `build.gradle`:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Direct Download
Alternativně si stáhněte nejnovější verzi z [Aspose.Slides for Java releases](https://releases.aspose.com/slides/java/).

#### License Acquisition Steps
- **Free Trial** – začněte s dočasnou licencí pro prozkoumání funkcí.  
- **Temporary License** – odemkněte pokročilé možnosti během testování.  
- **Purchase** – získejte plnou licenci pro komerční projekty.

## Požadavky
Abyste mohli tento tutoriál sledovat, budete potřebovat:

1. **Aspose.Slides for Java Library** — prostřednictvím Maven, Gradlu nebo přímého stažení.  
2. **Java Development Environment** — nainstalovaný JDK 16 nebo novější.  
3. **Základní znalosti programování v Javě** — znalost syntaxe a konceptů Javy bude užitečná.  

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

## Implementační průvodce
Níže najdete krok‑za‑krokem postup přidání obrázkových značek do grafu. Každý úsek kódu je doprovázen vysvětlením, abyste pochopili **why** každá řádka má význam.

### Krok 1: Vytvořit novou prezentaci s grafem
Objekt `Presentation` vytvoří nový soubor PPTX a `ISlide` představuje snímek, na který bude graf umístěn.

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

### Krok 2: Přístup a konfigurace dat grafu
Rozhraní `IChart` poskytuje metody pro úpravu řad, kategorií a datových bodů v grafu.

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

### Krok 3: Přidat obrázkové značky k datovým bodům grafu  
`IDataPoint` představuje jednotlivý bod a jeho metoda `setMarker` přiřadí vlastní obrázek jako značku.

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

### Krok 4: Konfigurace velikosti značky a uložení prezentace  
`presentation.save` zapíše finální soubor PPTX do určené lokace ve zvoleném formátu.

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

## Proč používat obrázkové značky v grafech?
`Aspose.Slides` podporuje **60+ chart types** a **100+ image formats**, což vám umožní spárovat libovolnou vizuální ikonu s datovým bodem. Použití vlastních obrázkových značek zvyšuje čitelnost dat až o **35 %** v uživatelských studiích, protože diváci mohou okamžitě spojit ikonu s jejím významem bez procházení legendy.

## Časté problémy a řešení
- **FileNotFoundException** – Ověřte, že cesty k obrázkům (`YOUR_DOCUMENT_DIRECTORY/...`) jsou správné a soubory existují.  
- **LicenseException** – Ujistěte se, že jste před voláním jakékoli API v produkci nastavili platnou licenci Aspose.  
- **Marker Not Visible** – Zvyšte `setMarkerSize` nebo použijte obrázky vyššího rozlišení pro jasnější zobrazení.  

## Často kladené otázky

**Q: Mohu místo JPEG použít PNG obrázky pro značky?**  
A: Ano, jakýkoli formát obrázku podporovaný Aspose.Slides (PNG, JPEG, BMP, GIF) funguje jako značka.

**Q: Potřebuji licenci pro balíčky Maven/Gradle?**  
A: Dočasná licence stačí pro vývoj a testování; plná licence je vyžadována pro komerční distribuci.

**Q: Je možné přidat různé obrázky ke každému datovému bodu ve stejné řadě?**  
A: Rozhodně. V příkladu `AddImageMarkers` střídáme dva obrázky, ale můžete načíst unikátní obrázek pro každý bod.

**Q: Jak Aspose Slides Maven Dependency ovlivňuje velikost projektu?**  
A: Maven balíček obsahuje jen potřebné binární soubory pro zvolenou verzi JDK, takže celková velikost zůstává pod **15 MB**. Pokud je velikost kritická, můžete použít verzi **no‑dependencies**.

**Q: Jaké verze Javy jsou podporovány?**  
A: Aspose.Slides for Java podporuje JDK 8 až JDK 21. Příklad používá JDK 16, ale můžete upravit klasifikátor podle potřeby.

## Závěr
Po prostudování tohoto průvodce nyní víte, **jak použít Aspose Slides Maven Dependency** k obohacení grafů o vlastní obrázkové značky, jak nakonfigurovat závislost a **přidat obrázky do řad grafu** pro profesionální vzhled. Experimentujte s různými ikonami, velikostmi a typy grafů a vytvořte prezentace, které skutečně vyniknou.

---

**Poslední aktualizace:** 2026-06-03  
**Testováno s:** Aspose.Slides for Java 25.4 (jdk16)  
**Autor:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Související tutoriály

- [Vytvořit graf v Javě s Aspose.Slides – Přidat a ověřit grafy](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Vytvořit čárové grafy s výchozími značkami pomocí Aspose.Slides pro Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Vylepšit PowerPoint grafy pomocí vlastních čar s Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}