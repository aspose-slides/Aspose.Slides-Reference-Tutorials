---
date: '2026-01-11'
description: Lär dig hur du använder Aspose Slides för Java, lägger till bildmarkörer
  i diagram och konfigurerar Aspose Slides Maven‑beroendet för anpassade diagramvisualiseringar.
keywords:
- Aspose.Slides for Java
- image markers in charts
- Java presentation enhancements
title: 'Hur man använder Aspose Slides Java: Lägg till bildmarkörer i diagram'
url: /sv/java/charts-graphs/aspose-slides-java-add-image-markers-charts/
weight: 1
---

{{< blocks/products/pf/main-wrap-class >}}

{{< blocks/products/pf/main-container >}}

{{< blocks/products/pf/tutorial-page-section >}}
# Så använder du Aspose Slides Java: Lägg till bildmarkörer i diagram

## Introduktion
Att skapa visuellt tilltalande presentationer är nyckeln till effektiv kommunikation, och diagram är ett kraftfullt verktyg för att på ett koncist sätt förmedla komplex data. När du undrar **hur du använder Aspose** för att få dina diagram att sticka ut är anpassade bildmarkörer svaret. Standardmarkörer kan se generiska ut, men med Aspose.Slides för Java kan du ersätta dem med vilken bild som helst – vilket gör varje datapunkt omedelbart igenkännbar.

I den här handledningen går vi igenom hela processen för att lägga till bildmarkörer i ett linjediagram, från att konfigurera **Aspose Slides Maven‑beroendet** till att ladda bilder och applicera dem på datapunkter. När du är klar kommer du att känna dig säker på **hur du lägger till markörer**, hur du **lägger till bilder i diagram‑serier**, och du har ett färdigt kodexempel att köra.

**Vad du kommer att lära dig**
- Hur du sätter upp Aspose.Slides för Java (inklusive Maven/Gradle)
- Skapa en grundläggande presentation och diagram
- Lägga till bildmarkörer på diagram‑datapunkter
- Konfigurera markörstorlek och stil för optimal visualisering

Redo att lyfta dina diagram? Låt oss gå igenom förutsättningarna innan vi börjar!

### Snabba svar
- **Vad är huvudsyftet?** Lägg till anpassade bildmarkörer på diagram‑datapunkter.  
- **Vilket bibliotek krävs?** Aspose.Slides för Java (Maven/Gradle).  
- **Behöver jag en licens?** En tillfällig licens fungerar för utvärdering; en full licens behövs för produktion.  
- **Vilken Java‑version stöds?** JDK 16 eller senare.  
- **Kan jag använda vilket bildformat som helst?** Ja – PNG, JPEG, BMP osv., så länge filen är åtkomlig.

### Förutsättningar
För att följa den här handledningen behöver du:
1. **Aspose.Slides för Java‑bibliotek** – skaffa via Maven, Gradle eller direkt nedladdning.  
2. **Java‑utvecklingsmiljö** – JDK 16 eller nyare installerad.  
3. **Grundläggande kunskaper i Java** – bekantskap med Java‑syntax och koncept är hjälpsamt.

## Vad är Aspose Slides Maven‑beroendet?
Maven‑beroendet hämtar rätt binärer för din Java‑version. Genom att lägga till det i din `pom.xml` säkerställer du att biblioteket är tillgängligt vid kompilering och körning.

### Maven‑installation
Lägg till följande beroende i din `pom.xml`‑fil:

```xml
<dependency>
    <groupId>com.aspose</groupId>
    <artifactId>aspose-slides</artifactId>
    <version>25.4</version>
    <classifier>jdk16</classifier>
</dependency>
```

### Gradle‑installation
Inkludera denna rad i din `build.gradle`‑fil:

```gradle
implementation group: 'com.aspose', name: 'aspose-slides', version: '25.4', classifier: 'jdk16'
```

### Direkt nedladdning
Alternativt kan du ladda ner den senaste versionen från [Aspose.Slides för Java‑utgåvor](https://releases.aspose.com/slides/java/).

#### Steg för att skaffa licens
- **Gratis provversion** – börja med en tillfällig licens för att utforska funktionerna.  
- **Tillfällig licens** – lås upp avancerade möjligheter under testning.  
- **Köp** – skaffa en full licens för kommersiella projekt.

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
Nedan följer en steg‑för‑steg‑genomgång av hur du lägger till bildmarkörer i ett diagram. Varje kodblock har en förklaring så att du förstår **varför** varje rad är viktig.

### Steg 1: Skapa en ny presentation med ett diagram
Vi lägger till ett linjediagram med standardmarkörer på den första bilden.

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
Vi rensar eventuella standardserier och lägger till våra egna serier, och förbereder kalkylbladet för anpassade datapunkter.

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

### Steg 3: Lägg till bildmarkörer på diagram‑datapunkter  
Här demonstrerar vi **hur du lägger till markörer** med hjälp av bilder. Ersätt platshållar‑sökvägarna med den faktiska platsen för dina bilder.

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

### Steg 4: Konfigurera markörstorlek och spara presentationen  
Vi justerar markörstilen för bättre synlighet och skriver den slutgiltiga PPTX‑filen.

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

## Vanliga problem och felsökning
- **FileNotFoundException** – Kontrollera att bildsökvägarna (`YOUR_DOCUMENT_DIRECTORY/...`) är korrekta och att filerna finns.  
- **LicenseException** – Se till att du har ställt in en giltig Aspose‑licens innan du anropar någon API i produktion.  
- **Markören syns inte** – Öka `setMarkerSize` eller använd högupplösta bilder för tydligare visning.

## Vanliga frågor

**Q: Kan jag använda PNG‑bilder istället för JPEG för markörer?**  
A: Ja, alla bildformat som stöds av Aspose.Slides (PNG, JPEG, BMP, GIF) fungerar som markör.

**Q: Behöver jag en licens för Maven/Gradle‑paketen?**  
A: En tillfällig licens räcker för utveckling och testning; en full licens krävs för kommersiell distribution.

**Q: Är det möjligt att lägga till olika bilder på varje datapunkt i samma serie?**  
A: Absolut. I `AddImageMarkers`‑exemplet växlar vi mellan två bilder, men du kan ladda en unik bild för varje punkt.

**Q: Hur påverkar `aspose slides maven dependency` projektets storlek?**  
A: Maven‑paketet innehåller endast de binärer som behövs för den valda JDK‑versionen, vilket håller fotavtrycket rimligt. Du kan också använda **no‑dependencies**‑versionen om storlek är en oro.

**Q: Vilka Java‑versioner stöds?**  
A: Aspose.Slides för Java stöder JDK 8 till JDK 21. Exemplet använder JDK 16, men du kan justera klassificeraren efter behov.

## Slutsats
Genom att följa den här guiden vet du nu **hur du använder Aspose** för att berika diagram med anpassade bildmarkörer, hur du konfigurerar **Aspose Slides Maven‑beroendet**, och hur du **lägger till bilder i diagram‑serier** för ett polerat, professionellt utseende. Experimentera med olika ikoner, storlekar och diagramtyper för att skapa presentationer som verkligen sticker ut.

---

**Senast uppdaterad:** 2026-01-11  
**Testat med:** Aspose.Slides för Java 25.4 (jdk16)  
**Författare:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}