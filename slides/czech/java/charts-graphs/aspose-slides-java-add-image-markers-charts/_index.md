---
"date": "2025-04-17"
"description": "Naučte se, jak vylepšit grafy v Aspose.Slides pro Javu přidáním vlastních značek obrázků. Zvyšte zapojení pomocí vizuálně odlišných prezentací."
"title": "Zvládněte Aspose.Slides v Javě&#58; Přidávání obrazových značek do grafů"
"url": "/cs/java/charts-graphs/aspose-slides-java-add-image-markers-charts/"
"weight": 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Zvládnutí Aspose.Slides v Javě: Přidávání obrazových značek do grafů

## Zavedení
Vytváření vizuálně poutavých prezentací je klíčem k efektivní komunikaci a grafy jsou mocným nástrojem pro stručné sdělení složitých dat. Standardní značky v grafech někdy nedokážou vaše data zvýraznit. S Aspose.Slides pro Javu můžete své grafy vylepšit přidáním vlastních obrázků jako značek, čímž je učiníte poutavějšími a informativnějšími.

V tomto tutoriálu se podíváme na to, jak integrovat obrázkové značky do grafů pomocí knihovny Aspose.Slides v Javě. Zvládnutím těchto technik budete schopni vytvářet prezentace, které upoutají pozornost svými jedinečnými vizuálními prvky.

**Co se naučíte:**
- Jak nastavit Aspose.Slides pro Javu
- Vytvoření základní prezentace a grafu
- Přidávání obrazových značek k datovým bodům grafu
- Konfigurace nastavení značek pro optimální vizualizaci

Jste připraveni vylepšit své grafy? Pojďme se ponořit do předpokladů, než začneme!

### Předpoklady
Pro postup podle tohoto tutoriálu budete potřebovat:
1. **Aspose.Slides pro knihovnu Java**Získejte jej prostřednictvím závislostí Maven nebo Gradle nebo stažením přímo z Aspose.
2. **Vývojové prostředí v Javě**Ujistěte se, že je na vašem počítači nainstalován JDK 16.
3. **Základní znalosti programování v Javě**Znalost syntaxe a konceptů Javy bude výhodou.

## Nastavení Aspose.Slides pro Javu
Než se ponoříme do kódování, nastavme si vývojové prostředí s potřebnými knihovnami.

### Instalace Mavenu
Přidejte do svého `pom.xml` soubor:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Instalace Gradle
Zahrňte toto do svého `build.gradle` soubor:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Přímé stažení
Nebo si stáhněte nejnovější verzi z [Aspose.Slides pro verze Java](https://releases.aspose.com/slides/java/).

#### Kroky získání licence
- **Bezplatná zkušební verze**Začněte s dočasnou licencí, abyste mohli prozkoumávat funkce Aspose.Slides.
- **Dočasná licence**: Získejte přístup k pokročilým funkcím pořízením dočasné licence.
- **Nákup**Pro dlouhodobé používání zvažte zakoupení plné licence.

### Základní inicializace a nastavení
Inicializujte `Presentation` objekt pro zahájení vytváření snímků:

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Sem vložte kód pro přidávání slajdů a grafů.
    }
}
```

## Průvodce implementací
Nyní si rozebereme proces přidávání obrazových značek do vaší série grafů.

### Vytvořte novou prezentaci s grafem
Nejprve potřebujeme snímek, kam můžeme vložit náš graf:

```java
import com.aspose.slides.*;

public class CreatePresentation {
    public static void main(String[] args) {
        // Inicializace objektu Presentation
        Presentation presentation = new Presentation();

        // Získejte první snímek z kolekce
        ISlide slide = presentation.getSlides().get_Item(0);

        // Přidání výchozího spojnicového grafu se značkami na snímek
        IChart chart = slide.getShapes().addChart(
            ChartType.LineWithMarkers, 0, 0, 400, 400
        );
    }
}
```

### Přístup k datům grafu a jejich konfigurace
Dále si pro správu řad otevřeme datový list našeho grafu:

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

        // Vymazat existující sérii a přidat novou
        chart.getChartData().getSeries().clear();
        chart.getChartData().getSeries().add(
            fact.getCell(defaultWorksheetIndex, 1, 1, "Series 1"), 
            chart.getType()
        );
    }
}
```

### Přidání obrazových značek k datovým bodům grafu
A teď ta vzrušující část – přidávání obrázků jako značek:

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

        // Načíst a přidat obrázky jako značky
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IImage image2 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/Tulips.jpg")));
        IPPImage imgx2 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        // Přidání datových bodů s obrázky jako značkami
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

### Konfigurace značky řady grafů a uložení prezentace
Nakonec upravme velikost značky pro lepší viditelnost a uložíme naši prezentaci:

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

        // Načtení a přidání obrázků jako značek (příklad s použitím zástupných cest)
        IImage image1 = presentation.getImages().addImage(Files.readAllBytes(Paths.get("YOUR_DOCUMENT_DIRECTORY/aspose-logo.jpg")));
        IPPImage imgx1 = presentation.getImages().get_Item(presentation.getImages().size() - 1);

        IChartSeries series = chart.getChartData().getSeries().get_Item(0);
        
        series.getDataPoints().addDataPointForLineSeries(fact.getCell(defaultWorksheetIndex, 1, 1, (double) 4.5))
            .getMarker().getFormat().getFill().setFillType(FillType.Picture)
            .getPictureFillFormat().getPicture().setImage(imgx1);

        series.getMarkerStyleType() = MarkerStyleType.Circle;
        series.getMarkerSize() = 10;

        presentation.save("Output.pptx", SaveFormat.Pptx);
    }
}
```

## Závěr
Dodržováním tohoto návodu jste se naučili, jak vylepšit grafy v Aspose.Slides pro Javu přidáním vlastních značek obrázků. Tento přístup může výrazně zvýšit poutavost a srozumitelnost vašich prezentací.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}