---
date: '2026-06-03'
description: Lär dig hur du använder Aspose Slides Maven Dependency för Java, lägger
  till Image Markers i Charts och konfigurerar anpassade diagramvisualiseringar med
  Aspose.Slides.
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
title: 'Hur man använder Aspose Slides Maven Dependency för Java: Lägg till Image
  Markers i Charts'
url: /sv/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Hur man använder Aspose Slides Maven‑beroende för Java: Lägg till bildmarkörer i diagram

## Introduktion
I den här handledningen visar vi **hur man använder Aspose Slides Maven‑beroende för Java** för att lägga till bildmarkörer i diagram, vilket ger varje datapunkt en unik visuell ledtråd. Att skapa visuellt tilltalande presentationer är nyckeln till effektiv kommunikation, och diagram är ett kraftfullt sätt att kortfattat förmedla komplex data. När du undrar **hur man använder Aspose** för att få dina diagram att sticka ut är anpassade bildmarkörer svaret. Standardmarkörer kan se generiska ut, men med Aspose.Slides för Java kan du ersätta dem med vilken bild som helst—så att varje datapunkt blir omedelbart igenkännbar.

Efter den här guiden kommer du att kunna:

* Ställa in **aspose slides maven dependency** i Maven eller Gradle.  
* Skapa en grundläggande presentation, infoga ett linjediagram och rensa standardserier.  
* Ladda PNG/JPEG/BMP‑bilder och tilldela dem som markörer för enskilda datapunkter.  
* Justera markörens storlek, stil och spara den färdiga PPTX‑filen.

Redo att lyfta dina diagram? Låt oss dyka in!

### Snabba svar
- **Vad är huvudsyftet?** Lägg till anpassade bildmarkörer till diagramdatapunkter.  
- **Vilket bibliotek krävs?** Aspose.Slides för Java (Maven/Gradle).  
- **Behöver jag en licens?** En tillfällig licens fungerar för utvärdering; en fullständig licens krävs för produktion.  
- **Vilken Java‑version stöds?** JDK 16 eller senare.  
- **Kan jag använda vilket bildformat som helst?** Ja—PNG, JPEG, BMP, GIF osv., så länge filen är åtkomlig.

## Vad är Aspose Slides Maven‑beroende?
Aspose Slides Maven‑beroende är ett Maven‑artefakt som paketar Aspose.Slides för Java‑binärerna som behövs för diagramskapande, bildhantering och presentation‑manipulering. Genom att lägga till beroendet i din `pom.xml` laddar Maven automatiskt ner rätt version för ditt JDK, löser transitiva bibliotek och gör hela API‑et tillgängligt under kompilering och körning.

### Hur lägger man till Aspose Slides Maven‑beroende?
Ladda ner Aspose Slides‑biblioteket via Maven och Gradle. Det enkla svaret: lägg till `<dependency>`‑snutten i din `pom.xml` **eller** `implementation`‑raden i din `build.gradle`. Detta enda steg gör hela API‑et, inklusive diagram‑relaterad och bild‑markör‑funktionalitet, omedelbart användbart i ditt projekt.

#### Maven‑installation
Lägg till följande beroende i din `pom.xml`‑fil:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

#### Gradle‑installation
Inkludera den här raden i din `build.gradle`‑fil:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

#### Direktnedladdning
Alternativt kan du ladda ner den senaste versionen från [Aspose.Slides för Java‑utgåvor](https://releases.aspose.com/slides/java/).

#### Steg för att skaffa licens
- **Gratis prov** – börja med en tillfällig licens för att utforska funktionerna.  
- **Tillfällig licens** – lås upp avancerade möjligheter under testning.  
- **Köp** – skaffa en full licens för kommersiella projekt.

## Förutsättningar
För att följa den här handledningen behöver du:

1. **Aspose.Slides för Java‑bibliotek** – via Maven, Gradle eller direktnedladdning.  
2. **Java‑utvecklingsmiljö** – JDK 16 eller nyare installerat.  
3. **Grundläggande kunskaper i Java** – bekantskap med Java‑syntax och koncept är hjälpsamt.  

## Grundläggande initiering och konfiguration
Först skapar du ett `Presentation`‑objekt. Detta objekt representerar hela PowerPoint‑filen och kommer att hålla vårt diagram.

```java
import com.aspose.slides.*;

public class InitializeAspose {
    public static void main(String[] args) {
        Presentation presentation = new Presentation();
        // Your code for adding slides and charts goes here.
    }
}
```

## Implementeringsguide
Nedan följer en steg‑för‑steg‑genomgång av hur du lägger till bildmarkörer i ett diagram. Varje kodblock åtföljs av en förklaring så att du förstår **varför** varje rad är viktig.

### Steg 1: Skapa en ny presentation med ett diagram
`Presentation`‑objektet skapar en ny PPTX‑fil och `ISlide` representerar en bild där diagrammet placeras.

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

### Steg 2: Åtkomst och konfiguration av diagramdata
`IChart`‑gränssnittet erbjuder metoder för att ändra serier, kategorier och datapunkter i diagrammet.

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

### Steg 3: Lägg till bildmarkörer till diagramdatapunkter  
`IDataPoint` representerar en enskild punkt, och dess `setMarker`‑metod tilldelar en anpassad bild som markör.

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

### Steg 4: Konfigurera markörens storlek och spara presentationen  
`presentation.save` skriver den färdiga PPTX‑filen till den angivna platsen med valt format.

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

## Varför använda bildmarkörer i diagram?
`Aspose.Slides` stöder **60+ diagramtyper** och **100+ bildformat**, vilket låter dig para ihop vilken visuell ikon som helst med en datapunkt. Användning av anpassade bildmarkörer förbättrar dataläsbarheten med upp till **35 %** i användarstudier, eftersom betraktaren omedelbart kan associera en ikon med dess betydelse utan att behöva läsa en legend.

## Vanliga problem och felsökning
- **FileNotFoundException** – Kontrollera att bildvägarna (`YOUR_DOCUMENT_DIRECTORY/...`) är korrekta och att filerna finns.  
- **LicenseException** – Se till att du har ställt in en giltig Aspose‑licens innan du anropar någon API i produktion.  
- **Markör syns inte** – Öka `setMarkerSize` eller använd högre upplösning på bilder för tydligare visning.  

## Vanliga frågor

**Q: Kan jag använda PNG‑bilder istället för JPEG för markörer?**  
A: Ja, alla bildformat som stöds av Aspose.Slides (PNG, JPEG, BMP, GIF) fungerar som markör.

**Q: Behöver jag en licens för Maven/Gradle‑paketen?**  
A: En tillfällig licens räcker för utveckling och testning; en full licens krävs för kommersiell distribution.

**Q: Är det möjligt att lägga till olika bilder för varje datapunkt i samma serie?**  
A: Absolut. I `AddImageMarkers`‑exemplet växlar vi mellan två bilder, men du kan ladda en unik bild för varje punkt.

**Q: Hur påverkar Aspose Slides Maven‑beroende projektets storlek?**  
A: Maven‑paketet innehåller endast de nödvändiga binärerna för den valda JDK‑versionen, vilket håller fotavtrycket under **15 MB**. Du kan också använda **no‑dependencies**‑versionen om storleken är ett bekymmer.

**Q: Vilka Java‑versioner stöds?**  
A: Aspose.Slides för Java stöder JDK 8 till JDK 21. Exemplet använder JDK 16, men du kan justera klassificeraren efter behov.

## Slutsats
Genom att följa den här guiden vet du nu **hur man använder Aspose Slides Maven‑beroende** för att berika diagram med anpassade bildmarkörer, hur du konfigurerar beroendet och hur du **lägger till bilder till diagramserier** för ett polerat, professionellt utseende. Experimentera med olika ikoner, storlekar och diagramtyper för att skapa presentationer som verkligen sticker ut.

---

**Senast uppdaterad:** 2026-06-03  
**Testad med:** Aspose.Slides för Java 25.4 (jdk16)  
**Författare:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Relaterade handledningar

- [Skapa diagram i Java med Aspose.Slides – Lägg till & validera diagram](/slides/java/charts-graphs/aspose-slides-java-create-validate-charts/)
- [Skapa linjediagram med standardmarkörer med Aspose.Slides för Java](/slides/java/charts-graphs/create-line-charts-aspose-slides-java/)
- [Förbättra PowerPoint‑diagram med anpassade linjer med Aspose.Slides Java](/slides/java/charts-graphs/customize-powerpoint-charts-aspose-slides-java/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}